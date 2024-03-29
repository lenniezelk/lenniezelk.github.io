---
title: Flutter loading screen with future builder
date: 2019-07-11T10:43:59+03:00
tags:
  - flutter
  - programming
  - dart
---

When developing UIs you need to give the user some feedback on a long running process. A loading widget is normally the go to solution. In React you would have a boolean property in the components state. If for example you are fetching some data from the internet, you would set the boolean to `true`. In the component's `render` method you would display a loading widget based on the value of that boolean property. When you have your data you show the right component. Something like:

{{< gist lenniezelk 9032ff0aacf00a59c7dd254d3019f118 >}}

This can be achieved easily in Flutter with [Future Builder](https://api.flutter.dev/flutter/widgets/FutureBuilder-class.html). FutureBuilder allows you to specify a future and a builder function. The builder function will be passed snapshots based on the state of the future. You can then check the snapshot and display your loading widget. The same can be achieved by using viewmodels and state management tools like [Provide](https://pub.dev/packages/provider). This is so much easier though. Example:

{{< gist lenniezelk 7275c14bcd1b61d3e190b80b4895c524 >}}
