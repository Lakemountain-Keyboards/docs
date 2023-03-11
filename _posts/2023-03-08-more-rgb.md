---
layout: post
title: "More RGB"
data: 2023-03-06 +0100
categories: [PCB]
tags: [PCB, RGB, VIA]
---

I might have been a bit too quick to reject the south-facing LEDs. I realized
that in my experiments I didn't mount the aluminum top plate, which of course
covers the direct LED flares I was annoyed by. This means that south facing
would work just fine.

I soldered on the full matrix and tested it mounted with
the top plate and keycaps and it look great! In the video I'm using transparent
switches which maximizes the brightness and spread of the illumination. When
using non transparent switches I think the light would not blend together as
much and the label on the keycap would not be as bright.
I still think I'll swap it around to north facing though just to make the labels
of the keycaps illuminate just a bit more.

<video muted controls loop autoplay width="480">
    <source src="../../assets/img/230308/recorded-2724684368886.MP4" type="video/mp4">
</video>

<video muted controls loop autoplay width="480">
    <source src="../../assets/img/230308/IMG_1779.mp4" type="video/mp4">
</video>

# VIA
---

Additionally I enabled VIA configuration on the board and tried that. Not fully configured for it yet but it works and makes it very easy to change illumination modes.
![via](/assets/img/230308/via.png)

# More derp
---

This is what prototypes are for, but I found another mistake. The alignment of the spacebar is wrong and does not match that of the top plate. It off by a `mm` which is enough to make the switch not fit. Quick fix, but very lucky that I found this!
