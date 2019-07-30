---
title: "Post 20: Async nightmares!!!!"
layout: rss
date: 2019-07-30
draft: false
---
Hello to all :smile:
<br>
<br>
The past few days have been spent working on a chrome extension. The purpose of this chrome extension is to be able to rotate between a set of URLs on the heartbeat monitors to give employees more insight on what's happening at HolidayCheck.
<br>
<br>
Now, you're probably thinking <i>an extension that rotates between tabs already exists</i>, and you'd be correct. But we want <i>this</i> extension to get some links from <i>somewhere</i>, open them up automatically, and <i>then</i> rotate between those tabs. Manually opening tabs every day for every monitor would be painful. So, up until yesterday, my extension opened specific urls (found in the code itself) in their own tab, and rotated between the tabs. Yesterday I attempted to put these links in an excel file in my One Drive, give my extension access to this file, and then use the Microsoft Graph API to fetch the data inside this file. Sadly, it didn't work. My app cannot be authorized to access any files unless it is logged in as someone, which would also be painful to do on all of the monitors.
<br>
<br>
So today I migrated this url file to good old Google Sheets. You can actually <i>easily</i> turn this Google Sheets document into an endpoint that serves you JSON. It's quite cool. Check it out <a href="https://medium.com/@scottcents/how-to-convert-google-sheets-to-json-in-just-3-steps-228fe2c24e6">here</a>.
<br>
<br>
But of course things never pan out that easy. Because I have little experience with asynchronous things (for lack of a better term), I was accessing a dictionary of urls that didn't have what I needed because the GET request to my Google Sheets didn't finish yet. Bad, bad, bad. I should've known better. I was just going crazy because I initialized my dictionary with dummy values, printed it out, and then printed the keys. When I extended the dictionary in the console, the urls were indeed there, but they were not being printed out in the place where I printed the keys. So it was printing these things when the urls weren't added yet, then adding the urls by the time I got there to extend the dictionary object 🥵
<br>
<br>
With Sebastian's help with promises, I got the functionality I wanted (and much, much cleaner code). But of course things never pan out that easy...
<br>
<br>
In the sheet of URLs, a duration can also be included in an entry. This represents, in milliseconds, how long a url should be displayed. I want to create a for loop (<i>I think</i>) that has a promise in it (<i>I think</i>) so that the url does not change until the previous url has been shown for the desired amount of time. I tried a solution that used recursion, but since I want to infinitely rotate the urls (until the browser window is closed), this creates stacks on stacks on stacks. 
<br>
<br>
Tomorrow, I will read about promises and hopefully solve this problem.
<br>
<br>
<br>