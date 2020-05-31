---
layout: post
title:      "Making a flexible project"
date:       2020-05-31 20:29:46 +0000
permalink:  making_a_flexible_project
---


When I started making my project, I knew that I wanted to make something I'd be passionate about using. While ambitious, I also immediately discovered that I'm not quite there skill-wise. By the time I arrived at my final submittable project I had already scrapped two half-way completed projects because they were not only growing out of the scope of the project, but because I had been designing projects beyond what I'm capable of creating. So what is one to do? My solution was to build something that not only fit my current capabilities, but also has the ability be expanded upon when I further develop my skills.

Let's be more specific and highlight where this magic happens! The core idea of my project is based on the video game Counter-strike: Global Offensive (or CS:GO for short). In short, CS:GO pits two teams of five against each other to win rounds by defeating the other team. However, what differentiates CS:GO from any other First-Person Shooter game is that there's an economy system that determines what weapons your character is capable of buying. This means that deciding which weapon to buy and when can be critical. 

![](https://i.imgur.com/uRycW3P.png)

Here is the code for my first scraper. 

Originally my project was designed to get stats about every single gun in the game, but I quickly realized that I was biting off more than I can chew. I decided to focus my project on specifically the pistols so that I could make my data more manageable. As you can see in the image above, I attempted to build my scraper in a way that only scrapes for pistols right now, but could "easily" be altered to scrape the site to scrape pistols and any other weapon type that I would want. To that effect, at the end of the of the scraper method I create a new weapon and assign it a "url." "Url" is not exctly the right term for the information I'm scraping, but what matters most is how I can use "weapon.url" in a second scraping method to drill down and get more information about it regardless of the weapon type.

![](https://i.imgur.com/gFUGLn7.png)

This is where my second scraper comes in. The selectors are annoyingly long so they get cut off, but the important part to highlight is the very first line in the method where I ammend the site we're scraping with #{weapon.url}. This automatically fills in the rest of the site url to match the page where the specific weapon information lives and we can scrape away from there. This saves me the time of having to scrape information for every weapon only to return one weapon's information. Now I can use this technique to scrape the specifics of whichever pistol the user selected, but I can also use this (or some slight variations on these scrapers) to expand the scope of the project and scrape for multiple weapon types when I'm ready to expand my skills.

### Moving Forward

So what's next? Ideally I'd like to add more weapon types and make the terminal output a little easier on the eyes. The first can be accomplished through some trial and error and possibly a new class of Type to manage what category each weapon fits into. The latter seems actually much more simple based on the plethora of available gems out there already made to gussy up my CLI. I've found two tools for improving the look of my CLI called TTY (https://ttytoolkit.org/) and another called Rainbow (https://rubygems.org/gems/rainbow/versions/3.0.0).

From there? Who knows! I'd like to keep iterating on this project as I learn more and more. How cool would it be if what is now a reference guide for the game's pistols became fully interactive web app with a lot more data than just pistols? I think it'd be very, very cool.
