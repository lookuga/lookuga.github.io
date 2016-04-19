---
layout: post
title:  "FireFox OS Lock Screen Pin Recovery"
date:   2016-04-19 00:00:00 +0100
tags: Awesomeness Development Hacking Security Old Projects
---
Over the last couple of years, we have accumulated a number of ideas, projects and proof of concepts, which never see the public light of day. Over the next few months we will be releasing them to the public either as partially or fully completed.

The first idea/project is a tool we developed to recover the PIN of Firefox OS lock screen. While the logic behind this tool is far from complex, it is a proof of concept to show how the PIN is stored  in clear text and is unprotected in Firefox OS.

<br>
<img style="width: 160px;" src="/images/fflockscreen.png">
<br>

The PIN is stored in a simple SQLite Database and is located in the following:
<br>
/data/local/storage/permanent/chrome/idb/

The tool uses the ADB to pull the SQLite Database and read the contents, you could use fastboot and other means to transfer the file off the phone, if ADB is disabled.

The source code for this tool is available here:
<br>
<a target="_blank" href="https://github.com/lookuga/FireFoxOSPinRecovery">https://github.com/lookuga/FireFoxOSPinRecovery</a>
