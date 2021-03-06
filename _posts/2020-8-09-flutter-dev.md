---
layout: post
title: Flutter dev!
tags: software Flutter
category: Software
---
![Flutter](https://www.becompany.ch/blog/assets/2019-06-17-creating-flutter-rss-reader/android_ios.png)

Just noting down some useful things for Flutter Dev

### Setup

The easiest setup on a mac uses [homebrew formula] (https://github.com/flschweiger/homebrew-flutter). Assuming you have already installed xCode and Android Studio, you are good to go in a few minutes!

### VS Code extensions

[Bracket colorizer](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer-2) and [pubSpec assist](https://marketplace.visualstudio.com/items?itemName=jeroen-meijer.pubspec-assist). There are also a bunch more listed [here](https://medium.com/flutter-community/must-have-vs-code-extensions-for-working-with-flutter-e31a421b9c68)

### CI/CD
[Codemagic](https://codemagic.io/start/) is a Flutter specific platform.

### Linting ###

### Jitpack ###
If you are going to create your own Android Libraries, then you can use [Jitpack](https://jitpack.io) to build your library, so that you can pull it in as a Gradle ``implementation`` dependency. It works best with Github, especially now that they have free private repos. If you want Jitpack to build private repos, you need to pay for that service.

### Dependency injection ###
I have been using [getIt](https://pub.dev/packages/get_it)

### App Store marketing material
[Previewed](https://previewed.app/) lets you make those professional banners.

### Semi colons
I find the Dart requirement for semi-colons at the end of every line pretty annoying, but making it optional seems to be a low priority. However, if you use intellijIdea for your flutter dev, you can [cmd+shft+enter](https://github.com/dart-lang/language/issues/69#issuecomment-629820487) and the semi colon will be auto-completed for you.

### Putting your money where your mouth is ###
The following things are worth paying for:
* [Gitkraken](https://www.gitkraken.com/)

### Reading List
* [State management](https://flutter.dev/docs/development/data-and-backend/state-mgmt/simple)
* [Popular flutter libs](https://medium.com/better-programming/the-10-best-and-most-liked-flutter-packages-f5813822e118)
* [layouts in Flutter](https://flutter.dev/docs/development/ui/layout#common-layout-widgets)
* [Flutter promoted libraries](https://pub.dev/flutter/favorites)
* [NoSQL Database - Hive](https://pub.dev/packages/hive)
* [MVVM example repo](https://github.com/scitbiz/flutter_pokedex)