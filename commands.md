### man [comando]

man ls → mostra a documentação do comando ls

man pwd → mostra a documentação do comando pwd

### pwd

**pwd**→ (print working directory) exibe o diretório atual

### cd

**cd Desktop** → (change directory)  muda para o diretório Desktop. O comando cd muda de diretórios

**cd - →** volta no diretório anterior

### cp

**cp arquivo.txt mensagem.txt** → copia todo o conteúdo do arquivo.txt para outro arquivo mensagem.txt

**cp workspace workspace-2** → ele copia o diretório workspace para wokspace-2 (somente se o diretório estiver vazio)

**cp -r workspace workspace-2** → ele copia o diretório workspace para wokspace-2 usando a flag de recursividade -r (copia tudo dentro do diretório workspace para workspace-2)

### mv

**mv arquivo.txt mensagem2.txt** → vai mover/renomear o arquivo.txt para mensagem2.txt

**mv bemvindo.txt projetos-java/bemvindo-novo-nome.txt** → vai mover o arquivo bemvindo.txt para o diretório projetos-java mas renomeando para bemvindo-novo-nome.txt

### ls

ls → lista os arquivos e diretórios

ls * → lista todos os arquivos, diretórios, subdiretórios e os arquivos dos subdiretórios

ls -l → lista os arquivos e diretórios (**d**rwxrwxr-x 2 gilmarferrini gilmarferrini 4096 ago 20 11:51 directory   esta saída é um diretório porque tem a letra d no começo e também mostra informações como grupo, usuário, tamanho e data de modicação)

ls bemvindo* → vai mostrar todos os arquivos/diretórios que começam com bemvindo

ls -la ou ls -l -a → mostra os arquivos e diretórios e também os arquivos e diretórios ocultos que começam por . (ponto) -


ll → é um atalho para o comando ls -la

### history

history → mostra o histórico de comandos digitados

### mkdir

mkdir workspace → (make dir) cria um novo diretório chamado workspace

mkdir -p /field/projects → vai criar a estrutura de pastas /field e dentro /projects

### echo e operadores >  >>

echo msg→ terminal imprime a mensagem "msg”

echo "Bem vindo" > bemvindo.txt → redireciona a saída do comando echo para o arquivo bemvindo.txt. O operador > é um operador STDOUT. Caso o arquivo já existir, ele vai ser substituido com o conteúdo fornecido para o echo.

echo "Bem vindo" >> bemvindo.txt → a diferença entre o operador > e >> é que o >> além de criar um novo arquivo caso não existir, ele também anexa o conteudo/arquivo no existente

exemplo:

echo "bem vindo" >> text.txt

echo "bem vindo" >> text.txt

o arquivo text.txt vai ter o conteúdo:

bem vindo

bem vindo

O < redireciona o conteudo de m arquivo para um comando

E o > direciona a saida de um comando para um arquivo

man pwd > pwdDocs.txt

### cat

cat bemvindo.txt → vai ler o conteúdo do arquivo bemvindo.txt e imprimir no terminal

cat b?.txt → vai ler todos os arquivos que tem a letra b, seguido por qualquer letra/numero/simbolo e logo em seguida termina com .txt

cat *.txt → vai ler todos os arquivos que terminam com .txt

cat nome*.txt → vai ler todos os arquivos que começam com nome e terminam com txt

### clear e ctrl + l

clear → limpa o terminal

ctrl + l → não limpa o terminal, apenas adiciona um espaço em branco abaixo do conteúdo para ter a sensação de terminal limpo

### nautilus

nautilus → abre a interface gráfica

nautilus -w $(pwd) → abre a interface gráfica a partir do retorno do comando pwd

nautilus . → abre a interface gráfica na pasta atual

nautilus -w /home→abre a interface gráfica dentro do diretório /home

### touch

touch arquivo.txt → cria um arquivo vazio com o nome arquivo.txt

touch b1.txt b2.txt b3.txt → cria 3 arquivos vazios: b1.txt b2.txt b3.txt

touch b{1..3}.txt → cria 3 arquivos vazios: b1.txt b2.txt b3.txt

rmdir

rmdir workspace → apaga o diretório workspace (somente se o diretório estiver vazio)

### rm

rm arquivo.txt → apaga o arquivo

rm -r workspace → apaga tudo que ta dentro do workspace, a flag -r significa recursividade (vai apagar tudo que ele encontrar dentro do diretório workspace inclusive o próprio diretório)

### zip

zip -r work.zip workspace→ compacta o diretório/arquivo. primeiro parametro é o nome do arquivo final.zip e o segundo é o arquivo/pasta. O -r vai compactar tudo dentro da pasta de forma recursiva, se não vai criar somente um arquivo zip com a pasta workspace vazia

zip -r -q work.zip workspace→ compacta o diretório/arquivo. primeiro parametro é o nome do arquivo final.zip e o segundo é o arquivo/pasta. O -r vai compactar tudo dentro da pasta de forma recursiva, se não vai criar somente um arquivo zip com a pasta workspace vazia e o -q vai compactar sem mostrar nenhuma mensagem

### unzip

unzip nome.zip → descompacta o arquivo.zip

unzip -l nome.zip → imprime os arquivos/pastas dentro do arquivo zip

unzip -q nome.zip → descompacta sem mostrar nenhum texto

### tar

tar -czf work.tar.gz workspace → Por padrão o tar já é recursivo. O tar.gz deixa o arquivo menor também

tar -xzf work.tar.gz → descompactar o arquivo work.tar.gz

podemos adicionar uma flag -v nos dois para indicar o verbose

O parâmetro `-c` indica ao comando `tar` que desejamos criar um novo arquivo.

O comando `tar` apenas empacota vários arquivos em um único arquivo, sem realizar compactação, e por isso passamos o parâmetro `-z` para indicar que queremos, além de criar um único arquivo, realizar um processo de compactação utilizando o formato `.gz`. Quando compactamos podemos reduzir o tamanho.

O parâmetro `-f` indica que compactaremos para um arquivo.

### grep

### less

less google.txt → vai abrir o arquivo e usar as setas como navegacao

### tail

tail -n 3 google.txt → vai mostrar as 3 últimas linhas

### head

head -n 3 google.txt → vai mostrar as 3 primeiras linhas

### dpkg  (baixo nível - usa em programas ja baixado no sistema - não podendo instalar dependencia)

—remove → remove um arquivo

—purge → além de remover, ele também apaga os arquivos de configurações

dpkg -l code → lista se o programa ta instalado

dpkg -l | grep vim → filtrar todos os programas que contenham vim no nome

### apt (alto nivel - busca em servidores remotos e instalam dependencias)

sudo !! ← o !! puxa o ultimo comando

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