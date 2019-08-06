---
layout: post
title: Android Adaptive Launcher Icons
tags: Software Android
---
Android 8.0 (API level 26) introduces adaptive launcher icons, which can display a variety of shapes across different device models. For example, an adaptive launcher icon can display a circular shape on one OEM device, and display a squircle (square circle) on another device.

![Adaptive Icon](https://developer.android.com/guide/practices/ui_guidelines/images/NB_Icon_Mask_Shapes_Ext_02.gif)

If you haven't updated your app, the launcher icon can all of a sudden look rather bad.
![Adaptive Icon](https://cdn-images-1.medium.com/max/1600/1*pK3VrY7GMQ2bGylStOLnYg.png)

## Making adaptive launcher icons

Basically, you still specify the png images, but the OS will prefer launcher icons specified in xml with vectors. You can specify a foreground and background or just one of those. Specifying both would allow the background colour to take on different shapes, while the foreground stays constant with app branding.

```
<adaptive-icon xmlns:android="http://schemas.android.com/apk/res/android">
    <background android:drawable="@drawable/ic_launcher_background" />
    <foreground android:drawable="@drawable/ic_launcher_foreground" />
</adaptive-icon>
```

![Example manifest](https://drive.google.com/uc?export=view&id=15oPCWvcyyBC4q-KN7nq5OHkZ8VK5ntZY)

![Android Vector](https://drive.google.com/uc?export=view&id=1B4XXidfI3dsWQvacwDQPrc1VA3039G_t)

## Useful Websites

* [Launch Icon creator](https://jgilfelt.github.io/AndroidAssetStudio/icons-launcher.html)
* [Png to svg converter](https://www.pngtosvg.com/)
* [Free SVG to android vector converter](https://inloop.github.io/svg2android/)
* [Paid SVG to android vector converter](https://svg2vector.com/)


![Android Vector](https://drive.google.com/uc?export=view&id=1DWXez0FhTjSxRqvgjqPncTyNWkrtUEFn)
