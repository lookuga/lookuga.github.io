---
redirect_from: "/post/azure-network-bandwidth-speed"
layout: post
title:  "Azure Network Bandwidth Speed"
date:   2015-03-11 00:00:00 +0100
tags: Development Mapace News Review
---
<p>If you try&nbsp;searching for&nbsp;the network bandwidth
speed of Azure VMs, you will probably spend a while trying to find even the
slightest bit of information, not even the official documentation has any
details on the topic. So I decided to publish my own findings and any other
source of information I have found.</p><p>The tests were performed on a Virtual Machine&nbsp;located in the Europe-West region using <a href="http://www.speedtest.net/" target="_blank">Ookla Speedtest.net</a> using their KPN Amsterdam-Netherlands test point.</p><table class="table table-bordered"><tbody><tr><td>Size<br></td><td>Ping<br></td><td>Download Speed<br></td><td>Upload Speed<br></td></tr><tr><td>A0 - 1 Shared Core 768MB Memory<br></td><td>1ms<br></td><td>226.07Mbps<br></td><td>5.13Mbps<br></td></tr><tr><td>A1 - 1 Core 1.75GB Memory<br></td><td>1ms<br></td><td>349.53Mbps<br></td><td>95.69Mbps<br></td></tr><tr><td>A2 - 2 Core 3.5GB Memory<br></td><td>1ms<br></td><td>435.75Mbps<br></td><td>183.22Mbps<br></td></tr><tr><td>A3 - 4 core&nbsp; 7GB memory<br></td><td>1ms<br></td><td>481.99Mbps<br></td><td>360.45Mbps<br></td></tr><tr><td>A4 - 8 core&nbsp; 14GB memory<br></td><td>1ms<br></td><td>488.74Mbps<br></td><td><p>677.58Mbps<br></p></td></tr></tbody></table>
<p><font size="1">Additional external references:</font></p><ul><li><a href="http://stackoverflow.com/questions/17303044/windows-azure-virtual-machine-is-slow-to-access-network-when-scaling"><font size="1">http://stackoverflow.com/questions/17303044/windows-azure-virtual-machine-is-slow-to-access-network-when-scaling</font></a></li><li><a href="http://blogs.msdn.com/b/thecolorofazure/archive/2014/05/13/azure-implementation-guidelines.aspx"><font size="1">http://blogs.msdn.com/b/thecolorofazure/archive/2014/05/13/azure-implementation-guidelines.aspx</font></a></li><li><a href="http://blogs.breeze.net/mickb/2014/05/01/AzureOutboundThrottlingOfVMs.aspx"><font size="1">http://blogs.breeze.net/mickb/2014/05/01/AzureOutboundThrottlingOfVMs.aspx</font></a></li><li><a href="https://msdn.microsoft.com/library/azure/dn197896.aspx"><font size="1">https://msdn.microsoft.com/library/azure/dn197896.aspx</font></a></li></ul><p><em><br></em></p><p><em>Don't forget to like us on our social media! </em></p>
