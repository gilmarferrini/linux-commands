
## Documentação e ajuda
### man [comando]
```console
foo@bar:~$ man ls
```
Exibe a documentação do comando ls
man pwd → mostra a documentação do comando pwd
> Nota: Alguns comandos não possuem uma documentação no man

### flag --help
```console
foo@bar:~$ ls --help
```
Exibe todas as flags possíveis do comando ls e algumas descrições

## Gerenciamento de Diretórios

### pwd (print working directory) exibe o diretório atual
```console
foo@bar:~$ pwd
/home/bar
```

### cd

```console
foo@bar:~$ cd /usr/share/fonts
```
Altera para o diretório fonts

```console
foo@bar:~$ cd /usr/share/fonts
foo@bar:/usr/share/fonts$
foo@bar:/usr/share/fonts$ cd -
foo@bar:~$
```
O comando cd - volta no diretório anterior
### cp

```console
foo@bar:~$ cp arquivo.txt mensagem.txt
```
Copia todo o conteúdo do arquivo.txt para outro arquivo mensagem.txt

```console
foo@bar:~$ cp workspace workspace-2
```
Copia o diretório workspace para wokspace-2 (somente se o diretório estiver vazio)

```console
foo@bar:~$ cp -r workspace workspace-2
```
Ele copia o diretório workspace para wokspace-2 usando a flag de recursividade -r (copia tudo dentro do diretório workspace para workspace-2)

### mv
```console
foo@bar:~$ mv arquivo.txt mensagem2.txt
```
move/renomeia o arquivo.txt para mensagem2.txt


```console
foo@bar:~$ mv bemvindo.txt projetos-java/bemvindo-novo-nome.txt
```
Vai mover o arquivo bemvindo.txt para o diretório projetos-java mas renomeando para bemvindo-novo-nome.txt

### ls
```console
foo@bar:~$ ls
Desktop Documents Downloads
```
Lista os arquivos e diretórios

```console
foo@bar:~$ ls *
Desktop:

Documents:
  homework.odt projetos/
```
Lista todos os arquivos, diretórios, subdiretórios e os arquivos dos subdiretórios

```console
foo@bar:~$ ls -l
drwxr-xr-x  2 foo bar  4096 jan 14 19:53 Documents/
```
lista os arquivos e diretórios (**d**rwxrwxr-x 2 foo bar 4096 ago 20 11:51 directory   esta saída é um diretório porque tem a letra d no começo e também mostra informações como grupo, usuário, tamanho e data de modicação)

```console
foo@bar:~$ ls bemvindo*
bemvindo.txt bemvindo-2.txt bemvindo-10.txt bemvindo.ts
```
Vai mostrar todos os arquivos/diretórios que começam com bemvindo


```console
foo@bar:~$ ls -la
drwxr-xr-x  2 foo bar  4096 jan 14 19:53 Documents/
drwxr-xr-x  2 foo bar  4096 jan 14 19:53 .themes/
```
ls -la ou ls -l -a → mostra os arquivos e diretórios e também os arquivos e diretórios ocultos que começam por . (ponto)

```console
foo@bar:~$ ll
drwxr-xr-x  2 foo bar  4096 jan 14 19:53 Documents/
drwxr-xr-x  2 foo bar  4096 jan 14 19:53 .themes/
```
ll → é um atalho para o comando ls -la

### history
```console
foo@bar:~$ history
 1  cd www
 2  ls
 3  cd my-projects/
 4  clear
 5  ls
 6  git clone git@github.com:gilmarferrini/linux-commands.git
 7  cd linux-commands/
 8  code .
 9  cd /usr/share/fonts
 ...
 1814  history
```
Exibe o histórico de comandos digitados

### mkdir
```console
foo@bar:~$ mkdir workspace
```
Cria um novo diretório chamado workspace

### mkdir
```console
foo@bar:~$ mkdir -p workspace/projects
```
Vai criar a estrutura de pastas /workspace e dentro /projects

### echo
```console
foo@bar:~$ echo "Hello World"
Hello World
```

echo msg→ terminal imprime a mensagem "msg”

### operadores > e >>

```console
foo@bar:~$ echo "Bem vindo" > bemvindo.txt
foo@bar:~$ cat bemvindo.txt
Bem vindo
```
Redireciona a saída do comando echo para o arquivo bemvindo.txt. O operador > é um operador STDOUT. Caso o arquivo já existir, ele vai ser substituido com o conteúdo fornecido para o echo.

```console
foo@bar:~$ echo "Bem vindo" >> bemvindo.txt
foo@bar:~$ cat bemvindo.txt
Bem vindo
foo@bar:~$ echo "Bem vindo" >> bemvindo.txt
foo@bar:~$ cat bemvindo.txt
Bem vindo
Bem vindo
```

A diferença entre o operador > e >> é que o >> além de criar um novo arquivo caso não existir, ele também anexa o conteúdo/arquivo no existente.

Outro exemplo:


```console
foo@bar:~$ man pwd > pwdDocs.txt
```
### cat

```console
foo@bar:~$ cat bemvindo.txt
Bem vindo
```
Imprime o conteúdo do arquivo bemvindo.txt no terminal

```console
foo@bar:~$ cat b?.txt
Bem vindo
```
Imprime todos os arquivos que tem a letra b, seguido por qualquer letra/numero/símbolo e logo em seguida termina com .txt

```console
foo@bar:~$ cat *.txt
Bem vindo
Hello World
Exemplo 1
Exemplo 2
```
Imprime todos os arquivos que terminam com .txt e contenham qualquer quantidade de caracteres antes do .txt

```console
foo@bar:~$ cat nome*.txt
Bob
Gilmar
```
Imrpime todos os arquivos que começam com nome e terminam com .txt

### clear e ctrl + l

```console
foo@bar:~$ clear
```
Limpa o terminal

ctrl + l → não limpa o terminal, apenas adiciona um espaço em branco abaixo do conteúdo para ter a sensação de terminal limpo

### nautilus
```console
foo@bar:~$ nautilus
```
Abre a interface gráfica no diretório /home/USUÁRIO


```console
foo@bar:~$ cd /usr/share/fonts
foo@bar:~$ nautilus -w $(pwd)
```
Abre a interface gráfica a partir do retorno do comando pwd (no exemplo acima na pasta fonts)

```console
foo@bar:~$ nautilus .
```
Abre a interface gráfica na pasta atual

```console
foo@bar:~$ nautilus -w /home
```
Abre a interface gráfica dentro do diretório /home

### touch

```console
foo@bar:~$ touch arquivo.txt
```
Cria um arquivo vazio com o nome arquivo.txt

```console
foo@bar:~$ touch b1.txt b2.txt b3.txt
```
Cria 3 arquivos vazios: b1.txt b2.txt b3.txt

```console
foo@bar:~$ touch b{1..3}.txt
```
Cria 3 arquivos vazios: b1.txt b2.txt b3.txt

### rmdir

```console
foo@bar:~$ rmdir workspace
```
Apaga o diretório workspace (somente se o diretório estiver vazio)

### rm
```console
foo@bar:~$ rm arquivo.txt
```
Apaga o arquivo.txt

### rm
```console
foo@bar:~$ rm -r workspace
```
Apaga tudo que ta dentro do workspace, a flag -r significa recursividade (vai apagar tudo que ele encontrar dentro do diretório workspace inclusive o próprio diretório)

### zip

### rm
```console
foo@bar:~$ zip -r work.zip workspace
```
Compacta o diretório/arquivo. Primeiro parâmetro é o nome do arquivo final.zip e o segundo é o arquivo/pasta. O -r vai compactar tudo dentro da pasta de forma recursiva, se não vai criar somente um arquivo zip com a pasta workspace vazia

```console
foo@bar:~$ zip -r -q work.zip workspace
```
Compacta o diretório/arquivo. Primeiro parâmetro é o nome do arquivo final.zip e o segundo é o arquivo/pasta. O -r vai compactar tudo dentro da pasta de forma recursiva, se não vai criar somente um arquivo zip com a pasta workspace vazia e o -q vai compactar sem mostrar nenhuma mensagem

### unzip
```console
foo@bar:~$ unzip nome.zip
```
Descompacta o arquivo.zip

```console
foo@bar:~$ unzip -l nome.zip
```
Imprime os arquivos/pastas dentro do arquivo zip

```console
foo@bar:~$ unzip -q nome.zip
```
Descompacta sem mostrar nenhum texto

### tar
```console
foo@bar:~$ tar -czf work.tar.gz workspace
```
Por padrão o tar já é recursivo. O tar.gz deixa o arquivo menor também

```console
foo@bar:~$ tar -xzf work.tar.gz
```
Descompactar o arquivo work.tar.gz

> Nota: Podemos adicionar uma flag -v nos dois comandos para indicar o modo verbose

O parâmetro `-c` indica ao comando `tar` que desejamos criar um novo arquivo.

O comando `tar` apenas empacota vários arquivos em um único arquivo, sem realizar compactação, e por isso passamos o parâmetro `-z` para indicar que queremos, além de criar um único arquivo, realizar um processo de compactação utilizando o formato `.gz`. Quando compactamos podemos reduzir o tamanho.

O parâmetro `-f` indica que compactaremos para um arquivo.

### less
```console
foo@bar:~$ less google.txt
```
Vai abrir o arquivo e usar as setas como navegação e outros atalhos

### tail
```console
foo@bar:~$ tail -n 3 google.txt 
```
Vai mostrar as 3 últimas linhas

### head
```console
foo@bar:~$ head -n 3 google.txt 
```
Vai mostrar as 3 primeiras linhas

### dpkg  (baixo nível - usa em programas ja baixado no sistema - não podendo instalar dependencia)

```console
foo@bar:~$ sudo dpkg --remove nome_pacote
```
Remove o pacote porém mantem os arquivos de configurações

```console
foo@bar:~$ sudo dpkg --purge nome_pacote
```
Além de remover, ele também apaga os arquivos de configurações

```console
foo@bar:~$ dpkg -l code
Desired=Unknown/Install/Remove/Purge/Hold
| Status=Not/Inst/Conf-files/Unpacked/halF-conf/Half-inst/trig-aWait/Trig-pend
|/ Err?=(none)/Reinst-required (Status,Err: uppercase=bad)
||/ Name           Version           Architecture Description
+++-==============-=================-============-=============================>
ii  code           1.74.3-1673284829 amd64        Code editing. Redefined.
```

### apt (alto nivel - busca em servidores remotos e instalam dependencias)

```console
foo@bar:~$ sudo !!
```
Execute o ultimo comando

### VI

i → sai do modo interativo e vai para modo de inserção de texto

a → sai do modo interativo e vai par ao modo inserção porém inserindo um caractere a frente

ESC → sai para o modo de interação

:q! → sai sem salvar

:w → salva

:wq ou :x→ salva e sai

r → entra no modo replace

delete ou x → deleta o caractere

:w [nome_novo].txt salva e cria um novo arquivo

dd → recorta a linha

yy → copia a linha
cop*ia a linha*

7dd → recorta 7 linhas

:20 → vai para a linha 20

gg → vai para a primeira linha

G → vai para a última linha

p → cola o conteúdo recortado com o dd abaixo da linha atual

P → cola o conteúdo recortado com o dd acima da linha atual

u → desfaz a última alteração