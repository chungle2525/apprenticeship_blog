---
title: "Post 18: Good practices"
layout: rss
date: 2019-07-23T12:50:23+02:00
draft: false
---
I first started today with a kata, in which we are creating a simple assembly code parser. Kay had brought up that we should start our katas by discussing a goal, which is something that we overlooked before. Our current code supports the "mov" (move an integer value into some register), "dec" (decrement the value contained in some register), "inc" (increment the value in some register), and "jnz" ("jump not zero": jump some number of instructions forward or backward as long as some register does not contain 0) commands.
<br>
<br>
Today, we refactored our code. We created a state object which holds the registers, program counter (<i>pc</i>), error status, and the program (a list of <i>commands</i>). This is much more readable, and it is good design to wrap all of these attributes in one object. We then modified our functions to be contained in a dictionary, where the key is the command and the value is the function that handles this command. It looks like this:
<br>
<code>const Interpreters = {<br>
&emsp;&emsp;"mov": movCommand,<br>
&emsp;&emsp;"inc": incCommand,<br>
&emsp;&emsp;"dec": decCommand,<br>
&emsp;&emsp;"jnz": jnzCommand<br>
}
</code>
<br>
That way, an instruction can be called like so:<br>
<code>const command = commands[state.pc];<br>
const [instruction, ...args] = command.split(' ');<br>
Interpreters\[instruction\](state, args);
</code>
<br>
<br>
Right now, we do not have a class object to wrap the state object and these methods into one thing. We discussed this, but it was brought up that because we only have one state instance, it might not be necessary to create this class object. Maybe this is still up for debate, because passing the state object with each call of these methods does not seem necessary either.
<br>
<br>
It does feel more beneficial when we do the katas this way, because I am learning about design and programming with a goal other than to just solve the kata (this is not to say that we ignored good coding practices, but it wasn't specifically a goal that we discussed every day). Also, because this kata has many parts (where more instructions are added), it was a good idea to do the refactoring (kind of) in the beginning to make our lives easier later :smile:
<br>
<br>
I also worked on Docker today. I worked on the tutorial found <a href="https://docs.docker.com/get-started/">here</a>. I am just not sure how much of the tutorial is applicable to the deployment process at HolidayCheck because of dust and kubernetes. Peri gave me and Markus the Dust platform training, and I surprisingly did not have many questions during the training. But, more and more questions arose as I was completing this docker tutorial and as I began the process of deploying the Hello World app (as the first step in the Heartbeat monitor journey). More on this tomorrow :)
<br>
<br>
I ended my day with a meeting with Álvaro (oh, and writing this blog post) concerning the whole compensation process. I learned a lot about his team's tenets, how/when/why salaries increase at HolidayCheck, and the north of Spain :sunrise_over_mountains:.
<br>
<br>
See you tomorrow :wave:
<br>
<br>
P.S. Sorry I've been MIA the past few (business) days. :sweat_smile:
<br>
<br>
<br>