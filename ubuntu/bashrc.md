<!-- TITLE: Bashrc -->
<!-- SUBTITLE: A quick summary of Bashrc -->

# Bashrc
Un shell interactif de connexion est lancé après une identification positive avec /bin/login en lisant le fichier /etc/passwd. Un shell interactif, sans login, est lancé à la ligne de commande (c'est-à-dire [prompt]$/bin/bash). Un shell non-interactif est présent habituellement lorsqu'un script shell tourne. Il est non interactif parce qu'il exécute un script et n'attend pas d'entrée utilisateur entre les commandes.

Le fichier `~/.bashrc` est lu quand le shell est invoqué comme shell interactif sans fonction de connexion.

```sh

# enable color support of ls and also add handy aliases
if [ -x /usr/bin/dircolors ]; then
    test -r ~/.dircolors && eval "$(dircolors -b ~/.dircolors)" || eval "$(dircolors -b)"
    alias ls='ls --color=auto'
    #alias dir='dir --color=auto'
    #alias vdir='vdir --color=auto'

    alias grep='grep --color=auto'
    alias fgrep='fgrep --color=auto'
    alias egrep='egrep --color=auto'
fi

# some more ls aliases
alias ll='ls -alF'
alias la='ls -A'
alias l='ls -CF'

if [ -f ~/.bash_aliases ]; then
    . ~/.bash_aliases
fi

# Turn the prompt symbol red if the user is root
PS1="[\e[01;32m\u\e[01;34m@\h\e[00m:\e[01;34m$(pwd)\e[00m]\n\$ "

# User
PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '

# Comment if user
PS1='${debian_chroot:+($debian_chroot)}\[\033[01;31m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '
```
