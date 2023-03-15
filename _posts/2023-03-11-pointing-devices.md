---
layout: post
title: "Pointing Devices"
data: 2023-03-11 +0100
categories: [hardware]
tags: [PCB, PMW3366, CIRQUE]
---

More testing of the new prototype, this time the side connector. The main thing
I will use the side connectors for is pointing devices. I've already talked
about this briefly in an earlier [post](../trackball-addons).

## Cirque Trackpad
---

The [cirque](https://www.cirque.com/glidepoint-circle-trackpads) GlidePoint
trackpads are small circular trackpads with an SPI/I2C interface. I've
experimented with them before on my old `atmega32u4` based keyboard but never
got a stable smooth experience using it. But oh boy with the `stm32` it was a
completely different experience. Connecting it to my new prototype PCB and
configuration for it in `QMK` was an easy and quick task. The touchpad feels
responsive and both scrolling and mouse movement is smooth. 

A feature I found that I didn't know about was the edge-based circular scrolling
you can enable with `POINTING_DEVICE_GESTURES_SCROLL_ENABLE` in `QMK`. This
allows you to scroll instead of moving the mouse just by starting with your
finger on the edge and then rotating.

Here's a video of me using it, sorry for the bad angle, it was hard to get both
the screen and trackpad in the picture. Also the trackpad module was moving
around making it harder to use.

<video muted loop autoplay width="480">
    <source src="../../assets/img/230311/IMG_1784.MP4" type="video/mp4">
</video>

## PMW3360 based trackball
---
I also connected a `PMW3360` based trackball module I build over a year ago.
This worked just as well as the trackpad. The ball is a small billiards ball
sitting on three ball bearings in a 3D printed holder.

To do scrolling with this one you can just bind another key that you hold to
momentarily do scrolling in stead of movement. 

Here it is, obviously not connected at the moment.
![pmw3360](/assets/img/230311/IMG_1786.JPEG)

## Connector MUX
---
For the side connector I added a `IO Mux` which allows me to select what to output
on the limited number of pins I have on the connector. This way I can select
between `SPI` or key-matrix pins being exposed on the connector. With the testing
I did today using pointing devices I have verified that the `MUX` works as
expected which is great. By connecting the select pins of the `MUX` to the `MCU` I
could of course also control this at runtime.

![](/assets/img/230311/20230311184825.png)
