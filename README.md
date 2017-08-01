# fe-curriculum
Stay sharp with front end skills by defining a curriculum to follow

## Shell Customizations
I have a number of modifications to my shell environment that are useful to me and may be useful to others. Feel free to take or leave any of these, leave suggestions or links to your own versions.

### ~/.bash_profile

```bash
# Get the aliases and functions
if [ -f ~/.bashrc ]; then
    . ~/.bashrc
fi

# Add tab completion to git commands
if [ -f $(brew --prefix)/etc/bash_completion ]; then
    . $(brew --prefix)/etc/bash_completion
fi

# Colors
export TERM=xterm-color
export CLICOLOR=1
export COLOR_NC='\e[0m' # No Color
export COLOR_WHITE='\e[1;37m'
export COLOR_BLACK='\e[0;30m'
export COLOR_BLUE='\e[0;34m'
export COLOR_LIGHT_BLUE='\e[1;34m'
export COLOR_GREEN='\e[0;32m'
export COLOR_LIGHT_GREEN='\e[1;32m'
export COLOR_CYAN='\e[0;36m'
export COLOR_LIGHT_CYAN='\e[1;36m'
export COLOR_RED='\e[0;31m'
export COLOR_LIGHT_RED='\e[1;31m'
export COLOR_PURPLE='\e[0;35m'
export COLOR_LIGHT_PURPLE='\e[1;35m'
export COLOR_BROWN='\e[0;33m'
export COLOR_YELLOW='\e[1;33m'
export COLOR_GRAY='\e[0;30m'
export COLOR_LIGHT_GRAY='\e[0;37m'

# Show git branch
parse_git_branch() {
     git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}
export PS1="\[${COLOR_BLUE}\]\$(parse_git_branch) \[${COLOR_RED}\]\w \[${COLOR_NC}\]\t $ "
```

Refresh your changes:
```bash
source ~/.bash_profile
```

### ~/.bashrc
```bash
# directory navigation
alias ..="cd .."
alias ...="cd ../.."
alias ....="cd ../../.."

alias magento="bash m-bin-magento"
```

### ~/.gitconfig
```bash
[user]
    name = Anthoula Wojczak
    email = anthoula@users.noreply.github.com

[alias]
  co = checkout
  ci = commit
  st = status
  br = branch
  hist = log --pretty=format:'%h %ad | %s%d [%an]' --graph --date=short
  type = cat-file -t
  dump = cat-file -p
  lg = log --oneline --decorate --graph --all -10

[color]
    ui = true
```
