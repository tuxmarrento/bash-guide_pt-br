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
    2.3. [Manipulação de String](#23-manipulação-de-string)  
    2.4. [Outros Truques com Strings](#24-outros-truques-com-strings)  
    2.5. [Funções](#25-funções)  
    2.6. [Condicionais](#26-condicionais)  
    2.7. [Loops](#27-loops)  
    2.8. [Regex](#28-regex)  
    2.9. [Pipes](#29-pipes)  
  3. [Truques](#3-truques)  
  4. [Depuração](#4-depuração)

# 1. Operações Básicas

### a. `export`
O comando `export` mostra todas as variáveis de ambiente. Caso você queira obter detalhes de uma variável específica, use `echo $NOME_DA_VARIAVEL`.  
```bash
export
```
Exemplo:
```bash
$ export
AWS_HOME=/Users/tuxmarrento/.aws
LANG=en_US.UTF-8
LC_CTYPE=en_US.UTF-8
LESS=-R

$ echo $AWS_HOME
/Users/tuxmarrento/.aws
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
Depois de executar o comando acima, você vai obter a seguinte saída:
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
Também pode-se usá-lo para criar uma árvore de diretórios — com diretórios "pais" como subdiretórios — ao mesmo tempo, com a opção `-p` ou `--parents`. Por exemplo, caso você queira criar um diretório chamado "projeto1" dentro de um novo subdiretório em "/exemplos/bash/projetos/", você poderia executar:
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
O comando `bg` lista trabalhos parados ou em backdround; reinicia um trabalho parado em segundo plano (background).

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
O comando `du` mostra o uso de disco por um arquivo ou diretório. Para mais informações a respeito do comando `du`, acesse o [link](http://www.linfo.org/du.html)
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
O comando `fg` exibe o trabalho mais recente em primeiro plano (foreground).

### h. `finger`
O comando `finger` mostra informações sobre o usuário 
```bash
finger usuario
```
### i. `jobs`
O comando `jobs` lista os trabalhos que estão executando no segundo plano e indica o número (ID) do trabalho.

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
      <td><a href="#c-&">&;</a></td>
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

### c. `&`
O símbolo `&` instrui o comando a executar como um processo em segundo plano num subshell.
```bash
comando &
```

### d. `nohup`
`nohup` significa "No Hang Up". Ele permite executar comandos, processos ou scripts que podem continuar sendo executados em segundo plano após você sair de um shell. 
```bash
nohup comando
```
Combine-o com `&` para criar processos em segundo plano.
```bash
nohup comando &
```


# 2. Programação Básica com Shell


A primeira linha que você vai escrever em um arquivo com script bash se chama `shebang`. Em qualquer script, essa linha determina qual interpretador será utilizado para rodar o executável sem precisar digitar sh, bash, python, php etc. previamente no terminal.

```bash
#!/usr/bin/env bash
```
Este modelo acima utiliza `env` com a finalidade de localizar o interpretador Bash através da variável de ambiente `$PATH`, sem precisar especificar o caminho exato. Ao especificar o caminho em absoluto — com `#!/usr/bin/bash` — reduz-se a portabilidade do script, enquanto usar `env` previne erros que podem decorrer de alguma alteração de localização ou de nome do executável Bash.

## 2.1. Variáveis

Criar variáveis com Bash é similar a outras linguagens. Não existem tipos de dados. Uma variável em Bash pode conter um número, um caracter, uma string de caracteres etc.. Não é necessário declarar uma variável, bastando assinalar um valor para que a sua referência seja criada.

Exemplo:
```bash
str="Olá, Mundo"
```
A linha acima cria uma variável `str` e assinala "Olá, Mundo" como valor para ela. O valor da variável é referenciado colocando um `$`no início do nome da variável.
Exemplo:
```bash
echo $str
```
Saída:
```bash
Olá, Mundo
```

## 2.2. Array

Assim como outras linguagens, o Bash também possui arrays. Um array é uma variável que contém múltiplos valores. Não existe um limite máximo para o tamanho do array. Em Bash, o primeiro elemento de um array é indexado como elemento 0. Existem muitas formas para criar arrays em Bash, conforme a seguir.

Exemplos:
```bash
array[0]=val
array[1]=val
array[2]=val
array=([2]=val [0]=val [1]=val)
array=(val val val)
```

Para exibir um valor de um índice específico, use a seguinte sintaxe:
```bash
${array[i]}     # em que i é o índice
```

Se nenhum índice for fornecido, o elmento 0 do array é assumido. Para saber quantos valores exisetem no array, use a seguinte sintaxe:
```bash
${#array[@]}
```

O Bash também oferece suporte a condições ternárias. Veja alguns exemplos:
```bash
${varname:-word} 		# se o varname existe e não for nulo, retorna o seu valor; caso contrário, retorna word.
${varname:=word} 		# se o varname existe e não for nulo, retorna o seu valor; caso contrário, define-o como word e retorna o seu valor.
${varname:+word} 		# se o varname existe e não for nulo, retorna o seu valor; caso contrário, returna null.
${varname:offset:length} 	# realiza a expansão de substring. Retorna a substring de $varname, começando no ponto de expansão e indo até o final dos caracteres.
```

## 2.3 Manipulação de String

Veja algumas das formas de sintaxe para manipular strings:
```bash
${variavel#parametro} 		# se o parâmetro corresponder ao início do valor da variável, exclui a parte mais curta que corresponde e retorna o restante.
${variavel##parametro} 		# se o parâmetro corresponder ao início do valor da variável, exclui a parte mais longa que corresponde e retorna o restante.
${variavel%parametro} 		# se o parâmetro corresponder ao final do valor da variável, exclui a parte mais curta que corresponde e retorna o restante.
${variavel%%parametro} 		# se o parâmetro corresponder ao final do valor da variável, exclui a parte mais longa que corresponde e retorna o restante.
${variavel/parametro/string} 	# a correspondência com o parâmetro mais longa na variável é substituída pela string. Apenas a primeira correspondência é substituída.
${variavel//parametro/string} 	# a correspondência com o parâmetro mais longa na variável é substituída pela string. Todas as correspondências são substituídas.
${#varname} 			# retorna o comprimento do valor da variável como uma sequência de caracteres.
```

## 2.4. Outros Truques com Strings

O Bash oferece vários truques de atalho para fazer diversas coisas com strings.

```bash
${variavel,,} 		# isso converte todas as letras da variável em minúsculas.
${variavel^^} 		# isso converte todas as letras da variável em maiúsculas.

${variavel:2:8} 	# isso retorna uma substring de uma string, começando no caractere de índice 2 (strings começam no índice 0, como explicitado acima, então esse é o terceiro caractere); a substring terá 8 caracteres, então isso retornaria uma string composta do 3º ao 11º caractere.
```

Aqui estão alguns truques úteis para combinar parâmetros:

```bash
if [[ "$variavel" == *subString* ]]  	# isso retorna true se a subString fornecida estiver na variável.
if [[ "$variavel" != *subString* ]]  	# isso retorna true se a subString fornecida não estiver na variável.
if [[ "$variavel" == subString* ]]   	# isso retorna true se a variável começa com a subString fornecida.
if [[ "$variavel" == *subString ]]   	# isso retorna true se a variável termina com a subString fornecida.
```
O truque acima pode ser encurtado usando uma instrução case e a palavra-chave INT:
```bash
case "$var" in
	inicio*)
		# a variável começa com "inicio"
	;;
	*subString*)
		# a subString está na variável
	;;

	*outraSubString*)
		# uma outraSubString está na variável
	;;
esac
```

## 2.5. Funções

Como em quase toda linguagem de programação, você pode usar funções para agrupar trechos de código de forma mais lógica ou praticar a divina arte da recursão. Declarar uma função é apenas uma questão de escrever `function minha_func { meu_codigo }`. Chamar uma função é como chamar outro programa: basta escrever o nome dela.

```bash
function nome() {
    comandos shell
}
```

Exemplo:
```bash
#!/bin/bash
function ola {
   echo mundo!
}
ola

function diga {
    echo $1
}
diga "ola mundo!"
```
Ao executar o exemplo acima, a função `ola` retornará "mundo!". As duas funções `ola` e `diga` acima são estruturalmente idênticas. A principal diferença é que a função `diga` imprime o primeiro argumento recebido. Argumentos, dentro de funções, são tratados da mesma maneira que argumentos fornecidos ao script.

## 2.6. Condicionais

A instrução condicional em Bash é similar a outras linguagens de programação. As condições têm muitas formas, como a mais básica: a expressão `if` seguida da instrução `then`, em que a instrução só é executada se a expressão for verdadeira.
```bash
if [ expressao ]; then
    será executado somente se a expressao for true
else
     será executado se a expressao for false
fi
```

Às vezes, as condições se tornam confusas, então você pode escrever a mesma condição usando as instruções `case`.
```bash
case expressao in
    parametro1 )
        instrucoes ;;
    parametro2 )
        instrucoes ;;
    ...
esac
```

Exemplos de expressão:
```bash
instrucao1 && instrucao2 	# ambas instruções são true
instrucao1 || instrucao2 	# ao menos uma instrução é true

str1=str2       # str1 corresponde à str2
str1!=str2      # str1 não corresponde à str2
str1<str2       # str1 é menor que str2
str1>str2       # str1 é maior que str2
-n str1         # str1 é não nula (tem um comprimento maior que 0)
-z str1         # str1 é nula (tem comprimento 0)

-a arquivo         # o arquivo existe
-d arquivo         # o arquivo existe e é um diretório
-e arquivo         # o arquivo existe; o mesmo que -a
-f arquivo         # o arquivo existe e é regulare (i.e., não é um diretório ou outro tipo especial de arquivo)
-r arquivo         # você tem permissão de leitura
-s arquivo         # o arquivo existe e não está vazio
-w arquivo         # você tem permissão de escrita
-x arquivo         # você tem permição de execução do arquivo, ou permissão de busca pelo diretório, caso seja um
-N arquivo         # o arquivo foi modificado desde a última leitura
-O arquivo         # seu próprio arquivo
-G arquivo         # o ID de grupo do arquivo corresponde ao seu

arquivo1 -nt arquivo2     # arquivo1 é mais novo do que o arquivo2
arquivo1 -ot arquivo2     # arquivo1 é mais velho do que o arquivo2

-lt     # menor que
-le     # menor que ou igual a
-eq     # igual a
-ge     # maior que ou igual a
-gt     # maior que
-ne     # não igual a
```

## 2.7. Loops

Existem três tipos de Loop em Bash. `for`, `while` e `until`.

Sintaxe `for`:
```bash
for nome in [lista]
do
  instrucoes que podem usar $nome
done
```
ou ainda:
```bash
for (( inicializacao ; condicao final ; atualizacao ))
do
  instrucoes
done
```

Sintaxe de `while`:
```bash
while condicao; do
  instrucoes
done
```

Sintaxe de `until`:
```bash
until condicao; do
  instrucoes
done
```

# 2.8. Regex

Existe uma ferramenta poderosa para manipular e buscar texto. Aqui estão alguns exemplos de expressões regulares que usam cada `metacharacter`:

<table>
   <tr>
      <td><a href="#a--ponto">`.` ponto</a></td>
      <td><a href="#b--asterisco">`*` asterisco</a></td>
      <td><a href="#c--plus">`+` plus</a></td>
      <td><a href="#d--interrogação">`?` interrogação</a></td>
      <td><a href="#c--plus">`|` pipe</a></td>
      <td><a href="#c--plus">`[]` classe caracter</a></td>
      <td><a href="#c--plus">`[^]` classe caracter recusado</a></td>
      <td><a href="#c--plus">`()` agrupamento</a></td>
      <td><a href="#c--plus">`{}` quantificador</a></td>
      <td><a href="#c--plus">`\` escape</a></td>
   </tr>
</table>

### a. `.` ponto
Corresponde a qualquer caracter, exceto uma nova linha. 
```bash
grep h.t arquivo.txt
```
Saída:
```bash
hat
hot
hit
```

### b. `*` asterisco
Corresponde a zero ou mais ocorrências do caracter ou grupo precedente.
```bash
grep ab*c arquivo.txt
```
Saída:
```bash
ac
abc
abbc
abbbc
```

### c. `+` plus
Corresponde a uma ou mais ocorrências do caracter ou grupo precedente.
```bash
grep ab+c arquivo.txt
```
Saída:
```bash
abc
abbc
abbbc
abbbbc
```

### d. `?` interrogação
Corresponde a zero ou uma ocorrência do caracter ou grupo precedente.
```bash
grep ab?c arquivo.txt
```
Saída:
```bash
ac
abc
```

### e. `|` pipe
Corresponde ao parâmetro à esquerda ou ao parâmetro à direita.
```bash
egrep "gato|cachorro" arquivo.txt
```
Saída:
```bash
gato
cachorro
```

### f. `[]` classe caracter
Corresponde a quaisquer caracteres que estão entre os colchetes.
```bash
[aeiou] 	# vai corresponder a qualquer vogal
[a-z] 		# vai corresponder a qualquer letra minúscula
```

### g. `[^]` classe caracter recusado
Corresponde a quaisquer caracteres que não estão entre os colchetes.
```bash
[^aeiou] 	# vai corresponder a qualquer consoante
[^a-z] 		# vai corresponder a qualquer caracter que não seja letra minúscula
```

### h. `()` agrupamento
Agrupa vários tokens juntos e cria um grupo de captura.
```bash
egrep "(ab)+" arquivo.txt
```

Saída:
```bash
ab
abab
ababab
```

### i. `{}` quantificador
Corresponde a um número específico de ocorrências de um caracter ou grupo precedente.
```bash
egrep "a{3}" arquivo.txt
```

Saída:
```bash
aaa
aaaa
aaaaa
```

### j. `\` escape
Remove o significado especial no Bash do próximo caractere para preservar seu valor literal, exceto para o caracter `n`, com o qual cria uma nova linha na combinação `\n`. 
```bash
egrep "a\+" arquivo.txt
```

Saída:
```bash
a+
```

Mais detalhes a respeito do escape podem ser encontrados no [link](https://ss64.com/bash/syntax-quoting.html)

## 2.9. Pipes

Vários comandos podem ser vinculados um ao outro através de um pipe, `|`. Um `|` enviará a saída padrão (standard-output) do comando A para a entrada padrão (standard-input) do comando B.

Os pipes também podem ser usados com os símbolos `|&`. Essa combinação enviará o standard-output **e** o erro padrão (standard-error) do comando A para o standard-input do comando B.


# 3. Truques


## Configurar um Alias
Execute `nano ~/.bash_profile` e adicione a seguinte linha:
```bash
alias dockerlogin='ssh www-data@tuxmarrento.local -p2222'  # adiciona seu alias ao arquivo .bash_profile
```

## Ir rapidamente para um diretório específico
Execute `nano ~/.bashrc` e adicione a seguinte linha:
```bash
export hotellogs="/workspace/hotel-api/storage/logs"
```

Agora você pode executar `source ~/.bash_profile` e usar o caminho salvo chamando-o como uma variável:
```bash
source ~/.bashrc
cd $hotellogs
```

## Execute novamente o comando anterior
Isso remonta ao tempo em que ainda não se podia confiar na tecla de seta para cima, mas ainda pode ser útil para executar o último comando do seu histórico.
```bash
!!
```

Um erro comum é esquecer de usar `sudo` como prefixo de um comando que requer execução privilegiada. Em vez de digitar o comando inteiro novamente, você pode:
```bash
sudo !!
```
Isso corrigiria um `mkdir qualquerdir` com `sudo mkdir qualquerdir`.

## Saia de armadilhas

Torne seus scripts bash mais robustos realizando limpezas de forma confiável.

```bash
function final {
  # sua limpeza aqui; por exemplo, encerrar qualquer fork de processo
  jobs -p | xargs kill
}
trap final EXIT
```

## Salvando as suas variáveis de ambiente

Quando você faz `export FOO=BAR`, a sua variável é exportada apenas no shell atual e todos os seus filhos. Para persistir em outras sessões, você pode simplesmente anexar ao seu arquivo `~/.bash_profile` o comando para exportar suas variáveis.
```bash
echo export FOO=BAR >> ~/.bash_profile
```

## Acessando os seus scripts

Você pode acessar os seus scripts facilmente criando um diretório bin em seu diretório home com `mkdir ~/bin`. Agora, todos os scripts que você colocar nessa pasta poderão ser acessados em qualquer diretório.

Se você não conseguir acessar, tente acrescentar o código abaixo ao seu arquivo `~/.bash_profile` e depois execute `source ~/.bash_profile`.
```bash
# defina o PATH para incluir o bin privado do usuário, se existir
if [ -d "$HOME/bin" ] ; then
    PATH="$HOME/bin:$PATH"
fi
```


# 4. Depuração

Você pode depurar facilmente o script bash passando diferentes opções para o comando `bash`. Por exemplo: 
- `-n` não executará comandos e verificará apenas erros de sintaxe;
- `-v` mostrará os comandos antes de executá-los;
- `-x` mostrará os comandos após o processamento da linha de comando.

```bash
bash -n nomeDoScript
bash -v nomeDoScript
bash -x nomeDoScript
```

## Contribuições
- Identificou algum erro ou problema? Por favor, relate. [Saiba como.](https://help.github.com/articles/creating-an-issue/)
- Abra um pull request com aprimoramentos. [Saiba como.](https://help.github.com/articles/about-pull-requests/)
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
