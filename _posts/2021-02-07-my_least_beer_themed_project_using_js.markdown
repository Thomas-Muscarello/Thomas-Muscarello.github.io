---
layout: post
title:      "My least Beer Themed Project Using JS"
date:       2021-02-07 19:25:52 +0000
permalink:  my_least_beer_themed_project_using_js
---


Mod 4 is Javascript. Surprisingly enough, I think I liked it a lot more than Rails, and I think it was because it was more hands on. There was a lot more blatant calling and selecting items in code unlike the auto-magical-ness of rails where it did a lot of the heavy lifting for you.

I would say one of the biggest challenges I faced was by working with canvas. I think that there were times when I thought that I 100% bit off more than I could chew because I hardly knew JS in the first place and dibbing my toe into using canvas felt more like a cannonball. The hardest part was creating a new game button. Typically, I would just need to call `new Game` in my `handleClickNewGame` of my `EnterScore` class. However because I was using canvas, I had to first create a `GAMESTATE.REST` in my `index.js` and then create a `reset()` method in my `Game` class that takes in the the context of the canvas and clears it for a new game whenever the gamestate is `WINNING` or `GAMEOVER`.

It was only until then, was I able to edit the `handleClickNewGame` by basically adding everything in the constructor of `Game` so that it would truly create a new game on the screen when the button was clicked.

I also added a delete user button within my code although it is comment out. I did this to help clean up my api while I was testing, however it is commented out because I don’t think someone should have the capability right out the gate to delete all the users.
-Thomas

