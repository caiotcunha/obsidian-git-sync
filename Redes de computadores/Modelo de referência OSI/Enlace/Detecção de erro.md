- bits podem vir errados
	- atenuação
	- ruído alto no meio
	- interferências
	- duas ou mais transmissão simultâneas
- adição de um cabeçalho de detecção/correção de erro no quadro

## Formas de detecção de erro
### bit de paridade
- detecta erros ímpares
### CRC ciclic redundancy check
- baseado em divisão por polinômios usando polinômios com coeficiente de base 2
- CRC é a divisão do polinômio da mensagem por um polinômio gerador -> pega o resto e transmite no final da mensagem
- capacidade de detecção depende da qualidade do polinômio gerador
- divisão é XOR -> eficiênte
- 