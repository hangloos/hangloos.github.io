---
layout: post
title:  "Using the server's log files"
date:   2016-07-28 14:58:50 +0000
---


I have been immersed in rails now for a good amount of time in my learning process. I wanted to highlight one subtle part about rails that I think is very important to someone's development. 

One of the biggest things in development is the ability to refactor your code, making it thinner and more efficient. This is an essential process that takes good organization and patience. One tool that I think it very helpful for this is the rails server log. When you are running your local rails server by entering rails s into your terminal, whatever action is performed in your application will display in your server log. Not only can reading this log help you figure out errors and bugs within your program but it will show you how many steps a method or part of your program is taking. 

**Example: **

Let's say you are using active record queries to look for different values in your tables. For the sake of the example, you have "posts" in your application. If you notice 2 lines in the log that  have "Select posts * where..." then this could show a point where refactoring could be done. There is a way to combine those lines into 1 active record query over your posts to make the method more efficient. 

Not only does the server log help with refactoring and debugging but it tells a story about what your program is doing. Being able to tell the full story about your application and code is what you need to strive for as a developer. Reading each step in the log helps you talk out what is actually happening in your program. Remember, we will have to talk this story out for our interviews so get talking!! 

The log has been a very helpful tool for me lately and I hope you can take advantage of it too during your development process. Good luck!! 
