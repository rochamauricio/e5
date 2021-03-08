# Modificando as cores do shell

- Fonte: https://blog.remontti.com.br/141
- Criar um arquivo oculto chamado .bashrc no diretório /home/mauricio
- Popular o arquivo com o seguinte conteúdo:

~~~shell
  export LS_OPTIONS='--color=auto'
  eval "`dircolors`"
  alias ls='ls $LS_OPTIONS'
  alias ll='ls $LS_OPTIONS -l'
  alias l='ls $LS_OPTIONS -lA'
 ~~~

# Extra colorindo o ==&gt; root@debian:~#

> Essa parte de baixo não precisa!!

~~~shell
  PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u\[\033[01;34m\]@\[\033[01;31m\]\h\[\033[00m\]:\[\033[01;37m\]\w\[\033[01;32m\]\$\[\033[00m\] '
~~~

# backup da variável $PS1
~~~shell
  ${debian_chroot:+($debian_chroot)}\u@\h:\w\$
~~~

# Algumas explicações: 

  \u #O nome do usuário atual
  \h #Nome da máquina
  \W #Nome do diretório atual
  \$ #Caractere que diferencia um usuário comum do super-usuário
  \t #A hora atual no formato de 24 horas hh:mm:ss
  \d #A data atual no formato “Dia_da_semana Mês Dia”




