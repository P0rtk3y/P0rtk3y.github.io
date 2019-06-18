---
layout: post
title:      "**¡Quoteworthy! A Sinatra App**"
date:       2019-06-18 05:41:17 +0000
permalink:  quoteworthy_a_sinatra_app
---


I created Quoteworthy to serve as an electronic memory space for all my favorite quotes from poems, books, and other stories. Quoteworthy's current existance allows for basic functions, beginning with the creation of an account. Once a user has signed up with a username unique to the user, the user will be able to login and create a page that will house all the user's saved quotes. Quotes are categorized under pages called Story Spaces that identify the name of the literary source and author. Each user can have multiple Story Spaces which are all populated on one screen as a clickable link to the user's saved listing of quotes. The User has the option to add, edit, and delete a Story Space. I designed the application to be specific to each user. A Story Space can only be viewed, edited, and deleted by the user logged in. 

One of the most challenging endeavors was applying the Separation of Concerns principle. I was tempted to use one controller to fulfill all functionality, but ultimately did separate the application's logic into four controllers: Application (main), Users, Stories, and Quotes. This was tricky because I wanted the Stories and Quotes controllers to essentially merge views so that all quotes associated with a story could appear together in a Story Space. Each controller was mounted into the config.ru file. Within the config.ru file, I also included Rack:MethodOverride which allows for PATCH and DELETE actions. Corneal, a gem I used to help build the scaffolding of Quoteworthy, was immensely helpful in pre-loading all the files I needed to get started. 

My main hope during this project was to better understand how SQL, ORM, Sinatra, ActiveRecord, and Rack all fit together in a complementary way. Quoteworthy could still use many added features and styling to improve the User Experience. For now I am silently pleased that Quoteworthy has the initial rumblings of indeed being worthy of quotes. 




