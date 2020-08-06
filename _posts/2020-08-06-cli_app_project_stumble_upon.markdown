---
layout: post
title:      "CLI App Project: Stumble_Upon"
date:       2020-08-06 22:23:22 +0000
permalink:  cli_app_project_stumble_upon
---

This project required me to create a CLI app that pulled information from an API. I figured to pick a topic that I enjoy which is craft beer. The website I used was "Open Brewery DB" and the actual API that was used was: `https://api.openbrewerydb.org/breweries`

The app's main goal is to have the user search for a brewery by Name, City, or by type. I wanted to put some extra spice into it so I added a `User` class. This made it so that whenever the user runs the program, they are required to input a username, their city, and their favorite style of beer, which in terms creates a new user for the `User` class. They are then able to view the profile they created in the main menu. I figured that if I wanted to build up this app in the future, it would be helpful to have a `User` class to pull info if needed.

Creating the actual API class wasn't to difficult because the code was fairly the same `BASE_URI`, and the only difference was having to add the search method to it; whether it was `"?by_city=#{city}"`, `"?by_name=#{name}"`, or `"?by_type=#{type}"`. The code would then interpolation the user input.

There is a little difference however when it came to search for a brewery by type. The API only accepted specific types of breweries, such as "micro", "large", "bar", etc. Therefore, instead of having the user guess what type of brewery they are looking for and hoping that it is on the list, I am using the `TTY::Prompt` gem. This allowed the user to select they only available types of breweries via the arrow keys.

The user can continue to search for a brewery by the different options by using the commands `1, 2, 3, 4, or 5`. However, when the user enters `5`, they will `exit` the program.

My favorite part about this ap, is the creative design I was able to add to it. Although it wasn't much, I enjoyed being able to bring color to the terminal as well as my own personal tone of voice when it came to requesting the user to enter information. I like to think that I was able to improve the user experience.

I would say the hardest part for me was creating an Error Input that didn't break my code. To solve this issue, I had to add an `if else` statement within my `CLI.rb` for each search method. `if` brewery.class == `Brewery` than it would pretty print, `else` it would return an error.

Overall, I really enjoyed this project, and I am looking forward to the future projects I will be working on.

`Cheers`

