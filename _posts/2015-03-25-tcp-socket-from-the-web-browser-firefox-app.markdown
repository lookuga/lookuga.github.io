---
redirect_from: "/post/tcp-socket-from-the-web-browser-firefox-app"
layout: post
title:  "TCP Socket From the Web Browser/Firefox App"
date:   2015-03-25 00:00:00 +0100
tags: Awesomeness Development Lookuga Mapace Review
---
<p>A couple of weeks ago I was&nbsp;testing some new merging technologies that should be coming to future web browsers.
</p><p>
The technology which I am going to write about in this post is Sockets (not Web Sockets), namely TCP Sockets.</p><p>This technology will allow developers using JavaScript to launch TCP connections to a remote server and or create a TCP server with only a couple lines of code.</p><p>
The applications for this technology are endless, but one of them comes to mind that I am interested in is real time multiplayer games via a web browser, this means a developer could write one app and would work across all supported systems without any plugins like Flash.</p><p>
While for now TCP Sockets are only available to certain user agents, one such is Boot-2-Gecko (Firefox OS), it is currently being standardised by W3 as the Raw Socket API.</p><p>
The Raw Sockets API also mentions UDP Sockets, but is yet to be made available to the Boot-2-Gecko (Firefox OS), it is possible that is available to other User Agents.</p><p>
Screenshot of working example&nbsp;App:</p>
<a href="/images/tcpsocketclient.png" target="_blank"><img style="width: 345px; height: 277px;" src="/images/tcpsocketclient.png"></a>
<p>
</p><p>I have uploaded the test application source to GitHub and is being released as GNU GPL, so go grab a copy of the source code and try it out, you will need Firefox Developer Edition along with a Firefox OS simulator.

 </p><p><a href="https://github.com/lookuga/CodeTests" target="_blank">https://github.com/lookuga/CodeTests</a></p>
<p><font size="1">References:</font></p><p><a href="http://www.w3.org/TR/raw-sockets" target="_blank"><font size="1">http://www.w3.org/TR/raw-sockets</font></a></p><p><a href="https://developer.mozilla.org/en-US/docs/Web/API/TCPSocket" target="_blank"><font size="1">https://developer.mozilla.org/en-US/docs/Web/API/TCPSocket</font></a></p><p><a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/mozTCPSocket" target="_blank"><font size="1">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/mozTCPSocket</font></a>
</p>