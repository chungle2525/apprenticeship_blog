---
title: "Post 19: Interview Blues (and deployment whew's)"
layout: rss
date: 2019-07-24
draft: false
---

I wanted to start this blog post with a relfection on the Software Crafter chapter about interviews. Sandro talks about how software crafters should (and shouldn't) interview cadidates. He writes that having phone interviews, writing code on paper or a white board, and only testing algorithmic knowlege or easily google-able problems (as opposed to giving a problem closely related to the actual work done during the job) are recipes for disaster. Or, rather, <i>not</i> recipes for success.
<br>
<br>
This chapter really surprised me because Sandro is talking down upon many interviewing techniques that I had experienced over, and over again while I was interviewing for my first full-time job just several months ago. I thought these methods were <i>good</i> and <i>normal</i>. I thought interviewing was something that will always feel like an uncomfortable and unnatural interrogation. I had a few great interviews where the interviewer was kind, personable, and did not make me feel like every word I spoke had the potential to kill me*. <i>I got lucky with those interviews because they were the exceptions</i>, I thought.
<br>
<br>
But Sandro emphasizes that we should treat the candidate like a peer in order to have the highest potential to see what it is like to actually work <i>with</i> this person. And he reminds the reader that the candidate is also interviewing the company to see if he/she would enjoy working there.
<br>
<br>
I remember one technical interview (that surprisingly did not blatantly test an algorithm) where the question was incorrect. The interviewer wanted me to do something with converting US Dollars to Euros (I don't remember the exact problem), and the conversion rate was reversed (stating that in order to convert US Dollars to Euros, one must <i>multiply</i> by, for example, 1.2 instead of <i>divide</i>). When I brought up the mistake to the interviewer, I was really shocked to see his reaction. He was very taken aback and said "oh, uh... yeah, you're right. Let's carry on with the correct way." But as I kept working through the problem, the interviewer acted very distant and did not seem to be paying full attention. After some time had passed, he finally said, "honestly I have no idea if you're going in the right direction because my solution was based around multiplying the conversion rate instead of dividing. Can you start over and solve the problem by multiplying?". Of course I did what he asked and, as a result, did not get as far in solving the problem as I would have liked.
<br>
<br>
Leaving this interview, I was definitely annoyed by the interviewer. The problem for me is not about who was right and who was wrong. Nor was it about him asking me to solve the problem twice. The problem is that he was not able to accept a solution that was different from his own. He had me sovle the problem again just so my solution was more in-line with his. Was he testing to see if my solution would be the exact same as his? Would any solution different to his own result in a "docking" of points? Who knows?
<br>
<br>
In this situation, I would retrospectively say that this interviewer did not move on to the next round of <i>my</i> interviews. Of course I cannot judge a company based on one employee, but it still left a sour taste in my mouth.
<br>
<br>
On another note, today I worked on docker, dust, and dmc (oh my!) and I finally deployed my Hello World app! Hooray!!!!
<br>
I was having a problem where my dmc deploy command would just cause the possible dmc commands to be printed to the terminal, so I knew I was doing <i>something</i> wrong, but I didn't know what. I seeked others for help which led me closer to my goal, no doubt. But I was still stuck and I had no idea why! I finally sent out an S.O.S. to Peri, and he really did save my shi(p/t). Some problems were as follows: I was using the wrong dmc (:sweat_smile:), there was a typo in my command (silly mistake, but hard for me to catch because the command was so long - I also learned from Peri that it can be reduced by omitting things already included in the deploymate.json file), I had an incorrect health check path ("/health" instead of "/_health"), and there was a misallocation of memory (as npm start takes up a lot of memory. This is something that needs to be changed, but more on this tomorrow).
<br>
<br>
Now I will go to the grocery store and continue reading about microservices later tonight.
<br>
<br>
Merry mittwoch!
<br>
<br>
* <i>Dramatized</i>
<br>
<br>
<br>