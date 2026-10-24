## Movimentação
- `w` move para o início da próxima palavra
- `W` move para o início da próxima palavra ignorando pontuação
- `e` move para o fim da próxima palavra
- `E` move para o fim da próxima palavra ignorando pontuação
- `b` volta para o início da palavra anterior
- `B` volta para o início da palavra anterior ignorando pontuação
- `ge` volta para o fim da palavra anterior
- `gE` volta para o fim da palavra anterior ignorando pontuação
- `0` move para o início da linha
- `$` move para o final da linha
- `f<caracter>` move o cursor para o próximo `<caracter>`
- `F<caracter>` move o cursor para o `<caracter>` anterior 
- `t<caracter>` move o cursor para o próximo caracter anterior ao `<caracter>`
- `T<caracter>` move o cursor para o caracter anterior ao `<caracter>` anterior ao cursor
- `%` move para o parênteses correspondente
- `G` move para o final do arquivo
- `gg` move para o início do arquivo
- `<line>+G` move para linha específica

**Obs.:** Para repetir um comando, basta adicionar o número de repetições na frente, por exemplo. `2w` para repetir o comando de pular para o início da próxima palavra **duas vezes**

---

## Edição de texto
- `x` deleta o caracter onde está o cursor
- `p` cola o valor depois oua abaixo de onde está o cursor (substitui o registro)
- `P` cola o valor atrás ou acima de onde está o cursor (não substitui o registro)
- `acento grave+[` vai para o início do que acabou de colar
- `acento grave+]` vai para o final do que acabou de colar
- `gp` e `gP` mesma coisa do `p` e `P` mas coloca o cursor no final da linha
- `y` copia
- `yy` copia a linha inteira
	- `j$` logo após copiar leva para o final da próxima linha
- `d<movimento>` deleta com base no movimento
    - por exemplo, `dw` que apaga apenas uma palavra
- `dd` deleta a linha inteira
- `u` desfaz o último comando executado
- `U` desfaz toda as alterações da linha onde está o cursor
- `CRTL+R` refaz o último comando
- `"<letter><comand>` joga o valor da ação do `<comand>` para o registro do `<letter>`
- `"<letter>p` usa o registro do `<num>`, por exemplo, `"1p`

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
- `:<range>s//<old>/<new>/g` substitui a última busca realizada

**Obs.:** O range das substituições pode ser passado com o modo de vizualização (v)

### Flags
- `g` realiza a substituição na linha onde o cursor está
- `c` solicita confirmação da substituição
- `i` realiza a busca sem diferenciar maiúscula de minúscula

---

## Buscar
- `/<search>` procura por uma frase ou palavra de cima para baixo
- `?<search>` procura por uma frase ou palavra de baixo para cima
- `n` move para o próximo resultado  da pesquisa
- `N` retorna para o resultado anterior da pesquisa
- `*` busca a próxima ocorrência da palavra onde está o cursor
- `#` busca a ocorrência anterior da palavra onde está o cursor
- `g*` e `g#` mesma coisa do `*` e `#` 

**Obs.:** Se colocar a flag `\c` no final, a busca vai ignorar case sensitive

### É possível combinar comandos com o de busca, por exemplo:
- `y/<word>` copia de onde o cursor está até a próxima ocorrência da `<word>`
- `d?<word>` apaga/corta tudo de onde o cursor está até a `<word>`
- `c/<word>` apaga e entra na inserção (change) de onde o cursor está até a `<word>`
- `v?<word>` seleciona tudo de onde o cursor está até a `<word>`

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
- `>>` e `<<` indenta o código para frente e para trás
- `==` corrige a indentação da linha
- `CTRL+e` movimenta a tela para cima sem tirar o cursor do lugar
- `CTRL+y` movimenta a tela para baixo sem tirar o cursor do lugar
- `zt` move a linha do cursor para o top
- `zz` move a linha do cursor para o meio
- `zb` move a linha do cursor para o rodapé
- `H` move o cursor para a primeira linha do viewport
- `L` move o cursor para a última linha do viewport
- `M` move o cursor para o meio do viewport
- `CTRL+d` move o cursor meia página pra baixo
- `CTRL+u` move o cursor meio página para cima
- `CTRL+f` move o cursor uma página para cima
- `CTRL+b` move o cursor uma página para baixo
- `{` e `}` move para o próximo espaço em branco antes do parágrafo
- `[` e `]` move para o início do parágrafo

---

## Preferências
- `:set ic` (Ignore Case)  ignora a diferença entre maiúscula e minúscula na pesquisa
- `:set hls is` realça as pesquisas

**Obs.:** adicione `no` no início do comando para desabilitar a preferência, por exemplo, `:set nohls` desabilita o realce das pesquisas

---

## Comandos úteis
- `CRTL+w` pular para outra janela quando mais de uma estiver aberta no Vim, por exemplo, sistema de ajuda (`F1` || `:help <ENTER> || :help <comand> <ENTER>`)
- `:registers` para ver os registros (itens deletados ou copiados)
