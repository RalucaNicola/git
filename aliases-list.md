This is a list of aliases that one of my colleague at work uses:

```
alias ll="ls -l"

alias emacs="emacs -fn 8x13 -geometry 80x80"
alias cninja="cmake -GNinja -DCLONE_SUBPROJECTS=ON -DCMAKE_INSTALL_PREFIX=${PWD}/install"

alias gam="git commit --amend"
alias gbr="git branch"
alias gch="git checkout"
alias gci="git push"
alias gcl="git clobber"
alias gco="git pull --rebase"
alias gcr="git pull root"
alias gdc="git diff-commit"
alias gdi="git diff"
alias gdt="git difftool"
alias gdr="find . -name .git -type d -print -execdir git diff \;"
alias gfe="git fetch"
alias gitdiff="env -i git diff --no-prefix"
alias glo="git log"
alias gap="git add -p"
alias gor="git push origin"
alias gpi="git cherry-pick"
alias gpa="git cherry-pick --abort"
alias gpc="git cherry-pick --continue"
alias gps="git cherry-pick --skip"
alias gra="git rebase --abort"
alias grc="git rebase --continue"
alias gre="git reset"
alias grp="git repu"
alias grr="find . -name .git -type d -print -execdir git reset --hard origin/master \;"
alias grs="git rebase --skip"
alias grv="git review"
alias gsr="find . -name .git -type d -print -execdir git status -s -uno \;"
alias gsu="git submodule update --init --recursive"
alias gst="git status"
alias gup="git pull --rebase user master && git pull --rebase"
alias hpr="hub pull-request"
alias xws='xrandr --auto --output DP-1-1 --primary --left-of eDP-1-1 --mode 3840x2160 --output eDP-1-1 --mode 1920x1080 --output DP1 --primary --left-of eDP1 --mode 3840x2160 --output eDP1 --mode 1920x1080'
alias xnb="xrandr --output eDP-1-1 --mode 3840x2160"
alias xhd="xrandr --output eDP-1-1 --mode 1920x1080"


alias nrb="npm run build"
alias nrt="npm run build:ts"
alias tsfix="node_modules/.bin/tslint --fix"
# tsfix `git diff --name-only --diff-filter=AMRC`

# For PRT build scripts:
alias cmake3=/usr/bin/cmake
alias ninja-build=/usr/bin/ninja

gri() { git rebase -i HEAD~"$1"; }
```