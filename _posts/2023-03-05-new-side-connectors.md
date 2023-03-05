---
layout: post
title: "New side connectors"
data: 2023-03-05 +0100
categories: [PCB]
tags: [PCB, CAD]
---

After some thinking back and forth I decided to switch out the magnetic side connectors used by the LS65 for something else.
The main reasons for this was:
- The magnetic connectors were kind of expensive and I could only find them on Aliexpress which comes with additional import tax.
- With the split connection being a proprietary USART bus now, the side connector will no longer be able to transport the split keyboard communication. They will only be for SPI/I2C extensions or extension of the key matrix.
- With other stuff going through the side connectors, I don't want stuff to short when the halves are put together.

So what connector to replace it with? I just chose USB-C since it's a good connector and it's cheap. At first I was hesitant because the male plug side of an USB-C connector seemed hesitant to create extensions with since I couldn't find any easy to solder male plugs for it. All of the PCB mount versions of it needs thin PCBs and are solders around the edge of the PCB.
Luckily I found [these](https://www.tindie.com/products/arturo182/usb-type-c-plug-breakout-usb-20-only/) easy to solder breakouts by [SolderParty](https://www.solder.party/) as well ass [these](https://www.tindie.com/products/arturo182/usb-type-c-smt-plug-30-only-pack-of-5/) pack of plugs. They are even located in Sweden, perfect!

![usbc-breakout](/assets/img/220305/usbc-breakout.png)

Of course I didn't stop there and also decided to add another connector on the side. So in the end it's gonna look something like this.

![cad-side-conn](/assets/img/220305/cad-side-conn.png)

With these connectors I will be able to add extensions with Displays, keys, rotary encoders, trackballs etc.
If this works it would be kind of awesome. All of these things are already supported in QMK. Trackball and display just needs an SPI connection. The keys will need col/row pins and the encoders also just needs their own pins. I will not support all modules working on all extension ports, but I'm fine with this limitation.
![example](/assets/img/220305/extension-example.png)
