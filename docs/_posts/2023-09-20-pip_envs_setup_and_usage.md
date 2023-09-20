---
layout: post
title: "pip environments. Setup and usage"
---

# Intro
All the information taken from [python docs](https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments/).

This guide for setting up the pip env and using it efficiently for deep learning.
I'm writing this guide because if you will follow docs, you can encounter errors that they don't explain how to solve. 
Some of the parts are actually outdated (like `python3 -m venv env` just doesn't work for me).

# Creating environment
## Setiing pip and virtualenv
```
sudo apt install python3-pip
python3 -m pip install --user --upgrade pip

# Install virtual envaroment
python3 -m pip install --user virtualenv
sudo apt install python3-venv

# Write virtualenv location in bashrc
echo 'export PATH="$PATH:/home/ivan/.local/bin"' >> ~/.bashrc
source ~/.bashrc

```
## Create env
```
# Create env
virtualenv env

# Activate env
source env/bin/activate

# Deactivate env
deactivate
```

## Setting up env in VSC
CTRL+SHIFT+P -> Python: Select Interpreter -> Enter interpreter path.. -> FInd...
select your_env/bin/python as your interpretator. 




