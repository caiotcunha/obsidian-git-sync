Pode ser baseado no relacionamento entre pixels. Invariante a tranformações monotônicas, pois a diferença se mantém.

# Local binary Patterns
olha a relação entre o pixel do meio e os vizinhos. Invariante ao brilho. 

## Extension of lbp -> center-symmetric
16 valores. Aumenta o valor da janela para um raio. Criar limiar de diferença de intensidade. 

## Graylevel Co-occurrence Matrix
joint probability distribuition of pairs of neighboring pixels.
Diagonal cheia em regiões homogêneas
Normalizado
definir o relacionamento (diagonal,vertical,horizontal) e calcular a probabilidade.
Criado para classificação de texturas
