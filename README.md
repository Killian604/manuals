.# Manuals -- FAQ


`huggingface-cli download meta-llama/Meta-Llama-3.1-8B-Instruct  --repo-type model --local-dir ./models/Meta-Llama-3.1-8B-Instruct/ --token $HFTOKEN  --exclude="*consolidate*"`


# vLLM
Example command: `vllm serve  ./NousResearch_Hermes-3-Llama-3.1-8B/ --gpu_memory_utilization=0.9 --max_model_len=40000`

`vllm serve` routes
Available routes are:
INFO 09-14 11:23:04 launcher.py:28] Route: /openapi.json, Methods: GET, HEAD
INFO 09-14 11:23:04 launcher.py:28] Route: /docs, Methods: GET, HEAD
INFO 09-14 11:23:04 launcher.py:28] Route: /docs/oauth2-redirect, Methods: GET, HEAD
INFO 09-14 11:23:04 launcher.py:28] Route: /redoc, Methods: GET, HEAD
INFO 09-14 11:23:04 launcher.py:28] Route: /health, Methods: GET
INFO 09-14 11:23:04 launcher.py:28] Route: /tokenize, Methods: POST
INFO 09-14 11:23:04 launcher.py:28] Route: /detokenize, Methods: POST
INFO 09-14 11:23:04 launcher.py:28] Route: /v1/models, Methods: GET
INFO 09-14 11:23:04 launcher.py:28] Route: /version, Methods: GET
INFO 09-14 11:23:04 launcher.py:28] Route: /v1/chat/completions, Methods: POST
INFO 09-14 11:23:04 launcher.py:28] Route: /v1/completions, Methods: POST
INFO 09-14 11:23:04 launcher.py:28] Route: /v1/embeddings, Methods: POST



# ollama
- Show available models: `ollama list`
- Pull new model: `ollama pull [MODELNAME]`
  - E.g. `ollama pull llama3.1:8b-instruct-fp16`
- Boot: `ollama run [MODELNAME]`
- - E.g. `ollama run llama3.1:8b-instruct-fp16`

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


# Numpy


## Visualizing segmented image results

```python
n_classes = 20
inputdata_B_C_H_W = torch.randn(1, 3, 520, 720)
out_b_cl_h_w = model(inputdata_B_C_H_W)
predicted_classes_HW = torch.argmax(out_b_cl_h_w.squeeze(0), dim=0).cpu().numpy()  # Shape (H,W) with class value at every idx
randomcolors_cl_RGB = np.random.randint(0, 255, size=(n_classes, 3))  # Shape (N_Classes, 3)
segmented_mask_colourized = randomcolors_cl_RGB[predicted_classes_HW]  # (CL, 3)[H,W]=>(H,W,3)
```

# Pycharm
To enable/disable inlay hints go to `settings`->`Editor`->`Code Style`->`Inlay Hints`
- These are the inline hints that can be useful or not


---


## 3d Printing

- Q: What are the PID tuning commands?
- A:
  - `PID_CALIBRATE HEATER=heater_bed extruder=215`
  - `PID_CALIBRATE HEATER=heater_bed TARGET=55`


    Line width for supports (in Quality settings): 'Around 50%' of what your main line width is (eg: set it to 0.25mm on a 0.4mm nozzle printing at 0.42mm line width) - THIS IS A KEY SETTING - UPDATE For 0.2mm nozzles do not change this setting it's already good and setting it any thinner will cause issues!
    Type: Tree (auto) - (I use this on average but it depends on the model so experiment with each type depending on your needs)
    Style: Tree Organic or Slim - (I use these on average but it depends on the model so experiment with each type depending on your needs)
    Top Z distance: 0.25mm
    Bottom Z distance: 0.2mm
    Base pattern spacing: 2.5mm
    Base Pattern: Hollow. - THIS IS A KEY SETTING
    Top interface layers: 3
    Bottom interface layers: 2
    Top interface spacing: 0.7mm

Additional settings I always use for print stability and avoiding warping, especially for longer-length prints or that are located on build plate edges. The brim keeps the print stable and comes off super easily

    Brim type: Outer brim only
    Brim width: 3mm
    Brim-object gap: 0.3mm


## Nordvpn

- Adding local network to whitelist: `nordvpn whitelist add subnet 192.168.0.0/24`

## General FAQ

Q: How do I add my conda environment to jupyter?

A: ipython kernel install --user --name=[YourCondaEnvName]


Q: packages required for i2c programming

A: asdf

Q: What about [internet cxn that takes too long]?

A: https://www.reddit.com/r/HomeServer/comments/1fmwgeh/why_does_this_take_so_long/



`python -c 'import torch;print(torch.cuda.device_count())'`conda config --set auto_activate_base false



# SD
https://github.com/lllyasviel/stable-diffusion-webui-forge/issues/1075


# VNC
`vncserver :1`
`vncserver :1 -geometry 1920x1080 -depth 24`
`vncserver -kill :1`
`nano ~/.vnc/xstartup`
`vncpasswd`
