---
title: "Day 15: Meetings galore"
layout: rss
date: 2019-07-12T12:50:23+02:00
draft: false
---
Today was filled with meetings. I had the daily, the "Blindspot" meeting with Alvaro and his whole group of people of which he's the PPM (not sure what to call this group), a meeting with Ugurcan concerning the setup of the Heartbeat project on my machine, a meeting with Wolfram, and my one-on-one with Alvaro. As a result, my Haskell book has collected (virtual) dust.
<br>
<br>
I spent a lot of my non-meeting time with the Elevator Saga again. I was having a problem where I was creating an event listener for each floor object (for the event where a person presses the up button or down button) in a for-loop. Each of these event listeners would then add the current floor to a set of floors called <i>upButtonFloors</i> and <i>downButtonFloors</i>, respectively. The problem with the following code is that, if there are 5 floors, the value of <i>floorNum</i> that was always being added to the sets is 5.
<br>
<br>
<code>for (floorNum = 0; floorNum < floors.length; floorNum++) {</code><br>
<code>&emsp; &emsp;floors[floorNum].on("up_button_pressed", function() {</code><br>
<code>&emsp; &emsp; &emsp; &emsp;upButtonFloors.add(floorNum);</code><br>
<code>&emsp; &emsp;}); </code><br>
<code>&emsp; &emsp;floors[floorNum].on("down_button_pressed", function() {</code><br>
<code>&emsp; &emsp; &emsp; &emsp;downButtonFloors.add(floorNum); </code><br>
<code>&emsp; &emsp;});</code><br>
<code>}</code><br>
<br>
This question turned my meeting with Wolfram into a JavaScript Closure meeting (instead of a meeting about ways to have the Heartbeat monitors rotate between different URLs). Wolfram taught me about the call stack and what happens with asynchronous instructions. We worked through a more general example in TDD bin that asynchronously added values to an array. We went over what works (and <i>why</i>) and what doesn't (and <i>why</i>). It was a lot to digest, but going through this example made everything a lot clearer. In the end, we learned that simply adding a "let" will reduce the scope of <i>floorNum</i> to just the body of the for loop, so when an event happens, the handler calls a function with the intended value. Though I know this is not a complete answer to "why this works."
<br>
<br>
If I were a more seasoned JavaScript programmer, I would have added the <i>let</i> in the first place and therefore would not have run into this problem. But I'm glad I did because it led me to ask Wolfram, which led to an in depth explanation of what is happening under the hood and how to fix it. If I had added the <i>let</i>, I would have no real understanding of the call stack, what happens when we call setTimeout(), and how asynchronous instructions are handled in JavaScript (which is single threaded, which I'm sure most of you know).
<br>
<br>
Regarding the Heartbeat monitors, there are quite a few chrome extensions that rotate between different URLs (one has the name "Rotisserie," which kind of displeases me because it makes me think of chicken) which, as of now, seems like the route I will take. The cool thing about this is that anyone who wants to add a feature may create their own application and add the link to the list of URLs on rotate. Alvaro was saying how this would be good for future apprentices/interns to contribute to as well. It would be an interesting why to learn how to create a web application while also adding value to the company!
<br>
<br>
So, my day flew by and it has come to an end. Next week I will move on to Haskell lists :smile:.
<br>
<br>
And the sun is finally out :sunglasses:
<br>
<br>
<br>
