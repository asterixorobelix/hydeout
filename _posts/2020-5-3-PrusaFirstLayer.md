---
layout: post
title: Prusa Mk3 first layer
tags: 3dPrinting
category: Machines
---
I've been struggling with my prints where the first few layers have not been sticking to the bed very well. Thankfully, I came across these two helpful posts on the matter [Thomas Sanladerer](https://www.youtube.com/watch?v=AaF28dnDgKA) and [Maker's muse](https://www.youtube.com/watch?v=ShFaJ027pFs). Basically, use some glue on the print bed and reduce speed and increase filament flow for the first few layers of print.

I also discovered that I was orders of magnitude off how much the nozzle needs to be smooshed into the bed. [This post](https://forum.prusaprinters.org/forum/original-prusa-i3-mk3s-mk3-assembly-and-first-prints-troubleshooting/life-adjust-z-my-way/) made it clear that the live z offset setting should be around -0.5 and -0.7 mm, which is way off what I was doing!. For calibration, I found that [this pattern](https://www.thingiverse.com/thing:3055929) worked much better than the built in one.  Potentially, [this one](https://www.youmagine.com/designs/bed-leveling-tramming-paralleling-test) could also be useful. [This post](https://projects.ttlexceeded.com/3dprinting_mk3_live_z_calibration.html#mk3-live-z-calibration-procedure), [this Prusa post was also helpful](https://help.prusa3d.com/en/article/first-layer-calibration_112364).

[This](https://pcboy.github.io/g81_relative/) can also be helpful with making the relative flatness is good with the [Nylock mod](https://www.reddit.com/r/prusa3d/comments/bp440f/full_guide_to_doing_nylock_mod_if_you_havent_you/).

In the end, what seemed to help the most was changing settings in the [PrusaSlicer](https://www.prusa3d.com/prusaslicer/). In the end, what seemed to help the most was simply changing the first layer height, width and print speed. I started with the 0.2mm Quality print settings, modified first layer height to be 0.4mm, made first layer speed 10 mm/s and first layer width of 0.72 mm.

![example first layers](https://forum.prusaprinters.org/wp-content/uploads/attachments/4570-22992-20170116-223130.jpg)