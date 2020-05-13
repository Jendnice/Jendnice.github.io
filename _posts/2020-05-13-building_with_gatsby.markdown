---
layout: post
title:      "Building with Gatsby"
date:       2020-05-13 19:34:44 +0000
permalink:  building_with_gatsby
---


*It’ll be fun*, they said. *It’ll be easy,* they said…

Several tabs open with tutorials, my Ubuntu blinking back at me—ready for input, I take a deep breath. Time to start building my portfolio website with Gatsby! First up, adding the Gatsby CLI globally.

	npm install -g gatsby-cli
	
So far so good. Next, initializing the new site and creating the folder it’s held in:

	gatsby new my-gatsby-site
	
Done. Whew, ok. Things are going well. I got this. Now, changing directories into the new Gatsby site directory folder, to begin coding.

	cd my-gatsby-site

I’m here. I’m in my new Gatsby site directory! Time to test things out so I can really begin coding.

	gatsby develop

According to the documentation, upon running this, “Gatsby will start a hot-reloading development environment accessible by default at http://localhost:8000.” So, I run the above code. And wait. And check localhost:8000 just to be sure. And wait longer. Something doesn’t seem right here. I check the other tutorial I have tabbed open, and before the above command, they recommend running:

	npm install gatsby-cli --save
	
So, I do that. Still no dice. Hmmm. Two important things to point out: somewhere in the above—I believe after installing the Gatsby-cli globally, I was prompted to choose between npm and yarn. I chose yarn. And continued onward from there.

Then when I ran the above code, I started getting errors. Most of these errors seemed to be regarding access, so I prepended the above command with “sudo” (which basically tells the terminal, “No I do have permission for this, so do it,”). Sudo didn’t help. More access errors, and a lot of other errors that were very convoluted and hard to pin. I was officially in error-rabbit-hole land.

I did a lot at this stage. Unfortunately, I can’t recount every individual thing because when I’m focusing on building (and especially when I’ve hit an error), I get a bit of tunnel vision. But, I do know that I read and reread both tutorials I was using. I also scanned through a more comprehensive guide from Gatsby. And finally, I did what we all do when we don’t know what to do next: I googled. And from there, read through post forums on GitHub as well as StackOverflow.

All of that led to me trying more things in an attempt to get the dang thing up and running on localhost:8000. All to no avail. But, as I continued to dig in, some layers (albeit not all of them!) started to unpeel themselves from my problem. Basically, somewhere in the above, I’d implemented both npm and yarn in my project. Which is not recommended, and can cause issues. (Me being the case in point.)

After trying some suggestions I read online (deleting the package.json file and reinstalling yarn, for example), I was closer, but still having issues. Ok, fine. I get it. I’ll start over.

So, I did.
	
But this time—I was prepared. When that question popped up asking me whether I wanted to use npm or yarn, I was ready to choose and use npm. No yarn, just npm. That should simply things and prevent the errors I was having. Right? Eyes peeled waiting for the npm/yarn prompt, I repeated the above steps and waited… and waited.

No question. No prompt. Nothing. I created my new directory and held my breath as I changed directories into it…

*Will it have yarn or npm?* (And more importantly—will it work?)

Ok, I’m here—inside my new website, take 2. Everything looks good. And it has… yarn. It has yarn! *Interesting! *But now the big question—will it work? I reviewed the tutorials and made sure that everything was installed, then ran:

	yarn start
	
One of the forums I’d read during my rabbit-hole adventure suggested using this command instead of “gatsby develop” to launch the local host. That’s the same command you use when traditionally using yarn, so I was comfortable with that.
	
Open up localhost:8000…moment of truth:
	
SUCCESS! 

On the webpage, I saw the landing page for my new Gatsby site. (The landing page is created by Gatsby, so the code is already built out to display this page.) I did it!

Now, because I’m hyper-curious, and why not—I wanted to see if the Gatsby cli worked. And specifically, if using the Gatsby cli to load the page (just like I did with “yarn start”) worked. So, I exited my page, and ran the following:

	gatsby develop
	
And wouldn’t you know it… there it was. Right there on localhost:8000, just like it had been through the “yarn start” command. As far as I was concerned, at this point, I’d done what I needed to start my website.

Reflecting on the hiccups of what should’ve been a quite easy process, I know that part of my issue initially was trying to use yarn and npm. Fixing that (by starting over) made that issue disappear. I can’t say that I understand all of the errors I ran into, because such are the layers of coding. 
				 
![coder life](https://pbs.twimg.com/media/DWu-97EXUAAv7WQ.jpg)

But! I have created the barebones of my Gatsby site. Now, I can now tweak, adjust, and make it entirely my own. The fun begins!


*References:*
- Gatsby Quick Start - [https://www.gatsbyjs.org/docs/quick-start/](https://www.gatsbyjs.org/docs/quick-start/)
- Gatsby Tutorial: [https://www.gatsbyjs.org/tutorial/](https://www.gatsbyjs.org/tutorial/)
- Netlify Guide to Gatsby: [https://www.netlify.com/blog/2016/02/24/a-step-by-step-guide-gatsby-on-netlify/](https://www.netlify.com/blog/2016/02/24/a-step-by-step-guide-gatsby-on-netlify/)

