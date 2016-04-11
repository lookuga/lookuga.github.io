---
layout: post
title:  "See ya BlogEngine.NET, Hello Jekyll!"
date:   2016-04-11 00:00:00 +0100
tags: Awesomeness Development Migration Jekyll
---
Since December 2015, we have had numerous hacking attempts on Lookuga.com, from SQL Injection to XSS attacks.

While we were kind of happy to see that the blog must be popular enough for people to try and hack it, we were also annoyed by the triggering alerts we were receiving when it was happening.

What a lot people may not be aware of, is that we were running a highly customized version of BlogEngine.NET, with a lot of auditing, reverse tracking and better integration with other platforms, both for security reasons and also to measure the metrics of the content.

While we were implementing these changes we had discovered a number of major security issues, one we even made public (<a href="http://lookuga.com/2014/11/16/blogengine-net-security-directory-traversal-attack/">http://lookuga.com/2014/11/16/blogengine-net-security-directory-traversal-attack/</a>), we were not officially credited for it we had still created the bug report. Along with these security issues, we also had numerus issues with performance when we received large amounts of concurrent hits.

Once we finally had enough with the alerts and issues we decided to move away from BlogEngine.NET to another solution.

We looked at quite a few alternatives, but we decided to choose a static site generator instead of using a dynamic content backend system.

We decided to go with a static site generator because of the following reasons:
<ul>
<li>Quicker Load Times
	<ul>
		<li>We can fully use CloudFlare's Static Edge Cache for the entire site</li>
		<li>No backend processing – it is simple HTML files</li>
	</ul>
</li>
<li>No Backend so no way to exploit it directly, unless you get access to github :-)</li>
<li>Less memory usage</li>
<li>More scalable if used for larger frontend projects</li>
</ul>

The static site generator we decided to use was Jekyll. We choose Jekyll, first because it has a cool name, secondly it is directly supported by GitHub (it was created by the same guy who founded GitHub) and thirdly is has some pretty amazing stuff included which we decided to use:
<ul>
<li>Jekyll-paginate – Enable paging</li>
<li>Jekyll-sitemap – Auto Sitemap generation</li>
<li>Jekyll-redirect-from – Always us to redirect old URLs from BlogEngine.NET to new preferred format of Jekyll</li>
<li>Minification both CSS and HTML (HTML via liquid add-on)</li>
</ul>

The entire switch took around a week and a half to do for the following:
<ol>
<li>learn everything about Jekyll</li>
<li>Create a new, simplistic and improved theme</li>
<li>Full migration of content and images</li>
<li>Create all the required redirects (pretty easy with plugin)</li>
<li>Configure GitHub (domain migration/CloudFlare)</li>
</ol>

Now with Jekyll there was a bit of a learning curve, but once you go through the docs provided both by Jekyll and GitHub it makes it a lot easier, I have committed the source of the blog and required configuration to GitHub, so if anyone is interested in looking through and learning a thing or two from it, please go ahead.

<a href="https://github.com/lookuga/lookuga.github.io">https://github.com/lookuga/lookuga.github.io</a>

Important Reads:
<ul>
<li><a href="http://jekyllrb.com/docs/usage/">http://jekyllrb.com/docs/usage/</a></li>
<li><a href="http://jekyllrb.com/docs/structure/">http://jekyllrb.com/docs/structure/</a></li>
<li><a href="https://jekyllrb.com/docs/templates/">https://jekyllrb.com/docs/templates/</a></li>
<li><a href="https://jekyllrb.com/docs/configuration/">https://jekyllrb.com/docs/configuration/</a></li>
<li><a href="http://jekyllrb.com/docs/frontmatter/">http://jekyllrb.com/docs/frontmatter/</a></li>
<li><a href="https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/">https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/</a></li>
<li><a href="https://jekyllrb.com/docs/github-pages/">https://jekyllrb.com/docs/github-pages/</a></li>
<li><a href="https://help.github.com/articles/using-jekyll-as-a-static-site-generator-with-github-pages/">https://help.github.com/articles/using-jekyll-as-a-static-site-generator-with-github-pages/</a></li>
<li><a href="http://jch.penibelst.de/">http://jch.penibelst.de/</a></li>
<li><a href="https://github.com/jekyll/jekyll-redirect-from">https://github.com/jekyll/jekyll-redirect-from</a></li>
<li><a href="http://jekyllrb.com/docs/permalinks/#permalink-style-examples">http://jekyllrb.com/docs/permalinks/#permalink-style-examples</a></li>
</ul>