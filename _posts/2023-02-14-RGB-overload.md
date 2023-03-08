---
layout: post
title: "RGB Overload! Actually probably..."
data: 2023-02-14 +0100
categories: [PCB]
tags: [RGB, sk6812, sk6805, schematic]
math: true
---

Next problem!

Adding per-key `sk6812` LEDs will amount to ~70 LEDs total combined over both halves. In the 65% configuration there is 31 on the left half and 42 on the right half.
Additionally there is the idea to add side facing underglow LEDs which would add even more.

Since these individually addressable LEDs are notorious to be power hungry there is a very real possibility to hit the USB power limit of 500mA.

The current draw of an `sk6812` is 12mA as indicated by the last two digits of the product number.

$$ I_{max} = 73*12 = 876 mA $$

So this doesn't sound possible... I have however seen multiple keyboards using >80 of these LEDs for per-key illumination so it might work anyways. The 12mA should correspont to max brightness at white setting, R, G and B maxed out and this could at least be avoided.

---
## Solutions

### External RGB controller
The recommended way to reduce power draw but keeping per key RGB is to use a separate RGB controller like the `IS31FL3731`. These will drive and control a matrix of RGB LEDs connected similarly to how the key-matrix is connected. The matrix can then be modulated to not power all LEDs at once and thus reduce the power draw. This however would be a huge pain when it comes to the PCB design and I really do want to avoid this.

### SK6805
Both the `sk6812mini-e` and `sk6812side` are available in `05` versions instead, meaning a current draw of 5mA instead of 12mA. This would reduce the power draw by more than half. The drawback of course would be less intensity in the LEDs.

$$ I_{max} = 73*5 = 365 mA $$

This sounds more reasonable and will probably be the way to go if the `sk6812` version doesn't work out. I can also mix and match if I want, for example the underglow LEDs could be the 12mA and the backlight 5mA.

---
## Preventing disaster

The first very simple preventive measure is to add decently large capacitors for the LEDs, which hopefully will help the board survive power spikes, for example when powering on the LEDs.

When adding the side-facing underglow LEDs to the design I at first integrated them into the already existing series of LEDs. I software I could afterwards define the order of each LED to make animations behave as expected. However I decided to add these as a separate loop at and connect them to the end of the other LEDs. The reasoning behind this is simple. If I don't want to populate the underglow LEDs I wont have to patch the Din/Dout chain of the backlight LEDs.

![RGB-matrix-sch](/assets/img/RGB-matrix-sch.png)  

In the end, I guess I will just try the `sk6812` and see what happens. I should probably by a USB power tester so that I can do some easy measurements of the full design as well. If disaster strike, `sk6805` is the backup plan.
