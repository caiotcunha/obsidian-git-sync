- Estabelecer uma separação clara entre domínio e restante do sistema
- Vantagens:
	- Permite que desenvolvedores se concentrem no domínio que representa o propósito do sistema e é responsável pela geração de valor
	- Testabilidade (mais fácil testar domínio limpo de tecnologia)
	- Mais fácil de trocar de bibliotecas
- Usar adaptadores para conectar o dominio ao resto do sistema
- Camada de domínio não conhece o banco de dados, nem o front-end do sistema
![[Pasted image 20230919231314.png]]