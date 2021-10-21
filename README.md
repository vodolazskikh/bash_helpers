# bash_helpers

Постоянно про это забываю, как только настроил мак... решил сохранить тут полезные штуки для bash-терминала, чтобы не искать каждый раз

### Подсветка ветки в git.

Добавить в ~/.bash_profile:

```bash
parse_git_branch() {
  git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}

export PS1="\u@\h \W\[\033[32m\]\$(parse_git_branch)\[\033[00m\] $ "
```

### Автокомплит ветки по нажатию TAB.

Дернть курл:

```
curl https://raw.githubusercontent.com/git/git/master/contrib/completion/git-completion.bash -o ~/.git-completion.bash
```

Добавить в ~/.bash_profile:

```bash
if [ -f ~/.git-completion.bash ]; then
  . ~/.git-completion.bash
fi
```
