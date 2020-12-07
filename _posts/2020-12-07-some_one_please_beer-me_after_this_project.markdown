---
layout: post
title:      "Some one please ‘Beer-Me’ after this project "
date:       2020-12-07 23:06:48 +0000
permalink:  some_one_please_beer-me_after_this_project
---


This project has taught me a lot, both of my own perseverance as well as coding. I hit a numerous amount of walls, but was able to break through each one. My project is called “Beer-Me” and it allows a user to create a Beer as well as post on other created beers. A user can also edit/destroy any beer, but can only edit/destroy their own comments.

 The first wall that I faced was working with the paths of a nested route. In my code I have my [Post] models resources nested within a [Beer]s resources.  I found this to be tricky to work with when trying to go to a specific post of a specific beer from my users page.

With that said, I realized that I had to call 2 arguments within my [beer_post_path] in order to properly go to the correct post. So rather trying to go to [beer_post_path(@post)], I had to go to:
beer_post_path(post.beer_id, post.id)


Another issues I faced was not having all of my posts deleted when a beer would be deleted. After some time spent on Google, I found out that to fix this, I had to make my Post model depend on the beer it belongs to. To do so, I had my Beer class’ model [has_many :posts, dependent: destroy]. Within my Post class’ model, I had to add [after_destroy :log_destroy_action] and: 

def log_destroy_action
       puts 'Post(s) destroyed'
    end

Finally I wanted to filter all of my beers to have a quick search if I wanted to see all beers that had an ABV higher than 5%. To do this I used a scope. To make a scope, I found it to be quite simple. I had to:

1.	Create a custom route:
          get 'beers/abv_rating_higher_than_5', to: 'beers#high_abv', as: "abv_higher_than_5"
2.	Create a method of it in my Beers Controller:
            def high_abv
                @beers = Beer.abv_higher_than_5
                render :index
              end
3.	Create the actual scope in my Beers Model:
          scope :abv_higher_than_5, ->{where('abv > 5')}
4.	Lastly, create the link for the user to click on via the layout:
          <%= link_to "ABV Above 5%", abv_higher_than_5_path %>

All in all it was a fun project!

