<p align="center">
  <img src="https://cloud.githubusercontent.com/assets/2059754/24601246/753a7f36-1858-11e7-9d6b-7a0e64fb27f7.png" alt="bash logo"/>
</p>

## Índice
  1. [Operações Básicas](#1-operações-básicas)  
    1.1. [Operações com Arquivo](#11-operações-com-arquivo)  
    1.2. [Operações com Texto](#12-operações-com-texto)  
    1.3. [Operações com Diretório](#13-operações-com-diretório)  
    1.4. [SSH, Informações do Sistema & Operações de Rede](#14-ssh-informações-do-sistema--operações-de-rede)  
    1.5. [Operações de Monitoramento de Processos](#15-operações-de-monitoramento-de-processos)
  2. [Programação Básica com Shell](#2-programação-básica-com-shell)  
    2.1. [Variáveis](#21-variáveis)  
    2.2. [Array](#22-array)  
    2.3. [Substituição de String](#23-substituição-de-string)  
    2.4. [Outros Truques com Strings](#24-outros-truques-com-strings)  
    2.5. [Funções](#25-funções)  
    2.6. [Condicionais](#26-condicionais)  
    2.7. [Loops](#27-loops)  
    2.8. [Regex](#28-regex)  
    2.9. [Pipes](#29-pipes)  
  3. [Truques](#3-truques)  
  4. [Depuração](#4-depuração)  
  5. [Multi-threading](#5-multi-threading)

# 1. Operações Básicas

### a. `export`
O comando `export` mostra todas as variáveis de ambiente. Caso você queira obter detalhes de uma variável específica, use `echo $NOME_DA_VARIAVEL`.  
```bash
export
```
Exemplo:
```bash
$ export
AWS_HOME=/Users/adnanadnan/.aws
LANG=en_US.UTF-8
LC_CTYPE=en_US.UTF-8
LESS=-R

$ echo $AWS_HOME
/Users/adnanadnan/.aws
```

### b. `whatis`
O comando `whatis` mostra a descrição dos comandos de usuário, system calls, funções de biblioteca e outros, extraídos das páginas de manual.
```bash
whatis alguma_coisa
```
Exemplo:
```bash
$ whatis bash
bash (1)             - GNU Bourne-Again SHell
```

### c. `whereis`
O comando `whereis` busca por executáveis, source files e páginas de manual, usando uma base de dados construída pelo sistema automaticamente.
```bash
whereis nome
```
Exemplo:
```bash
$ whereis php
/usr/bin/php
```

### d. `which`
O comando `which` busca por executáveis nos diretórios especificados pela variável de ambiente PATH. Este comando vai mostrar o caminho completo do(s) executável(eis).
```bash
which nome_do_programa
```
Exemplo:
```bash
$ which php
/c/xampp/php/php
```

### e. `clear`
O comando `clear` limpa o conteúdo da janela.

## 1.1. Operações com Arquivo
<table>
   <tr>
      <td><a href="#a-cat">cat</a></td>
      <td><a href="#b-chmod">chmod</a></td>
      <td><a href="#c-chown">chown</a></td>
      <td><a href="#d-cp">cp</a></td>
      <td><a href="#e-diff">diff</a></td>
      <td><a href="#f-file">file</a></td>
      <td><a href="#g-find">find</a></td>
      <td><a href="#h-gzip">gzip</a></td>
      <td><a href="#i-gzcat">gzcat</a></td>
      <td><a href="#j-gunzip">gunzip</a></td>
      <td><a href="#k-head">head</a></td>
   </tr>
   <tr>
      <td><a href="#l-less">less</a></td>
      <td><a href="#m-lpq">lpq</a></td>
      <td><a href="#n-lpr">lpr</a></td>
      <td><a href="#o-lprm">lprm</a></td>
      <td><a href="#p-ls">ls</a></td>
      <td><a href="#q-more">more</a></td>
      <td><a href="#r-mv">mv</a></td>
      <td><a href="#s-rm">rm</a></td>
      <td><a href="#t-tail">tail</a></td>
      <td><a href="#u-touch">touch</a></td>
   </tr>
</table>

### a. `cat`
O comando `cat` pode ser usado, no UNIX ou no Linux, para os seguintes propósitos: 
* Imprimir arquivos de textos na tela;
* Copiar arquivos de texto;
* Combinar arquivos de texto;
* Criar novos arquivos de texto. 
```bash
cat nome_do_arquivo
cat arquivo1 arquivo2 
cat arquivo1 arquivo2 > nome_do_arquivo_combinado
cat < arquivo1 > arquivo2 #copia o arquivo1 para o arquivo2
```

### b. `chmod`
O comando `chmod`, acrônimo para "change mode" (alterar modo), permite que você altere as permissões de leitura, escrita e execução dos seus arquivos e pastas. Para mais informações a respeito desse comando, acesse este [link](https://ss64.com/bash/chmod.html).
```bash
chmod -opcoes nome_do_arquivo
```

### c. `chown`
O comando `chown`, acrônimo para "change owner" (alterar proprietário), permite que você altere o proprietário de um determinado arquivo ou pasta, o qual pode ser um usuário ou um grupo. O uso básico é simples: primeiro vem o usuário (proprietário) e depois o grupo, delimitado por dois pontos.
```bash
chown -opcoes usuario:grupo nome_do_arquivo
```

### d. `cp`
O comando `cp` copia um arquivo de um local para outro.  
```bash
cp nome_do_arquivo1 nome_do_arquivo2
```
Em que `nome_do_arquivo1` é o caminho do arquivo original e `nome_do_arquivo2` é o caminho para o destino da cópia do arquivo.

### e. `diff`
O comando `diff` compara arquivos e lista suas diferenças.  
```bash
diff nome_do_arquivo1 nome_do_arquivo2
```

### f. `file`
O comando `file` determina o tipo do arquivo.  
```bash
file nome_do_arquivo
```
Exemplo:
```bash
$ file index.html
 index.html: HTML document, ASCII text
```
### g. `find`
O comando `find` encontra arquivos no diretório.
```bash
find diretorio opcoes parametro
```
Exemplo:
```bash
$ find . -name README.md
$ find /home/user1 -name '*.png'
```

### h. `gzip`
O comando `gzip` compacta arquivos.  
```bash
gzip nome_do_arquivo
```

### i. `gzcat`
O comando `gzcat` permite verificar o conteúdo no arquivo compactado pelo gzip sem precisar descompactá-lo.  
```bash
gzcat nome_do_arquivo
```

### j. `gunzip`
O comando `gunzip` descompacta arquivos compactados pelo gzip.  
```bash
gunzip nome_do_arquivo
```

### k. `head`
O comando `head` exibe as primeiras 10 linhas de um arquivo.
```bash
head nome_do_arquivo
```

### l. `less`
O comando `less` exibe o conteúdo de um arquivo, ou da saída de um comando, em uma página por vez. Ele é similar ao [more](#q-more), mas possui recursos mais avançados, permitindo navegar tanto para frente quanto para trás, através do arquivo. 
```bash
less nome_do_arquivo
```

### m. `lpq`
O comando `lpq` exibe a fila de impressão.  
```bash
lpq
```
Exemplo:
```bash
$ lpq
Rank    Owner   	Job     File(s) 	Total Size
active  tuxmarrento 	59      README.md 	399360 bytes
1st     tuxmarrento 	60      (stdin) 	0 bytes
```

### n. `lpr`
O comando `lpr` imprime um arquivo.  
```bash
lpr nome_do_arquivo
```

### o. `lprm`
O comando `lprm` remove algo da fila de impressão, usando o "número" (ID) do trabalho verificado na coluna "job" do comando lpq.  
```bash
lprm id_do_trabalho
```

### p. `ls`
O comando `ls` lista o conteúdo de um diretório. `ls`possui várias opções: `-l` lista os arquivos em formato estendido, o qual contém o tamanho exato do arquivo, o proprietário, quem tem a permissão para vê-lo e quando foi a última modificação; `-a` lista todos os arquivos, incluindo os ocultos. Para mais informações a respeito desse comando, acesse este [link](https://ss64.com/bash/ls.html).  
```bash
ls opcao
```
Exemplo:
<pre>
$ ls -la
rwxr-xr-x   33 tuxmarrento  staff    1122 Mar 27 18:44 .
drwxrwxrwx  60 tuxmarrento  staff    2040 Mar 21 15:06 ..
-rw-r--r--@  1 tuxmarrento  staff   14340 Mar 23 15:05 .DS_Store
-rw-r--r--   1 tuxmarrento  staff     157 Mar 25 18:08 .bumpversion.cfg
-rw-r--r--   1 tuxmarrento  staff    6515 Mar 25 18:08 .config.ini
-rw-r--r--   1 tuxmarrento  staff    5805 Mar 27 18:44 .config.override.ini
drwxr-xr-x  17 tuxmarrento  staff     578 Mar 27 23:36 .git
-rwxr-xr-x   1 tuxmarrento  staff    2702 Mar 25 18:08 .gitignore
</pre>

### q. `more`
O comando `more` exibe a primeira parte de um arquivo (mova a exibição com a tecla de espaço e digite "q" para sair). É uma versão mais antiga e simplificada do [less](#l-less), visto acima. 
```bash
more nome_do_arquivo
```

### r. `mv`
O comando `mv` move um arquivo de um lugar para outro..  
```bash
mv nome_do_arquivo1 nome_do_arquivo2
```
Em que `nome_do_arquivo1` é o caminho do arquivo original e `nome_do_arquivo2` o caminho para o destino do arquivo.

O comando `mv` também pode ser usado para renomear um arquivo.
```bash
mv nome_antigo novo_nome
```
Em que `nome_antigo` é o caminho do arquivo e `novo_nome` é o novo nome com o mesmo caminho para o arquivo; caso a linha de comando esteja executando no diretório onde está o arquivo, basta usar somente o nome, dispensando o caminho.

### s. `rm`
O comando `rm` remove o arquivo. O uso desse comando com um diretório retorna um erro:
`rm: diretorio: is a directory`
Para remover um diretório, deve-se acrescentar a opção `-r`, a qual remove o conteúdo do diretório recursivamente. Opcionalmente, pode-se usar a flag `-f` para forçar a exclusão, i.e., sem quaisquer confirmações etc.
```bash
rm nome_do_arquivo
```

### t. `tail`
O comando `tail` exibe as últimas 10 linhas de um arquivo. Use `-f` para exibir os dados apensados (appended: anexados ao final), à medida em que o arquivo cresce.  
```bash
tail nome_do_arquivo
```

### u. `touch`
O comando `touch` atualiza registros de data e hora de acesso e modificação do seu arquivo. Se o arquivo não existir, ele será criado.
```bash
touch nome_do_arquivo
```
Exemplo:
```bash
$ touch trick.md
```

## 1.2. Operações com Texto

<table>
    <tr>
      <td><a href="#a-awk">awk</a></td>
      <td><a href="#b-cut">cut</a></td>
      <td><a href="#c-echo">echo</a></td>
      <td><a href="#d-grep">grep</a></td>
      <td><a href="#e-egrep">egrep</a></td>
      <td><a href="#f-fgrep">fgrep</a></td>
      <td><a href="#g-fmt">fmt</a></td>
      <td><a href="#h-nl">nl</a></td>
      <td><a href="#i-sed">sed</a></td>
      <td><a href="#j-sort">sort</a></td>
   </tr>
   <tr>
      <td><a href="#k-tr">tr</a></td>
      <td><a href="#l-uniq">uniq</a></td>
      <td><a href="#m-wc">wc</a></td>
   </tr>
</table>

### a. `awk`
O comando `awk` é o comando mais útil para manipular arquivos de texto. Ele opera em um arquivo inteiro, linha por linha. Por padrão, ele usa espaçoes em branco para separar os campos. A sintaxe mais comum para o comando `awk` é:

```bash
awk '/parametro_de_busca/ { operacao_a_se_realizar_se_o_parametro_for_confirmado; }' arquivo_para_analisar
```

Para fins de exemplo, vamos pegar o seguinte arquivo `/etc/passwd`. Aqui estão os dados de amostra que este arquivo contém:
```
root:x:0:0:root:/root:/usr/bin/zsh
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
```
Então, agora vamos usar um comando para extrair somente o nome de usuário a partir desse arquivo, em que `-F` especifica a base onde nós vamos separar os campos. No nosso caso, é `:`. O trecho `{ print $1 }` significa extrair o campo correspondente.
```bash
awk -F':' '{ print $1 }' /etc/passwd
```
Depois de rodar o comando acima, você vai obter o seguinte output:
```
root
daemon
bin
sys
sync
```
Para mais detalhes a respeito do uso de `awk`, acesse o [link](https://www.cyberciti.biz/faq/bash-scripting-using-awk).


### b. `cut`
O comando `cut` remove seções de cada linha de arquivos.

*exemplo.txt*
```bash
o garoto de gorro vermelho foi ao parque brincar
```

*exibir as colunas 2, 6, e 9 com espaço como separador*
```bash
cut -d " " -f2,6,9 exemplo.txt
```
```bash
garoto foi brincar
```

### c. `echo`
O comando `echo` exibe uma linha de texto.

*exibir "Olá, Mundo"*
```bash
echo Olá, Mundo
```
```bash
Olá, Mundo!
```

*exibir "Olá, Mundo" com novas linhas entre as palavras*
```bash
echo -ne "Olá,\nMundo\n"
```
```bash
Olá,
Mundo
```

### d. `grep`
O comando `grep` procura texto dentro dos arquivos. Pode-se usá-lo para buscar linhas de texto equivalentes a uma ou mais expressões regulares e extrair somente as linhas correspondentes.

```bash
grep parametro nome_do_arquivo
```
Exemplo:
```bash
$ grep admin /etc/passwd
_kadmin_admin:*:218:-2:Kerberos Admin Service:/var/empty:/usr/bin/false
_kadmin_changepw:*:219:-2:Kerberos Change Password Service:/var/empty:/usr/bin/false
_krb_kadmin:*:231:-2:Open Directory Kerberos Admin Service:/var/empty:/usr/bin/false
```
Pode-se forçar o `grep` a ignorar maiúsculas, usando a opção `-i`. 
Com `-r`, pode-se buscar todos os arquivos dentro de um diretório específico, por exemplo:
```bash
$ grep -r admin /etc/
```
E a opção `-w` pode ser usada para buscar somente palavras. Para mais detalhes a respeito do comando `grep`, acesse o [link](https://www.cyberciti.biz/faq/grep-in-bash).

### e. `egrep`
O comando `egrep` imprime na tela as linhas correspondentes a um parâmetro - Expressão Estendida (alias para: 'grep -E')

*exemplo.txt*
```bash
Lorem ipsum
dolor sit amet, 
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

*exiba as linhas que contenham "Lorem" ou "dolor".*
```bash
egrep '(Lorem|dolor)' exemplo.txt
```
ou
```bash
grep -E '(Lorem|dolor)' exemplo.txt
```
```bash
Lorem ipsum
dolor sit amet,
et dolore magna
duo dolores et ea
sanctus est Lorem
ipsum dolor sit
```

### f. `fgrep`
O comando `fgrep` imprime na tela as linhas que correspondam a um parâmetro, exibindo o parâmetro correspondente fixado (alias para: 'grep -F')

*exemplo.txt*
```bash
Lorem ipsum
dolor sit amet,
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
foo (Lorem|dolor) 
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

*Econtre a exata string '(Lorem|dolor)' em exemplo.txt*
```bash
fgrep '(Lorem|dolor)' exemplo.txt
```
ou
```bash
grep -F '(Lorem|dolor)' exemplo.txt
```
```bash
foo (Lorem|dolor) 
```

### g. `fmt`
O comando `fmt` é um ótimo formatador simples de texto.

*exemplo.txt (com uma única linha)*
```bash
Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.
```

*edite as linhas de exemplo.txt para o comprimento de 20 caracteres*
```bash
cat exemplo.txt | fmt -w 20
```
```bash
Lorem ipsum
dolor sit amet,
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

### h. `nl`
O comando `nl` enumera linhas de arquivos.

*exemplo.txt*
```bash
Lorem ipsum
dolor sit amet,
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

*mostre exemplo.txt com linhas numeradas*
```bash
nl -s". " exemplo.txt 
```
```bash
     1. Lorem ipsum
     2. dolor sit amet,
     3. consetetur
     4. sadipscing elitr,
     5. sed diam nonumy
     6. eirmod tempor
     7. invidunt ut labore
     8. et dolore magna
     9. aliquyam erat, sed
    10. diam voluptua. At
    11. vero eos et
    12. accusam et justo
    13. duo dolores et ea
    14. rebum. Stet clita
    15. kasd gubergren,
    16. no sea takimata
    17. sanctus est Lorem
    18. ipsum dolor sit
    19. amet.
```

### i. `sed`
O comando `sed` é um editor de fluxo que filtra e transforma o texto.

*exemplo.txt*
```bash
Olá isso é um teste 1 2 3 4
``` 

*substitua todos os espaçoes por hífens*
```bash
sed 's/ /-/g' exemplo.txt
```
```bash
Olá-isso-é-um-teste-1-2-3-4
```

*substitua todos os dígitos por "d"*
```bash
sed 's/[0-9]/d/g' exemplo.txt
```
```bash
Olá isso é um teste d d d d
```

### j. `sort`
O comando `sort` organiza as linhas de arquivos de texto.

*exemplo.txt*
```bash
f
b
c
g
a
e
d
```

*organize exemplo.txt*
```bash
sort exemplo.txt
```
```bash
a
b
c
d
e
f
g
```

*randomize um exemplo.txt organizado*
```bash
sort example.txt | sort -R
```
```bash
b
f
a
c
d
g
e
```

### k. `tr`
O comando `tr` substitui ou deleta caracteres.

*exemplo.txt*
```bash
Olá Mundo Foo Bar Baz!
```

*substitua todas as minúsculas por maiúsculas*
```bash
cat exemplo.txt | tr 'a-z' 'A-Z' 
```
```bash
OLÁ MUNDO FOO BAR BAZ!
```

*substitua todos os espaços por novas linhas*
```bash
cat exemplo.txt | tr ' ' '\n'
```
```bash
Olá
Mundo
Foo
Bar
Baz!
```

### l. `uniq`
O comando `uniq` sinaliza ou omite linhas repetidas.

*exemplo.txt*
```bash
a
a
b
a
b
c
d
c
```

*mostre somente uma linha de cada repetição de linhas em exemplo.txt (primeiro você precisa organizá-lo, caso contrário ele não encontrará as repetições)*
```bash
sort exemplo.txt | uniq
```
```bash
a
b
c
d
```

*usando a opção `-c` ou `--count`, mostre somente uma linha de cada repetição de linhas e diga quantas ocorrências delas foram encontradas*
```bash
sort exemplo.txt | uniq -c
```
```bash
    3 a
    2 b
    2 c
    1 d
```

outras opções para o comando `uniq` são:
- `-d` ou `--repeated`: Exibe somente linhas que são repetidas;
- `-i` ou `--ignore-case`: Ignora maiúsculas ao comparar as linhas;
- `-u` ou `--unique`: Exibe somente as linhas sem repetição;

### m. `wc`
O comando `wc` conta a quantidade de linhas, palavras e caracteres existente em um arquivo.  
```bash
wc nome_do_arquivo
```
Exemplo:
```bash
$ wc exemplo.txt
7459   15915  398400 exemplo.txt
```
Onde `7459` é o total de linhas, `15915` é o total de palavras e `398400` é o total de caracteres.

Pode-se ainda filtrar a saída por opções:
- `-c` ou `--bytes`: imprime na tela o número de bytes;
- `-m` ou `--chars`: imprime na tela o número de caracteres;
- `-l` ou `--lines`: imprime na tela o número de linhas;
- `-w` ou `--words`: imprime na tela o número de palavras;

## 1.3. Operações com Diretório

<table>
   <tr>
      <td><a href="#a-cd">cd</a></td>
      <td><a href="#b-mkdir">mkdir</a></td>
      <td><a href="#c-pwd">pwd</a></td>
   </tr>
</table>

### a. `cd`
O comando `cd` muda de um diretório para outro.  
```bash
$ cd
```
move para o diretório HOME. 
Esse comando aceita um nome opcional, o qual pode ser o caminho para esse diretório, mudando você para ele.
```bash
cd nome_do_diretorio
```
Mude para o diretório anterior:
```bash
cd -
```
Mude para o diretório acima:
```bash
cd ..
```

### b. `mkdir`
O comando `mkdir` cria um novo diretório.  
```bash
mkdir nome_do_diretorio
```
Pode-se usá-lo para criar múltiplos diretórios de uma só vez dentro do diretório corrente.
```bash
mkdir nome_do_diretorio1 nome_do_diretorio2 nome_do_diretorio3
```
Também pode-se usá-lo para criar uma árvore de diretórios — com diretórios "pais" como subdiretórios — ao mesmo tempo, com a opção `-p` ou `--parents`. Por exemplo, caso você queira criar um diretório chamado "projeto1" dentro de um novo subdiretório em "/exemplos/bash/projetos/", você poderia rodar:
```bash 
mkdir -p /exemplos/bash/projetos/projeto1
```
ou
```bash 
mkdir --parents /exemplos/bash/projetos/projeto1
```
Caso qualquer um dos diretórios nessa árvore de diretórios não exista, ele será criado também.

### c. `pwd`
Imprime na tela em qual diretório você está no momento.  
```bash
pwd
```

## 1.4. SSH, Informações do Sistema & Operações de Rede

<table>
   <tr>
      <td><a href="#a-bg">bg</a></td>
      <td><a href="#b-cal">cal</a></td>
      <td><a href="#c-date">date</a></td>
      <td><a href="#d-df">df</a></td>
      <td><a href="#e-dig">dig</a></td>
      <td><a href="#f-du">du</a></td>
      <td><a href="#g-fg">fg</a></td>
      <td><a href="#h-finger">finger</a></td>   
      <td><a href="#i-jobs">jobs</a></td>
      <td><a href="#j-last">last</a></td>
   </tr>
   <tr>
      <td><a href="#k-man">man</a></td>
      <td><a href="#l-passwd">passwd</a></td>
      <td><a href="#m-ping">ping</a></td>
      <td><a href="#n-ps">ps</a></td>
      <td><a href="#o-quota">quota</a></td>
      <td><a href="#p-scp">scp</a></td>
      <td><a href="#q-ssh">ssh</a></td>
      <td><a href="#r-top">top</a></td>
      <td><a href="#s-uname">uname</a></td>
      <td><a href="#t-uptime">uptime</a></td>
   </tr>
   <tr>
      <td><a href="#u-w">w</a></td>
      <td><a href="#v-wget">wget</a></td>
      <td><a href="#w-whoami">whoami</a></td>
      <td><a href="#x-whois">whois</a></td>
      <td><a href="#y-rsync">sync</a></td>
      <td><a href="#z-curl">curl</a></td>
   </tr>
</table>

### a. `bg`
O comando `bg` lista trabalhos parados ou em backdround; reinicia um trabalho parado no background.

### b. `cal`
O comando `cal` mostra o calendário do mês.

### c. `date`
O comando `date` mostra o dia e a hora correntes.

### d. `df`
O comando `df` mostra o uso do disco.

### e. `dig`
O comando `dig` obtém a informação DNS para um domínio.  
```bash
dig dominio.com
```

### f. `du`
O comando `du` mostra o usdo de disco por um arquivo ou diretório. Para mais informações a respeito do comando `du`, acesse o [link](http://www.linfo.org/du.html)
```bash
du opcao arquivo|diretorio
```
Algumas opções:
- `-h` (leitura humanizada) mostra as informações em kilobytes (K), megabytes (M) ou gigabytes (G).
- `-s` (supresso ou sumarizado) mostra o uso total de disco por um diretório e suprime informações de subdiretórios.
Exemplo:
```bash
du -sh imagens
1.4M imagens
```

### g. `fg`
O comando `fg` exibe o trabalho mais recente no foreground.

### h. `finger`
O comando `finger` mostra informações sobre o usuário 
```bash
finger usuario
```
### i. `jobs`
O comando `jobs` lista os trabalhos que estão rodando no background e indica o número (ID) do trabalho.

### j. `last`
O comando `last` lista os últimos logins de um usuário específico.  
```bash
last nomeDeUsuario
```

### k. `man`
O comando `man` exibe o manual de um determinado comando.  
```bash
man comando
```

### l. `passwd`
O comando `passwd` permite mudar a senha do usuário logado.

### m. `ping`
O comando `ping` realiza o ping para o endereço indicado e mostra os resultados.  
```bash
ping host
```

### n. `ps`
O comando `ps` lista os processos em atividade. 
Com a opção `-u`, pode-se filtrar por usuário, ao indicá-lo:
```bash
ps -u nomeDeUsuario
```
Use as flags `-ef`: `e` para todos os processos e `f` para lista completa. 
```bash
ps -ef
```

### o. `quota`
O comando `quota` mostra qual a sua cota de uso de disco.  
```bash
quota -v
```

### p. `scp`
O comando `scp` permite a transferência de arquivos entre um host local e um host remoto; ou entre dois hosts remotos.

*copiar de um host local para um host remoto*
```bash
scp arquivo_original usuario@host:diretorio/arquivo_alvo
```
*copiar de um host remoto para um host local*
```bash
scp usuario@host:diretorio/arquivo_original arquivo_alvo
```
*para diretórios, como o `-cp`*
```bash
scp -r usuario@host:diretorio/diretorio_original diretorio_alvo
```
Esse comando também aceita uma opção `-P` que pode ser usada para conectar a uma porta específica.  
```bash
scp -P porta usuario@host:diretorio/arquivo_original arquivo_alvo
```

### q. `ssh`
O `ssh` (SSH client) é um programa para conectar-se e executar comandos em uma máquina remota. 
```bash
ssh usuario@host
```
Esse comando também aceita uma opção `-p` que pode ser usada para conectar a uma porta específica.   
```bash
ssh -p porta usuario@host
```

### r. `top`
O comando `top` exibe os processos ativos no sistema.

### s. `uname`
O comando `uname` exibe as informações do kernel.  
```bash
uname -a
```

### t. `uptime`
O comando `uptime` exibe o tempo corrente de atividade.

### u. `w`
O comando `w` exibe quem está logado.
Com a sintaxe `w opcoes usuario`, pode-se:
- `-h` ou `--no-header`: suprimir a informação do cabeçalho, mostrando apenas os detalhes do usuário;
- `-s` ou `--short`: exibir uma saída de formato curto, omitindo o tempo de login, as colunas JCPU e PCPU;
- `-u` ou `--no-current`: ignorar o processo atual, ver o tempo ocioso e o que o usuário está fazendo;
- `-i` ou `--ip-addr`: forçar a exibição de endereços IP, em vez de nomes de host, no campo FROM;
- `-o` ou `--old-style`: usar o formato de saída antigo, imprimindo na tela espaços em branco para tempos ociosos inferiores a um minuto.

### v. `wget`
O comando `wget` baixa um arquivo.  
```bash
wget arquivo
```

### w. `whoami`
O comando `whoami` retorna o usuário atualmente logado.

### x. `whois`
O comando `whois` obtém a informação whois para um domínio.  
```bash
whois dominio
```

### y. `rsync`
O comando `rsync` faz o mesmo trabalho do comando `scp`, mas transfere somente arquivos modificados. Muito útil quando se transfere o mesmo diretório para ou de um sevidor várias vezes.
```bash
rsync diretorio_original usuario@host:diretorio_alvo
rsync usuario@host:diretorio_original diretorio_alvo
```

### z. `curl`
Curl é uma ferramenta em linha de comando para requisitar ou enviar dados usando sintaxe URL. Muito útil para sistemas em que você tem somente um terminal disponível para fazer várias requisições.
```bash
curl url
```
Algumas opções são:
- `-X` ou `--request` para especificar qual método você gostaria de invocar (GET, POST, DELETE, ...);
- `-d <dados>` ou `--data <dados>` para dados de POST request em um determinado URL.

## 1.5. Operações de Monitoramento de Processos

<table>
   <tr>
      <td><a href="#a-kill">kill</a></td>
      <td><a href="#b-killall">killall</a></td>
      <td><a href="#c-&">&amp;</a></td>
      <td><a href="#d-nohup">nohup</a></td>
   </tr>
</table>

### a. `kill`
O comando `kill` encerra o processo usando o PID (Process IDentifier) que você informa.  
```bash
kill PID
```

### b. `killall`
O comando `killall` encerra todos os processos com o nome.  
```bash
killall nomeDoProcesso
```

### c. &
O símbolo `&` instrui o comando a rodar como um processo em background num subshell.
```bash
comando &
```

### d. `nohup`
`nohup` significa "No Hang Up". Ele permite executar comandos, processos ou scripts que podem continuar sendo executados em segundo plano após você sair de um shell. 
```bash
nohup comando
```
Combine-o com `&` para criar processos em background.
```bash
nohup comando &
```

# 2. Programação Básica com Shell


The first line that you will write in bash script files is called `shebang`. This line in any script determines the script's ability to be executed like a standalone executable without typing sh, bash, python, php etc beforehand in the terminal.

```bash
#!/usr/bin/env bash
```

## 2.1. Variáveis

Creating variables in bash is similar to other languages. There are no data types. A variable in bash can contain a number, a character, a string of characters, etc. You have no need to declare a variable, just assigning a value to its reference will create it.

Example:
```bash
str="hello world"
```

The above line creates a variable `str` and assigns "hello world" to it. The value of variable is retrieved by putting the `$` in the beginning of variable name.

Example:
```bash
echo $str   # hello world
```
## 2.2. Array
Like other languages bash has also arrays. An array is a variable containing multiple values. There's no maximum limit on the size of array. Arrays in bash are zero based. The first element is indexed with element 0. There are several ways for creating arrays in bash which are given below.

Examples:
```bash
array[0]=val
array[1]=val
array[2]=val
array=([2]=val [0]=val [1]=val)
array=(val val val)
```
To display a value at specific index use following syntax:

```bash
${array[i]}     # where i is the index
```

If no index is supplied, array element 0 is assumed. To find out how many values there are in the array use the following syntax:

```bash
${#array[@]}
```

Bash has also support for the ternary conditions. Check some examples below.

```bash
${varname:-word}    # if varname exists and isn't null, return its value; otherwise return word
${varname:=word}    # if varname exists and isn't null, return its value; otherwise set it word and then return its value
${varname:+word}    # if varname exists and isn't null, return word; otherwise return null
${varname:offset:length}    # performs substring expansion. It returns the substring of $varname starting at offset and up to length characters
```

## 2.3 Substituição de String

Check some of the syntax on how to manipulate strings

```bash
${variable#pattern}         # if the pattern matches the beginning of the variable's value, delete the shortest part that matches and return the rest
${variable##pattern}        # if the pattern matches the beginning of the variable's value, delete the longest part that matches and return the rest
${variable%pattern}         # if the pattern matches the end of the variable's value, delete the shortest part that matches and return the rest
${variable%%pattern}        # if the pattern matches the end of the variable's value, delete the longest part that matches and return the rest
${variable/pattern/string}  # the longest match to pattern in variable is replaced by string. Only the first match is replaced
${variable//pattern/string} # the longest match to pattern in variable is replaced by string. All matches are replaced
${#varname}     # returns the length of the value of the variable as a character string
```

## 2.4. Outros Truques com Strings
Bash has multiple shorthand tricks for doing various things to strings.

```bash
${variable,,}    #this converts every letter in the variable to lowercase
${variable^^}    #this converts every letter in the variable to uppercase

${variable:2:8}  #this returns a substring of a string, starting at the character at the 2 index(strings start at index 0, so this is the 3rd character),
                 #the substring will be 8 characters long, so this would return a string made of the 3rd to the 11th characters.
```

Here are some handy pattern matching tricks
```bash
if [[ "$variable" == *subString* ]]  #this returns true if the provided substring is in the variable
if [[ "$variable" != *subString* ]]  #this returns true if the provided substring is not in the variable
if [[ "$variable" == subString* ]]   #this returns true if the variable starts with the given subString
if [[ "$variable" == *subString ]]   #this returns true if the variable ends with the given subString
```


The above can be shortened using a case statement and the IN keyword
```bash
case "$var" in
	begin*)
		#variable begins with "begin"
	;;
	*subString*)
		#subString is in variable
	;;

	*otherSubString*)
		#otherSubString is in variable
	;;
esac
```

## 2.5. Funções
As in almost any programming language, you can use functions to group pieces of code in a more logical way or practice the divine art of recursion. Declaring a function is just a matter of writing function my_func { my_code }. Calling a function is just like calling another program, you just write its name.

```bash
function name() {
    shell commands
}
```

Example:
```bash
#!/bin/bash
function hello {
   echo world!
}
hello

function say {
    echo $1
}
say "hello world!"
```

When you run the above example the `hello` function will output "world!". The above two functions `hello` and `say` are identical. The main difference is function `say`. This function, prints the first argument it receives. Arguments, within functions, are treated in the same manner as arguments given to the script.

## 2.6. Condicionais

The conditional statement in bash is similar to other programming languages. Conditions have many form like the most basic form is `if` expression `then` statement where statement is only executed if expression is true.

```bash
if [ expression ]; then
    will execute only if expression is true
else
    will execute if expression is false
fi
```

Sometime if conditions becoming confusing so you can write the same condition using the `case statements`.

```bash
case expression in
    pattern1 )
        statements ;;
    pattern2 )
        statements ;;
    ...
esac
```

Expression Examples:

```bash
statement1 && statement2  # both statements are true
statement1 || statement2  # at least one of the statements is true

str1=str2       # str1 matches str2
str1!=str2      # str1 does not match str2
str1<str2       # str1 is less than str2
str1>str2       # str1 is greater than str2
-n str1         # str1 is not null (has length greater than 0)
-z str1         # str1 is null (has length 0)

-a file         # file exists
-d file         # file exists and is a directory
-e file         # file exists; same -a
-f file         # file exists and is a regular file (i.e., not a directory or other special type of file)
-r file         # you have read permission
-s file         # file exists and is not empty
-w file         # you have write permission
-x file         # you have execute permission on file, or directory search permission if it is a directory
-N file         # file was modified since it was last read
-O file         # you own file
-G file         # file's group ID matches yours (or one of yours, if you are in multiple groups)

file1 -nt file2     # file1 is newer than file2
file1 -ot file2     # file1 is older than file2

-lt     # less than
-le     # less than or equal
-eq     # equal
-ge     # greater than or equal
-gt     # greater than
-ne     # not equal
```

## 2.7. Loops

There are three types of loops in bash. `for`, `while` and `until`.

Different `for` Syntax:
```bash
for name [in list]
do
  statements that can use $name
done

for (( initialisation ; ending condition ; update ))
do
  statements...
done
```

`while` Syntax:
```bash
while condition; do
  statements
done
```

`until` Syntax:
```bash
until condition; do
  statements
done
```

# 2.8. Regex

They are a powerful tool for manipulating and searching text. Here are some examples of regular expressions that use each `metacharacter`:

<table>
   <tr>
      <td><a href="#a-dot">`.`(dot)</a></td>
      <td><a href="#b-asterisk">`*`(asterisk)</a></td>
      <td><a href="#c-plus">`+`(plus)</a></td>
      <td><a href="#d-question_mark">`?`(question mark)</a></td>
      <td><a href="#c-plus">`|`(pipe)</a></td>
      <td><a href="#c-plus">`[]`(character class)</a></td>
      <td><a href="#c-plus">`[^]`(negated character class)</a></td>
      <td><a href="#c-plus">`()`(grouping)</a></td>
      <td><a href="#c-plus">`{}`(quantifiers)</a></td>
      <td><a href="#c-plus">`\`(escape)</a></td>
   </tr>
</table>

### a. `.` (dot)
Matches any single character except newline.  
```bash
grep h.t file.txt
```
Output:
```bash
hat
hot
hit
```

### b. `*` (asterisk)
Matches zero or more occurrences of the preceding character or group.
```bash
grep ab*c file.txt
```
Output:
```bash
ac
abc
abbc
abbbc
```

### c. `+` (plus)
Matches one or more occurrences of the preceding character or group.
```bash
grep ab+c file.txt
```
Output:
```bash
abc
abbc
abbbc
abbbbc
```

### d. `?` (question mark)
Matches zero or one occurrence of the preceding character or group.
```bash
grep ab?c file.txt
```
Output:
```bash
ac
abc
```

### e. `|` (pipe)
Matches either the pattern to the left or the pattern to the right.
```bash
egrep "cat|dog" file.txt
```
Output:
```bash
cat
dog
```

### f. `[]` (character class)
Matches any character inside the brackets.
```bash
[aeiou] will match any vowel
[a-z] will match any lowercase letter
```

### g. `[]` (negated character class)
Matches any character not inside the brackets.
```bash
[^aeiou] will match any consonant
[^a-z] will match any non-lowercase letter
```

### h. `()` (grouping)
Groups multiple tokens together and creates a capture group.
```bash
egrep "(ab)+" file.txt
```

Output:
```bash
ab
abab
ababab
```

### i. `{}` (quantifiers)
Matches a specific number of occurrences of the preceding character or group.
```bash
egrep "a{3}" file.txt
```

Output:
```bash
aaa
aaaa
aaaaa
```

### j. `\` (escape)
Escapes the next character to match it literally.
```bash
egrep "a\+" file.txt
```

Output:
```bash
a+
```
=======
## 2.9. Pipes

Multiple commands can be linked together with a pipe, `|`. A `|` will send the standard-output from command A to the standard-input of command B.
Pipes can also be constructed with the `|&` symbols. This will send the standard-output **and** standard-error from command A to the standard-input of command B.

# 3. Truques

## Set an alias

Run `nano ~/.bash_profile` and add the following line:

```bash
alias dockerlogin='ssh www-data@adnan.local -p2222'  # add your alias in .bash_profile
```

## To quickly go to a specific directory

Run `nano ~/.bashrc` and add the following line:

```bash
export hotellogs="/workspace/hotel-api/storage/logs"
```

Now you can use the saved path:

```bash
source ~/.bashrc
cd $hotellogs
```

## Re-execute the previous command

This goes back to the days before you could rely on keyboards to have an "up" arrow key, but can still be useful. 
To run the last command in your history
```bash
!!
```
A common error is to forget to use `sudo` to prefix a command requiring privileged execution. Instead of typing the whole command again, you can:
```bash
sudo !!
```
This would change a `mkdir somedir` into `sudo mkdir somedir`.

## Exit traps

Make your bash scripts more robust by reliably performing cleanup.

```bash
function finish {
  # your cleanup here. e.g. kill any forked processes
  jobs -p | xargs kill
}
trap finish EXIT
```

## Saving your environment variables

When you do `export FOO = BAR`, your variable is only exported in this current shell and all its children, to persist in the future you can simply append in your `~/.bash_profile` file the command to export your variable
```bash
echo export FOO=BAR >> ~/.bash_profile
```

## Accessing your scripts

You can easily access your scripts by creating a bin folder in your home with `mkdir ~/bin`, now all the scripts you put in this folder you can access in any directory.

If you can not access, try append the code below in your `~/.bash_profile` file and after do `source ~/.bash_profile`.
```bash
# set PATH so it includes user's private bin if it exists
if [ -d "$HOME/bin" ] ; then
    PATH="$HOME/bin:$PATH"
fi
```

# 4. Depuração
You can easily debug the bash script by passing different options to `bash` command. For example `-n` will not run commands and check for syntax errors only. `-v` echo commands before running them. `-x` echo commands after command-line processing.

```bash
bash -n scriptname
bash -v scriptname
bash -x scriptname
```

# 5. Multi-threading
You can easily multi-threading your jobs using `&`. All those jobs will then run in the background simultaneously and you can see the processes below are running using `jobs`.

```bash
sleep 15 & sleep 5 &
```

The optional `wait` command will then wait for all the jobs to finish.

```bash
sleep 10 & sleep 5 &
wait
```

## Contribuições

- Relate problemas [How to](https://help.github.com/articles/creating-an-issue/)
- Abra um pull request com aprimoramentos [How to](https://help.github.com/articles/about-pull-requests/)
- Compartilhe!

## Guia Original
- [Inglês | English](https://github.com/Idnan/bash-guide)

## Outras Traduções
- [Chinês | 简体中文](https://github.com/vuuihc/bash-guide)
- [Espanhol | Español](https://github.com/mariotristan/bash-guide)
- [Japonês | 日本語](https://github.com/itooww/bash-guide)
- [Russo | Русский](https://github.com/navinweb/bash-guide)
- [Turco | Türkçe](https://github.com/omergulen/bash-guide) 
- [Vietnamita | Tiếng Việt](https://github.com/nguyenvanhieuvn/hoc-bash)
