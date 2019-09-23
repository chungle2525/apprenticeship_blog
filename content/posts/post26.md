---
title: "Post 26: Back to MUC"
layout: rss
date: 2019-09-20
draft: false
---
Only three weeks of the business phase remain. Time is <i>really</i> flying. I guess this has a lot to do with being a part of a different team every week, as there are so many things to learn and people to meet.
<br>
<br>
Last week I was with the Deep Learning team in Munich. One main thing they are working on is the chat feature. First of all, they want to increase the chat acceptance rate (which is the percentage of people who see the chat box that begin a conversation). Right now, there is a bug (which can only be fixed by the chat platform provider) where if a user clicks away the chat and navigates to another page, the chat feature will reappear. This can be skewing this acceptance rate because it is increasing the number of times a person sees the chat feature and does not choose to start a conversation.
<br>
<br>
Kamal is also working on the chat bot. Right now they want to identify and predict the top 20 intents (e.g. how to apply the Gutschein, what is an airline's baggage allowance, or hotel availability). So he is working on creating a model which predicts these top 20 intents with a high accuracy rate. The three intents which have automated responses are the following: Gutschein, baggage allowance, and recommendations.
<br>
<br>
The other main thing the DL team is working on is offer recommendations. We talked about the current offer recommendations and other potential criteria. One potential criterion is flight quality. This could be something like a flight at 9 am versus a flight at 11 pm, a flight with 1 connection vs. 2 connections, a layover of 1.5 hours versus a layover of 8 hours, or perhaps a destination airport that is 30 minutes from the hotel versus an airport that is 3 hours from the hotel. All of these examples show varying travel quality, and Thomas brought up that spending more time at the destination also brings value to the Urlauber. This creates an upsell opportunity. Because it could show up on page 4 or 5, an offer with a better flight that is 50 euros more expensive is potentially an attractive offer that may never be seen. This is the reason we want to recommend an offer like this to the Urlaubers: it puts an offer with great value that is harder to find (or at least takes more time to find) on the very first page.
<br>
<br>
This is something super powerful because we are making it easier for Urlaubers to find offers with higher value, with the potential of selling a pricier offer. It could be a win-win :smile:
<br>
<br>
Nadja is a working student and she is working with the PR team to (hopefully) determine what is the most frequent review topic. She created a model that embeds the sentences of reviews, showing them in a multi-dimensional graph. Right now, the model does not show any obvious clusters (meaning no significantly more frequent topics or keywords in the reviews). However, her test data is the reviews of only one hotel, so maybe more clusters will appear when she feeds more reviews into her model (I have a feeling that my wording doesn't make a lot of sense to anyone with data science knowlege, but the hope is to make sense to those who do not :sweat_smile:).
<br>
<br>
I also got a change to speak with Isabelle and Ulrike from PR about what they do for HolidayCheck. Their team is small, and they handle all TV, print, and online content. They must keep up with media trends and find ways to integrate it with informatoin from HolidayCheck. One examples is doing a piece on fake reviews with things such as how to recognize them, what to do about them, and what HolidayCheck is doing to fight them. They also create content for less serious/more fun topics such as Oktoberfest-themed hotels. In contrast to brand marketing, the PR team is more focused on quality over quantity. This means that they care more about how long they can maintain a reader/viewer's attention (which can translate to the quality of the information transfer) and less about the quantity of readers/viewers (but of course, having high quality <i>and</i> quantity is ideal). This was just a very brief overview of what they do, but it was definitely interesting to see how they are working towards creating and maintaining relationships with our audience.
<br>
<br>
In the mean time, I got to work a little bit with Scala (but not as much as I would have liked). I wanted to play around with Options and created a simple Paczki (Polish filled donuts) project to do so. I created a Paczek (singular of Paczki) class and a Shop class, and I created a method which checks if a shop has a Paczek in stock with a certain filling. If the Paczek is in stock, the method returns the Paczek's name (Some(paczek.name)). Otherwise, it would return nothing (Nothing). I showed the code to Lewis and he commented that it was organized in a very OO way, which just shows how used to OO design I am. We had a session today to talk about some modifications such as preferring 'sealed type' extensions over class instances. I'll work more on this during the week (I hope!).
<br>
<br>
The time is coming where I have to think of masterpiece ideas. It came faster than I could anticipate, so it totally escaped me to ask around for pain points or suggestions. Brainstorming sessions are also on this week's agenda.
<br>
<br>
Until then - Happy Monday!
<br>
<br>
<br>