---
layout: post
title: "How to configure and upload ferris/sweep fireware"
---
# How to configure and upload ferris/sweep fireware


My keymap: [keymap.json](https://github.com/veax-void/justdevblog.github.io/blob/master/sources/ferris_sweep_layout_split_3x5_2_sps.json)  
My keyboard: [pics](https://www.reddit.com/r/olkb/comments/sn708r/made_my_ferris_sweep_on_qmk/)

## Linux
1. Go to the https://config.qmk.fm and select ferris/sweep or just upload your_keymap_name.json
2. Download your_keymap_name.json file
3. Put your_keymap_name.json file to `./qmk_firmware/keyboards/ferris/keymaps/sps/your_keymap_name.json`
4. In this folder(sps) run: `$ qmk json2c your_keymap_name.json >> keymap.c`
6. From `~/qmk_firmware` run: `make ferris/sweep:sps:avrdude-split-right` while right side conected (don't forget to shorten reset with ground)
7. From `~/qmk_firmware` run: `make ferris/sweep:sps:avrdude-split-left` while left side conected   p


Done, now everything must be ready.


## Windows
1. Go to the https://config.qmk.fm and select ferris/sweep or just upload your_keymap_name.json
2. Press 'Compile' 
3. After compolation is finished, press 'Firware' to download .hex file
4. Then upload .hex file to qmk-toolkit and flash it on the board

  
