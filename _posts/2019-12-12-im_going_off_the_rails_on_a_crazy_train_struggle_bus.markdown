---
layout: post
title:      "I'm going off the rails on a ~~crazy train~~ struggle bus"
date:       2019-12-12 23:15:48 +0000
permalink:  im_going_off_the_rails_on_a_crazy_train_struggle_bus
---


<p style="text-align: center;">![struggle_bus](https://media1.giphy.com/media/l0K4hqqqwgFijgVLa/200.webp?cid=790b761105613a16bb9e145eee50518c4ac72c8b98bae01f&rid=200.webp)</p>

I did it. I finished my Rails project. Three project-starts, endless hours logged, and a migraine later, I did it. And as much as this project challenged me, the struggles were *tremendous* for my learning. In this blog, I’ll cover my top three struggles (and the subset of struggles within them) and what I learned from all of it. 

**_1. Start with the MVP_**

I can hear Corinna’s voice now as she coached us through our Rails Project Prep. “Start with the minimum viable product to meet the project requirements. Then once that’s set, you can add other fun stuff from there.” Wise words from a truly incredible cohort lead. If only I had listened. 

See, I had this idea for the app I wanted to build based on a lab we did where users go on “rides” at an “Amusement Park.” I wanted users to take “adventures” in “lands.” I could picture these lands and adventures in great detail. There could be happiness points and character points, gained from completing adventures. There could be sidekicks based on each adventure and land. A Hogwarts Land, an Upside-Down, a galaxy far-far away. THERE COULD EVEN BE A BABY-YODA SIDEKICK. I think that’s what really screwed me. I really just wanted to create something that involved Baby Yoda. So onward I went; with my detail of the lands highly envisioned, but my framework for the actual *project* and implementation not nearly as focused as it needed to be. And my goals quite lofty.

I started out Project Attempt # 1 by implementing the Devise gem to handle user authentication. Devise is an incredible gem that does a *ton* of the heavy lifting for you. But, for what I wanted, I needed a lot of legit hands-on access to the User controller and views, which just isn’t ideal for Devise. I tried. *Oh, I tried.*

<p style="text-align: center;">![Params-picbe807349db3e4edd.png](https://www.pastepic.xyz/images/2019/12/12/Params-picbe807349db3e4edd.png)</p>

As shown in the screenshot above, I implemented a “username” attribute for Users by overriding Devise’s sign_up_params and account_update_params. And that was about as far as I got. Every time I tried to reroute a User to a page I wanted to define, it was like hitting a brick wall. *Fine,* I thought, amidst gritted teeth and sweaty palms as the project week’s days peetered along. *Can’t stop me. I’ll just start over and make my app without Devise. That way I can do what I want.*

And that, my friends, leads me to point 2.

**_2. Don’t force a project to fit specs if it’s not the right project for the specs_**

As I mentioned earlier, I wanted to build an app where users take “adventures” in “lands.” I hit my head so hard against Devise in those first few hard-core project sessions, that I thought leaving Devise in the dust and going rogue would be the answer to my Rails project glory. Well, then, my project of users taking “adventures” in “lands” evolved into users taking “adventures” that belonged to “challenges.” Because that seemed to make more sense and fit the specs better. Except, that got really confusing and weird semantically. And started to surface other major problems with my idea in regards to what we needed to achieve with our project.

Two more days trying to make my square idea fit into oval project specs, and I realized for the second time that I needed to start over. But this time, I needed to rethink everything, not just Devise. It wasn’t Devise. It wasn’t my “adventures” idea. It was both of them, and so much more that I was trying to force to work when ultimately I needed to dial my ambitions way back. I needed to create a project that could walk and talk before forcing it to run a marathon and recite Homer’s *Odyssey.*

Onward, I went. Again. A bit more battered, a few tears shed. But ready to do what I needed to create a project that met requirements, and that I was proud of.

<p style="text-align: center;">![programming-meme6d6072e16b1ad0ab.jpg](https://www.pastepic.xyz/images/2019/12/12/programming-meme6d6072e16b1ad0ab.jpg)</p>

**_3. Be relentless_**
	
Here’s a secret: I don’t like failure. (That’s not a secret at all. I hate failure. Everyone who knows me knows it. I’m the definition of an uber perfectionist.) But, here’s the layer that’s not quite as obvious: oftentimes, mistakes to me equate to failure. Which is ridiculous if you think about it. Especially in programming. I’m learning to embrace my mistakes as true opportunities to learn. Not to find the answer or simply solve the problem, but to *learn*.

Several years ago, even a couple of months ago, having to start my project over for the third time--let alone having to abandon my original idea--would’ve felt like a massive failure. One that likely would’ve crippled my learning, and my ability to do my best work on my Rails project. And don’t get me wrong, I definitely feel like I have a one-way, nonstop ticked on the struggle bus at times. But, last week I came to the realization that I need to start over way sooner than I usually would have. And here’s the kicker: I welcomed it. Instead of beating myself up, I reflected on how much I’d learned trying to get through Devise the first time around, and manipulating my project idea the second attempt. I was ready for the third go at it.

I realized I had to start over, so I wore my mistakes like badges of honor and dug in. And now here I am, with a complete Rails app to show for it--one that I’m proud of!--and all the lessons I learned along the way. Bonus: I also know some areas I can continue to really lean in and learn more. Because ultimately that’s the best we can do for ourselves--find the areas where we can grow the most and give ourselves the space and grace to do so.

<p style="text-align: center;">![Spray_to_Send60826b2da193afed.png](https://www.pastepic.xyz/images/2019/12/12/Spray_to_Send60826b2da193afed.png)</p>
	
So those are my three biggest lessons from building my Rails app. If you’re on a similar educational path to what I’m on, maybe you’ll spare yourself the same struggle by heeding my mistakes. Or maybe you’ll jump right in and make the same. Either way, roll up your sleeves and put your game face on--programming isn’t for the faint of heart. BUT. As real as the struggle is, I promise it will be worth it.

<p style="text-align: center;">![baby-yodaf62ae6e251f211c4.jpg](https://www.pastepic.xyz/images/2019/12/12/baby-yodaf62ae6e251f211c4.jpg))</p>

<p style="text-align: center;">*Ha! Did manage to get Baby Yoda in my project after all! ;)*</p>

