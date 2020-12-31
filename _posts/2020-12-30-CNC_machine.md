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

#### Limit Switches
![Limit Switches wiring](https://wiki.shapeoko.com/images/1/1c/Generichomeswitches.png)

![Multiple limit Switches wiring](https://forum.shapeoko.com/download/file.php?id=1322)

### Linux CNC
[This video](https://www.youtube.com/watch?v=F4xHCwtaS3w) is helpful in getting setup with [Linux CNC](https://linuxcnc.org/docs/2.8/html/)

I got a result of 26125 ns on the base thread from the Linux latency test.

This [steps per mm calculator](https://blog.prusaprinters.org/calculator_3416/#stepspermmlead) is useful for configuring LinuxCnc.

### CAD
I use Solidworks, an alternative might be [freecad](https://www.freecadweb.org/), since it has CAM built in. Fusion360 also has built in CAM, apparently. [Onshape](https://www.onshape.com/en/products/free) looks like a good option, it has a free version for openSource hobbyists and integrates with [kiri](https://www.youtube.com/watch?v=AbbZjj5FMGE).

### CAM
CAM programs take your CAD model and, together with information such as bit size, material being cut, etc, use it to create g-code. CAM is probably the biggest issue in this whole workflow. There is a distinct lack of options. There is a [wiki](https://wiki.shapeoko.com/index.php/CAM) which has some potential options. This [toolchain wizard](https://sienci.com/dmx-longmill/choosing-software/) is a helpful tool for some of the options.

From my reading, the options are, in order of preference below.

#### 2D 
* [ESTLCAM](https://www.estlcam.de/index.php) - $59, but you can download an [older version](https://www.estlcam.de/changelog.php)
* [CAMLAB](http://camlab.sienci.com/camlab) and [Kiri](https://grid.space/kiri/), some [starter tutorial](https://www.youtube.com/watch?v=KDhMujKX1QQ) - Free
* [bCNC](https://github.com/vlachoudis/bCNC) - free
* [DXF2Gcode](https://sourceforge.net/projects/dxf2gcode/) - Free!
* [MakerCAM](https://wiki.shapeoko.com/index.php/MakerCAM), [Github](https://github.com/shapeoko/makercam), [basic tutorial](https://www.makercam.com/tutorial.html) - Free
* [Easel](https://www.inventables.com/technologies/easel) - Free, very basic but easy to use.
* [OpenBuildsCAM](https://cam.openbuilds.com/#) - Free, but doesnt work very well with DXF
* [Carbide Create](https://carbide3d.com/carbidecreate/) - Free, but doesnt work very well with DXF
* [Web based](https://cam.openbuilds.com/#) and [this](https://cnc.js.org/) - Free
* [PathCam](https://github.com/xenovacivus/PathCAM) - free, didnt work with solidworks STL

EstlCam or CamLab/Kiri.

#### 3D
* [MeshCam](http://www.grzsoftware.com/) - $250
* [VCarve](https://www.vectric.com/products) - $400
* [HSMWorks](https://www.autodesk.com/products/hsmworks/overview?plc=F360&term=1-YEAR&support=ADVANCED&quantity=1) CAM addon for Solidworks - $495 per year
* [Freemill plugin for Solidworks](https://mecsoft.com/freemill-for-solidworks-free-cam-software-in-solidworks/) - upwards of $600, depending on version
* [CamBam](http://www.cambam.info/downloads/) - $150, but you can download an older version
* [PyCam](http://pycam.sourceforge.net/) - linux only at the moment - Free

Cambam or meshcam, based on price.

### Alternatives

#### Buy
Expensive, but at least they do the job, some include software for toolchain from CAD to gCode.

* [Bantam desktop machine](https://www.bantamtools.com/machines/desktop-cnc-milling-machine) - $3 600
* [ShopBot desktop machine](https://www.shopbottools.com/products/desktop) - $7 600
* [Carbide3d Nomad desktop cnc](https://shop.carbide3d.com/collections/machines/products/nomad-3?variant=32912906289213) - $2 800
* [Cheap milling machine](https://www.adendorff.co.za/product/mac-afric-mini-drillingmilling-machine/) and [CNC conversion kit](https://www.mbbilici.com/index.php?route=product/product&path=57&product_id=63), like [this](https://youtu.be/OY5VUsJ2Gu4) - approx $1 600
* [Openbuilds-c-beam-machine](https://openbuildspartstore.com/openbuilds-c-beam-machine/) - $700
* [Openbuilds mini mill](https://openbuildspartstore.com/openbuilds-minimill/) - $550
* [Bulkman mini mill rip off](https://bulkman3d.com/product/mn01/) - $200
* [Bulkman c-beam rip off](https://bulkman3d.com/product/cbxl01/) - $233

#### Build
Noise, dust, frustration! Not to be understestimated! Making something stiff, square and repeatable is not a small task. The smaller, the better here; both for stiffness and to build an enclosure. 

To be honest, unless you already have access to precision tools, it may be better to build your own lasercutter or plasma cutter instead. In order of preference:

* Cast from [epoxy granite](https://youtu.be/4aBVAbfxLJw?t=491) - at least this allows for taking your time making a mould and making sure its all square. Once its set, no take backsies though! [Here](https://youtu.be/2woA1BxZ7Pg) and [here](https://www.model-engineer.co.uk/forums/postings.asp?th=139042). Will also need quality components.
* Weld a steel frame. You will need to spend much time grinding and lapping to make it flat and much time making it square. Will probably require [granite parallels](https://www.starrett.com/category/precision-measuring-tools/granite-parallels/130207#currentPage=1&displayMode=grid&itemsPerPage=12&sortBy=wp/asc)
* Aluminium extrusion frame - these are the most accessible and there are [plenty designs](https://openbuilds.com/) out there. The few which I have tried have been almost commically flexible when milling material, so design needs to be bulletProof. Perhaps, these designs are worth considering: [here](https://wikifactory.com/+mekanika/mekanika-cnc-router) and [here](https://bulkman3d.com/product/queenbee-pro-cnc-machine-mechanical-kit-upgrade-kit/) or [here](https://gitlab.cba.mit.edu/jakeread/clank)

### Dust Shoe
Milling is extremely messy. A dust shoe is a necessity and a split one seems like a good idea.
![Split dust shoe example design](https://static.wixstatic.com/media/bdcd45_a70767520fc2499bbd0daf5a66e4c5bb~mv2.png/v1/fill/w_551,h_551,al_c,q_90,usm_0.66_1.00_0.01/bdcd45_a70767520fc2499bbd0daf5a66e4c5bb~mv2.webp)