---
title: "Post 21: Promises vs. Async/await"
layout: rss
date: 2019-08-05
draft: false
---
<script src="https://cdn.rawgit.com/google/code-prettify/master/loader/run_prettify.js"></script>
<body onload="prettyprint()">
The last time you heard from me was when I was struggling with Javscript promises. Here's what I said about the problem in the previous post:
<br>
<div style="margin-left: 1em;"">"In the sheet of URLs, a duration can also be included in an entry. This represents, in milliseconds, how long a url should be displayed. I want to create a for loop (<i>I think</i>) that has a promise in it (<i>I think</i>) so that the url does not change until the previous url has been shown for the desired amount of time. I tried a solution that used recursion, but since I want to infinitely rotate the urls (until the browser window is closed), this creates stacks on stacks on stacks."</div>
<br>
I have learned 2 <b>grand</b> things since then: <br>
&emsp;&emsp;1. I don't actually need to use promises here because there is nothing asynchronous happening, so setTimeout is our better friend here<br>
&emsp;&emsp;2. Using setTimeout in a recursive function is good! There will only be one frame for the function on the stack at one time (<a href="https://develoger.com/settimeout-vs-setinterval-cff85142555b">https://develoger.com/settimeout-vs-setinterval-cff85142555b</a>)<br>
<br>
<br>
So with these 2 things in mind, I got what I needed. I created a function <i>setDurations</i> where for a each tab, I call setTimeout with the specific tab's duration. After this duration has passed, the (recursive) callback function to switch to the next tab is called. Here is my code:
<br>
<pre class="prettyprint"><code>function setDurations (urlSettings, openTabs, tabIdx, time) {
	setTimeout(function() {
		chrome.tabs.update(openTabs[tabIdx].id, {active: true});
		const nextTabIdx = (tabIdx + 1) % openTabs.length;
		setDurations(urlSettings, openTabs, nextTabIdx, getDuration(urlSettings, openTabs[tabIdx].url));
	}, time);
}
</pre></code>
And it works like a charm :smile:
<br>
<br>
My next endeavor was to handle faulty urls in the google sheets document. My goal was to create a fetch request to the given url, and then add that url to my set if (and only if) the status returned is "ok." When playing around with recursive promises again, I hoped that I could make this better. Because we want to move on to check the next url no matter the result of current fetch, a recursive call is needed in both the .then() and the .catch() blocks, which is not ideal. I could not get my recursive solution to work originally (more about this later), but here's what I came up with after some research (note that the "async" before the function definition makes it so the function returns a promise, with the returned value being the "resolved" value of the promise):
<br>
<pre class="prettyprint"><code>async function recursiveCheckUrls(entries, settings, index) {
    if (index === entries.length) return settings;
    let urlString = entries[index]['gsx$url']['$t'];
    let duration = entries[index]['gsx$duration']['$t'];
    fetch(urlString)
        .then(() => {
            settings[urlString] = duration;
            recursiveCheckUrls(entries, settings, index + 1);
        })
        .catch((err) => {
            console.log(urlString + ": " + err);
            recursiveCheckUrls(entries, settings, index + 1);
        });
}
</code></pre>
While reading about other approaches, I came across the "async/await" method, which allowed for a non-recursive method (and also allowed me to understand why my recursive approach was not working!!):
<br>
<pre class="prettyprint"><code>async function checkUrls(entries, settings, index) {
	for (let i = 0; i <= entries.length; ++i) {
		if (i === entries.length) return settings;
		let urlString = entries[i]['gsx$url']['$t'];
        let duration = entries[i]['gsx$duration']['$t'];
	    await fetch(urlString)
	        .then(() => {
	            settings[urlString] = duration;
	        })
	        .catch((err) => {
	            console.log(urlString + ": " + err);
	        });
	}
}
</code></pre>
So here, I wait for the current url to be fetched (and either added to the map of urls or not), and then move on to the next. Later, I showed my code to Ewa because she has been working a lot with promises and async/await. She told me that usually awaits are used to get rid of multiple .then() blocks. She sent me a really nice <a href="https://hackernoon.com/6-reasons-why-javascripts-async-await-blows-promises-away-tutorial-c7ec10518dd9">link</a>, too.<br><br>
One thing this article talks about is nicer error handling, where all errors (synchronous and asyncronous) can be handled by one try/catch block when we use await. In my case, I want to stay in the function and continue as normal if an error is thrown, so I put a catch block in the for loop:
<br>
<pre class="prettyprint"><code>async function checkUrls(entries, settings, index) {
	for (let i = 0; i <= entries.length; ++i) {
		if (i === entries.length) return settings;
		let urlString = entries[i]['gsx$url']['$t'];
        let duration = entries[i]['gsx$duration']['$t'];
	    try {
            let response = await fetch(urlString);
            if (response.ok) {
                settings[urlString] = duration;
            } 
        } catch (err) {
            console.log(urlString + ": " + err);
        }
	}
}
</code></pre>
This code is much nicer for me to read, though I'm still searching for some improvements... (if you have any suggestions, please reach out :smile:)
<br>
<br>
That was a lot of code, but it was worth writing down here. Besides all of this refactoring, today I also read about testing chrome extensions. I set up Selenium to automatically open Chrome with the extension already installed. This took me much longer than anticipated. But now it works - and tomorrow I will actually start testing. My plan is to create a dummy set of urls, and then loop through the html of the open tabs to make sure that valid urls were opened, and those that are invalid were not.
<br>
<br>
Until then, friends.
<br>
<br>
<br>
</body>