---
layout: post
title:      "Keeping Track of Your Files"
date:       2020-06-28 20:37:02 +0000
permalink:  keeping_track_of_your_files
---

## Do yourself a favor and take the time to organize your file structure. You can thank me later.

Working on my own project was one thing, but the importance of following the MVC file structure properly became incredibly apparent when I was trying to help others debug their projects. Routes had overly complex name schemes, .erb files weren't in the right folders, controllers were bloated with routes that should have been elsewhere, and the list goes on. First of all let me say that my file structure was by any means perfect. I tried hard to keep everything organized, but it can be hard to force yourself to follow the best practices, but for beginner developers we naturally want to code in a way that makes sense to us as individuals. This can be totally fine for personal projects, however to build the complex enterprise web applications we'll find in the workplace, we need to be prepared to write code for a team not just ourselves.

### The MVC

![](https://i.imgur.com/u4d0PPb.png)

The MVC file structure I referenced before stands for Model - View - Controller. These are the three core elements that make up the functionality of our web applications. The Model contains your classes, like your Users, Posts, Tweets, or Comments. The Model is responsible for managing the data of the app and it receives input from the Controller. The Controller is the go between for the Model and View files. The Controller handles user input, performs operations on the Model data, and handles what information is then sent back to the View. Lastly, the View is what your users will see in their browsers. This is the HTML, CSS, JS that foms the visual representation of the web app (your homepage, sign up form, profile page, etc.) as well as what handles the repesentation of data passed to and from the Controller.

### Why is MVP SOOO Important to follow?

![](https://i.imgur.com/QBbnQRn.png)

Put simply, it's because it's extremely difficult for someone not already familiar with the app to know why a persistent bug is happening, where is the improperly written code, and how they can continue building the app. Whether your employer hires more developers for you to work with or you move on to a new job, you won't be the sole developer of an enterprise web app forever.

Linked above is the file structure for my Sinatra project. Not including the other files that are needed to create a working project, my MVC structure alone has 14 different files. Being able to know what routes are in what controller or what view belongs to what controller can dramatically decrease how long you need to spend debugging when really we all just want to keep building. So do yourself a favor and adhere strictly to a clean file structure that anyone from novice to expert can follow. It may take more of a time investment up front, but will pay dividends down the line. You can thank me later.
