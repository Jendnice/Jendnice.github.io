---
layout: post
title:      "HTML Validator"
date:       2020-05-20 16:56:29 +0000
permalink:  html_validator
---

You know what I love? Surprises. Actually, scratch that. I don’t. I don’t love surprises. Not all of them, anyway. Because sometimes a person just needs head up, you know? But, one surprise that I do love?!—The HTML Validator. What is this, you ask? Fret not—I shall tell you.

Before attending software engineering bootcamp, I tinkered around with different facets of programming in very small-scale ways. For example, I’d used Markdown for formatting. And delved briefly into HTML. But I mean *briefly*.

So, when I started learning JavaScript, the HTML aspect felt a bit foreign, to say the least. I learned as I went, reading supplementary articles about whatever aspect of HTML I needed to execute the JavaScript at that time. And my HTML knowledge definitely grew. But now that I’m focusing on my growing my knowledge base and trying to really build a solid foundation—and then some—HTML and CSS are two areas I knew I wanted to revisit.

I circled back to some of the bonus material that was offered during bootcamp, some of which targets HTML and CSS specifically. And in one of the HTML lessons, they introduced the Great Surprise I mentioned above: the [W3C Markup Validation Service](https://validator.w3.org/).

Based on how I'm using it the most currently (and explaining it in this blog), I'm referring to it as the *HTML Validator*. But it's important to note that it also validates other markup. As described on the site, “This validator checks the markup validity of Web documents in HTML, XHTML, SMIL, MathML, etc.” Pretty sweet, right? Here’s how it works:

1.	You enter the HTML code. (You can do this by URI, File Upload, or Direct Input. Most often, I use Direct Input.)
2.	You click “check.” 
3.	You let it do its magic.

That’s it! And the magic that it does? It checks your HTML for any errors and then highlights those specific errors explicitly so that you can go back and fix your HTML. While many text editors highlight these errors as you code, having this tool to check your entire HTML file, and give you a comprehensive look at where there are errors is tremendous. *And*, if there are no errors—it tells you that!

As programmers, attention to detail and eagle-eye skills are paramount. But many times, we’re given task to dig into legacy code. Or we’re spending so much time *with* our code that our usually acute detection of errors is starting to blur ever so slightly. Whatever the situation, having such an easy, accessible, and fast tool to comprehensively check HTML and highlight any errors is crucial.

Another way this can be beneficial is by helping you fine-tune best practices. Here’s an example of an error it caught when I was playing around with it:

![HTML-validator-errors98f6691f978306ad.png](https://www.pastepic.xyz/images/2020/05/20/HTML-validator-errors98f6691f978306ad.png)

In this HTML file, I embedded a video. When I wrote that code, I defined the height and width of the video. I’ve run this code in my browser, and it all works perfectly. However, in the above, the HTML Validator points out that the height and width attributes should not have “px” (pixels) defined. Those attributes should just have their numeric values. (“400” and “600” respectively.) I totally overlooked this! Especially because my text editor didn’t call it out—and the code works! It runs!

Now, obviously if everything is working, the errors above might not be life-altering. But, in a field where the little nuances matter tremendously, being able to learn something like the above can make a big difference in knowledge and abilities over time.

Once I fix the above as follows:

```
<video controls autoplay width="600" height="400">
      <source src="https://curriculum-content.s3.amazonaws.com/skills-front-end-web-development/real-estate-lab-assets/real-estate.mp4" type="video/mp4">
      <source src="https://curriculum-content.s3.amazonaws.com/skills-front-end-web-development/real-estate-lab-assets/real-estate.ogg" type="video/ogg">
</video>
```


And run it back through the HTML Validator, here’s what I get back:

 ![HTML-Validator-all-good-green-messageccd16d298fbd0f0a.png](https://www.pastepic.xyz/images/2020/05/20/HTML-Validator-all-good-green-messageccd16d298fbd0f0a.png)
 
*Happy sigh*. That’s a rewarding feeling. Thank you, HTML Validator. I feel so...validated. :)

But now—time to keep learning and see what other surprises I can find and add to my knowledge-arsenal!


*References:*
- [W3C Markup Validation Service](https://validator.w3.org/)

