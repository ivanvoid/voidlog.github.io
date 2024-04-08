---
layout: post
title: "How to reinstall CUDA and keep your sanity."
---
# How to reinstall CUDA and keep your sanity, or installing CUDA.11.8 on Ubuntu 22.04.

## Gathering information
Before reinstall we need to know what parameters of our system are.

OS version: `Ubuntu 22.04.3LTS` 

Do we have Nvidia GPU?  
```lspci | grep -i nvidia```  
GPU: `01:00.0 VGA compatible controller: NVIDIA Corporation Device 24c9 (rev a1)`  
Correspond to `NVIDIA GeForce RTX 3060 Ti` with the GDDR6X memory  


## Removing garbage
This step requerd to clean previous instalations.
```
sudo apt purge nvidia* -y
sudo apt remove nvidia-* -y
sudo rm /etc/apt/sources.list.d/cuda*
sudo apt autoremove -y && sudo apt autoclean -y
sudo rm -rf /usr/local/cuda*

sudo apt update && sudo apt upgrade -y
```

## Installing Drivers

Mics packeges:  
```
sudo apt install g++ freeglut3-dev build-essential libx11-dev libxmu-dev libxi-dev libglu1-mesa libglu1-mesa-dev
```  

Go to 
[https://www.nvidia.com/Download/index.aspx?lang=en-us](https://www.nvidia.com/Download/index.aspx?lang=en-us)  
Grab your version of driver  
Make sure that gcc version is correct!!!   

Instalation:  
```
chmod -x Nvidia-Linux-x86_64-550.67.run
sudo sh Nvidia-Linux-x86_64-550.67.run
```

It will tell you any Errors at the end of `/var/log/nvidia-installer.log`
```
https://docs.nvidia.com/cuda/cuda-toolkit-release-notes/index.html
```

you can relink your gcc compiler:
```
sudo ln -s -f /usr/bin/gcc-12 /usr/bin/gcc
```

Run:
```
nvidia-smi
```
to make sure that drivers are installed correctly, it should display GPU data.


## Installing CUDA-toolkit

[https://developer.nvidia.com/cuda-downloads](https://developer.nvidia.com/cuda-downloads)

## Installing PyTorch

[https://pytorch.org/](https://pytorch.org/)

### Testing torch
```
python
>>>
import torch
torch.cuda.is_available()
>>> True # Output we want
```
  
  
