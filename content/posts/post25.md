---
title: "Post 25: POZ"
layout: rss
date: 2019-09-13
draft: false
---
Today is Friday, Friday the 13th, Slack day, <i>and</i>, most importantly, Programmer's Day. Does anyone know why it's Programmer's Day? Because it's the 2^8th day of the year. Thank you Jacek for this important news :joy:
<br>
<br>
This week I was in Poznań, spending most of my time in meetings, trying to pronounce Polish words, and drinking beer with Markus. Can't complain about that!
<br>
<br>
I sat with the AdShop team, who are under some pressure these days because of an approaching deadline. I caught them at a stressful time, but I was still able to learn a lot from people and see what they are working on.
<br>
<br>
To give some background about what the AdShop team does, I should tell you that they are part of the b2b initiative. Marta is the PM of the AdShop team and she gave me in-depth explanations of each type of ad that HolidayCheck sells to hoteliers and business partners (for example hotel chains).
<br>They are as follows:
<br>
<p style="margin-left:6%; margin-right:4%;">1) Premium: A hotelier can choose to enhance their hotel page on HolidayCheck with a link to their own website, a special offer, a special "profile picture"-esque photo (for example of the staff or the manager), and a small blurb about the hotel.
<br>
2) Ranking: A hotelier can choose to show up at the top of the hotel list page (after a user makes a search). This ad can be booked on the city, region, touristic region (e.g. Bayerische Alpen), and country level.
<br>
3) Competition: This is where a hotelier chooses to put a banner for their own hotel on the hotel page of a competition hotel(s).
<br>
4) Branding: The Branding Ads are displayed on the right-hand side of the hotel list. This entails a larger banner and larger photo of the hotel.
</p>
This background information was complemented by the information I got from Alex. Alex (UX Designer, Writer & Guru (:wink:)) showed me the campaign manager that they are working on (a lot of which she designed). This is service where HolidayCheck sales managers can form advertisement offers for hoteliers. They can pick the type of ad(s) and see the prices for each available week. Once created, the form can be sent to the hotelier for review and/or confirmation, and then an actual order is created.
<br>
<br>
Alex told me that the ads are often bought during an in-person meeting where the time frames and types of ads are chosen. This campaign manager will hopefully help this process. In the face-to-face meetings, a large excel spreadsheet is shown to the potential customers where they can see which weeks are available and which prices HolidayCheck is offering. As far as I understand the campaign manager is a tool for the sales managers during these meetings <i>and</i> potentially a tool to replace them. I thought one benefit that face-to-face transactions have (over booking online/via email) is that prices can be negotiated, possibly giving the hoteliers a better deal (which would make the hoteliers prefer the face-to-face transactions). I asked Alex about this and she said that the prices for each ad type + location + week combination are predetermined, so this does not cause any issues. They had user testing at the end of this week - so I'll hopefully learn about the results soon :smile:.
<br>
<br>
I was able to "pair" with Jannick and Piotr, too, which was pretty cool. A little bit of JavaScript and a little (little) bit of Scala :sweat_smile:. Jannick had to add a "back to offer details" button on the page visible when a customer/business partner is on the "checkout" page. Piotr was working on the method that removes sold out (unavailable) ad slots from the final offer. This is needed because when a sales manager makes an offer for a hotelier, the hotelier goes through the offer and can accept it. This process may take some time, so it is possible that an ad slot was bought by someone else by the time the hotelier accepts the offer and an actual order needs to be created. So Piotr wanted to make a check that all products (ad types) and variations (date and quantity) were still available, and delete those which are sold out from the order. I really appreciate how they both took time to not only show me what they were doing but also explain each step they wanted to take.
<br>
<br>
Piotr especially made an effort to explain a lot of the Scala stuff (which wasn't all <i>completely</i> foreign to me thanks to my Haskell knowlege), which was really interesting and cool! One thing is he compared having a Option object versus having an if else flow. The typical OO way of thinking is: "If some fetched object is null, then return null. Otherwise, access some member variable <i>name</i>, a String for example, and return it." The way that Piotr showed me in Scala was thinking more along the lines of "No matter what this object is, we'll return a <i>Some String</i> value." It was much nicer to both code and read, because we don't have to explicitly take care of each situation. We just wrap the value to say "maybe we'll get an object with a name, maybe we won't." I will spend more time on this next week and actually blog some code to understand it a little better.
<br>
<br>
Separate from the A-Team, Michał spent some time explaining the Wave Design System, which he, Luis, Jens and Bruce work on. I did get a brief rundown on the Design System from Luis one day on the tram to work. Previously, every element of HolidayCheck's website was (re)developed by every team that needed to use it. For example, two teams could spend time on creating a "search" button, where on one page it could look slightly different (in color, size, font-size, border radius, etc.) than another. The goal of the Wave Design System is to define these elements (and things such as colors, font sizes and shadow sizes) for use and reuse. This, in turn, will save time for developers who would otherwise create these elements on their own. That's cool :thumbsup:.
<br>
<br>
I learned a lot this week, and I know Markus and I both felt extremely welcome. We got the chance to hang out with some employees outside of work and get to know the city better. I definitely recommend visiting if you have the chance! And if you ever consider booking a city tour - <i>forget it!</i> Jannick is a better solution (seriously, he knows so much about the city and it was such a pleasure to walk around with him).
<br>
<br>
Next week I will be joining the ML team - which will also be quite interesting. I'm grateful for the past week in Poznań and am excited for the week to come! Oh - and expect some Polish cookies on Monday!
<br>
<br>
<br>