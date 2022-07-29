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

---

## Helpful alises

alias 'cgits'="clear ; gits"
alias 'cl'='clear'
alias 'gits'='git status -uno'
alias 'hist'="history | egrep $1"  # First arg requires a grep-able pattern

alias 'nbash'="bash ~/.bashrc"



## Helpful git configs
