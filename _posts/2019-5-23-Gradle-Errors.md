---
layout: post
title: Finding Gradle Errors
tags: gotchas Software Gradle Android Studio
---

Recently, I had an issue where my Android Studio build was failing with warnings, but no errors being shown in the build display.

A nice trick is to run the build command from the command line, in order to get more verbose error logging. Navigate to the project folder containing the Bradley folder. 

Then, on a Mac:

```
./gradlew assembleBuild
```

or


```
./gradlew build --stacktrace
```