# Path to your oh-my-zsh installation.
export ZSH=/Users/benno/.oh-my-zsh
source $ZSH/oh-my-zsh.sh

plugins=(git)

#Convenience aliases
alias ls="ls -hAG"
alias diff="colordiff"
alias tree="tree -aCphF -L 5 -I \".git\""
alias emacs="emacs -nw"
alias histogram="(tr ' ' '\n' | sort | uniq -c) <"
alias copy="pbcopy"
svndiff () {svn diff $* | wdiff -nd | colordiff}

# PROMPTS
autoload -Uz vcs_info
zstyle ':vcs_info:*' enable git svn
precmd () {
    zstyle ':vcs_info:*' formats "%{$fg_bold[red]%}:%{$fg_bold[yellow]%}%b%%{$reset_color%}"
    vcs_info
}
setopt prompt_subst
PROMPT='%{$fg_bold[red]%}%* %{$fg_bold[cyan]%}%~%{$fg_bold[yellow]%}${vcs_info_msg_0_} %{$fg_bold[red]%}λ%{$reset_color%} %}'

source /usr/local/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh

#SETTINGS
export HISTSIZE=30000
export EDITOR=emacs
setopt AUTO_CD
setopt AUTO_PUSHD
setopt PUSHD_SILENT
setopt IGNORE_EOF
autoload -Uz compinit && compinit -D # git autocompletion

# OPAM configuration
. /home/benno/.opam/opam-init/init.zsh > /dev/null 2> /dev/null || true
. /home/benno/.opam/opam-init/init.zsh > /dev/null 2> /dev/null || true

# PySMT configuration
#export PYTHONPATH="/home/benno/.smt_solvers/python-bindings-2.7:${PYTHONPATH}"

#Brew Setup
if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi
export PATH="/usr/local/sbin:${HOME}/bin:$PATH:${HOME}/.cargo/bin"

#Java Setup
export JDK_18=$(/usr/libexec/java_home -v 1.8)
#export JDK_17=$(/usr/libexec/java_home -v 1.7)
#export JDK_16=$(/usr/libexec/java_home -v 1.6)
export JAVA_HOME=$JDK_18

# Checker Framework Setup
#export CHECKERFRAMEWORK=${HOME}/jsr308/checker-framework-2.1.11
#export PATH=${CHECKERFRAMEWORK}/checker/bin:${PATH}
