---
layout: post
title: HTML5 vs. Native [thoughts]
date: 2014-02-26 11:53:42.000000000 +01:00
---
*Going mobile* – in the past years tablets and smart phones have taken over the technology world, computer sales are stagnating. Web sites need to be *“responsive”* and to be hip, you need an App. The biggest technical decision to be made when starting the development of an Application is if it’s a native App or a HTML5 App. Various things float around the web when searching for the differences, some are true, some were true some years ago and some are just completely wrong.

There’s a common problem with the term of web and HTML5 apps. They are pretty much the same, both use the same language: JavaScript and HTML and both are practically web application running on your phone. Both terms are used hand-in-hand, but there is a significant difference: “Web apps” run in the browser; “HTML5 apps” are web apps, they run in a browser-like environment, which is installed from an App Store just like any other app. These environments (for example Apache Cordova) allow the app to access resources on the device, like geolocation, address book, or photo access. Given all these resources, there’s a lot you can do with an HTML5 app and the gap between native apps and HTML5 apps is getting smaller day by day.

Going for HTML5 apps is especially interesting, if there is a co-existing web platform or if the product is supposed to cover as many markets as possible at the same time: iOS, Android, Windows OS, Firefox OS, to name a few. HTML5 apps are not written in a compiled, device specific language like Objective-C for iOS and Java for Android but in JavaScript, which has been declared the “lingua franca” of the web. Once written (and with a few minor, device specific tweaks), an HTML5 application can be build for all platforms the same time, which reduces development time for all markets up to 80%.
