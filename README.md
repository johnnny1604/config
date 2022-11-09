# My Config

## .zshrc

### Prompt with pathname, git branch and some styling

```bash
function parse_git_branch() {
    git branch 2> /dev/null | sed -n -e 's/^\* \(.*\)/[\1]/p'
}

COLOR_DEF=$'\e[0m'
COLOR_USR=$'\e[4;36m'
COLOR_DIR=$'\e[4;33m'
COLOR_GIT=$'\e[4;35m'
setopt PROMPT_SUBST
export PROMPT='${COLOR_USR}%n ${COLOR_DIR}%~ ${COLOR_GIT}$(parse_git_branch)${COLOR_DEF} $ '
```
