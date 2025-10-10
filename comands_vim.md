## 1: Editar textos - remoção
	- x - (apenas um caracter)
## 1: Editar textos - adicionar
	- A - (final da linha no modo inserção)
	- a - (depois do caracter selecionado)
## 2: Comandos de remoção
	- dw - deleta até o início da próxima palavra 
	- d$ - deleta até o final da linha
	- de - deleta até o fim da palavra atual
	- dd - deletar a linha inteira
## 2.4: Contador de movimentos
	- <numero>w - mover quantidade de palavras
	- <numero>e - mover para o fim da palavra
**Obs.:** Para repetir um comando, basta adicionar um número na frente.
**Ex.:** 2dd - Para apagar duas linhas seguidas
	- 0 - mover para o início da linha
	- w - mover palavra por palavra
##  2.7: Comando undo (desfazer) e refazer
	- u - desfaz o último comando executado
	- U - retorna a linha ao seu estado original
	- CRTL+R - refaz os comandos	
## 3: Comando colar
	- p - Para colar o que estiver guardado no registro do vim
	- r<caracter> - Para substuir o caracter sob o cursor
	- ce - Para mudar a palavra a partir do cursor
	- c$ - Para mudar até o fim da linha a partir do cursor
**Obs.:** O comando change (c) funciona igual ao delete (d), ou seja, podendo ser usado com [número] e movimento.
**Ex.:** c2w - para mudar duas palavras
## 4: Localização do cursor e estado do arquivo
	- CRTL+G - Para ver nome do arquivo e posição no arquivo
	- G - Para mover para o final do arquivo
	- gg - Para mover para o início do arquivo
	- G+<linha> - Para mover para linha específica
##4.2: Comando de buscar
	- /<frase> - Para procurar por uma frase ou palavra
	- ?<frase> - Para procurar por uma frase ao contrário
	- n - Para ir para a próxima palavra encontrada
	- N - Para retornar a palavra anterior 
**Obs.:** `CTRL+O` e `CRTL+I` servem para voltar aonde o cursor estava anteriormente e retornar ao local mais recente, nesta ordem
	- % - Para buscar parênteses correspondentes ou voltar ao primeiro
**Ex.:** ([{}]) - Cada um tem seu correspondente, ou seja, é aberto e fechado
## 4.4: Comando substituir
	- :s/<velho>/<novo>/g - Expressão que pode ser usado para substituir palavras na linhas que está o cursor
	- :#,#s/<velho>/<novo>/g - Substituir em linhas específicas, onde o # é as linhas
	- :%s/<velho>/<novo>/g - Para mudar todas as ocorrências no arquivo inteiro
	- :%s/<velho>/<novo>/gs - Para mudar todas as ocorrências no arquivo inteiro, com a opção de confirmar
## 5: Executar comandos externos
	- :!<comando> - Para executar comando como se estivesse no shell
## 5.2: Salvar arquivos
	- :w <nome> - Para salvar arquivo com o nome passado
**Obs.:** Para salvar parte de um arquivo, selecione ele com o modo visual (v) e siga o passo de salvar arquivos
	- :r <nome_arquivo> - Para recuperar e unir arquivo abaixo do cursor
**Obs.:** Também é possível unir saída de um comando shell
**Ex.:** :r !ls - Uni o resultado que sair desse comando
## 6: Comando abrir
	- o - Inserir uma linha abaixo no modo de inserção
	- O - Inserir uma linha acima no modo de inserção
## 6.3: Outra forma de substituição
	- R - Modo de substituição, onde altera a partir de onde está o cursor apagando o próximo caracter
## 6.4: Copiar e colar texto
	- y - Copiar texto
	- p - Colar texto
**Obs.:** Logo após copiar (y), se digitar j$ vai para o final da próxima linha
**Obs.:** É possível usar o copiar (y) como um operador; por exemplo, yw copia uma palavra

	PAREI NA LIÇÃO 6.5
