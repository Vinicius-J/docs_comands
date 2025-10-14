## Editar textos
- `x` deleta apenas um carácter por vez
- `p` cola o que estiver guardado no registro do vim
- `y` copiar texto selecionado no modo visualização (v)
	- Pode ser usado com contador e movimento, por exemplo, `yw` copia a palavra onde está o cursor
	- `j$` logo após copiar leva para o final da próxima linha
- `A` vai até o final da linha e entra no modo inserção
- `a` vai para depois do cursor e entra no modo inserção
- `dw` deleta até o início da próxima palavra 
- `d$` deleta até o final da linha
- `de` deleta até o fim da palavra atual
- `dd` deletar a linha inteira

---

## Contador e movimentos
- `w` move para o início da próxima palavra
	- `<num>w` mover quantidade de palavras
- `e` move para o fim da próxima palavra
	- `<num>e` move para o fim da `<num>` palavra
**Obs.:** Para repetir um comando, basta adicionar o número de repetições na frente, por exemplo. `2w` para repetir o comando de pular para o início da próxima palavra **duas vezes**
- `0` move para o início da linha
- `o` cria uma linha **abaixo** de onde o cursor está, no modo de inserção
- `O` cria uma linha **acima** de onde o cursor está, no modo de inserção

---

##  Comando undo (desfazer) e refazer
- `u` desfaz o último comando executado
- `U` desfaz toda as alterações da linha onde está o cursor
- `CRTL+R` refaz os comandos	

---

## Colar e mudar
- `r<caracter>` substitui o carácter sob o cursor
- `R` substitui a partir de onde o cursor está, apagando conforme inserir novos caracteres
- `ce` muda os caracteres a partir de onde está o cursor
- `c$` muda até o fim da linha a partir do cursor
**Obs.:** O comando change (c) funciona igual ao delete (d), ou seja, podendo ser usado com **contador** e **movimento**.
**Ex.:** `c2w` muda duas palavras seguidas

---

## Localização do cursor e estado do arquivo
- `CRTL+G` mostra nome do arquivo e posição do cursor no arquivo
- `G` move para o final do arquivo
- `gg` move para o início do arquivo
- `G+<linha>` move para linha específica
- `CTRL+O` retorna para posição anterior do cursor
- `CRTL+I` retorna para o local mais recente do cursor

---

## Comando de buscar
- `/<search>` procura por uma frase ou palavra de cima para baixo
- `?<search>` procura por uma frase ou palavra de baixo para cima
- `n` move para o próximo resultado  da pesquisa
- `N` retorna para o resultado anterior da pesquisa
- `%` busca por parentese correspondente (o que abre e o que fecha)

---

## Comando substituir
- `:s/<old>/<new>/g` substitui o `<old>` pelo `<new>` na mesma linha
- `:#,#s/<old>/<new>/g` substitui o `<old>` pelo `<new>` em linhas específicas (alterar o `#` pelas linhas)
- `:%s/<old>/<new>/g` substitui todos os `<old>` pelo `<new>` no arquivo
- `:%s/<old>/<new>/gs` substitui todos os `<old>` pelo `<new>` no arquivo, com a opção de confirmar

---

## Executar comandos externos
- `:!<comand>` executa comando como se estivesse no shell

---

## Salvar arquivos
- `:w <name>` salva arquivo com o nome de `<name>`
	- Para salvar parte de um arquivo, selecione ele com o modo visual (v) e salve normalmente
- `:r <doc_name>` recupera o `<doc_name>` e uni no arquivo atual logo abaixo do cursor
	- `:r !<comand>` pega o resultado do `<comand>` e uni no arquivo atual

---

## Configuração de preferência
- `:set ic` (Ignore Case)  ignora a diferença entre maiúscula e minúscula na pesquisa
- `:set hls is` realça as pesquisas
**Obs.:** adicione `no` no início do comando para desabilitar a preferência, por exemplo, `:set nohls` desabilita o realce das pesquisas

---

## Comandos úteis
- `CRTL+w` pular para outra janela quando mais de uma estiver aberta no Vim, por exemplo, sistema de ajuda (`F1` || `:help <ENTER> || :help <comand> <ENTER>`)
