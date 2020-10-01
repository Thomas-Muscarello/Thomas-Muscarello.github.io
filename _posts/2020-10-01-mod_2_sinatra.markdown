---
layout: post
title:      "Mod 2: Sinatra"
date:       2020-10-01 23:40:19 +0000
permalink:  mod_2_sinatra
---


Well this mod of the program has definetly been the trickiest for me. Creating, Reading, Updating and Deleting items seems like a simple concept however for me it just wasn't sticking until the end. With that said, I created an app that helps brewers keep track of their beer recipes.

There were a couple of times where I would struggle and get stumped with this project. 

The first was when my "Update" wasnt working. I was using my instance variable `@beers` in my `erb :edit` and iterate over it. However it would  show the beers information but wouldnt allow me to actually save any of the updated information. To fix this I realized that when I was iterating over `@beers` I was also using it in my method such as

`
<% @beers.each do |beer| %>
 <a href= "/beers/<%=@beers.beer.id%>">
    <div class="beer">
    <p> Beer Name: <%= @beers.beer_name %></p>
    <p> Malt Used: <%= @beers.beer.malt_type %></p>
  ...
 <% end %>`
 
 By removing the `@beers` within the iteration, I was able to get my code to work. I realized that I was basically calling it twice.
 
 The second stuggle I faced was trying to make sure that one user couldnt find another users beer. I solved this by adding an if/else statement that would verify the beer is a beer, as well as belongs to that current user:
 
 ```get "/beers/:id" do
    @beer = Beer.find_by(id: params[:id]) 
        if @beer && @beer.user == current_user
            erb :"/beers/show"
        #if beer belongs to user
        else
            redirect "/beers"
        end
    end```

Lastly the final struggle I had was with CSS as a whole. I didn't really have any prior experience with CSS so I would have to google some styling techniques as well as ask for help. 

I think my favoirte part about this project was seeing it all come together. I can definetly see myself adding to this app one day so that brewers can add more information to their beer recipes.

Best,
Thomas
		
		


