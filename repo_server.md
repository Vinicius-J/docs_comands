# Como criar um repositório bare no servidor para interligar o projeto final com a produção
## Na máquina principal:
1. Abrir a pasta do projeto pelo terminal
2. Confirmar o email e nome de usuário no **git**:
    - `git config --global user.email "<EMAIL_DO_USUARIO>"`
    - `git config --global user.name "<NOME_DO_USUARIO>"`
3. Com o **git** configurado, inicie ele na pasta do projeto com o comando `git init`
4. Crie o arquivo que irá fazer o **git** ignorar alguns arquivos que não precisam ir para o servidor
    - `nano .gitignore`
    - Dentro do arquivo digite o nome dos arquivos que quer ignorar, como por exemplo **node_modules** e **.env**, salve e saia do arquivo
5. Adicione os arquivos do projeto no **git**
    - `git add .`
    - `git commit -am "<MENSAGEM_QUE_QUISER>"`
## Na máquina que será usada como servidor:
1. Crie uma pasta no servidor que será responsável por armazenar os dados do projeto:
    - `mkdir <NOME_DA_PASTA_PRINCIPAL>`
        - Ex.: `mkdir projeto-agenda`
2. Dentro da pasta principal do projeto crie duas pastas, sendo uma reponsável por armazenar os arquivos do projeto e outra que será o respositório do projeto, lembrando que a pasta **repo-projeto** pode ser substituida por um repositório no **github**
    - `mkdir repo-<NOME_DO_PROJETO>`
        - Ex.: `mkdir repo-agenda`
    - `mkdir <NOME_DO_PROJETO>`
        - Ex.: `mkdir agenda`
### Caso tenha criado a pasta **repo-<NOME_DO_PROJETO>** :
1. Entre na pasta **repo-<NOME_DO_PROJETO>**
2. Crie um repositório git com o comando `git init --bare`
3. Entre na pasta dos arquivos do projeto
4. Inicie o git na pasta dos arquivos do projeto com o `git init`
5. Adicione o **repo-<NOME_DO_PROJETO>** como repositório remoto com o comando `git remote add <NOME_DO_REPOSITORIO> <DIRETORIO_DO_REPOSITORIO>`
    - Ex.: Usando como exemplo um projeto de agenda:
    - `git remote add agenda_origin /home/vinicius/projeto-agenda/repo-agenda`
- **Obs.:** Caso não tenha criado a pasta **repo-projeto**, no lugar de **<DIRETORIO_DO_REPOSITORIO>** coloque o endereço web do repositório no github
## Na máquina principal
1. Abra a pasta do projeto pelo terminal
2. Adicione o **repo-<NOME_DO_PROJETO>** como repositório remoto com o comando `git remote add <NOME_DO_REPOSITORIO> <IP_DO_SERVIDOR>:<NOME_DA_PASTA_PRINCIPAL>/repo-<NOME_DO_PROJETO>`
 - Ex.: Usando como exemplo um projeto de agenda:
 - `git remote add agenda_origin 999.999.9.999:projeto-agenda/repo-agenda`
 3. Envie os aquivos do projeto com o comando `git push <NOME_DO_REPOSITORIO> master` ou apenas `git push`
    - Ex.: `git push origin_agenda master`
## Na máquina que será usada como servidor:
1. Abra a pasta que ficará os arquivos do projeto e digite o comando `git pull <NOME_DO_REPOSITORIO> master` ou apenas `git pull`