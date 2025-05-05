
# Abstract
We develop and evaluate strategies for e cient computation and propagation of wavefronts using a multi-level queue structure. This queue structure improves the utilization of fast memories in a GPU and reduces synchronization over heads. We also develop a tile-based parallelization strategy to support execution on multiple CPUs and GPUs. We evaluate our approaches on a state-of-the art GPU accelerated machine (equipped with 3 GPUs and 2 multicore CPUs) using the IWPP implementations of two widely used image processing opera tions: morphological reconstruction and euclidean distance transform. Our re sults show signi cant performance improvements on GPUs. The use of multiple CPUs and GPUs cooperatively attains speedups of 50 and 85 with respect to single core CPU executions for morphological reconstruction and euclidean distance transform, respectively.

# Introduction
This paper investigates e cient parallelization on hybrid CPU-GPU sys tems of operations or applications whose computation structure includes what we call the irregular wavefront propagation pattern (IWPP).
Our work is motivated by the requirements of analysis of whole slide tissue images in biomedical research. With rapid improvements in sensor technolo gies and scanner instruments, it is becoming feasible for research projects and healthcare organizations to gather large volumes of microscopy images. We are interested in enabling more e ective use of large datasets of high resolution tissue slide images in research and patient care.
A whole slide tissue image is analyzed through a cascade of image normalization, object segmentation, object feature computation, and object/image classi ca tion stages.The segmentation stage is expensive and composed of a pipeline of substages. The most expensive substages are built on several low-level oper ations, notably morphological reconstruction and distance transform. E cient implementation of these operations is necessary to reduce the cost of image analysis.

The processing structures of the morphological reconstruction and distance transform operations bear similarities and include the IWPP on a grid. The IWPPis characterized by one or more source grid points from which waves origi nate and the irregular shape and expansion of the wave fronts.The composition of the waves is dynamic, data dependent, and computed during execution as the waves are expanded. Elements in the front of the waves work as the sources of wave propagations to neighbor elements.

![[Algoritmo 1.png]]

During propagation phase, a single element (ei) is extracted from the wavefront and its neighbors (Q <- NG(ei)) are identifed.

# Irregular wavefront propagation pattern in image analysis

## Morphological Reconstruction
Morphological operators are basic operations used by a broad set of image processing algorithms. These operators are applied to individual pixels and are computed based on the current value of a pixel and pixels in its neighborhood. A pixel p is a neighbor of pixel q if (pq) G. G is usually a 4-connected or 8-connected square grid.
Quando aplicada em imagens binárias gera os componenter conectados por uma imagem marcada. 
![[Reconstrução morfologica.png]]

2 inputs para o algoritmo: imagem original(mask) e marker. Reconstruimos as estruturas marcadas para gerar o algoritmo. É feita performando dilatações de tamanho 1 na imagem para reconstruir a estrutura.

### Dilatação
Exemplo para uma imagem binária
structuring segment / image segment -> dilatation
$$

\begin{bmatrix}

0 & 1 & 0\\

1 & 1 & 1\\

0 & 1 & 0\\

\end{bmatrix}
 
\begin{bmatrix}

0 & 0 & 0 & 0 & 0\\

0 & 1 & 1 & 1 & 0\\

0 & 1 & 1 & 1 & 0\\

0 & 1 & 1 & 1 & 0\\

0 & 0 & 0 & 0 & 0\\
\end{bmatrix}
-> 
\begin{bmatrix}

0 & 1 & 1 & 1 & 0\\

1 & 1 & 1 & 1 & 1\\

1 & 1 & 1 & 1 & 1\\

1 & 1 & 1 & 1 & 1\\

0 & 1 & 1 & 1 & 0\\

\end{bmatrix}

$$
Se algum dos segmentos do elemento estruturante for 1 e do segmento de imagem também o resultado é 1.

### Sequential Reconstruction (SR)
É compuado alterando entre raster e anti-raster. Raster começa do pixel (0,0) e o anti-raster do pixel final (N-1,M-1) ambos de maneira a seguir a linha ( raster da esquerda para a direita e anti-raster da direita para a esquerda). Itera até alcançar a estabilidade. 

### Queue-based Reconstruction (QB)
Uma fila FIFO é inicializada com os pixels regional maxima. A computação vai tirando um pixel da queue e avaliando seus vizinhos, se o valor muda adiciona esses pixels que mudaram à fila. Continua até que a fila esteja vazia.

### Fast Hybrid Reconstruction (FH)
A computação da região maxima que é necessária para inicializar a fila no QB tem custo computacional significativo. O FH incorpora as características de SR e QB para diminuir o custo da inicialização. primeiro faz uma passada usando raster e anti-raster como em SR. Depois dessa passada continua a computação com uma fila FIFO como em QB. Ng+ e Ng- denotam o conjunto de vizinhos em Ng(p) que são atigidos antes e depois de tocar o pixel p durante o raster
![[pseudo-código algoritmo FH.png]]

## Transformada da distância euclidiana
Computa um mapa de distâncias M de uma imagem binária I, onde para cada pixel p de I o valor dele no mapa M(p) é a menor distância de p a um pixel de fundo.
É fundamental para a análise de forma, que pode ser usada para separar objetos um em cima do outro. Também pode ser usado para calcular operações morfológicas.

### Diagrama de voronoi
Um **Diagrama de Voronoi** é um tipo especial de decomposição de um dado espaço, por exemplo, um [espaço métrico](https://pt.wikipedia.org/wiki/Espa%C3%A7o_m%C3%A9trico "Espaço métrico"), determinado pela distância para uma determinada família de objetos (subconjuntos) no espaço. Estes objetos são normalmente chamados de sítios ou geradores (apesar de nomes como “sementes” estarem também em uso). Cada sítio está associado a célula de Voronoi correspondente, isto é um conjunto de todos os pontos no dado espaço o qual a distância para o dado sítio não é maior que sua distância para os outros objetos.


## Implementation of Irregular Wavefront Propagation Pattern on a GPU

## Parallelization Strategy
Depois da inicialização do IWPP, os dados da wavefront inicial são colocados em uma fila global para a computação. Para possibilitar a execução paralela, os elementos da fila global são partidos em algum número de filas menores. Cada uma dessas filas é designada para uma thread da GPU. Cada bloco pode levar as computações independente dos outros blocos. Assim o custo de comunicação e sincronização com a fila global. Com essa estratégia não é necessário sincronizar os blocos ou usar continuamente Memory fence operations para garantir a consistência por todos os multi-processadores da GPU.

### Memory Fence Operations
**Memory fences** (também conhecidas como **memory barriers**) são instruções que **impõem restrições à ordem em que as operações de leitura e escrita em memória podem ser feitas** por múltiplas **threads (ou warps)** executando em paralelo.

![[Wavefront propagation phase on a GPU.png]]

## Warp operations
- Um _warp_ é um grupo de 32 threads que executam simultaneamente na GPU.
- Operações dentro do warp são **ultrarrápidas** e podem usar **warp-level intrinsics**, como:
    - `__shfl_up_sync()`  
    - `__shfl_down_sync()`
    - `__shfl_xor_sync()`
Essas permitem fazer **prefix-sum eficiente em hardware**, sem precisar de sincronizações complicadas.

# Prefix-sum
Acha o lugar onde  a thread deve escrever na fila
- prefix-sum exclusivo: soma de todos os anteriores sem incluir i

# Dequeue
