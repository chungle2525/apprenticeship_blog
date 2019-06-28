---
title: "Day 8: (Only Sometimes) Go With Your Instinct"
layout: rss
date: 2019-06-28T16:30:23+02:00
draft: false
---
Today I worked on more Haskell. I also asked Sergii about the problem I shared in the previous post. As a reminder:<br>
<code> 6 / length [1, 2, 3] </code><br>
does not work
<br>
<br>
But, for whatever reason (which we now know),<br>
<code>6 \`quot\` length [1, 2, 3]</code><br>
works just fine.
<br>
<br>
The <code>length</code> function returns an Int, but it turns out that the '/' operator only works on the 'Fractional' typeclass, of which 'Int' is not an instance. The <code>quot</code> function works on instances of the 'Integral' typeclass. Also, both functions require the arguments to be of the same type :smiley:
<br>
<br>
Anyways... Wolfram shared a video (in the #apprenticeship channel) of an Agile lightning talk. The speaker talks about the basics of TDD and shares the very first step, which is simply "Think." This step was relevant in my talk with Peri today. He was talking about how it's usually the case that the ideas we have (regarding our work) when we are lying in bed (e.g. "AH! So <i>that's</i> the solution to my problem", or "I just came up with the greatest solution 'y' to some universal problem 'x.' I'm a genius!") are usually not as great the second or third time we think over them.
<br>
<br>
This has been relevant in many of my previous projects. I tend to jump on my first instinct on how to approach a problem, sometimes to later learn that either a) my instinct was wrong, or b) there was a much better solution. As shared in the video, the first step in TDD is just to think. It can be very powerful to practice TDD every day because it has the potential to make this process habit. I have participated in a few coding katas by now, and we always start off by reading the question and having some time to reflect and ask questions before we dive in. This is a process that is really good for me to practice.
<br>
<br>
So, when it comes to programming (or I suppose work in general), it is always good to go beyond your insticts. Think about the negatives of your approach or the alternatives to your method.
<br>
<br>
On the non-technical aspects of life, however, I do believe that it is good to go with your insticts :wink:
<br>
<br>
On the final note, my one-on-one with <span>&#193;</span>lvaro included some Espa<span>&#241;</span>ol! I'm very grateful for this because my Spanish is very rusty. Also, the language part of my brain has been in overdrive the past few weeks. More than once, I have answered German (which I <i>barely</i> understood) with Spanish. Apparently I just have to exercise that part of my brain more :sweat_smile:
<br>
<br>
Here, I'll go with the safe, universal farewell: :wave:
<br>
<br>
<br>