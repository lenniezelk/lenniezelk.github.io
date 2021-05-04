---
title: Running flutter app on Genymotion
date: 2019-07-15T11:41:24+03:00
tags:
  - flutter
  - programming
  - dart
---

To run flutter apps for android development you have the option of running the app on android studio AVDs or genymotion. I prefer genymotion since I find more lightweight and I can run vagrant boxes usually for the backend of the application. This is not possible with AVDs. Flutter fails to recognize the devices created using genymotion. After searching around the internet I could not find a solution so I'm going to post what worked for me.

Ensure you have installed the Android SDKs for the target platforms. You can do this from the SDK manager in Android Studio. Launch Genymotion. On the menu bar go to: `Genymotion > Settings`. This will launch a dialog box. Select `ADB` in the dialog. Enter the path to your Android SDK folder. For example on my local setup this is `/home/lk/Android/Sdk`. Restart Genymotion and launch your devices. I had some problems with devices I had created before I made these changes. In this case I deleted and recreated them. When you run `flutter devices` your launched device should appear now. Run `flutter run` to launch the app. Happy fluttering.
