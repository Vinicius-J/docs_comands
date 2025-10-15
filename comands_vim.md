## Movimentação
- `w` move para o início da próxima palavra
- `e` move para o fim da próxima palavra
- `0` move para o início da linha
- `$` move para o final da linha
- `f<caracter>` move o cursor para o próximo `<caracter>`
- `F<caracter>` move o cursor para o `<caracter>` anterior 
- `t<caracter>` move o cursor para o próximo caracter anterior ao `<caracter>`
- `T<caracter>` move o cursor para o caracter anterior ao `<caracter>` anterior ao cursor
- `%` move para o parênteses correspondente
- `G` move para o final do arquivo
- `gg` move para o início do arquivo
- `G+<linha>` move para linha específica


**Obs.:** Para repetir um comando, basta adicionar o número de repetições na frente, por exemplo. `2w` para repetir o comando de pular para o início da próxima palavra **duas vezes**

---

## Edição de texto
- `x` deleta o caracter onde está o cursor
- `p` cola o que estiver guardado no registro do vim
- `y` copia
	- `j$` logo após copiar leva para o final da próxima linha
- `d<movimento>` deleta com base no movimento
    - por exemplo, `dw` que apaga apenas uma palavra
- `dd` deleta a linha inteira
- `u` desfaz o último comando executado
- `U` desfaz toda as alterações da linha onde está o cursor
- `CRTL+R` refaz o último comando

**Obs.:** Alguns comandos podem ser usado com contador e movimentos, por exemplo, `yw` copia a palavra onde o cursor está; `2p` cola duas vezes o que foi copiado 

---

## Inserção
- `i` inseri onde o cursor está
- `A` vai para o final da linha e entra no modo inserção
- `a` vai para depois do cursor e entra no modo inserção
- `o` cria uma linha **abaixo** de onde o cursor está, no modo de inserção
- `O` cria uma linha **acima** de onde o cursor está, no modo de inserção
- `gi` entra no modo inserção no último lugar que entrou nesse modo 

---

## Vizualização
- `v` entra no modo de vizualização
- `vg_` seleciona até o último caracter da linha a partir do cursor
- `gv` refaz a última seleção (v)
- `vip` seleciona todo o parágrafo 

---

## Substituição
- `r<caracter>` substitui o carácter onde o cursor está
- `R` substitui a partir de onde o cursor está, apagando conforme inserir novos caracteres
- `c<movimento>` apaga(substitui) conforme o movimento e entra no modo inserção
- `:s/<old>/<new>/g` substitui o `<old>` pelo `<new>` na mesma linha
- `:#,#s/<old>/<new>/g` substitui o `<old>` pelo `<new>` em linhas específicas (alterar o `#` pelas linhas)
- `:%s/<old>/<new>/g` substitui todos os `<old>` pelo `<new>` no arquivo
- `:%s/<old>/<new>/gs` substitui todos os `<old>` pelo `<new>` no arquivo, com a opção de confirmar

---

## Buscar
- `/<search>` procura por uma frase ou palavra de cima para baixo
- `?<search>` procura por uma frase ou palavra de baixo para cima
- `n` move para o próximo resultado  da pesquisa
- `N` retorna para o resultado anterior da pesquisa

---

## Editor
- `g+CRTL+g` mostra nome do arquivo e posição do cursor no arquivo
- `CTRL+O` retorna para posição anterior do cursor
- `CRTL+I` retorna para o local mais recente do cursor
- `:!<comand>` executa comando como se estivesse no shell
- `:w <name>` salva arquivo com o nome de `<name>`
	- Para salvar parte de um arquivo, selecione ele com o modo visual (v) e salve normalmente
- `:r <doc_name>` recupera o `<doc_name>` e uni no arquivo atual logo abaixo do cursor
	- `:r !<comand>` pega o resultado do `<comand>` e uni no arquivo atual
- `gc` para comentar uma linha ou seleção
- `>>` indenta o código para frente
- `<<` indenta o código para trás
- `==` corrige a indentação da linha

---

## Preferências
- `:set ic` (Ignore Case)  ignora a diferença entre maiúscula e minúscula na pesquisa
- `:set hls is` realça as pesquisas

**Obs.:** adicione `no` no início do comando para desabilitar a preferência, por exemplo, `:set nohls` desabilita o realce das pesquisas

---

## Comandos úteis
- `CRTL+w` pular para outra janela quando mais de uma estiver aberta no Vim, por exemplo, sistema de ajuda (`F1` || `:help <ENTER> || :help <comand> <ENTER>`)


