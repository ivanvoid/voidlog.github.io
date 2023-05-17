---
layout: post
title: "How to compile xeyes on Ubuntu"
---
# How to compile xeyes on Ubuntu

## Get source code of xeyes
`git clone https://gitlab.freedesktop.org/xorg/app/xeyes`

## Install next packages
```
sudo apt-get install libxt-dev
sudo apt-get install autoconf
sudo apt install xutils-dev
sudo apt-get install libxmu-dev
sudo apt install libxcb-damage0-dev libxcb-present-dev libxcb-xfixes0-dev libx11
-dev
sudo apt-get install -y libx11-xcb-dev
```

## Compile xeyes
```
cd xeyes
sh autogen.sh
make
```
