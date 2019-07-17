---
title: "Blog 16: New plans"
layout: rss
date: 2019-07-17T12:50:23+02:00
draft: false
---
For some reason, the task of blogging has totally escaped me the past couple of days. I've completed the Haskell chapters on recursion and lists, and I feel pretty accomplished! I'm currently learning about folding lists, which is not as pleasant. Here's an exercise from the book:
<br>
<br>
The following fold has an error. Fix it and then test it in your REPL.
<br>
<code>foldr const 'a' [1..5]</code><br>
<br>
If we check the type of <code>const</code> (a function that takes two arguments and returns the first), we get:
<br>
<code>const :: a -> b -> a</code>
<br>
<br>
Now, let's check the type of <code>foldr</code>:
<br>
<code>foldr :: Foldable t => (a -> b -> b) -> b -> t a -> b</code>
<br>
<br>
Do you see the problem? The type of <code>const</code> does not align with the type required by <code>foldr</code>. The solution is fairly simple: apply <code>flip</code> to <code>const</code>:
<br>
<code>foldr (flip const) 'a' [1..5]</code><br>
The type of <code>(flip const)</code> is:
<br>
<code>(flip const) :: b -> c -> c</code>
<br>
<br>
This is a solution that took me quite some time to figure out. To no avail, I was filling my notebook with scribbles and parentheses. The solution <code>:t</code> was just waiting for my in my REPL :smile:
<br>
<br>
Another thing that doesn't work:
<br>
<code>foldl (:) [] [1..3]</code>  (The (:) is the cons function that prepends a head to a list)
<br>
I really had no idea why this didn't work as I wrote it out. Here's what I wrote:
<br>
(([] : 1) : 2) : 3
<br>
([1] : 2) : 3
<br>
([2, 1]) : 3
<br>
[3, 2, 1]
<br>
<br>
But, no! The REPL throws an error because the type of the (:) function is <code>(:) :: a -> [a] -> [a]</code>. The first argument must be some object of type a, and the second must be a list that contains objects of type a, and the function returns a list that contains objects of type a. The arguments cannot be switched.
<br>
<br>
The topic of folding is very confusing for me, but checking the types of the functions in these exercises help me see the errors and how to fix them. I'll take more time tomorrow to work through the chapter.
<br>
<br>
I also met with Peri today to discuss my progress and the plan for the coming month. One suggestion he made is to rehearse my Haskell learnings through blog posts or lightning talks, hence the small exercise example above. Once I understand foldr and foldl better, I plan to write a more in-depth blog post on the topic. This is just a way to deepen my understanding of the topic. I shouldn't treat it like a university course and mechanically work through the book and exercises just to get it done. I should treat it as a topic that I want to learn and, more importantly, teach others about (of course this is not to say that I haven't been enjoying Haskell - because I do! Suprisingly!) Writing blog posts about any of the things I am learning is a way to articulate my thoughts, and I think this is especially helpful for something like functional programming, which confused and angered me in a previous life :leaves:
<br>
<br>
After this, I met with Ugurcan to talk about the Heartbeat project and my goals. The first goal he suggested is to create a simple "Hello World" application and deploy it, just to learn about docker and the dust platform. This was a great suggestion, because it is something that I need to understand before I can move on with this project.
<br>
<br>
I made many new plans today. I have also added 3 trainings/workshops to my TODO list thanks to Peri's and Ugurcan's suggestions.
<br>
<br>
So much to do! So much to see! So much to learn! :nerd_face:
<br>
<br>
<br>