# Expressões regulares:

>grep (comando usado para pescar linhas dentro de um texto)

~~~shell
grep '^aaa' arquivo    #pega todas as linhas que começam com aaa
grep 'aaa$' arquivo    #pega todas as linhas que terminam com aaa
grep '^$'  arquivo     #pega todas as linhas em branco
egrep '^a?b' arquivo   #pega todas as linhas que começam com ab ou com b (a é opcional)
grep "^a*$" arquivo    #pega todas linhas: vazio, a, aa, aaa, aaaa, ...
egrep "^a+$" arquivo   #pega todas linhas com 1 ou mais a: a, aa, aaa, aaaa, ...

grep "^.$" arquivo        #pega todas linhas que têm apenas 1 único caractere
grep "^..$" arquivo       #pega todas linhas que têm apenas 2 caracteres
egrep "^.{5}$" arquivo    #pega todas as linhas que têm apenas 5 caracteres - com o grep: grep '^.\{6\}$' arquivo  
egrep "^.{2,5}$" arquivo  #pega todas as linhas que têm de 2 a 5 caracteres (inclusive)
egrep "^.{5,}$" arquivo   #pega todas as linhas que têm 5 ou mais caracteres
egrep "^.{,5}$" arquivo   #pega todas as linhas que têm até 5 caracteres

grep '[Cc]arlos' arquivo        #pega as linahs que contém Carlos e carlos
grep '^[ab]' arquivo            #pega todas as linhas que começam com 'a' ou com 'b'
egrep '^[a-z]' arq              #pega todas linhas que começam com uma letra minúscula
egrep '^[A-Z]' arq              #pega todas linhas que começam com uma letra maiúscula
egrep '^[0-9]' arq              #pega todas linhas que começam com um número
grep '^.[aeiou]' arq            #pega todas as linhas que começam com qualquer caractere e a segunda letra é uma vogal
egrep '^[0123456789]{3}$' arq   #pega todas as linhas que começam com 3 dígitos, ex.: 123, 444, 345 
egrep '^[0123456789]{3,}$' arq  #pega todas as linhas com 3 dígitos ou mais
egrep '^[aeiou].*FIM$' arq      #pega todas linhas que começam com vogais e terminam com "FIM"
egrep '^(aaa|bbb)' arq          #pega todas linhas que começam com aaa ou com bbb     
egrep '^[0-9][0-9]?' arq        #pega todas linhas com primeiro caractere numero e o segundo tendo ou nao um numero

grep "^[^aeiou]" arq    #pega todas as linhas que não começam com vogais = Lista negada
grep "^[^0-9]" arq      #pega todas as linhas que não começam com números = Lista negada
grep "^[a-f]" arq       #pega todas as linhas que começam com a, b, c, d, e ou f
grep "^[:-@]" arq       #pega todos caracteres da tabela ASCII entre : e @ == : ; < = > ? @
~~~

# Anotações:

- Uma Expressão Regular (ER) é um método formal de se especificar um padrão de texto.
- Diz-se que um texto casa com uma expressão regular.
- Protegemos uma ER utilizando nela aspas simples, ex: grep 'bash$' /etc/passwd
- para usar o grep em ERs que contenham chaves precisamos escapá-las: grep '^.\{27\}$' arquivo
- as chaves fazem parte de um conjunto avançado de Expressões Regulares ("extended") por isso o egrep lida melhor com ela

~~~shell
^   # metacaractere que simboliza o começo de uma linha
$   # metacaractere que simboliza o fim de uma linha
^$  # linha em branco
?   # opcional - Pode aparecer ou não (opcional)
*   # asterisco - Pode aparecer em qualquer quantidade
+   # mais - Deve aparecer no mínimo uma vez
.   # pega um unico caractere

^.....    # pega 5 caracteres a partir do começo da linha
^.{5}     # pega 5 caracteres a partir do começo da linha - .{5} é o mesmo que ..... (só com egrep)
^.{5,10}  # pega entre 5 e 10 caracteres (só com egrep)
^.{5,}    # pega 5 caracteres ou mais (só com egrep)
^.{,5}$   # pega até 5 caracteres (só com egrep)

[Cc]arlos    # [] é uma lista: pode casar Carlos e carlos - uma lista, por maior que seja, representa apenas um caractere
[rgp]ato     # [] é uma lista: pode casar "rato", "gato" e "pato"
[0-9]        # pega um caractere que pode ser qualquer dígito de 0 até 9
[a-z]        # pega um caractere que pode ser qualquer letra de a até z    
[A-Z]        # pega um caractere que pode ser qualquer letra de A até Z

^(aaa|bbb)  #pega todas linhas que começam com aaa ou com bbb (só com egrep)
.*          #curinga, casa tudo, pega todos caracteres

^a?      #pode começar ou não com um literal 'a' (só com egrep)
^a*      #pode começar zero ou ilimitado numero de 'a', ex.: , a, aa, aaa, aaaa, ...
^a+      #pode começar com um ou mais a (só com egrep)

a         #literal a: literais são letras: a, b, c, ..., A, B, ..., espaços em branco são espaços em branco
aaa.*bbb  #pega tudo entre os literais "aaa" e "bbb"
~~~

  
# Links:

[aurelio](http://aurelio.net/regex/)
[regex101](https://regex101.com/)
[regexpal - casamento de texto com expressoes regulares](https://www.regexpal.com/)
[gethifi - marca os grupos da ER com cor diferente](http://www.gethifi.com/tools/regex)
[nregex - faz um replace de uma string](http://www.nregex.com/)


# Continua:

- Apostila.
- [aurelio](https://aurelio.net/regex/guia/)