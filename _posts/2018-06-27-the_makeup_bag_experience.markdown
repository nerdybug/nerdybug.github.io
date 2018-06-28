---
layout: post
title:      "the Makeup_Bag experience"
date:       2018-06-28 02:23:20 +0000
permalink:  the_makeup_bag_experience
---


For my Sinatra portfolio project I chose to create a web app to track a user's makeup items entitled Makeup_Bag. Seems trivial but I bought a color of lipstick that I already owned and was not running out of before beginning this project and it seemed like a perfect fit! 

I knew I needed to have users who could log into the website, they would then be able to add items and create a sort of inventory list for all their makeup items. Makeup_Bag was a natural name choice as most people who wear makeup have an actual bag or zippered pouch to haul favorite makeup items around for every day use or travel or work. The idea being that the website would function sort of like a digital makeup bag to see what all you have when away from the items themselves.

When it came to laying the foundation for my app, I had to first think about what models I would need and how they would relate to each other. A User model would for sure be needed, an Item model for each User's items and a Brand model for the item's brand (I wanted the brand to be more than just an attribute for an item). Relationally, a User would have many Items, an Item would belong to a User, an Item would also belong to a Brand and a User would have many brands through their Items. I needed to have these relations laid out in my mind and my notes to then setup the tables in the necessary way and the rest was just getting views and routes to function how I wanted them to.

What I found most helpful throughout this process was keeping notes in a code editor instead of a word document (I used Sublime Text 3) so I could jot down thoughts formatted in Ruby. If I tried to brainstorm Ruby code snippets in a word document, the formatting would easily get out of hand. I kept track of ideas that I wanted to implement, changes that needed to be made and requirements that were not yet met in Ruby as methods and comments. Perhaps that's what everyone does but it sure helped me. 

These portfolio projects have taken me much longer than I anticipated due to stress from my day job and self-doubt. Each time I have wanted the end result to be perfect and polished and I forget that I am still learning! The loop of feeling bad for taking so long which turns into feeling bad for feeling bad is just not a productive loop to let the mind get stuck in. To anyone reading this who is on the path of learning and is feeling some kind of way about it: don't let self-doubt pin you down, remember that your brain is still absorbing information you'll always be learning new things so stick with it. We are in this together. 

And with that bit of potential motivation, I conclude this post. Makeup_Bag was a long but fun journey and I'm ready to move on to the next chapter.

