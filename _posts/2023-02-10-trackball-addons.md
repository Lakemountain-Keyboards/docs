---
layout: post
title: "Trackball Addons"
data: 2023-02-10 +0100
img_path: /assets/img/
categories: [Modules]
tags: [LS65, Trackball, Trackpad]
---
Even though I never actually finished one of the thumb extensions using the side port on the LS65, I had several working prototypes. The main reason for never actually using them is the flash size limit and performance of the atmega32u4 which was really lacking.

## PMW3389 based trackball
I have experimented with the [pmw3389](https://www.tindie.com/products/jkicklighter/pmw3389-motion-sensor/) and that worked pretty well so I think I will try to use that one for a module on my next keyboard adventure. I never actually connected this one to the LS65 though. The module as a SPI interface meaning I could not directly connect it to the side port of the LS65 which only has i2c. I looked into connecting it to a separate atmega32u4 and talk to that over the i2c bus but qmk is not really supportive of 3-split keyboard communication so that would require some larger modifications to the i2c transport layer of qmk.
There are qmk based keyboards that have actually already done something like this though. For example the [DC01](https://mechboards.co.uk/products/mbuk-dc-01) that is very cool and does a lot of want I wanted to do with the LS65. Even though I still think it is cool, I think it is a bit of a gimmick to be able to hot swap and reconfigure on the fly so until qmk has better official support for multi-split keyboards I will just build "static" modules.

![pmw3389](pmw3389.png)

## Cirque trackpad
I also played around with the small [cirque](https://www.cirque.com/glidepoint-circle-trackpads) trackpads. I only ran them on a separate atmega32u4 based mcu running qmk but never got them fully stable. Most of the time the trackpad worked well but every few seconds the mouse point would spass out making it unusable. Without much debugging of why this happened my guess was because of the atmega32u4 and slow i2c clock. I'll give this a go again with the stm32 in the future.

![cirque](cirque.png)  
 
## Pimoroni trackball
Here is a video of me experimenting with the [pimoroni trackball](https://shop.pimoroni.com/products/trackball-breakout). It doesn't actually show me using the trackball (which did work) but only playing with the RGB underglow lighting in combination with the one in the trackball.

<!-- <video muted controls>
    <source src="../../../assets/img/keyboard/IMG_0616.mp4" type="video/mp4">
</video> -->
