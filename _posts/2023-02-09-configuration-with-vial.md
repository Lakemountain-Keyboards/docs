---
layout: post
title: "Configuration with Vial"
data: 2023-02-09 +0100
img_path: /assets/img/
categories: [Configuration]
tags: [Vial, VIA, LS65]
---
The lakemountain keyboards can be configured using [Vial](https://get.vial.today/) (or [VIA](https://www.caniusevia.com/)), meaning that you don't have to reflash you keyboard to change the keymap.

What is really handy is that vial is available as a web application! Just head over to vial.rocks and you will be prompted to connect your keyboard.
![vial_url](vial_url.png)

After connecting you will be able to change your keymap on the fly with this GUI.
![vial_configuration](vial_configuration.png)

It seems like the web version of via is missing functionality to save/load your configuration to/from a file. If you want to use this you have to download the application form [their website](https://get.vial.today/)

#### Why not VIA
If you have use a QMK based keyboard before, you might have used (VIA)[https://www.caniusevia.com/]. Since this was not at the time open source and had some limitations, the LS65 used the open source version vial instead. I think however there have been some changes to how VIA handles custom keyboard configurations and they have also a web assembly version now, so for the next version of the lakemountain keyboard, I will have to look into if this is the better alternative now.
