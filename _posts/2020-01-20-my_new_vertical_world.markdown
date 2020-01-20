---
layout: post
title:      "My (New) Vertical World"
date:       2020-01-20 18:46:47 +0000
permalink:  my_new_vertical_world
---


   If you read (and enjoyed) how real my struggle was with our Rails project, you’ll be happy to know I struggled just as hard with our most recent Javascript project. But here’s the thing--I’m learning to actually enjoy the struggle. The struggle means I’m pushing myself, growing as a developer... that I’m *learning*. I know that probably seems obvious, but as a lifelong perfectionist, failure has oft been a nemesis of mine. And my view of “failure” was pretty skewed. As in, *any* mistake in *anything* was unacceptable.
	 
 This new relationship with struggle (and mistakes) is one of the things that has most surprised me about programming, and myself. I’m beginning to embrace the areas where I struggle. Instead of seeing them as shortcomings or weaknesses, I’m starting to understand that they are areas where I can work harder, strive further, and better myself in a multitude of ways. To be fair, it doesn’t always feel that way. In fact, I’d say *most* of the time, it doesn’t. But the core of it--the belief in the struggle, and in my ability to prevail--still reigns supreme, regardless how it feels in one particular moment.
	
  But, I’m sure you didn’t come here for a pep talk. You came here for code. And code I shall give. (With a small dose of mental fortitude on the side, because that’s just how I do.) Keeping in tune with the above, let’s dig into one area that could easily be overlooked, but I feel made a massive difference in my Javascript project takeaway and learning growth overall: how to actually start your project (or application) and build it out in a way that promotes more learning than frustration. (Because, face it, there will be frustration. But, hopefully the following advice will help prevent that frustration from *taking away from* the learning!)
	
 To give you a bit of background, my app is called *To Have and to Honeymoon* and gives users a platform to gather locations, and experiences in those locations, that they’re interested in traveling to on their honeymoon. As someone currently planning a honeymoon, I wanted a snapshot version of all the endless info I could find online about the different, amazing places we could go. But I wanted all that info, narrowed down to what *we* were specifically interested in, and in bite size pieces. Now, please.
	
  So that’s what I created.

  From the get go, I can acknowledge that there are two things I tend to do when I start, well, anything. But especially structured projects.

   1. I plan. *A lot.*
   2. I like doing things my way. Which is usually the way I’ve always done them. (What can I say? I’m a creature of stubborn habit.)

Number 1 is usually great, as long as I remember to stop planning at some point and actually get started. Number 2, however, is not very conducive to any learning process. And it’s something I’m working on.
	
 As I read over the project guidelines, one thing kept leaping out at me. Maybe I took particular note of it because it was heavily emphasized, or maybe I simply knew it wasn’t how *I* typically did things, and that made it stand out to me. (And made me anxious.) But, it also made me stop and think.
	
 I realized that I have a not-particularly-productive-habit of trying to build projects horizontally. I want to build the database completely. And then be done with it. And then build the models. And be done with them. And the build the routes. And be done with them. Obviously, I’m exaggerating here, because you’re never actually done with the different components. (There is always room for iteration and future features!) But, mindset-wise, I was very much about building each aspect out completely before moving on to the next.
	
 However, in the guidance notes for this project, they strongly recommended *not* doing this. Instead, they suggested we construct *vertically*. Build one piece of one thing. Make sure it works. Build one piece of the next aspect of that same thing. (Ex. *One* route in the routes.rb file to match the *one* controller action that you built.) Make sure it works. Repeat.
	
 This went against my natural instinct, hence the instant anxiety. But here’s the important part--*I didn’t hesitate.* Vertical, you say? Vertical, it is. I mapped out my notes, and plodded headfirst into my project, building one vertical piece at a time.
	
  I started with my Location resource, creating the Locations database first. Then the Location model. Then *one* controller action in the Locations controller. (I started with “index”.) Then that *one* route in the routes.rb file:
	
	`get '/locations', to: 'locations#index'  `
	
At this point, I added the Fast JSON API gem to my project, and built out the necessary relationships and attributes in my Location Serializer:

```
class LocationSerializer

  include FastJsonapi::ObjectSerializer

  has_many :experiences

  attributes :name, :description, :travel_season

end

```
  I also went into my Rails console to ensure the Locations database was up and running, and created some seed data. This way, when I got to coding the frontend, there would be backend data ready for fetching.
	 
  Honestly, I thought building vertically would stress me out. But shy of the *“Ah, this is change and I panic with change,”* initial reaction, it was actually quite lovely. And thought-provoking. And learning-supportive. And lots of other awesome, unique adjectives. Basically, I am so glad I heeded the project guidance advice. 
	 
 Building vertically gave me the opportunity to literally check each block as I put it in place and then test its strength and balance *before* moving on. On many a project or lesson, I’ve hit a bug, only to find that I have to go back several functions to find where the bug actually originated. Now, I’m not saying building vertically will prevent bugs. But I can say with confidence that it will help you catch them before they begin crawling rampant through your code. (Nice image, right?)
	 
  Of course, one could argue that building horizontally, if done incrementally, would yield the same results. And to a certain extent, absolutely. Part of the succes in this type of strategy  is literally taking it one piece at a time so that you can examine each component in action. But, therein lies the problem--when building horizontally, you *can’t* examine each piece in action. Because when you’re building horizontally, you can’t *test* each piece in action.
	 
  Sure you can test little bits--the database in the Rails console, for example. But seeing how each entity interacts with the other parts of your build is essential for a fully functioning application. (I mean, it literally *is* what makes an application fully functional.) And you can only do that by building each component *to test it*.
	 
  By building vertically, it forces you to build your code incrementally, but also in a way that can be continuously tested at each juncture. That is *invaluable*. Not only did this help me catch tons of missteps before they became real live bugs of frustration; but maybe even more importantly--I got to spend intimate time with my code and all of its nuances. Each line of code can be lost when you’re building a project that has so many pieces. But every line of code *matters*. Figuratively and literally. And building vertically gave me the opportunity to see exactly how.

  So, if you’re not building vertically, hopefully this blog encourages you to try it. And if you’re already building vertically, props to you. Hopefully this blog inspires you to step outside your comfort zone in some other way. After all, on the other side of failure is a whole lot of knowledge. :) 


