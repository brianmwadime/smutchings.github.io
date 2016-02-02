---
layout: post
title: visualaborate
date: 2011-05-31 15:53:14.000000000 +02:00
---
<img src="http://patrickheneise.files.wordpress.com/2011/05/visualaborate.png?w=1024&h=576" alt="" title="visualaborate" width="600" height="336" class="aligncenter size-large wp-image-372" />

<p>visual collaboration - that was my theme for the final '<a href="http://www.nmnt.nl">New Media &amp; New Technology</a>' course within the 'Media Technology' programme.</p>

<h3>Final Result</h3>
<p>With 8 participants after 5 hours exhibition time.</p>
<a href="http://patrickheneise.files.wordpress.com/2011/05/img_1111.jpg"><img src="http://patrickheneise.files.wordpress.com/2011/05/img_1111.jpg?w=1024&h=764" alt="" title="IMG_1111" width="600" height="448" class="aligncenter size-large wp-image-395" /></a>
<a href="http://patrickheneise.files.wordpress.com/2011/05/img_1110.jpg"><img src="http://patrickheneise.files.wordpress.com/2011/05/img_1110.jpg?w=1024&h=764" alt="" title="IMG_1110" width="600" height="448" class="aligncenter size-large wp-image-400" /></a>

<h3>Concept</h3>
<img src="http://patrickheneise.me/wp-content/uploads/2011/05/Photo-Mai-30-8-38-46-nachm.-225x300.png" alt="" title="Photo Mai 30, 8 38 46 nachm." width="225" height="300" class="alignleft size-medium wp-image-375" /><p>I took the underlaying idea from <a href="http://www.patrickheneise.me/eggdaprof"><em>eggDaProf</em></a>: controlling a virtual instance with an iOS device and be part of something big. Instead of a game I wanted to do something more permanent and stable, so I decided to do a visualisation. The "big picture" is a collection of peoples own preferences and attitudes. Everybody can contribute a personal touch without artistic skills, as the visualisation does not rely on dexterity, but pure fun and movement of the device.</p>

<h3>Implementation</h3>
Instead of HTML and JavaScript I created my own iPhone App "GyroTransmitter" which sends accelerometer- and gyroscope-data with some additional custom values like colour and line size/number to the network as UDP broadcast.</p>
<p>On the other end I used Quartz Composer again, as it has very powerful visualisation engines. However, I did not have the skills in OpenGL and OpenCL for personalised visuals, so I had to rely on the ready-made patches from Apple. Some things couldn't be handled without a little bit of scripting, for example the device queue, which holds all actual values for all devices without any duplicates. This was rather a challenge, as it is quite confusing to work with so many structures:</p>

<pre><code>function (__structure device, __structure outputQueue, __string debug) main (__structure inputStructure, __structure inputQueue)
{
  var result = new Object();
  var device = new Object();
  var qObj = new Object();
  var queue = new Array();
  
  device.attributes = new Object();
  if(inputStructure != undefined) {
    device.id = inputStructure[0];
    device.attributes["ax"] = inputStructure[1];
    device.attributes["ay"] = inputStructure[2];
    device.attributes["az"] = inputStructure[3];
    if (!_testMode) {
      if(inputQueue != undefined) {
        var found = false;
        for(i=0; i &lt; inputQueue.length; i++) {
          qObj = inputQueue[i];
          if(String(qObj[&quot;id&quot;]) == String(device.id)) {
            queue[i] = device;
            found = true;
          } else {
            active = qObj[&quot;active&quot;];
            queue[i] = qObj;
            newObj = queue[i];
          }
        }
        if(!found) {
          queue.push(device);
        }
      }
    }
  }
  result.device = device;
  result.outputQueue = queue;
  return result;
}</code></pre>

<img src="http://patrickheneise.me/wp-content/uploads/2011/05/Screen-shot-2011-05-30-at-8.22.04-PM-1024x515.png" alt="" title="Screen shot 2011-05-30 at 8.22.04 PM" width="600" height="300" class="aligncenter size-large wp-image-373" /><p>The base patch is pretty simple: get the values from the network, split them into the right attributes, queue them and display them. As mentioned above, there is some JavaScript processing required to create the queue and an iterator to display one "<em>Line Family</em>" for each device.</p>

<img src="http://patrickheneise.files.wordpress.com/2011/05/screen-shot-2011-05-30-at-8-22-14-pm.png" alt="" title="Screen shot 2011-05-30 at 8.22.14 PM" width="600" height="414" class="aligncenter size-full wp-image-374" />

<h3>Problems with Quartz Composer</h3>
<p>Quartz Composer can be tricky sometimes and it took me dozens of hours to debug and get the patch running. Some information which is worth sharing about Quartz Composer:</p>
<h4>No Integration or Random in Iterations</h4>
<p>By integration I'm talking about the mathematical term. Adding values up/down, which is a pretty simple task. However, once you're in an iterator-patch, the output of the Integrator-patch is always the same for all instances, so even if one device sends to command to go down and the other one the command to go up, they're both doing the same. Random is also the same value for all instances, no matter how many random generators you use. This is also valid for any kind of trickiness you might get into your mind. I tried JavaScript, Math, Mathematical Expression, Integrator and a complex Sample &amp; Hold combination, nothing worked.</p>

<h4>No JavaScript Debugging</h4>
<p>This is actually the worst thing in Quartz Composer: there is no debugging. If there is a logical mistake (which is not recognised by the syntax-check), the output of the patch is simply 'virtual', there is no clue on where the mistake actually is. And as JavaScript is an untyped language, you can just write attrbute instead of attribute and search for the error for a while.</p>

<h3>Conclusion</h3>
<p>Overall I'm quite happy with the results, even if I will probably not use Quartz Composer again and try to use the Quartz Engine with Objective-C next time. To figure things like the iteration problem out just costs too much time and usually works in every other language. The output of the patch and the collaboration on a visualisation is fun, even if the network broadcasting is still not perfect and there could be more options in the graphical device interface instead of random values, but I wanted to avoid too much focus on the interface, but controlling the visualisation with gyro and accelerometer data. For future work I would display the visualisation also on the device and get rid of interface input completely, but use simpler visualisations. These '<em>private</em>' visualisations could then be added up in a crowd-visualisation, without users seeing the end result while they're adding their part.</p>

<h3>Video</h3>
[vimeo http://www.vimeo.com/24476236 w=480&h=270]

<h3>Source</h3>
<p><a href='http://patrickheneise.me/visualaborate/gyrotransmitter' rel='attachment wp-att-380'>GyroTransmitter iOS App</a> and <a href='http://patrickheneise.me/visualaborate/visualaborate-2' rel='attachment wp-att-381'>visualaborate Quartz Composer Patch</a></p>

<h3>License</h3>
<p><a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/3.0/"><img alt="Creative Commons License" style="border-width:0;" src="http://i.creativecommons.org/l/by-nc-sa/3.0/88x31.png" /></a><br /><span>visualaborate and GyroTransmitter</span> by <a href="http://www.patrickheneise.me" rel="cc:attributionURL">Patrick Heneise</a> are licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/3.0/">Creative Commons Attribution-NonCommercial-ShareAlike 3.0 Unported License</a>.</p>
