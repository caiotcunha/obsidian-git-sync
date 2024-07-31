pyramid Scale and dense sampling tem custo computacional alto
- Podemos fazer a subtração de background
	- problemas:
		- objetos no background
		- Falta de sentido
		- comportamento diferente dependendo da hora do dia
		- mudança de iluminação repentina
		- objetos que se movem
		- camuflagem
		- need for background learning

Region Proposal
- Maneira rápida de gerar hipoteses de objetos
- Propoe regiões onde o detector deveria olhar antes
	- descartar a janela é mais rápido do que testar no detector
- Aplica maneiras rápidas de processamento de imagem para remover regiões com pouca chance de ter um objeto
- Ainda precisa gerar janelas de candidatos

Regression
- Adiciona a regressão para melhorar a localização da janela em torno

## Detectores baseados em deep learning
Não é possível construir uma rede convolucional tradicional seguida por uma fully connected - the lenght of the output layer ir variable -> numero de ocorrência não é fixo

Duas formas:
- Two stage detectors -> rede de região proposta e classificação
	- R-CNN
	- FAST R-CNN
	- FASTER R-CNN
- Single stage detectors -> direct location and classification of objects
	- SSD - single Shot MultiBox Detector
	- You Only Look Once - Unified, Real-Time Object Detection

Fast R-CNN
- convolução para a imagem toda
- para cada região de interesse aplica uma camada de pooling para gerar um feature vector de tamanho fixo
- Apresenta o feature vector para uma camada totalmente conectada e ai:
	- to one softmax layer with K classes
	- To one output with four real-valued number for each of K classes (regressão)

YOLO - you only look once

- Split image into SxS grid
- Predicts B bounding boxes (x,y,w,h), confidence and C class probabilities for each
- 