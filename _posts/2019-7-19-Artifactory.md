---
layout: post
title: Use Artifactory for private library archiving
tags: Artifactory Gradle
---
I have recently started developing my own Kotlin libraries. I wanted a nice way of managing these library artifacts. [Jeroen Mols](https://jeroenmols.com/blog/2015/08/06/artifactory/) has a nice discussion of how to push Gradle builds to your own locally hosted [Artifactory](https://jfrog.com/artifactory/) server (which can all be done for free).

The Artifactory wiki has [instructions on how to install Artifactory for a mac](https://www.jfrog.com/confluence/display/RTF/Installing+on+Linux+Solaris+or+Mac+OS), but I found that they weren't very good. So, I decide to [install using Docker](https://www.jfrog.com/confluence/display/RTF/Installing+with+Docker) instead. [Installing docker](https://docs.docker.com/v17.12/docker-for-mac/install/#install-and-run-docker-for-mac) is pretty easy, once installed you can run docker commands from the mac command line.

You can then pull the artifactory docker image with: ```docker pull docker.bintray.io/jfrog/artifactory-oss:latest```

You then run Artifactory in the docker container with: ```docker run --name artifactory -d -p 8081:8081 docker.bintray.io/jfrog/artifactory-oss:latest```

You can then open a browser in order to see the Artifactory UI:
![Artifactory landing](https://drive.google.com/uc?export=view&id=1kqDzIwtvb6AWZOt7FZ4m9Zm9QEaqxEP6)

Place this at the top of your build.gradle (there should be no lines above this):
```
buildscript {
    dependencies {
        classpath "org.jfrog.buildinfo:build-info-extractor-gradle:4.9.7"
    }
}
```

You then need to configure Gradle to upload your library to Artifactory. [Jeroen's guide](https://jeroenmols.com/blog/2015/08/06/artifactory/) assumes that you are building an Android library.

I'm building a kotlin library with Intellij Idea, so one needs to deviate slightly from his instructions.
The publishing field in your build.gradle needs to look like this:

```
publishing {
    publications {
        aar(MavenPublication) {
            groupId packageName
            version = libraryVersion
            artifactId project.getName()

            // Tell maven to prepare the generated "*.aar" file for publishing
            artifact("$buildDir/libs/${project.getName()}.jar")
        }
    }
}
```

You should then be able to write the following command in the command line:
``` gradle build artifactoryPublish ```

if successful, you can refresh the locally hosted artifactory website and see your artifact there.

Jeroen also covers some more [advanced Artifactory customizations](https://jeroenmols.com/blog/2015/08/13/artifactory2/), which is also worth a read.