---
layout: post
title: CNC machine
tags: CNC hardware electronics
category: Machines
---
![Writing Image](https://drive.google.com/uc?export=view&id=17JBbc0t2IA4Nqgqf68PRvaYJb4fYev4o)

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
I use Solidworks, an alternative might be [freecad](https://www.freecadweb.org/), since it has CAM built in. Fusion360 also has built in CAM, apparently.

### CAM
CAM programs take your CAD model and, together with information such as bit size, material being cut, etc, use it to create g-code. CAM is probably the biggest issue in this whole workflow. There is a distinct lack of options. There is a [wiki](https://wiki.shapeoko.com/index.php/CAM) which has some potential options.

From my reading, the options are, in order of preference below.

#### 2D 
* [ESTLCAM](https://www.estlcam.de/index.php) - $59, but you can download an [older version](https://www.estlcam.de/changelog.php)
* [PathCam](https://github.com/xenovacivus/PathCAM) - free
* [CAMLAB](http://camlab.sienci.com/camlab) and [Kiri](https://grid.space/kiri/) - Free
* [bCNC](https://github.com/vlachoudis/bCNC) - free
* [DXF2Gcode]https://sourceforge.net/projects/dxf2gcode/ - Free!
* [Easel](https://www.inventables.com/technologies/easel) - Free, very basic but easy to use.
* [OpenBuildsCAM](https://cam.openbuilds.com/#) - Free, but doesnt work very well with DXF
* [Carbide Create](https://carbide3d.com/carbidecreate/) - Free, but doesnt work very well with DXF
* [Web based](https://cam.openbuilds.com/#) and [this](https://cnc.js.org/) - Free

#### 3D
* [MeshCam](http://www.grzsoftware.com/) - $250
* [HSMWorks](https://www.autodesk.com/products/hsmworks/overview?plc=F360&term=1-YEAR&support=ADVANCED&quantity=1) CAM addon for Solidworks - $495 per year
* [Freemill plugin for Solidworks](https://mecsoft.com/freemill-for-solidworks-free-cam-software-in-solidworks/) - upwards of $600, depending on version
* [CamBam](http://www.cambam.info/downloads/) - $150, but you can download an older version
* [PyCam](http://pycam.sourceforge.net/) -linux only at the moment - Free

### Alternatives

#### Buy
* [Bantam desktop machine](https://www.bantamtools.com/machines/desktop-cnc-milling-machine) - $3 600
* [ShopBot desktop machine](https://www.shopbottools.com/products/desktop) - $7 600
* [Carbide3d Nomad desktop cnc](https://shop.carbide3d.com/collections/machines/products/nomad-3?variant=32912906289213) - $2 800
* [Cheap milling machine](https://www.adendorff.co.za/product/mac-afric-mini-drillingmilling-machine/) and [CNC conversion kit](https://www.mbbilici.com/index.php?route=product/product&path=57&product_id=63) - approx $1 600 
