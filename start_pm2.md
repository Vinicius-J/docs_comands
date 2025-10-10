# Como inicializar o projeto atráves do pm2

## Na máquina que será usada como servidor:

1. Instale o **curl** usando o comando `sudo apt install curl -y`
2. Instale o nodejs na versão LTS da forma recomendada pelo site
3. Entrar dentro da pasta com os arquivos do projeto
4. Rodar o comando `npm i` para iniciar o **npm**
5. Instale o **pm2** de forma global com o comando `sudo npm i -g pm2`
6. Para subir o projeto usando o **pm2** use o comando `pm2 start <CAMINHO_DO_SERVER.JS> --name <NOME_PARA_O_SERVIÇO>`
   - Ex.: `pm2 start /home/vinicius/agenda/server.js --name Agenda`
   - **Obs.:** Lembrando que deve ter todos os arquivos do projeto, incluindo o arquivo **.env**, na pasta do servidor
