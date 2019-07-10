---
title: "Days 12 & 13: Homework"
layout: rss
date: 2019-07-10T12:50:23+02:00
draft: false
---
Yesterday I spent my time completing the bash tutorial and going through the Haskell book.
<br>
<br>
Here is something I came accross in the Haskell book yesterday, regarding function composition:
<br>
<br>
"<code>(.) :: \[1\](b -> c) -> \[2\](a -> b) -> \[3\](a -> c)</code>
<br>
<br>
In English:<br>
1. given a function <i>b</i> to <i>c</i><br>
2. given a function <i>a</i> to <i>b</i><br>
3. return a function <i>a</i> to <i>c</i>
<br>
<br>
The result of (<i>a</i> -> <i>b</i>) is the argument of (<i>b</i> -> <i>c</i>) so this is how we get from an <i>a</i> argument to a <i>c</i> result. We’ve stitched the result of one function into being the argument of another."
<br>
<br>
This is another example of initially being very confused as a result of overthinking. I think point 3 is what really tripped me up. The wording of "returning a function" is weird to me, but the book does a nice job of explaining what exaclty happens. And for that, I am very grateful :smile:.
<br>
<br>
I also spoke with Wolfram and Markus (Scheuermann, not Heilig) about potential additions to Ugurcan's Heartbeat project. We discussed making the information more personal, with hopes to spark conversation. Markus said something like "information that encourages action." I think that's a good mindset to have going forward with this project. Wolfram and I briefly discussed our first step: Come up with a way to have multiple urls on rotation, where one can easily add/remove urls displaying different information. Exciting!
<br>
<br>
Today I did more Haskell and read some of the Software Crafter book. I also spent some time refreshing my memory on the short stories of Jorge Luis Borges (this urge was sparked when I saw the Haskell book quote him at the beginning of the recursion chapter), and I stumbled accross some information that he was incredibly racist and said awful things about black people. That was a disappointing tangent to which, oddly enough, the Haskell book led me.
<br>
<br>
But back to the main path of focus: Recursion, hooray! Here's one of the first examples they give, where a number <i>n</i> is incremented <i>times</i> times:
<br>

<code>incTimes :: (Eq a, Num a) => a -> a -> a</code><br>
<code>incTimes 0 n = n</code><br>
<code>incTimes times n = 1 + (incTimes (times - 1) n)</code>
<br>
<br>

Then the function is called like so:<br>
<code>Prelude> incTimes 10 0</code><br>
<code>10</code><br>
<code>Prelude> incTimes 5 0</code><br>
<code>5</code><br>
<code>Prelude> incTimes 5 5</code><br>
<code>10</code>
<br>
<br>
The only unintuitive thing, for me, is seeing <code>incTimes 0 n = n</code>. It's strange to see how this is how base cases (and, similarly, conditionals) are defined. It's just weird not to see an <i>if</i> in there.
<br>
<br>
Otherwise, things are smooth sailing with Haskell. Things are also smooth sailing regarding my Bürgerbüro visits... I finally got my tax ID!!!! The next step is the Ausländerbehörde, which is even more complicated and even more inaccessible :sweat_smile:.
<br>
<br>
More on recursion tomorrow :smile:
<br>
<br>
<br>
