# Manuals -- FAQ


## GitHub tokens
One way to add token is through .git/config

Add in like:

	[remote "origin"]
		url = https://USERNAME:TOKEN@github.com/USERNAME/REPONAME.git

Another suggestion is below:
git remote add origin https://$GITHUB_ACCESS_TOKEN@github.com/$GIT_REPO_USERNAME/$REPO_NAME.git

Another suggestion -- clone entire repo using token and then token is stored for future pulls/pushes
git clone https://$USERNAME:$TOKEN@github.com/$REPO_USER/$REPO_NAME

## Heplful commands

Updating conda: `conda update -n base -c defaults conda`

Installing new kernels for Jupyter: `python -m ipykernel install --user --name myenv --display-name "Python (myenv)"`

Viewing installed kernels: `jupyter kernelspec list`

---

## Helpful alises

alias 'cgits'="clear"

alias 'cl'='clear'

alias 'gits'='git status -uno'

alias 'hist'="history | egrep $1"  # First arg requires a grep-able pattern

alias 'nbash'="bash ~/.bashrc"



## Helpful git configs

	[alias]
	graph = log --format=format:'%C(bold blue)%h%C(reset) - %C(green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --graph --all --abbrev-commit --decorate
	log2 = log --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) ' --oneline --graph --all --decorate
	st = status
	l1 = log --pretty=format:'%C(yellow)%h%Cred%d\\ %Creset%s%Cblue\\ [%cn]' --decorate --numstat
	l2 = log --pretty=format:'%C(yellow)%h\\ %C(green)%ad%Cred%d\\ %Creset%s%Cblue\\ %C(dim white)%cn(reset)' --decorate --date=short --graph
	l3 = log --pretty=format:"%C(green)%h \\ %C(yellow)[%ad]%Cred%d \\ %Creset%s%Cblue \\ [%cn]" --decorate --date=relative

	[user]
	name = Your Name
	email = your@email.com

	[core]
	longpaths = true
	packedGitLimit = 1024m
	packedGitWindowSize = 1024m
	autocrlf = true

	[pack]
	deltaCacheSize = 512m
	packSizeLimit = 512m
	windowMemory = 1024m


## i2c programming commands

- sudo apt-get install i2c-tools
- i2cdetect -y 1
- https://github.com/mheidenreich/LCDDemo/
- https://www.youtube.com/watch?v=DHbLBTRpTWM
- sudo pip3 install rpi_lcd
- https://www.circuitbasics.com/raspberry-pi-lcd-set-up-and-programming-in-python/

_

---


# Pycharm
To enable/disable inlay hints go to `settings`->`Editor`->`Code Style`->`Inlay Hints`
- These are the inline hints that can be useful or not


---


## 3d Printing

- Q: What are the PID tuning commands?
- A:
  - `PID_CALIBRATE HEATER=heater_bed extruder=215`
  - `PID_CALIBRATE HEATER=heater_bed TARGET=55`

## General FAQ

Q: How do I add my conda environment to jupyter?

A: ipython kernel install --user --name=[YourCondaEnvName]


Q: packages required for i2c programming

A: asdf


`python -c 'import torch;print(torch.cuda.device_count())'`conda config --set auto_activate_base false
