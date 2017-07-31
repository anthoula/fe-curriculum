# fe-curriculum
Stay sharp with front end skills by defining a curriculum to follow

## Shell Customizations
I have a number of modifications to my shell environment that are useful to me and may be useful to others. Feel free to take or leave any of these, leave suggestions or links to your own versions.

### ~/.bash_profile

Show git branch in CLI
```bash
parse_git_branch() {
     git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}
export PS1="\u@\h \[\033[32m\]\W\[\033[33m\]\$(parse_git_branch)\[\033[00m\] $ "
```

#### aliases
Create aliases in `.bash_profile` to assign shortcuts for common Terminal commands
```bash
alias magento="bash m-bin-magento"
```

Refresh your changes:
```bash
source ~/.bash_profile
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
