---
layout: post
title:      "Run toward the Roar"
date:       2019-10-06 16:22:08 +0000
permalink:  run_toward_the_roar
---


   That’s what my education coach said in our first call together as an Online Software Engineering cohort. The timing was perfect—we were all diving headfirst into this new adventure; and I, for one, was terrified. And excited. And anxious. And psyched. And all of the other things. I had feelings. It’s hard to believe that day was almost a month ago. I’ve learned so much in the past few weeks. But I’ve also become even more aware of how very much I still have to learn. 
		
   There were definitely some hiccups in the first few weeks—adjusting to the online curriculum, immersing myself in content I’d never studied before, structuring my days so I could spend enough time studying while still being a (somewhat) functioning adult. But about a week ago came the first real roar. 
		
   Our first portfolio project. 
		
   We were asked to create a CLI Data Gem that scrapes data from a website and then uses that data in its exchange with the user. I knew our project was coming up; but to be honest, the curriculum has been so intense (and wonderfully so!) that the project still managed to sneak up on me. And I could feel *it* sneak in at the same time… It. The doubt. The what ifs. What if I couldn’t… do it? (*Roar!*) What if I built a data gem that was horrible? (*Roar!*) Or couldn’t even figure out how to get started? (*Roar!*)
		
   Why are these “roars” and what does that even mean? Let me explain. Katie, our education coach, pointed out to us in our first talk that there’s this saying, (which actually traces back to an old teaching story from the African savannahs… I looked it up), that talks about how lion prides will place their older, weaker lions in strategic positions to roar really loudly just before a hunt. The roar causes the prey to sprint away in fear. Away from the noise, away from the roar. But, in doing so, they run directly *into* the strong, able, healthy lions, who are waiting to take them down. It’s a trap. In fact, the animals who are most likely to survive are the ones who run straight toward the roar—run straight toward their fear.
		
   So, when I felt the doubt creeping in, and heard my own “roars”, I thought about this. Yeah, my project could turn out awful. But if it does, I’ll dig in. I’ll learn more. I’ll fix it. I’ll do better next time. And continue to learn and grow in every way I can. Or, it could be amazing. Or anything in between. 
		
   I’ll only know if I run toward the roar. 
	
   Once I got over the initial nerves, I have to say, not only was I surprised at how much I proved to myself that I do know, but also how incredibly fulfilling and fun it was to build something that works, and runs, and is all mine. My own idea, my own code. Mine. I did this. 
		
I took this:
	
	
`climbing_cli.rb`


 And turned it into this:
 ```

class ClimbingCli::CLI
  
  
  def call 
    puts "Hello, climber! It's a beautiful day to get outside!".colorize(:green)
    make_climbs
    climbing_list_options 
    specific_climbing_lists
  end

  def make_climbs
    ClimbingCli::Climb.create_from_collection(ClimbingCli::Scraper.all_climbs_info)
  end
```
And this:
```
class ClimbingCli::Climb
  
  attr_accessor :name, :grade, :description, :location, :protection 
  
  @@all = []
  
  def initialize(climb_hash)
   climb_hash.each do |key, value| self.send(("#{key}="), value)
   end 
   @@all << self
  end
  
  def self.all
    @@all.uniq 
  end 
  
  def self.list_all_climbs
    self.all.each.with_index(1) do |climb, index|
    puts "#{index}. #{climb.name} (#{climb.grade})".colorize(:light_blue)
   end 
  end 
```
And this: 
```
class ClimbingCli::Scraper 

  @@climbs_info = []
  
  
  def self.scrape_climb_with_url(url)
    page = Nokogiri::HTML(open(url))
    
    name = page.css("h1").text.strip
    grade = page.css("h2 span.rateYDS").text.chomp(" YDS")
    description = page.css("div.fr-view")[0].text
    location = page.css("div.fr-view")[1].text
    protection = page.css("div.fr-view")[2].text
    
    climb_info_hash = {:name => name, :grade => grade, :description => description, :location => location, :protection => protection} 

    @@climbs_info << climb_info_hash
  end 
```
 (*Note - these are just snippets of my code, not all of it!*)

  I’m not saying it was easy. And the fact that this is very small in the world of programming is intimidating. Because it took a lot of work from me and my brain to put this together. But it’s also so exciting.
	
 Just a week and a half ago I was worried about my inability to write clean code in any of our labs. Everything I wrote seemed to have unnecessary if’s and else’s, arrays that were more for decoration than use, and everything in between. And I am not a refactoring master, by any means. But one thing that I was really proud of with this project was that when I went back through to do several passes of refactoring and removing any lingering anti-patterns, everything was already fairly clean. And I improved things even more from there. What was previously taking me four or five lines of code is now taking one or two. For example, here’s a method I’m particularly proud of:
 ```
  def make_climbs
    ClimbingCli::Climb.create_from_collection(ClimbingCli::Scraper.all_climbs_info)
  end
```

  I seriously get a bit of a Disney-World-fireworks expression on my face when I talk about my code–lines like this in particular—because they feel that exciting. And magical. (Yes, I went there. Don’t judge me.)
	
  So, my first project is just about wrapped up. I’m the proud owner of a new data gem! I love my code and what it can do. I’m so excited for what I’ve learned, and will continue to learn. But I’m also even more aware of just how much I don’t know. And how that’s ok, too. Because that, at its core, is what programming is—constant learning. And not just the willingness to do so—but the drive for it. I’m ready. And I know exactly what to do any time I hear my doubt roar up again. If you need me, I’ll be running directly toward it. 😉

	
	
	

			  
				 
				  
					 
		   
			  
			   
	



