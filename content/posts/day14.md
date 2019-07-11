---
title: "Day 14: Errors, Errors, go away"
layout: rss
date: 2019-07-11T12:50:23+02:00
draft: false
---
My day started normally with a long hike to work, a daily, and a kata. Today, Wolfram joined the kata, but neither Masha nor Kay could join and Markus had to leave early.
<br>
<br>
Our current kata does not involve TDD (:scream:). The problem is called "<a href="https://play.elevatorsaga.com">Elevator Saga</a>." Each level provides a task to move <i>x</i> amount of people in some amount of time, using only a certain number of elevators. The simulator is the main source of testing, which provides random input to test your solution.
<br>
<br>
In the katas that I joined, we only made it to level 5. Our next step was to refactor to make it more readable and pass the simulation more often (:sweat_smile:). Wolfram was grilling me with all these questions: "What is your goal?", "How do you know when you have improved?", "What is your approach?", "What do you want to learn from this problem?". I never thought about neither these questions nor their answers. My approach was just to pass each level.
<br>
<br>
So after explaining the half-baked solution to him, Wolfram suggested many ways to make the code more readable. He also taught me that creating an event listener inside of an event listener results in only creating the inner event listener when the outer even is triggered (and, it will do this <i>every</i> time). This is <i>bad</i>. My solution to this aspect was to create an event listener once for each floor object. There are many other ways in which the code needs to be improved. Right now when it is passing a floor on which people are waiting, the elevator does not pick them up. More on this tomorrow.
<br>
<br>
I also worked on Haskell today which was focused on recursion. I was getting some pretty headache-y errors in the REPL when trying to create a function that took an integer <i>n</i> and return a list that contains each digit, in order, of <i>n</i>.
<br>
<br>
Here is the error:
<p>
<code>Non type-variable argument in the constraint: Num [a]</code><br>
<code>(Use FlexibleContexts to permit this)</code><br>
<code>&emsp; When checking the inferred type</code><br>
<code>&emsp; &emsp; go :: forall a. (Integral a, Num [a]) => a -> [a] -> [a]</code><br>
<code>&emsp; In an equation for ‘digits’:</code><br>
<code>&emsp; &emsp; digits n</code><br>
<code>&emsp;&emsp; &emsp; = go n []</code><br>
<code>&emsp;&emsp; &emsp; where</code><br>
<code> &emsp;&emsp; &emsp; &emsp; go num list</code><br>
<code> &emsp;&emsp; &emsp; &emsp; | num == 0 = list</code><br>
<code> &emsp; &emsp;&emsp; &emsp; | otherwise = go (num \`div\` 10) ([num \`rem\` 10] + list)</code><br>
</p>

It turns out I was creating my list incorrectly in the recursive call.
<br>
Instead of <code>([num \`rem\` 10] + list)</code>, I need <code>((num \`rem\` 10) : list)</code>. This was kind of hard to figure out because the error message is hard to interpret.
<br>
<br>
Time to end my workday normally: with a long hike home. Only this time, it's raining.
<br>
<br>
<br>

