---
title: "Day 11: The fourth week already?!?!"
layout: rss
date: 2019-07-08T4:50:23+02:00
draft: false
---
It's so weird that it is already my fourth week at HolidayCheck. Time is flying (I just realized that I have probably said this at the beginning of every week of my (adultish) life).
<br>
<br>
Today, I worked through more of the Haskell Programming book. I went over pattern matching, case examples, and higher order functions. Though the book does a good job explaining the why's and how's, functional programming still feels quite unintuitive to me. One thing that is hard for me to conceptualize (and I tend to overthink) is function types. An example given in the book is:
<br>
<br>
<code>returnAfterApply :: (a -> b) -> a -> c -> b</code>
<br>
<code>returnAfterApply f a c = f a</code>
<br>
<br>
At first, only looking at the function type, I'm thinking: Ok, returnAfterApply takes a function and returns a function that takes a function and returns something of type <i>b</i>??? :sweat_smile:
<br>
<br>
But then I look at the function definitions and I think: Ohhhh, so it takes three parameters: 1. a function <i>f</i> that takes some thing of type <i>a</i> and returns something of type <i>b</i>, 2. something of type <i>a</i>, and 3. something of type <i>c</i>. Then it applies the function <i>f</i> to <i>a</i> and returns whatever is returned by <i>f</i> (something of type <i>b</i>).
<br>
<br>
Then all is good again in my brain. But still, I'm prepared for more unintuition.
<br>
<br>
Other things I did today include reading the Software Crafter book, doing part of a bash tutorial (which I really enjoy, thanks Masha!), and cloning the repo for Ugurcan's heartbeat project. I plan to make more progress on all of these things tomorrow as well. I feel like I have plenty to do, without feeling spread too thin. It's a good place to be :sunglasses:. But will it always be this good????
<br>
<br>
<br>
