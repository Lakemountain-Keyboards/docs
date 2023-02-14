---
layout: post
title: "Time for a new version. Again!"
data: 2023-02-08 +0100
categories: [PCB Design]
tags: [New, PCB, sk6812, stm32]
pin: true
---
I've gotten more requests from people at work that they want to build one of my keyboards. Even though I could order more PCBs for the LS65, I think it is time for an updated version.

The LS65 have been awesome to use as my daily driver for the last couple of years and my friends that build one still use them every day, so I guess they also like it.
There are however a few things that I would like to fix and have been requested by others.

### Hotswap sockets
This is something that I before though was just a waste of money but I have realized that it would be nice to be able to switch the keycaps without the tedious task of desoldering all of them, something I have done several times already... This is also the main request from new buyers.
This will require some small additions to the case design. Since the PCB is held up by being soldered to the switches in the LS65, no mounting screws for the PCB was needed and the bottom part of the case could be removed easily. I want to keep the design like that so instead I think i will add something holding the mounting plate and the PCB together.

![hotswap_sockets](/assets/img/hotswap_sockets.png)  

### Per key RGB LED
The LS65 had RGB backlight and single color individual LEDs in the keys. This was ok for the time but now with the sk6812mini-e LEDs that you can very easily design into your PCBs it is time for an upgrade.

![sk6812mini-e](/assets/img/sk6812/sk6812mini-e.png)


### ARM based MCU
The atmega32u4 in the LS65 have worked great but the limited flash memory blocks me from doing more updates and adding all the features I want. This has been the main reason the extension modules for the side ports of the LS65 have only been prototypes. The flash is too small to fit my whole layer configuration, mouse keys, VIA, etc. Adding for example a trackball extension on top of that is not possible at the moment.

For the new version I will most likely use the stm32f411 ARM based MCU. This is already supported in QMK but requires some design changes to the PCB and concept.
The whole idea of having one i2c bus connecting the keyboard halves and the extension modules is no longer possible because of limitations in the HAL layer used by qmk called ChibiOS. Unfortunately the I2C drivers cannot be used for split keyboards in QMK because of this. I will probably write another post about how I will solve this.

The current concept for the split keyboard with side connector extensions looks something like this. 
![new-keeb](/assets/img/split_concept.excalidraw.png)

A mux will allow the user to select if the side connector should output and i2c or spi bus, or if just some of the empty slots in the key matrix is output on the connector instaed which would allow for a completely passive module with a few switches to be connected.


### Current Status
So I've ordered a first prototype that tests some of these concepts. It looks something like this.

![new-keeb](/assets/img/keyboard/new-lakemountain-left.png)  

### And...
here is something cool to end this post with. An [interactive BOM](../../assets/new-left-ibom.html) of the new pcb layout!

<iframe src="../../assets/new-left-ibom.html" width="100%" height="500px"></iframe>
