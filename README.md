# Manuals -- FAQ


## Github tokens
One way to add token is thru .git/config

Add in like:
[remote "origin"]
	url = https://USERNAME:TOKEN@github.com/USERNAME/REPONAME.git

Another suggestion is below:
git remote add origin https://$GITHUB_ACCESS_TOKEN@github.com/$GIT_REPO_USERNAME/$REPO_NAME.git

Another suggestion -- clone entire repo using token and then token is stored for future pulls/pushes
git clone https://$USERNAME:$TOKEN@github.com/$REPO_USER/$REPO_NAME

## Heplful commands

Updating conda: `conda update -n base -c defaults conda`

---

## Helpful alises

alias 'cgits'="clear"

alias 'cl'='clear'

alias 'gits'='git status -uno'

alias 'hist'="history | egrep $1"  # First arg requires a grep-able pattern

alias 'nbash'="bash ~/.bashrc"



## Helpful git configs


### [alias]
graph = log --format=format:'%C(bold blue)%h%C(reset) - %C(green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --graph --all --abbrev-commit --decorate

log2 = log --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) ' --oneline --graph --all --decorate

st = status

l1 = log --pretty=format:'%C(yellow)%h%Cred%d\\ %Creset%s%Cblue\\ [%cn]' --decorate --numstat

l2 = log --pretty=format:'%C(yellow)%h\\ %C(green)%ad%Cred%d\\ %Creset%s%Cblue\\ %C(dim white)%cn(reset)' --decorate --date=short --graph

l3 = log --pretty=format:"%C(green)%h \\ %C(yellow)[%ad]%Cred%d \\ %Creset%s%Cblue \\ [%cn]" --decorate --date=relative

_

### [user]

name = Your Name

email = your@email.com

_

[core]

longpaths = true

packedGitLimit = 1024m

packedGitWindowSize = 1024m

autocrlf = true

### [pack]
deltaCacheSize = 512m

packSizeLimit = 512m

windowMemory = 1024m
