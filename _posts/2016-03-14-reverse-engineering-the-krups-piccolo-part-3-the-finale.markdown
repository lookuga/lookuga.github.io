---
redirect_from: "/post/reverse-engineering-the-krups-piccolo-part-3-the-finale"
layout: post
title:  "Reverse Engineering the Krups Piccolo - Part 3 - The Finale"
date:   2016-03-14 00:00:00 +0100
tags: Awesomeness Development Electronics Malta
---
This is the final part of this 3-part blog post, there is a possibility that in the future we may continue with adding further modifications and improvements but they will be published on separate blog posts.<br><br>Furthermore, if you haven't already checked out part 1 and 2, we encourage you to check these out at the following links:
<br>
Part 1: <a target="_blank" href="https://lookuga.com/post/reverse-engineering-the-krups-piccolo-part-1">https://lookuga.com/post/reverse-engineering-the-krups-piccolo-part-1</a>
<br>
Part 2: <a target="_blank" href="https://lookuga.com/post/reverse-engineering-the-krups-piccolo-part-2-teardown">https://lookuga.com/post/reverse-engineering-the-krups-piccolo-part-2-teardown</a>
<br>
<br>
So let's get on with the final post. I would like to start by mentioning that we wanted to challenge ourselves by allocating a budget of just 10 euros to design and build a replacement mainboard. After a couple of minutes we had our part list ready and a couple of minutes later we also found the required parts which we are also sharing with you below:
<br>
<br>
<span style="font-weight: bold;">
Part list
</span>
<br>
<ul>
<li>
5V Relay x2
</li>
<li>
TVR
</li>
<li>
Transistor x2
</li>
<li>
Diode x2
</li>
<li>
Routing Wire
</li>
<li>
ATmega168 or equivalent with internal pull-up resistors (Arduino Pro Mini)
</li>
<li>
Resistor for switch (10k)
</li>
<li>
5v Power Supply
</li>
<li>
Various Parts from the broken Krups Machine
</li>
</ul>
<br>
The brains for this mainboard is the ATMEGA168, although we could have used the Atmel Studio to develop on it, we decided to stick with the Arduino Framework, as we thought it might be easier for beginners to use and experiment upon.
<br>
<br>
<img style="width: 380px;" src="/images/KrupsPiccolo/Part3/mock.jpg">
<br>
<br>
Once we had a working prototype built on a breadboard the next step was to shrink it to fit on a protoboard with the maximum size of  9.4 CM X 5.1 CM with all components and wiring routing.
<br>
<br>
<img style="width: 676px;" src="/images/KrupsPiccolo/Part3/ProtoBoard.png">
<br>
<br>
<img style="width: 303px;" src="/images/KrupsPiccolo/Part3/board.jpg">
<br>
<br>
(the TVR is missing from this photo, but should be soldered between the live and natural)<br><br>All of the designs and code is licensed under GPL, so you are free to build your own with improvements as long as you release them back to public for free.
<br>
<br>
As stated earlier, other improvements or modification could be done, which include:
<br>
<br>
<ul>
<li>WIFI Enabled - Make a coffee from your mobile</li>
<li>Factory Printed PCB - Product designed PCB instead of the Protoboard</li>
<li>Solid State Relays with built-in snubbers - smaller footprint, quieter and more reliable than mechanical relays</li>
</ul>
If anyone, does decide to build one for themselves or would like to get a built one, let us know on facebook!
<br>
<br><span style="font-weight: bold;">GitHub Link for source code and design:</span>
<br>
<a href="https://github.com/lookuga/DolceGusto">https://github.com/lookuga/DolceGusto</a>
<br>
<br>
<span style="font-weight: bold;">ProtoBoard.ai<br></span>
Contains multi-layer illustrator file, broken down (pcb, top wiring,bottom wiring, components etc)<br<br>
<span style="font-weight: bold;">KrupsPiccolo_OpenSource.ino<br></span>
Contains the source code for the microcontroller<br><br>
<span style="font-weight: bold;">Instructions to Use</span>
<br>
<ol>
<li>Connect power to coffee machine</li>
<li>Should start pulsing green</li>
<li>On pressing the power button, should turn to yellow (means heating up)</li>
<li>Once heated up should turn to solid green</li>
<li>On switch to start pump, it should start to pump water (either hot or cold) and should be yellow (heating while pumping)</li>
<li>Show red, if the capsule holder is not detected when trying to start pump</li>
</ol>