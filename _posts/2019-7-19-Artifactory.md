---
layout: post
title: Use Artifactory for private library archiving
tags: Artifactory
---
I have recently started developing my own Kotlin libraries. I wanted a nice way of managing these library artifacts. [Jeroen Mols](https://jeroenmols.com/blog/2015/08/06/artifactory/) has a nice discussion of how to push Gradle builds to your own locally hosted [Artifactory](https://jfrog.com/artifactory/) server (which can all be done for free).

The Artifactory wiki has [instructions on how to install Artifactory for a mac](https://www.jfrog.com/confluence/display/RTF/Installing+on+Linux+Solaris+or+Mac+OS), but I found that they weren't very good. So, I decide to [install using Docker](https://www.jfrog.com/confluence/display/RTF/Installing+with+Docker) instead. [Installing docker](https://docs.docker.com/v17.12/docker-for-mac/install/#install-and-run-docker-for-mac) is pretty easy, once installed you can run docker commands from the mac command line.

You can then pull the artifactory docker image with: ```docker pull docker.bintray.io/jfrog/artifactory-oss:latest```

You then run Artifactory in the docker container with: ```docker run --name artifactory -d -p 8081:8081 docker.bintray.io/jfrog/artifactory-oss:latest```

You can then open a browser in order to see the Artifactory UI:
![Artifactory landing](https://drive.google.com/uc?export=view&id=1kqDzIwtvb6AWZOt7FZ4m9Zm9QEaqxEP6)