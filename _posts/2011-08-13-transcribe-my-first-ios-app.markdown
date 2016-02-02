---
layout: post
title: Transcribe - My First iOS App
date: 2011-08-13 15:24:28.000000000 +02:00
---
![](/images/2014/Sep/img_0018.jpg)
<h2>A Modern Approach to the Transcription of Vintage Literature using Mobile Technology and Cloud Services</h2>
For my master thesis with the title named above I developed a prototype iOS application called "Transcribe". The application should help students and researchers to transcribe vintage literature by creating TEI (Text Encoding Initiative) files. I will write more to the thesis itself another time, this article is more about the experience of developing the first app and the first steps with iOS programming.

<h2>The Start</h2>
![](/images/2014/Sep/img_0019.jpg)
I never thought Objective-C would be that hard. There are a couple of websites which offer help to start Objective-C development, but they certainly don't have enough information for a project bigger than "Hello World". They focus on the step-by-step programming part for beginners and not on theoretical basics and "best practices" for experienced programmers. For example finding `<a title="How do I look at an object in Xcode's debugger?" href="http://stackoverflow.com/questions/978476/how-do-i-look-at-an-object-in-xcodes-debugger" target="_blank">po</a>' and learning how to use it would have helped me in the beginning a lot. Just making these connections between outlets and the corresponding code can drive somebody into debugging craziness, especially as there are no error messages saying 'Hey, you forgot a connection there, that's why the whole thing doesn't work'. More than once I was wondering why I made this decision instead of developing a web-app. But I completed the project, and it works good.

<h2>The Couch</h2>
![](/images/2014/Sep/img_0020.jpg)
On iOS, the Couch(DB) was not relaxing at all. Luckily, this changed within the last 4 weeks as CouchBase made some great improvements to their <a href="https://github.com/couchbaselabs/iOS-Couchbase/" target="_blank">mobile framework</a>. As I started at a very early stage, I had to struggle with a lot of issues with CouchDB and iOS, starting with the basic data synchronization to database views and lists. But the CouchDB was crucial to my development as I needed to store document-oriented data. It was pretty clear at this point, that XML was no option any more, so instead of importing XML to a data field in JSON, I transferred the TEI attributes to JSON and into CouchDB, which is a great improvement for search and semantics. All the data is now in one place and not spread over thousands of XML files.

<h2>The Interface</h2>
![](/images/2014/Sep/img_0021.jpg)
iOS made something clear for me once and for all: I'm no designer. I am used to HTML and CSS and am able to get things together that look OK, but with Xcode this was just a pain. I tried making screenshots of my app and edit them later in Photoshop, but I didn't want to design buttons, labels and everything else by hand, so I just left it with a new background image, which doesn't look very good either. But fortunately, this was a scientific prototype. So it was more important that the app works and is easy to use, than that it looks stunning. For the user experience, there were no guidelines or any experience-based data on how to create the perfect interface for literature transcription. I created several paper drawings and non-functional interface prototypes which I tested with the target group. Only with this process I found the easiest and fastest way for users to transcribe literature.

<h2>Conclusion</h2>
Honestly, there were many many hours of debugging were I cursed Apple for using this programming language. But after getting used to it, the next app will definitely be easier and faster to program.
