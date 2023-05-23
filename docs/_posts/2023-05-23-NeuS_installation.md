---
layout: post
title: "Neus installation"
---
# Neus installation
## Intro 
I notesed that I using comments in pull/issues like my blogs/logs, so it's better that I will be just writing here.  
So this is the process of installing [NeuS](https://github.com/jenkspt/NeuS)

### Install cnpy
```
git clone https://github.com/rogersce/cnpy
cd cnpy/
mkdir build
cd build
mkdir ../install-dir
cmake ../ -DCMAKE_INSTALL_PREFIX=../install-dir
make
make install
```

### Install opencv

```
mkdir opencv && cd opencv 
# Get opencv source files 
wget -O opencv.zip https://github.com/opencv/opencv/archive/refs/tags/4.6.0.zip
unzip opencv.zip
# Create build directory
mkdir -p build && cd build
# Configure
cmake  ../opencv-4.6.0
# Build
cmake --build .
```
modifided code from [here](https://docs.opencv.org/4.x/d7/d9f/tutorial_linux_install.html)
