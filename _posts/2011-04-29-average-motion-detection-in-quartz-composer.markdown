---
layout: post
title: Average Motion Detection in Quartz Composer
date: 2011-04-29 09:57:22.000000000 +02:00
---
<a href="http://patrickheneise.me/average-motion-detection-in-quartz-composer/screen-shot-2011-04-28-at-17-14-58" rel="attachment wp-att-290"><img src="http://www.patrickheneise.me/wp-content/uploads/2011/04/Screen-shot-2011-04-28-at-17.14.58-300x100.png" alt="" title="Screen shot 2011-04-28 at 17.14.58" width="300" height="100" class="aligncenter size-medium wp-image-290" /></a>For the lecture Machine Mediated Vision I created my first patch in Quartz Composer. The patch shows a minute-long clip from the movie "The Big Lebowski" on the right, and the average motion in grayscale on the left. <a href="http://patrickheneise.me/average-motion-detection-in-quartz-composer/screen-shot-2011-04-28-at-17-16-40" rel="attachment wp-att-292"><img src="http://patrickheneise.me/wp-content/uploads/2011/04/Screen-shot-2011-04-28-at-17.16.40-300x106.png" alt="" title="Screen shot 2011-04-28 at 17.16.40" width="300" height="106" class="aligncenter size-medium wp-image-292" /></a>
<a href="http://patrickheneise.me/average-motion-detection-in-quartz-composer/screen-shot-2011-04-28-at-17-16-28" rel="attachment wp-att-291"><img src="http://patrickheneise.me/wp-content/uploads/2011/04/Screen-shot-2011-04-28-at-17.16.28-300x106.png" alt="" title="Screen shot 2011-04-28 at 17.16.28" width="300" height="106" class="aligncenter size-medium wp-image-291" /></a>
The patch queues the images and compares the actual image to another one earlier in the clip which can be specified with an index. Then a difference blend filter is applied combined with a small custom core image filter and the area average filter to get the grayscale value. The output here was only 1x1 pixels and for some reason "Image Pixel" couldn't be applied here, so I had to transform the image and scale it up a bit to extract one pixel and get the RGBA values from it. These are multiplied by 10 and then displayed in the sprite.

<h3>Download</h3>
You can <a href='http://patrickheneise.me/wp-content/uploads/2011/04/AverageMotion.zip'>download AverageMotion here</a> (25 MB).

<h3>License</h3>
<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/3.0/"><img alt="Creative Commons License" style="border-width:0;" src="http://i.creativecommons.org/l/by-nc-sa/3.0/88x31.png" /></a><br /><span>AverageMotion</span> by <a href="http://www.patrickheneise.me" rel="cc:attributionURL">Patrick Heneise</a> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/3.0/">Creative Commons Attribution-NonCommercial-ShareAlike 3.0 Unported License</a>.
