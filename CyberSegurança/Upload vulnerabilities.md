1. Overwriting Existing Files
2. Remote Code Execution
	1. webshells
	2. reverse/bind shells
3. filtering:
	1. Client side filtering: Filtragem que roda no navegador do usuário. É trivial consegui passar por ela.
	2. Server side filtering: feita pelo servidor, muito difícil ou impossível de passar.
	3. MIME (Multipurpose Internet Mail Extension) validation: tipos são usados como identificadores para arquivos.
	4. Magic Number Validation: É a string de bytes no início do arquivo que identifica o conteúdo. Esse número pode ser falseado.
	5. File lenght filtering: Previne que arquivos enormes sejam enviados.
	6. File Name Filtering: Utilizar um sistema de nomes aleatórios para os arquivos que foram subidos para o site, também checar se já existe algum arquivo com aquele nome. 
	7. File content Filtering: Sistemas mais complicados de filtragem podem escanear o conteúdo do arquivo para averiguar se ele é seguro ou não.