---
layout: post
title: Access .net core web api from xamarin emulator
tags: Software .netCore webAPi Xamarin Android
---
I recently started building a .net core web api for a personal xamarin project. I struggled to get the app to connect to the api, running on my local machine. By default, VS 2017 starts the api on http://localhost:port with IIS express. The problem is that your app code cannot refer to local host because that is shorthand for "this machine", which in this case means the Android virtual machine, not the machine running your web api. There is also a bunch of port forwarding stuff mentioned on the internet which I couldnt be bothered to dig into.

Thankfully, [SharpProxy](https://github.com/jocull/SharpProxy), can do most of the work for you. I was able to hit breakpoints in my api code from the android emulator. Here is a [Tutorial](https://www.barelycompetent.co.za/debugging-your-rest-service-from-your-emulator-device-using-sharpproxy/).

# Executive summary

APP_BASE_API_URL = "http://YOUR_IP_ADDRESS:5000/";
Launch API and check port number. Eg - http://localhost:8888/
SharpProxy - 
Enter your ip address
External port: 5000
Internal port: bit after localhost in locally hosted api url (eg 8888)
click start

## Other options
[ngrok](https://ngrok.com/product) and [iisexpress-proxy](https://github.com/icflorescu/iisexpress-proxy)
