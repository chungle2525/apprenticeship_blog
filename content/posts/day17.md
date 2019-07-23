---
title: "Post 17: It takes a village!!"
layout: rss
date: 2019-07-18T12:50:23+02:00
draft: false
---
Today was a Haskell day. My current endeavors include foldr and foldl, and believe me: the going got tough.
<br>
<br>
One thing that confused me is the following:
<br>
<code>Prelude> foldr const 0 ([1..3] ++ undefined)</code><br>
<code>>1</code><br>
This works!<br>
(Note that simply concatenating <i>undefined</i> to a list throws an error, because the list - in its entirety - is evaluated, and the (++) function requires two list arguments.)<br>
(Also note that <i>const</i> takes two arguments and returns the first argument.)<br>
(Also also note that foldr works like so: <br>
<code>foldr f z (x:xs) = f x (foldr f z xs)</code>)<br>
<br>
Let's name our list ([1..3] ++ undefined) <i>lst</i>. Here is what happens first:
<br>
<code>foldr const 0 lst = const (head lst) (foldr const 0 (tail lst))</code>
<br>
Since the <i>const</i> function just ignores the second argument, 1 is returned.
<br>
<br>
But, when I wrote this out on paper, I was getting so confused:<br>
<code>(const 1 (const 2 (const 3 (const undefined 0))))</code><br>
<i>Why doesnt 'const undefined 0' throw an error?</i> Because it is never evaluated as the outer most parentheses are evaluated first, and <b>const just ignores the second argument</b> (bold for emphasis).
<br>
<br>
As for foldl:<br>
<code>Prelude> foldl const 0 ([1..3] ++ undefined)</code><br>
<code>>*** Exception: Prelude.undefined<br>
>CallStack (from HasCallStack):<br>
>&emsp;&emsp;&emsp;error, called at libraries/base/GHC/Err.hs:78:14 in base:GHC.Err<br>
>&emsp;&emsp;&emsp;undefined, called at <interactive>:119:26 in interactive:Ghci20</code><br>
This doesn't work!<br>
Here's how it is written out on paper:
<br>
<code>((((1 \`const\` 0) \`const\` 2) \`const\` 3) \`cons\` undefined)</code>
<br>
Here, the outermost parentheses contain <i>undefined</i>, and therefore an error is thrown. (I put the \`\` around <i>const</i> to make it an infix operator for visual purposes. Otherwise, the expansion looks similar to that of foldr).
<br>
<br>
This really confused me. I was thinking: <i>How does foldr know where the end of the list is without having to evaluate the undefined part and foldl doesn't? How does foldr know when to stop looking for more elements in the list and foldl doesn't?</i>
<br>
<br>
But after some help from Lewis, Frank, Francesco, and Daniel (and God (kidding)), it all makes sense. It was funny to see the confusion this question caused, but it thankfully came to a resolution :smile:
<br>

Tomorrow I will (start my day at the Ausländerbehörde at 7:30*, then) implement some functions (which I already completed with recursion) using folds such as <i>myOr</i> (a function that applies logical or to a list of booleans), <i>myAny</i> (a function that returns whether or not some value in a list meets a certain condition), and <i>squish</i> (which flattens a list of lists into one list). It will be pretty tough to get out of the recursive mindset and implement these functions with folds, but I'm sure I'll come out alive :sweat_smile:
<br>
<br>
I will also do some research on the testing pyramid and Docker (whether that be using online or human sources).
<br>
<br>
Signing off! :wave:
<br>
<br>
<br>
<br>
* When I was at the Ausländerbehörde the other day, I ended up waiting in the wrong line for 1.5 hours, only to get to the correct place for Blue Card applications and be told that there were no more spots for the day. At first I was really upset and annoyed that I couldn't get an appointment, but now I realize that maybe it was a blessing because, in said correct place, I saw people wearing suits, and I was wearing running shorts and a t-shirt.
<br>
<br>
<br>