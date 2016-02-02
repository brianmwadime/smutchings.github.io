---
layout: post
title: Getting started with Mobile JavaScript
date: 2013-01-29 23:08:28.000000000 +01:00
---
For the <a title="Firefox App Days" href="https://wiki.mozilla.org/Engagement/Developer_Engagement/FirefoxAppDays">Firefox Open App Days</a> I wrote a chat demo to introduce various technologies for mobile Apps including a native iPhone application created with Apache Cordova, an HTML5 App for the brand new Firefox OS and a HTML5 web site for mobile Browsers. To broadcast chat messages between users, socket.io is used. The source code can be downloaded and forked from GitHub: <a title="OpenAppChat" href="https://github.com/PatrickHeneise/OpenAppChat">OpenAppChat</a>.

To run the demo, you just need <a title="node.js" href="http://nodejs.org">node.js</a> installed on your computer. In your Terminal, cd to the OpenAppChat directory and run:
<pre>node app.js</pre>
Navigate with your web browser of choice to <a href="http://localhost:3000">http://localhost:3000</a> to see the chat. Inside your local network, you might need to figure out your local IP and change the corresponding JavaScript files to access this IP:

<pre>iOS: iOS-OpenAppChat/www/js/index.js
Firefox OS: fOS-OpenAppChat/www/js/lib/app.js</pre>

Change:

<code>io.connect('http://192.168.0.1:3000');</code>

I can also recommend to have a look at <a title="nodejitsu" href="http://nodejitsu.com">nodejitsu</a>, those guys are doing a pretty good job in hosting node.js applications, so you can just change the file <code>package.json</code>, change the subdomain and run
<pre>jitsu deploy</pre>
to deploy the app to your account. To run one of the apps, change the socket.io connect line to your nodejitsu subdomain which you can specify in <code>package.json</code>.

To install the Firefox OS App in the simulator or on a device, go to the directory and run <code>volo serve</code>.

Feel free to modify the code and please share your experience and learnings with the community.
