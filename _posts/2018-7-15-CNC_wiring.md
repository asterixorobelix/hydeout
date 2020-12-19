---
layout: post
title: CNC machine
tags: CNC hardware electronics
category: Machines
---
### Wiring
I've been struggling to work out the wiring for the [TB6560 stepper motor driver](https://www.diyelectronics.co.za/store/stepper-motor-drivers/1393-tb6560-stepper-motor-driver.html) and the [Mach3 parallel port breakout board](http://www.communica.co.za/catalog/Details/P3942944907).

Now that I have figured it out, I figured that I would share a schematic for all posterity.
![Wiring diagram image](https://drive.google.com/uc?export=view&id=14QUk2w_1RywGVUqnTGJyKSLMWa8E6o1o)

![Mach3 breakout board](https://drive.google.com/uc?export=view&id=1zbJ_lkMZAB2Chat0t6-mVzk2WIW2ICWt)

How to wire up the extras
![extras](https://drive.google.com/uc?export=view&id=0B822K1X9crfFQUIzcGc1NFkzOFk)

How to wire up the TB6560 stepper driver
![TB6560](https://drive.google.com/uc?export=view&id=0B822K1X9crfFMjRSX0hLY0d1NEE)

About the [breakout board](https://youtu.be/0D2uYMVrglw)
How to [test the parallel port](https://youtu.be/uglCm_qsojk)

### Linux CNC
[This video](https://www.youtube.com/watch?v=F4xHCwtaS3w) is helpful in getting setup with [Linux CNC](https://linuxcnc.org/docs/2.8/html/)

I got a result of 26125 ns on the base thread from the Linux latency test.

This [steps per mm calculator](https://blog.prusaprinters.org/calculator_3416/#stepspermmlead) is useful for configuring LinuxCnc.

### CAD
I use Solidworks

### CAM
* [CamBam](http://www.cambam.info/downloads/) - $150
* [MeshCam](http://www.grzsoftware.com/) -$250
