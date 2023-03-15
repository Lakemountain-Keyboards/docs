---
layout: post
title: "OLED Display"
data: 2023-03-15 +0100
categories: [PCB]
tags: [PCB, OLED]
---

Another silly feature of the side connector expansion port is connecting a small
display. This could be somewhat useful to show current layer or configuration of
the keyboard for example. I however like the more silly applications like
displaying a bongo cat that reacts to your wpm. The WPM is just a rolling
average of the key presses and the cat animation frames i found on [github](https://github.com/nwii/oledbongocat).

<video muted controls loop autoplay width="480">
    <source src="../../assets/img/230315/IMG_1788.MP4" type="video/mp4">
</video>

This is using a [128x64 OLED LCD](https://www.electrokit.com/produkt/lcd-oled-0-96-128x64/)
connected via I2C. It's good to see that I can use I2C over the side connector
as well. My other pointing devices have been connected via the same connector
but to other pins talking SPI instead. So my IO MUX works!
