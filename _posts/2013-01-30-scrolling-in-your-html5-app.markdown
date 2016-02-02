---
layout: post
title: Scrolling in your HTML5 App
date: 2013-01-30 02:28:52.000000000 +01:00
---
For my last app I ran into the problem of scrolling an area within an HTML5 App while other areas, for example the header remains at a static position. There are a couple options:
<ul>
	<li><a href="http://cubiq.org/iscroll"><span style="line-height:14px;">iScroll</span></a></li>
	<li><a href="http://joehewitt.github.com/scrollability/">Scrollability</a></li>
	<li>a major mobile Framework such as <a href="http://www.sencha.com/products/touch">Sencha Touch</a></li>
</ul>
I started with iScroll which seems to be the most popular option but ran into major troubles and headaches with it. Digging into the topic, I found Scrollability, which is unfortunately not maintained any more (last commit 2 years ago?). And including a major framework into an existing App just for scrolling was kind of using a sledge-hammer to crack a nut. Since the App is supposed to run on iOS first, I figured I'll try the native way: <code>-webkit-overflow-scrolling: touch</code>.

However, this is also kind of tricky. Here's what you need:

Change UIWebViewBounce in your config.xml to false:
<script src="https://gist.github.com/PatrickHeneise/4669518.js"></script>

Unfortunately, the height of the wrapper is 50px too short, the height of the header. The only solution I found was resizing the height with some JavaScript.

This can be done after rendering, for example with <a href="https://github.com/janl/mustache.js/">mustache.js</a>.
