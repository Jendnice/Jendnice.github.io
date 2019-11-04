---
layout: post
title:      "Models and Controllers and Views, Oh My!"
date:       2019-11-04 13:08:26 -0500
permalink:  models_and_controllers_and_views_oh_my
---


Here’s something I struggle with on a daily basis: *balance*. Managing self-care with adulting, home life with career goals and responsibilities. Not to mention working out, eating healthy, laughing, and generally allowing myself to be a human. These things seem really easy, but giving enough space and time for them on a consistent basis is actually quite hard.
	 
Last month I had the absolute pleasure of seeing my twin sister marry her longtime boyfriend and best friend. As a part of this, I also took about a week away from scheduled Flatiron coursework to allow myself to be present and available for such a special time. And I wouldn’t change any of that for a second. However, managing both sides of this emotionally and intellectually was not easy. (Full disclosure: I’m still playing catch up!)
			 
But here’s the thing: *that’s ok.*
			 
When we rolled into our project week (or, in my case, screeched into it amidst a torrent of stress energy), I was overwhelmed. Oh, so excited! But overwhelmed. Despite the long days and hours catching up on my coursework, I was still several days into project week when I actually began my app. But I realized as I started at the blank screen in front of me that I wasn’t overwhelmed because I couldn’t do it. It was the opposite. I *knew* I could, and I didn’t want to rob myself of that opportunity by not appropriately balancing the different pieces of my life.

And some of that just takes trust.

One thing that’s been popping up in my head recently (don’t worry, it relates), is the idea of SRP. The Single Responsibility Principle. This has come up continuously in our learning—for Ruby, Sinatra, and everything in between. “The single responsibility principle (SRP) states that every class or module in a program should have responsibility for just a single piece of that program's functionality.” ([`https://medium.com/@severinperez/writing-flexible-code-with-the-single-responsibility-principle-b71c4f3f883f`](http://))

I love this. Not just in programming, but in life. And so, I’ve, somewhat inadvertently, been implementing this into my own life. I am responsible for one thing in one moment. That’s all. One thing at a time. I remembered this when I began my project, and it helped narrow my focus beautifully. 

If I tried to analyze and map out everything in detail for my app at once, it was way too much. Models, Controllers, and Views. And databases. And authentication. And validation. Whoa, *mind spinning*. But in taking it down a notch and targeting one thing at a time, I was able to dig into my project head on. And not with a force of stressful adrenaline, but one of genuine excitement and gusto.

That’s not to say everything has been peachy and I’m cruising through my new levels of confidence with admirable speed. Hardly. In fact, I’d venture to say I’m even *more* nervous, because the further I delve into my studies and the more I learn, the more invested I am in *what* I’m learning and my drive for this career and how much it means to me. But in allowing myself the space and grace to break things down and address them one at a time, I allow myself to commit fully to whatever task is at hand. 

For example, one piece that was particularly tricky for me in this project was figuring out how to ensure a user doesn’t repeatedly hit ActiveRecord error pages whenever they plug an “:id” in their URL that doesn’t have a record saved in the app database. I hit this error many, many times during my build out. Each time. I swear I could feel my blood pressure rise. But I breathed. And focused on the specific task I was working on, jotting small notes of things I noticed and knew I’d circle back to later. 

I focused on building out the necessary components of the app, testing each piece and their relationships and collaboration with other pieces of the app as I went. I built out the authentication and validation. I made sure that a user can only complete CRUD actions on their own content. And that ActiveRecord error remained, folks. During all that build out, the error remained. But instead of getting pulled into that black hole prematurely, I held off and focused on *one thing at a time.* Finally, ratcheting down my to-do list, it was time to bury that error and replace it with something that would support my app instead of breaking it.

Ultimately, I solved it by redirecting a user to their own “Company List” page if an “:id” was plugged in that didn’t have a valid entry in the database.

```
get "/company_interests/:id" do 
    redirect_if_not_logged_in
    @company = CompanyInterest.find_by_id(params[:id])
    
     unless !(@company == nil)
      redirect "/company_interests"
     end 
     
      if @company.user == current_user
        erb :"/company_interests/show"
      else 
        redirect to "/company_interests"
      end 
  end 
```

Basically, when a user types in the “/:id” for a specific company, the app now screens that “:id” from the get-go to ensure it has a match in the database. If it doesn’t, the person is rerouted right then. This not only prevents the app from breaking, but also provides a more seamless and guided experience for the user. And truth be told, the actual fix in its entirety took me maybe 30 minutes. If that. But that’s because I encouraged myself to do *one thing at a time*, putting full focus into each individual item as I built it out.

I’m still playing catch up. I still try to tackle multiple things at once sometimes. I still struggle with balance. But, I’m learning, and I’m getting there.

The original quote that inspired this blog title is, of course, “Lions and tigers and bears, oh my!” and centers around Dorothy, the Tin Man, and Scarecrow when they feel that danger could be anywhere and everywhere around them. 
With the Tin Man wanting a heart, and the Scarecrow wanting a brain, I found this whole image very applicable and resonant. I can be scared of all the things that could be everywhere, or I can know that it’s okay. That even if they *are* everywhere, that’s ok. That I can just do one thing at a time. 

And ironically, somehow, that *is* a balance of heart and brain.


