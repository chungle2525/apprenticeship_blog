---
title: "How to: Implement an RSS feed with Hugo"
layout: rss
date: 2019-06-26
draft: false
---

<p>Here is a guide to help you add an RSS feed to your Hugo blog.
<br>
1. Edit the config.toml file:
<p style="margin-left: 20px">a. Make sure the baseURL is valid (e.g. "https://leahchung.netlify.com")<br>
b. Add the following lines:<br>
	<code>
		[outputs]  
		home = [ "RSS", "HTML"]<br><br>
		[outputFormats]
		[outputFormats.RSS]
		mediatype = "application/rss"
		baseName = "rss"
	</code>
</p>
2. Edit the header.html file.
<p style="margin-left: 20px">a. Add the following line: <br>
	<code>
		&lt;link href="{{ .RSSLink }}" rel="alternate" type="application/rss+xml" title="{{ .Site.Title }}" /&gt;<br>
	</code>
	I added this in my 'header-widget' div, but this will depend on your theme.
</p>
3. Add an rss.xml file in the your_theme/layouts/ directory.  
Then add the code found <a href="https://gohugo.io/templates/rss/#the-embedded-rss-xml">here.</a>
<br>
<br>
4. Add the following to the top of each post markdown file:  
<p style="margin-left: 20px">
	<code>
		layout: rss
	</code>
</p>
Voila! This should do the trick, but I suppose everyone's unique theme will create unique issues.  
I hope you found this post useful!
<br>
<br>
<br>
</p>
