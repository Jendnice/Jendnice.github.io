---
layout: post
title:      "What Kind of Sorcery is This? "
date:       2020-05-02 19:34:01 +0000
permalink:  what_kind_of_sorcery_is_this
---

**_Unlocking the Power of Chrome DevTools_**

One of the discoveries I found extremely cool during bootcamp was that you can inspect websites through Chrome DevTools. And even open up a console in the DevTools and code JavaScript in it. Who knew that there was so much fun (and so much info!) accessible through a few simple keyboard commands! In this blog, I’m going to explain three ways I use Chrome DevTools.

But first! Let’s start your console:

Open up a webpage in Chrome. For me a new tab yields a beautiful pic and quote from Momentum’s Chrome extension, so I’ll use that for our example. (Feel free to use whatever page you wish.) Now, press and hold the “ctrl”, “shift” and “j” keys, so you have all three pressed at the same time. Then release them. This should open up a blank gray screen on the righthand side of the page. Congratulations! You’ve just opened your first DevTools console. There are a ton of awesome things you can do in here, but for today we’re going to focus on three. Ready for number 1? Let’s do it.
	
- ** Fetch an API**

If you want to pull data from another API, you can fetch it through the DevTools console, utilizing JavaScript. To do so, your code would be similar to the following:

```
fetch('http://example.com/movies.json')
  .then(response => response.json())
  .then(data => console.log(data));
```

The reason I say similar is because you need to replace the example URL above with the URL you’re fetching from. There’s a great example of this being done (and additional info about fetching an API!) from [https://www.sitepoint.com/introduction-to-the-fetch-api/](https://www.sitepoint.com/introduction-to-the-fetch-api/)

In the above piece, they fetch the top five posts in a reddit thread through the following:

```
fetch('https://www.reddit.com/r/javascript/top/.json?limit=5')
  .then(response => response.json())
  .then(data => console.log(data));
```

If you enter the above into your console, sure enough you’ll see the following response:

```
{kind: "Listing", data: {…}}
data:
after: "t3_gbiq0x"
before: null
children: (5) [{…}, {…}, {…}, {…}, {…}]
dist: 5
modhash: ""
__proto__: Object
kind: "Listing"
__proto__: Object
```

In your console, click through the arrows to open the above response further. For example, look at the “children” elements. There are five, because we fetched the top five posts. Pretty neat! 

So fetching is super fun, and makes you feel really nifty, but if you’re new to programming, or are even just looking to dabble in your DevTools console for fun, you might not know when you’d actually need to fetch an API. The following trick, however, I’ve already used quite a bit for my own personal learning. (And even some job application questions!)

- ** Search for something on a webpage**

This sounds pretty straightforward and maybe a bit dull, but hold on. Let me explain. I don’t mean Google-searching. Or hitting “Ctrl” and “f” on your keyboard to search a webpage. I mean, being able to search the elements that make up the webpage. Let’s see this in action.

Start the same way we did before we looked at Fetch an API. (Open any webpage and click the “ctrl”, “shift” and “j” keys.) Now, in your console (that gray screen on the righthand side), type the following and hit enter:

`document.querySelector("head")`

What do you see? You should see something like the following:

`<head>..</head>`

And, when expanded, this probably looks something like this:

```
<head>
	<meta charset="utf-8">
<title>New Tab</title>
<meta name="viewport" content="width=device-width">
<link rel="stylesheet" href="css/style.min.css">
	<style>..</style>
```

(And it continues on from there.)

What you’ve just done is taken that webpage (the “document” piece of your code), and applied a search on it (the “.querySelector” part), utilizing a specific search term (in this case we used “head”).

As a response, we see the “head” element of that particular webpage. See where my code says, “New Tab” above (in between the `<title>` tags)? That’s because the webpage I’m using my DevTools console in was a *new tab* on my browser.

This can be very helpful if you’re trying to find something specific in a webpage’s HTML. But if you know more info, you can also look more directly at the different HTML pieces. For example, instead of using “querySelector”, you can search for a specific class name via the following code:

`document.getElementsByClassName(classname)`

In my new tab, I know there is a class name “overlay loading-overlay” so if I needed to find that particular HTML element, I could do the above typing that class name in, as follows:

`document.getElementsByClassName("overlay loading-overlay")`

Here’s what I get back:

`HTMLCollection [div.overlay.loading-overlay]`

If I expand that HTMLCollection array, I’ll see that there is one element in it, because there is only one element with that class name in the document. (There is also a ton of other info about our searched element like outerHTML, nodeName, outerText, and more!)

Still not impressed by our ability to dig into the nitty gritty behind the scenes of webpages? Don’t worry. The next trick is something I actually use on websites *all the time*. And not just for coding purposes.

- **Pull something from a webpage (ex. a picture, video, or some text)**

How often have you been on a webpage where you wanted to save the image or video being shown, or grab the text displayed, only to have the website throw a cold shoulder and prevent you from being able to do it? No longer, friends. No longer.

For this, we’re actually going to inspect the webpage. So, you can still open your DevTools up the same way as before, but then click the “Elements” section that is just left of the “Console” section in your DevTools. (Alternatively, you can right click on the webpage, and choose “Inspect” in the menu.”)

Ok, so now you see a ton of code. What is this? This is the webpage’s html! *(See all those “class=…” scattered throughout? Those are the class names we searched in the previous trick!)*

But onto the good stuff—how can we use this? It’s pretty simple, really!

Find the element on the website that you want to grab. For example, let’s say I want to grab the time displayed on my Momentum screen. Find the arrow in the top left of the DevTools window. You’ll notice that when you roll your mouse over this arrow a little dropdown says, “Select an element in the page to inspect it. Ctrl + Shift + C”. You can either click this arrow, and then click the element on the screen you want to inspect; or, instead of clicking the mouse, you can press the key commands given, (Ctrl + Shift + C), and then click on the element you’re interested in. Either method will allow you to inspect that particular element. In our example, we want to use the time being displayed.

So, with two clicks—one on the arrow in the top left of our console, and one on the time in the actual webpage—and we can see the following highlighted in our DevTools Elements:

`	<div class="time">6:25</div>`

Voila! All I have to do is highlight this element, right click, go to copy, and then choose “Copy element.” That will copy the entire html code for that element. If all I want is the time itself, not the whole element, I can do this by right-clicking, but instead of going to “Copy”, click on “Edit as HTML.” From here, I’m able to simply highlight the time in the console and copy it via “Ctrl” + “c”. (Or you can use your mouse to copy it.) Then I can paste that content wherever I want:

6:27

Done! This might not seem like a lot, because all we did was grab the time, but this same process can be applied to longer content, pictures, and even videos. And sometimes you have to dig a little! The time element was super easy for us to find and grab. Pictures are often buried a bit deeper in the html. In the example above, if I wanted to grab the background image, I would do so via the following element:

`<li class="background-item fadein" style="background-image: url(&quot;https://images.unsplash.com/photo-1499615767948-e6a89ef6060f?ixlib=rb-0.3.5&amp;q=99&amp;fm=jpg&amp;crop=entropy&amp;cs=tinysrgb&amp;w=2048&amp;fit=max&amp;s=af3e0a1abbea09aee0f3ba8d26edd2c3&quot;);"></li>`

In this element, we can see that the actual URL used is:
	
[https://images.unsplash.com/photo-1499615767948-e6a89ef6060f?ixlib=rb-0.3.5&amp;q=99&amp;fm=jpg&amp;crop=entropy&amp;cs=tinysrgb&amp;w=2048&amp;fit=max&amp;s=af3e0a1abbea09aee0f3ba8d26edd2c3&quot](https://images.unsplash.com/photo-1499615767948-e6a89ef6060f?ixlib=rb-0.3.5&amp;q=99&amp;fm=jpg&amp;crop=entropy&amp;cs=tinysrgb&amp;w=2048&amp;fit=max&amp;s=af3e0a1abbea09aee0f3ba8d26edd2c3&quot)

Try plugging that URL in to your browser. Go on, try it. Do you see green hills with a winding road? Congratulations, you’re seeing the pic we grabbed from my Momentum tab’s html. 😊

Becoming comfortable with your Chrome DevTools is tremendous for debugging. But it’s also incredibly helpful for coding practice and additional learning—it’s the ultimate sandbox! And it’s also a great way to utilize webpages you’re already interacting with. Just remember, though…with great DevTools power, comes great responsibility. Please always use these tricks and other coding practices ethically and appropriately!


*References:*
- [https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)
- [https://www.sitepoint.com/introduction-to-the-fetch-api/](https://www.sitepoint.com/introduction-to-the-fetch-api/)
- [https://www.w3schools.com/jsref/met_document_queryselector.asp](https://www.w3schools.com/jsref/met_document_queryselector.asp)
- [https://developers.google.com/web/tools/chrome-devtools/console/javascript](https://developers.google.com/web/tools/chrome-devtools/console/javascript)

