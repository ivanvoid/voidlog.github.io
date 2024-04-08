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
```sudo apt install g++ freeglut3-dev build-essential libx11-dev libxmu-dev libxi-dev libglu1-mesa libglu1-mesa-dev```  

```
sudo add-apt-repository ppa:graphics-drivers/ppa
sudo apt update
```

Check recomended driver:  
```ubuntu-drivers devices```  

Install drivers:  
```sudo apt install libnvidia-common-<branch> libnvidia-gl-<branch> nvidia-driver-<branch> -y```  
For me `nvidia-driver-545` recomended, replaceing brunch with recomended version:  
```sudo apt install libnvidia-common-545 libnvidia-gl-545 nvidia-driver-545 -y```  



## Installing CUDA-toolkit



  
  
