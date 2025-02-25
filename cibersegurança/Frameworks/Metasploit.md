# Modúlos
- Auxiliary: guarda módulos de suporte como scanners, crawlers e fuzzers
- Encoders: possibilita ofuscar os exploits e paylods
- Evasion: tenta desviar de antivirus
- Exploits: códigos que exploram uma vulnerabilidade
- NOPs: usados para preencher o buffer
- Payloads: códigos que vão rodar na máquina alvo
- Post: para post-exploitation


# Exploitation practice
Rodei um nmap -sS -a na maquina alvo
Encontrei várias portas abertas e pesquisei uma por uma as informações. Acabei encontrando uma vulnerabilidade conhecida a MS17-010, no exploit-db estava escrito eternalblue então pesquisei isso no search do metasploit e usei o primeiro retornado. Coloquei as configurações corretas e foi só executar o expoit.
