# Compilar um programa em C
~~~shell
gcc prog.c -o prog
cc -pthread programa.c -o programa	#compilar programa C com Threads
~~~

# Atalhos
~~~shell
arrasta ícone para prompt para obter seu caminho da pasta atual 
ctrl + alt + t 				#abre cmd
ctrl + c 					#cancela uma ação
ctrl + l 					#limpa a tela
ctrl + shift + v 			#colar		
ctrl + shift + c			#copiar
ctrl + shift + t			#abrir nova guia 
ctrl + shift + w			#fechar nova guia 
ctrl + shift + f			#pesquisar na janela do prompt
ctrl + windows + cima		#maximizar a janela
ctrl + windows + baixo		#restaurar tamanho da janela
~~~

# Comandos gerais (formato: comando opções parâmetros )
~~~shell
algumComando --help 	#exibe ajuda sobre o comando
man algumComando		#chama página de manual do comando (q to quit)
info algumComando		#informações sobre o comando
nomePrograma --version	#obter versão do programa ou
clear					#limpa a tela (ctrl L)
exit					#fecha shell
reboot					#reinicia ou shutdown -r
shutdown -h 20:30   	#(cancelar: ctrl C ou fechando o terminal)
shutdown now 			#ou -h now 
date					#exibe a data
cal						#mostra calendário do mês cal -m 12 == mostra dezembro
uptime					#mostra há quanto tempo o sistema está ativo
arch					#mostra a arquitetura da maquina
lsb_release -r			#desocobrir a versão do ubuntu
env						#lista variáveis que o shell define por padrão
sleep 1					#faz sistema ficar parado por segundo
~~~

# Diretórios 
~~~shell
ls						#lista arquivos do diretório atual
ls nomePasta			#lista arquivos do diretório nomePasta
ls -l					#mostra em forma de lista
ls -a					#lista tudo (all) - arquivos que começam com '. e  mostra ocultos
ls -t					#lista na ordem de modificação
ls -r					#lista arquivos na ordem reversa
ls -la					#combina -l e -a
ls -ltr					#combina -l -t e -r

cd ..					#volta um diretório
cd .. /.. 				#volta dois diretórios
cd /home/mauricio/pasta #vai de qualquer lugar para o diretório chamado pasta :D

mkdir nomeDiretorio	 								#cria pasta
mkdir -pv pastaMae/{filha1,filha2}					#cria árvore de diretórios (não pode ter espaços) 
mkdir -pv pastaMae/{filha1/{neta1,neta2},filha2}	#cria árvore de diretórios (não pode ter espaços)

rmdir			#apaga pasta vazia
rm -r 			#remove arquivo ou pasta e seu conteúdo

pwd				#mostra diretório atual
du				#verifica tamanho dos arquivos do diretório e dos subdiretórios
cp nomeArq caminho/nomeArq
cp -r * ../pasta 			#copia recursivamente (-r) todos os arquivos para a pasta
mv arquivo.txt ../pasta2/ 	#move para pasta2 (dentro de uma pasta acima)
mv nomeArq novoNomeArq  	#renomeia arquivo
~~~

# operador ~ substitui a variável $HOME
~~~shell
ls ~/cursos 	#é o mesmo que ls $HOME/cursos
ls /opt/		#'/' é o diretório raíz != do home
~~~

# operador ! 
~~~shell
!c + enter		#executa ultimo comando iniciado com 'c'
~~~

# Comandos para arquivos
~~~shell
xdg-open nomeArquivo 	#abre imagens, vídeos, músicas etc
eog -f abreImagem.gif	#abre imagens
find -name nomeArq		#encontra arquivos nos dir e subdir opç: -name, -iname, -type f, -exec
~~~

# Operador pipe ( “|” )
~~~shell
ls  | more 	# Saída de ls vira entrada de more (exibe os arquivos lentamente na tela)
grep "mauricio" /etc/passwd | cut -d ":" -f 1,3,4  #exibe trechos 1,2,3 delimitados por : 
~~~

# Redirecionamento ( < entrada ) e ( > saída)
~~~shell
./etapa1 < entrada.txt > saida.txt 	#programa etapa1 recebe etrada.txt, e escreve saída em saida.txt
ls > arquivo.txt 					#grava conteúdo do ls no arquivo.txt
./script.sh > saida.txt  			#grava saída do script.sh no arquivo saida.txt
echo "$(comando com uma saída)" > textoTeste1.txt
~~~

# Comandos para compactar arquivos
~~~shell
tar cvfz nomeArq.tar.gz [arquivos|diretório]	#para compactar .tar.gz 
tar cvzf nomeArq.tgz arquivo1 arquivo2			#para compactar .tgz - aprendi em compiladores
~~~

# Comandos para descompactar arquivos
~~~shell
tar -xvf nomedoarquivo.tar 		#para descompactar tar
tar -vzxf nomedoarquivo.tar.gz	#para descompactar tar.gz
tar -xvfz nomeArq.tar.gz		#para descompactar tar.gz 
tar -jxvf nomedoarquivo 		#para descompactar tar.bz2
tar -xvzf nomedoarquivo.tgz		#para descompactar .tgz
unzip nomedoarquivo.zip 		#para descompactar zip
unrar x nomedoarquivo.rar 		#para descompactar rar
bunzip nomedoarquivo.bz2 		#para descompactar bz2
~~~

# Comandos usuários e disco
~~~shell
whoami		#retorna usuário logado
who			#retorna usuários logados no sistema
su			#muda para root ou outro usuário
w			#mostra usuários conectados
df			#mostra disponibilidade das partições ou df -h 
free		#mostra quanto de ram temos disponível 
mount		#monta (ativa) devices
umount		#desmonta (desativa) devices
echo $PATH	#diretórios que estão no PATH
~~~

# Comandos de rede - gerais
~~~shell
ifconfig	#verificar ip da máquina
hostname	#retorna nome do computador na rede
~~~

# Comandos de rede 
> wget - https://www.hostinger.com.br/tutoriais/wget-o-que-e-como-instalar-comandos-wget
~~~shell
wget [link]	#downloads via FTP, SFTP, HTML e HTTPS 
~~~

# Comandos de rede - ssh
~~~shell
ssh
~~~

# Comandos sobre processos
~~~shell
ps 					#mostra processos rodando ex.: ps aux PID é o número do processo
ps aux | grep bash 	#mostra processos relacionados ao bash
top 				#mostra processos rodando em tempo real + info (q to quit)
kill -9 8731		#parar a exec de um programa -9 matar processos, 2315 num processo
~~~



# Arquivos de texto - criar / visualizar arquivos
~~~shell
touch nomeArq	#cria rapidamente um arquivo de texto
gedit nomeArq & #abre arquivo de texto e não trava o prompt
nano nomeArq 	#Editor de texto 
cat nomeArq		#imprime arquivos na tela
cat -n nomeArq	#imprime arquivos na tela com linhas 
head nomeArq	#mostra início arquivo  opções -n -c
tail nomeArq	#exibe últimas linhas
more nomeArq 	#exibe na tela e espera enter
less nomeArq	#mostrar arquivos grandes na tela com rolagem pelas setas - q to quit
~~~

# Arquivos de texto - geral
~~~shell
rev nomeArquivo			#inverter texto do arquivo
wc texto.txt			#conta letras
uniq texto.txt			#remove as linhas duplicadas e consecutivas do arquivo
sort texto.txt			#ordena as linhas do arquivo de acordo com o primeiro caractere
sort -n texto.txt		#ordena as linhas do arquivo de acordo com o o caractere numérico do início da linha
sort texto.txt | uniq 	#ordena arquivo e remove linhas duplicatas
> texto.txt				#apaga conteúdo do arquivo texto.txt
echo "oi" > texto.txt 	#escreve "oi" no arquivo texto.txt (sobreescreve arquivo)
echo "oi2" >> texto.txt	#escreve "oi2" no arquivo texto.txt (faz append - adiciona no final do arquivo sem sobrescrevê-lo)
cat texto.txt >> t2.txt	#escreve texto.txt no final do arquivo t2.txt (faz append)

echo $(( RANDOM % 101 ));	#Gerando números aleatórios de 0 a 100 - usando a variável $RANDOM

seq 0 10 100; 	#gera números de 10 em 10 até 100. 
seq 5;			#gera numeros 1 2 3 4 5
seq -10 10;		#gera do número -10 ao 10

~~~


# Arquivos de texto - comando tr
~~~shell
tr -d ' ' < texto.txt			#(-d == delete) remove espaços do arquivo. outra forma echo "mauricio rocha" | tr -d ' ' 
tr -d ',-' < texto.txt			#remove todos ',' e todos os '-' juntos e separados
tr -s a-z A-Z < texto.txt		#(-s == substituir) torna maiúscula, funciona sem o "-s" outra forma: 
tr -s A-Z a-z < texto.txt		#torna minúscula, outra forma: tr [:upper:] [:lower:] < texto.txt
tr [:lower:] [:upper:] < txt	#torna maiúsculo
tr -s ' ' '\t' < texto.txt		#substitui todos espaços por tabs (funciona com caracteres quaisquer)
tr -s '\n' ' ' < texto.txt		#substitui quebras de linha por espaços
tr -s ' ' ' ' < texto.txt		#substitui espaços repetidos por um único espaço
~~~

# Arquivos de texto - comando grep: grep [opções] padrão [ARQUIVO] Opções -n -i -v -qs -w -x (podemos combiná-las)
grep palavra texto.txt 		#imprime linha do arquivo texto.txt que contém a palavra (pode ser uma string)
grep -n palavra texto.txt 	#imprime nº da linha e linha do arquivo texto.txt que contém a palavra
grep -i palavra texto.txt 	#imprime linha do arquivo texto.txt que contém a palavra sem diferenciar maiúsculas de minúsculas
grep -c palavra texto.txt	#mostra a quantidade de linhas que contém a palavra procurada
grep -r -n mauricio			#mostra nº de linha e linha de todos arquivos do diretório que contém a palavra "maurício". -r habilita pesquisa recursiva no diretório atual. 
grep -r -c palavra 			#mostra a quantidade de linhas que contém a palavra procurada em cada arquivo do diretório corrente. 
grep -v palavra texto.txt	#mostra tudo menos a linha do texto que contém a palavra
grep ^a texto.txt			#mostra todas as linhas que iniciam com a
grep a$ texto.txt			#mostra todas as linhas que terminam com a
grep -qs alegria texto.txt && echo "contido" || echo "não contido" # -qs == retorna true or false and quit without message


# Arquivos de texto - comando  cut - opções: -c (caractere) -d (delimitador) -f (intervalo) 
cut -c 1 texto.txt   				#imprime somente o caractere 1 de cada linha (começa em 1)
cut -c 1-5 texto.txt 				#imprime do caractere 1 ao 5 de cada linha
cut -c 1,3,5 texto.txt				#imprime os caracteres 1, 3, 5 de cada linha
cut -c 1-3,5-10 texto.txt			#imprime os caracteres nos intervalos especificados
cut -c 2- texto.txt					#imprime do caractere 2 até o fim da linha 
cut -c -7 texto.txt					#imprime do caractere até o caractere 7
cut -c 1-3 texto.txt --complement	#imprime tudo menos do caract 1 ao 3
cut -d "." -f 1 texto.txt  			#imprime o 1º campo delimitado pelo ponto
cut -d "." -f 1,5 texto.txt			#imprime campos 1 e 5 delimitados pelo ponto
cut -d "." -f 2- texto.txt  		#imprime do campo 2 em diante
cut -s -d "." -f 1- texto.txt --output-delimiter="$" 	#substitui na tela o delimitador . pelo $




# Arquivos de texto - programa sed
#O sed lê um arquivo, linha por linha, e aplica a expressão do parâmetro a cada uma delas.
#caracteres especiais: espaço (\ ), ponto (\.) Funcionamento: sed 'expressão regular' arquivo

sed 's/tristeza/alegria/' texto.txt  	#s=substitui 1º "tristeza" de cada linha por "alegria"
sed 's/tristeza/alegria/g' texto.txt  	#g=substitui todas ocorrências de tristeza por alegria
sed '1s/aaa/ccc/' texto.txt	 			#substitui "aaa" por "ccc" na linha 1
sed '1,3s/aaa/ccc/g' texto.txt	 		#substitui todos "aaa" por "ccc" entre as linhas 1 e 3
sed 's/^/biscoito /' texto.txt   		#coloca "biscoito" no inicio de cada linha
sed 's/$/ bolacha/' texto.txt			#coloca "bolacha" no fim de cada linha
sed 's/aaa\|bbb/ccc/g' texto.txt 		#substitui todos "aaa" e "bbb" por "ccc"
sed 's/aaa.*bbb/ccc/' texto.txt			#substitui aaa, bbb e tudo entre aaa e bbb por ccc
sed -i 's/aaa/bbb/g' texto.txt			#troca aaa por bbb DIRETAMENTE no arquivo (-i)
sed '/aaa/ s/bbb/ccc/g'  texto.txt 		#nas linhas que contem "aaa" subst "bbb" por "ccc" 
sed '/aaa/! s/bbb/ccc/g' texto.txt 		#nas linhas que não contem "aaa" substitui "bbb" por "ccc"
sed 's/[aeiou]/X/g' texto.txt			#substitui todas vogais por X 

sed '5q' texto1.txt 					#Imprime 5 primeiras linhas e q=quit
sed -n '44p' texto.txt					#p=print, imprime SÓ linha 44
sed -n '6,9p' arquivo.txt				#imprime da sexta até a nona
sed -n '/^aaa/p' texto.txt		  		#imprime todas as linhas que começam com "aaa"
sed -n '/^aaa\|^bbb/p' texto.txt		#imprime todas as linhas que começam com "aaa" ou com "bbb"
sed -n '/aaa$/p' texto.txt		  		#imprime todas as linhas que terminam com "aaa"
sed -n '/aaa/p' texto.txt		  		#imprime todas as linhas que contém "aaa"
sed -n '/aaa/!p' texto.txt		  		#imprime todas as linhas que NÃO contém "aaa"
sed -n '/aaa/{p;q;}' arquivo.txt  		#imprime somente primeira linha que contém a string "aaa"

sed '1,5d' texto.txt					#d=deleta as linhas 1 até a 5
sed '/^aaa/d' texto.txt 				#d=deleta todas linhas que começam com a string "aaa"
sed '/aaa/d' texto.txt					#d=deleta todas as linhas que contem a string "aaa"
sed '/^$/d' texto.txt					#d=deleta linhas em branco









#__________________________________________________________________________________________________


<< Shell

	Shell é um programa que permite ao usuário interagir com o sistema operacional através de comandos digitados pelo teclado. 
	O shell mais famoso do linux é o Bash (o bash é um interpretador de comandos do sh). 
	A Extensão do é arquivo: .sh e a Primeira linha do arquivo precisa ser: #!/bin/bash
	Cada comando digitado é lido, verificado, interpretado e enviado ao sistema operacional para ser de fato executado.
	
Shell

<< Bash

	O nome Bash significa Bourne Again Shell, um produto GNU. 
	Ele é a interface padrão de linha de comando utilizada praticamente em todas as distribuições GNU/Linux.
	A aparência do prompt é controlada pela variável PS1.

Bash

<< aprofundar

como receber um argumento $1 contendo a string --version, por exemplo e exibir um texto ilustrativo sobre a versão e
caso nao seja passado nenhum argumento não realizar nenhuma ação. Como fazer isso de maneira "bonita"?


***Há várias maneiras de protegermos comandos, que são: 
aspas simples (''), aspas duplas ("") e a contra-barra, ou barra inversa (\)


diretório do $PATH para inserir scripts
*** criar um link simbólico em /usr/local/bin


***variáveis de ambiente
https://devcontent.com.br/artigos/windows/o-que-sao-como-alterar-criar-excluir-variaveis-de-ambiente

# ver o operador '~'



colocar um bin no PATH para permitir executá-lo de qualquer lugar
[OPTIONAL] Add "{installation home}/bin" to your PATH environment
     variable so that you may start Android Studio from any directory.

aprofundar





: 'Comandos a partir de arquivo.sh'

#!/bin/bash		
comandos aqui


#Tornar arquivo.sh executável
chmod +x arquivo 


#Executar um arquivo.sh
./arquivo.sh 	


# Comentários
# Sou um comentário de uma linha

<<NomeComentario
	sou um comentario
	de varias linhas 
NomeComentario

:<<'NomeComentario'
	Sou um Comentário 
	de várias linhas 
NomeComentario

: '
	Sou um Comentário 
	de várias linhas 
	(não se esqueça de dar um espaço após o ':' ) 
'

#Escrevendo na tela
echo sou um texto;
echo "eu também sou" $variavel;	#não usa concatenadores 
echo -n nao quebro a linha;
echo -e "\n saida \t formatada"; 
echo					#printa linha em branco
printf "Obrigado.\n" 	#usando o comando printf 

#Lendo do teclado
read nome;				#pode ler mais de uma variável ao mesmo tempo: read nome sobrenome;
echo Boa noite $nome;


#Variáveis
num=5			#Criação/atribuição - Não é necessário declarar variáveis, sem espaço!
echo $num		#Uso do ponto e vírgula é facultativo
unset num		#apaga variável num
hoje=$(date)  	#armazenar saída do comando em variável: var=$(comando)
nome="Mauricio"
echo $nome


#Constantes e variáveis especiais
$PATH
$HOME		#fazer ls $HOME/nomePasta é o mesmo que fazer ls ~/nomePasta
$USER

$0 	#nome do script
$1	#primeiro argumento
$2 	#segundo argumento
$# 	#número de argumentos
$* 	#todos argumentos


# Exemplo salvo em arquivo chamado script.sh. Abrir o arquivo: ./script.sh argumento1 argumento2
#!/bin/bash
echo "nome do script = " $0			#escreve ./script.sh
echo "argumento 1 = " $1			#escreve argumento1
echo "argumento 2 = " $2			#escreve argumento2
echo "numero de argumentos = " $#	#escreve 2
echo "todos argumentos = " $*		#escreve argumento1 argumento2

#Expressões aritméticas
x=$(( 1500 + 200 ));	#jeito 1: não pode ter espaço antes nem depois do sinal de igualdade
x=$[ 1500 + 200 ];		#jeito 2: não pode ter espaço antes nem depois do sinal de igualdade

#Operadores aritméticos
x=$[2**3]	#faz 2 elevado a 3 == 8
x=$[5%3]	#resto da divisão, == 2



#Operadores lógicos: &&	|| 


#Operadores relacionais e de igualdade (para variáveis) - VER USO
#<	>	<=	>=	==	!=	!(negação), ex.: !$num => retorna true se num=0, senão retorna false



#comando test - operadores para NÚMEROS:  -lt		-gt		-le		-ge		-eq		-ne
[ $nota -ge 6 ] && echo good || echo bad		# se nota >= 6 imprime good, senão imprime bad
[ $x -eq 2 ] && echo igual || echo diferente 	# se x == 2 imprime igual, senão imprime diferente
test $x -eq 2  && echo igual || echo diferente  # comando test é equivalente ao comando [ ] 


#comando test - operadores para STRINGS:  ==		!=		-z		-n
test "$nome" == "Mauricio" && echo "é igual" || echo "não é igual"	# == testa se String é igual (funciona com '=' também)
test "$nome" != "Mauricio" && echo "é diferente" || echo "não é"	# != testa se String é diferent
test -z "$nome" && echo "String é nula"								# -z testa se String é nula
test -n "$nome" && echo "String é não nula"							# -n testa se String é não nula
[ $nome == "Mauricio" ] && echo igual || echo diferente				# outra forma, == testa se String é igual


#comando test em arquivos obs: aaa ==  nome do arquivo
test -d aaa && echo "é um diretório" 	#-d testa se $aaa é um diretório outra forma: [ -d aaa ] && echo "é" || echo "nao é"
test -f aaa && echo "é um arquivo" 		#-f testa se $aaa é um arquivo
test -r aaa && echo "pode ler" 			#-r	o arquivo tem permissão de leitura
test -s aaa && echo "tam > 0"			#-s	o tam do arquivo maior que zero
test -w aaa && echo "pode w"			#-w	o arq tem permissão de escrita
test -x aaa && echo "pode x"			#-x o arq tem permissão de execução
test aaa -nt bbb && echo "é + novo"		#-nt testa se o arquivo em $aaa é mais recente que o em $bbb
test aaa -ot bbb && echo "é + old"		#-ot	o arquivo é mais antigo
test aaa -ef bbb && echo "mesmo arq"  	#-ef testa se o arquivo é o mesmo
test -f aa -a -s aa  && echo "ok"		#-a	E lógico - "aa é arquivo e não está vazio"
test -d aaa -o -d bbb  && echo "ok"		#-o	OU lógico - "aaa ou bbb são diretórios"


#Comandos de seleção:	if … else - em Shell Script o if testa um comando e não uma condição!
if test "$media" -ge 6; then   #se colocar o then na outra linha pode-se suprimir o ';' 
	echo aluno aprovado
else 
	echo aluno reprovado	
fi


#Comandos de seleção:	if … else
if [ $media -ge 6 ]; then 	#esses espaços são todos obrigatórios - o comando [ ... ] é um atalho para o comando test
	echo aluno aprovado; 
else	
	echo aluno reprovado;
fi


#Comandos de seleção:	if … else - versão que suporta somente os operadores: <	>	<=	>=	! 	==	!= 
if(( $media >= 6 )); then 			#dois parênteses são obrigatórios e não pode ter espaços entre o if e o (( 
    echo aluno aprovado;
else
	echo aluno reprovado;
fi;


#Comandos de repetição:	while  	
x=0
while test "$x" -le 10; do #se colocar o do na outra linha pode-se suprimir o ';' 
	echo -n "$x "	#printa na mesma linha
	x=$((x+1))
done


#Comandos de repetição:	while  	
i=0
while [ $i -lt 10 ]; do
	echo $(( i * 5 ))
	i=$(( i + 1 ))			#outra forma: x=$[ x + 1 ]
done


#Comandos de repetição:	while - versão que suporta somente os operadores: <	>	<=	>=	! 	==	!= 
i=0;
while(( $i <= 10 )); do
	echo $i;
	i=$(( $i + 1 ));
done;


#Comandos de repetição:	for
for i in 0 1 2 3 4; do
	echo $i
done


#Comandos de repetição:	for
for i in $(seq 0 10); do
	echo $i
done


#Comandos de repetição:	for
for i in {0..20}; do			#nao pode ter espaços
	echo $i
done


#Comandos de repetição:	for
for i in {0..10..2}; do 		#pula de 2 em 2
     echo $i
done


#Comandos de repetição:	for
for(( i=1; i<=10; i++ )); do
	echo -n " " $i	
done


#Função sem parâmetros
#!/bin/bash
function funcao1() {
   echo "Sejam bem vindos."
}
funcao1		#chama a função - interessante: echo "ola amigos" $(funcao1)


#Função "com parâmetros" - por valor
#!/bin/bash
function funcao2() {
	echo "bom dia" $1 e bom dia $2;
}
funcao2 "Mauricio" "Joana";	


#Função com variávels como parâmetro
#!/bin/bash
function funcao3() {
	echo $1
}
x=2
f1 $x


#Função com variávels como parâmetro - por referência
#!/bin/bash
function funcao4() {
	echo $(( $1 + 200 ))  
}
x=3
soma x

#Função com variávels como parâmetro - por referência
#!/bin/bash
function funcao5() {
	eval echo \$$1 
}
nome="Mauricio"
funcao3 nome	


#Função que modifica valor de variável recebida como parâmetro
#!/bin/bash
function atribuiValor() {
	eval $1=100
}
atribuiValor x
echo $x


#Função que realiza swap entre 2 variáveis
#!/bin/bash
function swap() {
	eval temp=\$$1
	eval $1=\$$2
	eval $2=$temp
}
a=2
b=5
echo "a = $a b = $b"
swap a b
echo "a = $a b = $b"



#Vetores
#elementos são separados por espaços e começam com índice zero

nomes=("mauricio" "maria" "josé");	#declarando e inicializando um vetor
echo ${nomes[0]};					#usando elementos do vetor - sem espaços! não funciona isto: echo nomes[0];
nomes[1]="joaquina";				#alterando um elemento do vetor
echo ${nomes[*]};					#exibe todos os elementos do vetor. outra forma: echo ${nomes[@]};
echo ${#nomes[*]};					#exibe o número de elementos do vetor ou numElementos=${#nomes[@]};
echo ${#nomes[2]};					#exibe o tamanho do segundo elemento do vetor
echo ${!nomes[*]};					#exibe todos os índices dos elementos do vetor, outra forma: echo ${!nomes[@]};
echo ${nomes[*]:2};					#exibe elementos do vetor somente a partir do índice 2 ou echo ${vetor[@]:$i}
echo ${nomes[*]:2:3};				#exibe somente os 3 elementos a partir do elemento 2 ou 
echo ${nomes[0]:0:1};				#obtem primeira letra do elemento 0 do vetor
unset nomes;						#apaga vetor
unset nomes[1];						#apaga somente elemento de índice 1 do vetor
nomes=("joaquina" ${nomes[*]});		#adiciona elemento no início do vetor. aceita variável: nomes=(${nomes[*]} $novoNome);
nomes=(${nomes[*]} "joaquina");		#adiciona elemento no fim do vetor. aceita variável: nomes=($novoNome ${nomes[*]}); 
frase=(${frase[*]});				#transforma a string frase em um vetor, usando os espaços como separador de elementos

nomes=${nomes[*]};					#transforma o vetor nomes em uma string. outra forma: com @ no lugar do *;
echo ${#nome};						#exibe o número de caracteres de uma string
echo ${nome:0:4};					#exibe 4 letras a partir da posiçao 0


#IFS é uma variável que modifica o separador de elementos de um vetor (antes era o espaço)
#exemplo:
export IFS=: #torna o separador do vetor o caractere ':'
nomes="Mauricio Rocha : Joana Antunes"
echo $nomes
nomes=($nomes)	#converte string nomes em um vetor
echo $nomes



#Comando chmod

chmod -r a	#arquivo 'a' não pode ser lido
chmod +r a	#arquivo 'a' pode ser lido
chmod -w a	#arquivo 'a' não pode ser editado
chmod -w a	#arquivo 'a' pode ser editado
chmod +X a	#arquivo 'a' pode ser executado




#__________________________________________________________________________________________________


#Exemplos de código:

#testa se string passada como primeiro argumento está contida na string passada como segundo argumento
#!/bin/bash
test $# -ne 2 && exit	# sai se script não tiver 2 parâmetros
echo $2 | grep -qs $1 && echo "$1 está contida em $2" || echo "$1 nao esta contida em $2"


#Usando comandos read, test
#!/bin/bash
echo "quer continuar? s ou n?"
read resposta
test "$resposta" = "n" && exit # se digitar n -> exit interrompe o script. O inverso de && é ||
echo "disse sim"


#Escreve números de 1 a 10 dizendo se são pares ou ímpares
#!/bin/bash
for(( i=1; i<=10; i++ )); do
	if(( ($i % 2) == 0 )); then
		echo $i "- par";
	else
		echo $i "- impar ";
	fi;
done;

#Escreve os parâmetros linha a linha enumerando-os.  
#!/bin/bash
i=1
while test "$1"; do
   echo "Parâmetro $i: $1"
   shift			#elimina argumento $1 fazendo com que o argumento $2 passe a ser o $1 e o $3 o $2
   i=$((i+1))
done


#Usando $0, $#, $1, $2   
#!/bin/bash
echo "Nome do script $0"
echo "Primeiro argumento: $1"
echo "Segundo argumento $2"
echo "Recebidos $# argumentos: $*"
#chamando script: ./nomeScript.sh argumento1 argumento2


#escreve todos elementos do vetor cada um em uma linha
#!/bin/bash
nomes=("mauricio" "maria" "josefa" "betina")
x=0
while test $x -lt ${#nomes[*]}; do
	echo ${nomes[x]}
	x=$((x+1))
done



#__________________________________________________________________________________________________


: ' sed página oficial: https://www.gnu.org/software/sed/ '
https://aurelio.net/sed/sed-howto/ 
http://terminalroot.com.br/2015/07/30-exemplos-do-comando-sed-com-regex.html 
http://rberaldo.com.br/o-comando-sed-do-linux/ 


http://www.dltec.com.br/blog/linux/exemplos-de-uso-do-comando-tr-no-linux/
http://cleitonbueno.com/linux-o-comando-cut/


# Arquivos de texto - programa awk
http://rberaldo.com.br/tutorial-awk/




#AVANÇAR

https://www.codecademy.com/articles/command-line-commands
http://rberaldo.com.br/curso-de-shell-script-modulo-1-scripts-shell-estruturas/ 
https://www.vivaolinux.com.br/topico/Comandos/Como-alterar-o-conteudo-de-um-arquivo-sem-abrilo.
http://www.linuxpro.com.br/dl/guia_500_comandos_Linux.pdf
http://computeirodadepressao.com/guia-com-mais-de-500-comandos-do-linux-explicados/ 
http://aurelio.net/shell/ 
https://www.vivaolinux.com.br/artigo/Prompt-Bash-avancado/

Buscar sobre ssh (salvar em comandos de rede)

#__________________________________________________________________________________________________

#	Links legais

https://www.diolinux.com.br/ #muito conteudo legal publicações diárias
https://pt.wikipedia.org/wiki/Utilit%C3%A1rios_Unix #dicas bem legais de linux
https://pt.wikipedia.org/wiki/Uniq # tem um guia de comandos legal
http://www.diolinux.com.br/2011/05/os-diretotios-do-linux.html





