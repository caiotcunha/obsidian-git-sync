- permite que os dispositivos identifiquem onde começa e termina um quadro
- Assim, conseguimos distinguir o que é ruído e o que são transmissões
- usamos uma sequência pré-definida de bits para marcar o início dos dados
- Componentes:
	- indentificador de início
	- identificador de fim
	- tamanho
	- origem e destino (depende)
	- bits detecção/correção de erro
- caracteres de escape: para poder transmitir uma sequência de bits de início no meio do dado
- ![[Pasted image 20230928193827.png]]
- isso não é eficiênte
## bit stuffing
- adicionar um bit apenas para evitar sequências proibidas
- receptor ignora o bit adicional
- bem mais eficiente
- adiciona um bit depois de uma sequência específica de bits