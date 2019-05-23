---
layout: post
title: Today I learnt
tags: gotchas Software OneSignal PushNotification
---
Been having some issues with implementing [OneSignal](https://onesignal.com/) push notifications in an Android app at work lately.
Main issue was that clicking a push notification was causing the app to do a fresh start, showing the splashscreen, rather than navigating to the correct page.
Eventually came across this [SO post](https://stackoverflow.com/questions/31946545/tapping-a-notification-from-onesignal-does-not-open-a-result-activity-andr),
which basically says that the default OneSignal behaviour is to do a fresh start of the app. Seems stupid, but you have to edit the manifest.xml to stop this behaviour:
```
<application ...>
   <meta-data android:name="com.onesignal.NotificationOpened.DEFAULT"  android:value="DISABLE" />
</application>
```
