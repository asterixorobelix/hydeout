---
layout: post
title: Android dev!
tags: software Android
category: Software
---
![Android](https://img.favpng.com/5/10/23/android-logo-icon-png-favpng-Uv2JWf9XFEXampUMn5wPsbLHz.jpg)

Just noting down some useful things for Android Dev

### Linting ###

### Jitpack ###
If you are going to create your own Android Libraries, then you can use [Jitpack](https://jitpack.io) to build your library, so that you can pull it in as a Gradle ``implementation`` dependency. It works best with Github, especially now that they have free private repos. If you want Jitpack to build private repos, you need to pay for that service.

### Dependency injection ###
* [Koin](https://github.com/InsertKoinIO/koin)

### Putting your money where your mouth is ###
The following things are worth paying for:
* [Gitkraken](https://www.gitkraken.com/)
* [Jitpack](https://jitpack.io)
* [Cool logo generator!](https://looka.com/)

### PNG to SVG ###
* [Online converter](https://onlineconvertfree.com/convert-format/png-to-svg/)

## Kotlin MultiPlatform
There is Kotlin Multiplatform (KMP) and [Kotlin MultiPlaform Mobile (KMM)](https://kotlinlang.org/lp/mobile/), which is of interest as an alternative to cross platform systems to share code between iOS and Android. Choosing between KMM and Flutter is actually a difficult choice at the moment, although their approaches are entirely different. 

Some things to note:
* KMP is deeply experimental at this time of writing and the documentation is also not the best
* The Kotlin code is compiled into an Objective-C Framework for iOS consumption, so now you need to know Kotlin, Swift and Objective-C
* Implementing the iOS UI natively may be non trivial, particularly if the design is complex.

### Getting started
I found it helpful to watch this video by [Kevin Galligan](https://www.droidcon.com/media-detail?video=481183953) and [Ellen Shapiro](https://www.youtube.com/watch?v=JHUY1Ckmo64).
A reading list of interesting stuff to get you started is [here](https://www.one-tab.com/page/97BSLOTrQveaEj5eW33lEA)