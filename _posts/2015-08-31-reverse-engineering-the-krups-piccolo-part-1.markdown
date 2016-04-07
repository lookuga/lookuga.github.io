---
redirect_from: "/post/reverse-engineering-the-krups-piccolo-part-1"
layout: post
title:  "Reverse Engineering the Krups Piccolo - Part 1"
date:   2015-08-31 00:00:00 +0100
tags: Awesomeness Development Electronics Lookuga Malta Mapace
---
As a house warming gift, we (my awesome girlfriend and I) received a Krups Piccolo Pod Coffee machine. After a couple of months the machine decided to die on us while making our nightly hot drink before bed. The problem was that the pump was no longer working.
<br>
<br>
Being naturally curious as to how things work, we decided to take a look at the inners of this little machine to see how exactly it works and perhaps fix it if we had any matching replacement parts on hand in my "electronic junk box".
<br>
<br>
<center><img style="width: 262px;" src="/images/KrupsPiccolo/back.png"></center>
<br>
<br>
After a while investigating and tracing all the parts that are on the main board, we produced the below lists
<br>
<br>
<img style="width: 702px;" src="/images/KrupsPiccolo/frontboard.png">
<br>
<br>
<ul>
<li>
CBB62B x2 0.47uF
</li>
<li>
CBB62B x2 0.22uF
</li>
<li>
TVR 14431
</li>
<li>
470uF16v
</li>
<li>
BTB08-600CW
</li>
<li>
Z7N F308
</li>
<li>
Number of General Transistors
</li>
<li>
Number of General Resistors
</li>
<li>
Generic IC – F8212 201PM02
</li>
</ul>
<br>
Other items/Info:
<br>
<ul>
<li>
Board Size 9.4 x 5.1 CM
</li>
<li>
1-Wire Analog Resistor Temperature Sensor
</li>
<li>
Capsule Holder (Magnetic Reed Switch)
</li>
<li>
3-Position Spring loaded Switch
</li>
<li>
Power Board (Green/Red LED and Toggle Button)
</li>
<li>
Pump
</li>
<li>
Water Heater
</li>
</ul>
<br>
While the above list is not a complete component list, it gives you an overview of how few components are required to build a working board, even if the power supply is unsafe and designed in a way that is not isolated from the main power grid.
<br>
<br>
After testing all the usual suspects of as to why the pump was not working, it was traced back to the mainboard generic microcontroller IC (which is on the underside of the PCB).
<br>
<br>
<center><img style="width: 120px;" src="/images/KrupsPiccolo/unknownic.jpg"></center>
<br>
<br>
Now with all the power of google on our side, I was unable to find much information about this IC. The only information I was able to find with regards to the IC and the machine itself is the below. Which either means the IC is a custom designed one or it relabeled from some other manufacture. Either way, fixing/replacing this IC was going to be next to impossible.
<br>
<br>
<a target="_blank" href="http://www.helbling.ch/htk-en/project-examples/kaffeemaschine-piccolo-1">http://www.helbling.ch/htk-en/project-examples/kaffeemaschine-piccolo-1</a>
<br>
<br>
<a target="_blank" href="http://www.mikrocontroller.net/topic/211586">http://www.mikrocontroller.net/topic/211586</a>
<br>
<br>
Check back soon for part 2 for a complete tear down tutorial of the Krups Piccolo and part 3 which we replace the stock mainboard with an open source one that has more features that anyone can build.
<br>