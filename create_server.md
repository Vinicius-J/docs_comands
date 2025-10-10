# Como transformar um computador em um servidor de teste e fazer conexão com o computador principal
## Na máquina que será o servidor:
1. Pegar o IP do computador que será usado como servidor:
    - Comando usado no terminal para ver o **IP**: `ip address show`
    - Comando usado no computador principal para confirmar se realmente o **IP** coletado é o correto: `ping <ip_servidor>`
2. Use o comando para instalar o **ssh** na máquina que será o servidor `sudo apt install ssh`
3. Bloquear o acesso via senha da máquina principal para máquina do servidor:
    - No terminal do servidor digite: `sudo nano /etc/ssh/sshd_config`
    - Proucure por `PasswordAuthentication`
    - Tire do comentário e coloque `no` no lugar de `yes`
    - Caso tenha mais de **6 chaves ssh** procure por `MaxAuthTries`, tire o comentário e coloque o número de chaves que você possui
    - Reinicie o ssh com o comando `sudo systemctl restart ssh`
## Na máquina principal:
1. Crie a chave ssh com o comando `ssh-keygen -f ~/.ssh/<NOME_DA_CHAVE> -t rsa -b 4096`
2. Você poderá colocar ou não uma senha
3. Para vizualizar a chave pública que foi criada digite o comando `cat /home/<NOME_DO_USUARIO>/.ssh/<NOME_DA_CHAVE>.pub`
4. Copie a chave pública e cole no arquivo **authorized_keys** na máquina que será o servidor
## Na máquina que será o servidor:
1. Digite o seguinte comando para abrir ou criar o arquivo de chaves autorizadas: `nano ~/.ssh/authorized_keys`
2. Cole a chave pública copiada da máquina principal
    - **Obs.:** A cada nova chave que for preciso colocar no servidor, copie e cole abaixo da chave anterior, mantendo uma chave por linha