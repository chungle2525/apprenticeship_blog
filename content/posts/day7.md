---
title: "Day 7: Getting acquianted with Haskell"
layout: rss
date: 2019-06-27T15:50:23+02:00
draft: false
---
I'd like to start off by apologizing for the short blog post. I've been learning a lot of basics with Haskell so I dont have many interesting, noteworthy insights save the ones to follow. Enjoy :smiley:
<br>
<br>
Today, I completed 3 chapters of the Haskell Book. This book is written for absolute beginners, not only to Haskell but also to programming in general. This really forced me to get into the "wearing the white belt" mindset, because I did not want to skim any part with the chances of skipping over something important for Haskell.
<br>
<br>
I did come over a quite confusing problem that I will seek answers to:
<br>
<code> 6 / length [1, 2, 3] </code><br>
... does not work!
<br>
<br>
The type of the length function returns:  
<code> length :: Foldable t => t a -> Int </code>
<br>
<br>
For whatever reason,
<code>6 \`quot\` length [1, 2, 3]</code><br>
works just fine.
<br>
<br>
More on the "why" later...
<br>
<br>
On a non-Haskell-related-note, yesterday, I accidentally pushed my RSS feed post and I did not have time to look over it today.  
Hopefully, I wont see any issues or catch missing information. If so, however, updates will be coming your way :smiley:
<br>
<br>
<br>
</p>
