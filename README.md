# fun-stuff
MISC

### Adding git branch and current path to terminal.  
Add below code to `~/.zshrc`.  
You can customize colors and styles. More -> https://misc.flogisoft.com/bash/tip_colors_and_formatting
Finally `source ~/.zshrc`

```
parse_git_branch() {
    git branch 2> /dev/null | sed -n -e 's/^\* \(.*\)/(\1)/p'
}
COLOR_DEF=$'\e[0m 👉 '
COLOR_USR=$'\e[38;5;48m'
COLOR_DIR=$'\e[38;5;249m'
COLOR_GIT=$'\e[38;5;39m'
NEWLINE=$'\n'
setopt PROMPT_SUBST
export PROMPT='${COLOR_USR}[%n@%M] ${COLOR_DIR}%d ${NEWLINE}% ${COLOR_GIT}🔀$(parse_git_branch)${COLOR_DEF}'
```
