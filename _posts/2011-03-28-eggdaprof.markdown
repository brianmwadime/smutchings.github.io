---
layout: post
title: eggDaProf
date: 2011-03-28 11:00:26.000000000 +02:00
---
<img class="alignright size-full wp-image-188" title="ofw-logo" src="http://patrick.heneise.de/wp-content/uploads/2011/03/ofw-logo.gif" alt="" width="114" height="100" />

Finally, we moved on and created a a project without Twitter. <a href="http://twitter.com/#!/web_martin">Martin Weber (@web_martin)</a> and me worked at "eggDaProf" for <a href="http://www.nmnt.nl">New Media, New Technology</a> — the name says it all: throw virtual eggs at the professors, the right theme for easter. The task was to "create something with openframeworks in space", so we had the idea of real and virtual space in our classroom 413 in LIACS and play a game.
<h3>The Architecture</h3>
<ul>
	<li>QR-Code with an URL to map real players to virtual players in the room</li>
	<li>HTML/JavaScript Website to read iPhone accelerometer data</li>
	<li>PHP script to send received accelerometer data to openframeworks</li>
	<li>openframeworks for the visualisation and the game handling</li>
</ul>
<img class="alignleft size-full wp-image-189" title="chart" src="http://patrick.heneise.de/wp-content/uploads/2011/03/chart.png" alt="" width="100" height="100" />

Distributed in the room are some printed QR-Codes with embedded URLs. To participate in the game, a player can scan the code with an iPhone or iPad and gets redirected to the game website, with the player id in the URL as parameter. The virtual representation is showed on the screen as long as the player is on the web-site and sending data. With HTML and JavaScript it is possible to read the accelerometer data live and in realtime through the iPhone Device API and the <a href="http://dev.w3.org/geo/api/spec-source-orientation.html">W3C DeviceOrientation Event Specification</a>.
<h4>JavaScript/AJAX code to read the y-axis and send it via XMLHttpRequest</h4>
<pre>window.ondevicemotion = function(event) {
	y = event.accelerationIncludingGravity.y;
	p = &lt;?=$_GET["p"] ?&gt;;$.post("udp.php", { y: y, p: p }, function(data) {});
}</pre>

This data is sent via XMLHttpRequest to the web-server which runs a PHP script. The script transforms the data and sends them further via UDP to another Mac running <a href="http://www.openframeworks.cc/">openframeworks</a> with a UDP listener. We used the networkUdpReceiverExample example and tried to use multi-threading for the players, which is unfortunately not supported by OpenGL.
<h4>PHP code to send data via UDP</h4>
<pre>$fp = pfsockopen( "udp://10.0.1.3", 11999, $errno, $errstr );
if ($_POST["y"]) {
	$yval = $_POST["y"];

	if ($yval &lt; -6.0) {$yval = -6.00;} 	if ($yval &gt; 6.0) {$yval = 6.00;}

	$yval = substr($yval, 0, 3);
	$write = fwrite( $fp, $_POST["p"]."".$yval);
}</pre>

<h3>The Game</h3>
The game in openframeworks is quite simple. The "professor" is standing in front of the classroom and faces the class. He can see the game on a laptop to control his virtual representation. The students can control the virtual rotation of the image and shoot eggs by pressing a button on the website. The eggs get faster over time, so it's harder for the professor to dodge.
<h3>The Video</h3>
[vimeo http://www.vimeo.com/21586573 w=480&h=360]
<h3>The Source</h3>
<a href="http://patrick.heneise.de/wp-content/uploads/2011/03/of-eggDaProf.zip">openframeworks project</a> and <a href="http://patrick.heneise.de/wp-content/uploads/2011/03/php-js.zip">php/js source</a>
<h3>License</h3>
<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/3.0/"><img style="border-width:0;" src="http://i.creativecommons.org/l/by-nc-sa/3.0/88x31.png" alt="Creative Commons License" /></a>
<span>eggDaProf</span> by <a rel="cc:attributionURL" href="http://patrick.heneise.de">Patrick Heneise</a> and <a rel="cc:attributionURL" href="http://twitter.com/web_martin">Martin Weber</a> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/3.0/">Creative Commons Attribution-NonCommercial-ShareAlike 3.0 Unported License</a>.
