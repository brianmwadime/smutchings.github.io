---
layout: post
title: Learning Swift&#58; My First Steps
date: '2016-06-27 12:00:00'
description: I recently started learning Swift for iOS development. Here's what I managed to do in my first week.
meta-description: I recently started learning Swift for iOS development. Here's what I managed to do in my first week.
---

I've long been a believer in iOS devices and the computing power they're able to bring to (and along with) the masses. As part of this belief, I've always wanted to learn how to make my own application. Recently, I decided to jump in a learn some Swift, to [take my first steps towards walking to the moon](http://samhutchings.co/thought/walk-to-the-moon/) ;). 

## The Tools I've Used

Before we get started looking at what I've learnt, let's take quick stock of how I learnt. 

I used the following tools and resources:

- TapCoding [[Web Link](http://tapcoding.com)] [[App Store](https://itunes.apple.com/us/app/tapcoding-coding-trainer-for/id1106047716?mt=8)]
- StackOverflow [[Web Link](http://stackoverflow.com)]
- Apple Developer Website [[Web Link](http://developer.apple.com)]
- Hacking With Swift [[Web Link](https://www.hackingwithswift.com)]

## What I Created

For my first app, I decided to create something that would be handed a couple of variables and then manipulated those variables to get an output. To me, the simplest form of this appeared to be an addition machine. So, that's what I made.

Here it is running on my iPhone 6s Plus:

<center><img src="/img/learning-swift/app-on-iPhone-in-hand.jpg" width="100%"></center>

The prime version of the application took two numbers, entered by tapping on the respective fields, and added them together on command. It was very simple, but it was something I had made and it was running on my iPhone.

I then added some very simple error handling. You see, when there is no value assigned to a [text field](https://developer.apple.com/library/prerelease/content/documentation/UserExperience/Conceptual/UIKitUICatalog/UITextField.html), the Swift compiler gives it a value of *nil*. Unfortunately, you can't just add *nil* to a number, so I had to check for a value in the text field and present an alert when you tried to do something that would break the app. 

Here's the code which generated the alert:

<center><img src="/img/learning-swift/alert-code-snippet.png" width="100%"></center>

And here it is running on the iPhone:

<center><img src="/img/learning-swift/error-alert.png" width="100%" max-height="960px"></center>

It's incredibly simple, and probably the totally wrong way to do this on the iPhone, but it works. 

## Working Towards V2.0

Once I had simple addition working within my app, I wanted a way to select the operation that would be performed on the two numbers. So, I added a *[Segmented Control](https://developer.apple.com/library/prerelease/content/documentation/UserExperience/Conceptual/UIKitUICatalog/UISegmentedControl.html)* to allow users of the app to select their preferred operation.

Version 2.0 of the application can add, subtract, multiple and divide 2 numbers, returning a *[Float](https://developer.apple.com/reference/swift/float)* as a *[String](https://developer.apple.com/reference/swift/string)* answer the user can see. It's still very simple, but a big improvement over version 1.0.

Here's a screenshot of the new version:

<center><img src="/img/learning-swift/simple-calculator-v2.jpg" width="100%"></center>

And here it is in action:

<center><video width="540" height="960" controls>
  <source src="/img/learning-swift/simple-calculator-demo.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video></center>

## How Many Lines?

The application is only about 40 lines of code, and I'm sure it could be done in fewer, but that's 40 lines of code which I wrote and which didn't exist before.

<center><img src="/img/learning-swift/code-snapshot.png" width="100%"></center>

## What's next?

Next, I think I'll work on adding some new features and design to my application. It's currently made with a very barebones look, as I was focussing on getting it to work, rather than making it look pretty.

I'd like the "Calculate" button to be disabled when incorrect values are entered, instead of the current *[UIAlertController()](https://developer.apple.com/reference/uikit/uialertcontroller)*. This is more subtle, but disturbs the flow less.

And maybe, I'll even work out how to use [Auto Layout](https://developer.apple.com/library/prerelease/content/documentation/UserExperience/Conceptual/AutolayoutPG/), so that it's not limited to my own iPhone 6s Plus. 