---
redirect_from: "/post/task-parallel-library-tpl-vs-task-based-async-pattern-tap-vs-async-programming-model-apm"
layout: post
title:  "Task Parallel Library (TPL) vs Task-based Async Pattern (TAP) vs Async Programming Model (APM)"
date:   2014-12-22 00:00:00 +0100
tags: Lookuga Mapace Review
---
<p>For a number of
upcoming projects (make sure to follow/like on Facebook and other social media
to stay up to date of when I release them), I needed to create high
performance, low impact .NET code which was able to scan a large range of IP addresses and
ports in the quickest amount of time possible.</p>
<p>So naturally, I
performed some tests to see the outcome of each of the patterns,
using them in a normal way and using them in a number of different
combinations to try and squeeze as much as possible out of them.</p>

<p>The patterns that I am going to base the tests on are the following:</p>

<ul type="disc" style="margin-top: 0in; margin-bottom: 0in; margin-left: 0.375in; unicode-bidi: embed; direction: ltr;">
 <li style="margin-top: 0px; margin-bottom: 0px; vertical-align: middle;"><span>Task Parallel Library (TPL)
     is designed to make developers more productive by making it easier to add
     parallelism and concurrency to applications TPL scales dynamically to make
     use of all processors that are available. Using TPL allows you to focus
     more on the application's core functionality.</span></li>
 <li style="margin-top: 0px; margin-bottom: 0px; vertical-align: middle;"><span>Task-based Async Pattern
     (TAP) allows for a single method to represent the initiation and
     completion of an asynchronous operation.</span></li>
 <li style="margin-top: 0px; margin-bottom: 0px; vertical-align: middle;"><span>Async Programming Model (APM)
     uses the IAsyncResult design pattern, which is implemented using two
     methods named BeginMethodName and EndMethodName that are used to begin and
     end asynchronous operations respectively.</span></li>
 <li style="margin-top: 0px; margin-bottom: 0px; vertical-align: middle;"><span>Event-based Async Pattern
     (EAP) allows easy implementation of "in the background"
     operations, without interrupting the application. (this has been replaced
     by TAP completely and will not be tested as the Async method of the TCP
     client uses TAP)</span></li></ul><p style="margin-top: 0px; margin-bottom: 0px; vertical-align: middle;"><span><br></span></p><ul type="disc" style="margin-top: 0in; margin-bottom: 0in; margin-left: 0.375in; unicode-bidi: embed; direction: ltr;">
</ul>
<p>The following test were performed using port 80 for 255 unique IP Addresses using the following machine specs:</p>
<p>First Machine: Dual-Core CPU &amp; 4 GB RAM</p>
<p>Second Machine: Octa-Core CPU &amp; 14 GB RAM</p>
<div style="direction: ltr;">
<table style="border: 1pt solid rgb(163, 163, 163); border-image: none; border-collapse: collapse; direction: ltr;" border="1" cellspacing="0" cellpadding="0" valign="top">
 <tbody><tr>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.265in; vertical-align: top;">
  <p style="margin: 0in;"><strong>Solution</strong></p><strong>
  </strong></td><strong>
  </strong><td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 3.559in; vertical-align: top;"><strong>
  </strong><p style="margin: 0in;"><strong>TCP Client Type &amp; Notes</strong></p><strong>
  </strong></td><strong>
  </strong><td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.499in; vertical-align: top;"><strong>
  </strong><p style="margin: 0in;"><strong>Seconds taken on&nbsp;1st machine</strong></p><strong>
  </strong></td><strong>
  </strong><td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.581in; vertical-align: top;"><strong>
  </strong><p style="margin: 0in;"><strong>Seconds taken on&nbsp;2nd machine</strong></p>
  </td>
 </tr>
 <tr>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.265in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">Normal
  (Control Test)</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 3.559in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">APM</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.499in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">129.57</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.581in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">134.38</p>
  </td>
 </tr>
 <tr>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.265in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">*</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 3.559in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">TAP</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.499in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">130.48</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.581in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">131.42</p>
  </td>
 </tr>
 <tr>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.265in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">Task-Based
  Only</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 3.559in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">Task
  Based Loop with TAP</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.499in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">131.33</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.581in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">130.27</p>
  </td>
 </tr>
 <tr>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.265in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">Task-Based
  Run Loop</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 3.559in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">APM</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.499in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">10.13</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.581in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">7.39</p>
  </td>
 </tr>
 <tr>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.265in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">*</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 3.559in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">TAP</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.499in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">6.26</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.581in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">7.62</p>
  </td>
 </tr>
 <tr>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.265in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">*</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 3.559in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">Mix
  and Mash with 4 pre task runners and multiple sub task runners with TAP</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.499in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">8.07</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.581in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">6.32</p>
  </td>
 </tr>
 <tr>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.265in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">Parallel
  For Each Loop</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 3.559in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">Max
  Degree of parallelism set to default and with APM</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.499in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">22.58</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.581in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">16.03</p>
  </td>
 </tr>
 <tr>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.265in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">*</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 3.559in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">Max
  Degree of parallelism set to default and with TAP</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.499in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">16.20</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.581in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">15.30</p>
  </td>
 </tr>
 <tr>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.265in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">*</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 3.559in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">Max
  Degree of parallelism set to 999 and with APM</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.499in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">8.6</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.581in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">7.11</p>
  </td>
 </tr>
 <tr>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.265in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">*</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 3.559in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">Max
  Degree of parallelism set to&nbsp;999 and with TAP</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.499in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">8.7</p>
  </td>
  <td style="padding: 4pt; border: 1pt solid rgb(163, 163, 163); border-image: none; width: 1.581in; vertical-align: top;">
  <p style="margin: 0in; text-align: center;">7.16</p>
  </td>
 </tr>
</tbody></table>
</div>
<p><br></p><p>Looking at the
results above, it seems that they are all&nbsp;relative to each other in the terms of
time it takes for each test to execute. The only visible difference seems to be
with the amount of cores used, the more cores used, the less time it takes.</p>

<p>Depending on the scenario, it would be ideal to either use TPL or TAP to implement parallel or asynchronous code as recommended by .NET best practices and avoid the use of legacy APM or EAP as they will be phased out over time.</p>

<p>I have uploaded the test application source to GitHub and is being released as GNU GPL, so go grab a copy and perform the tests on your machine from here if you wish: <a href="https://github.com/lookuga/CodeTests">https://github.com/lookuga/CodeTests</a></p>