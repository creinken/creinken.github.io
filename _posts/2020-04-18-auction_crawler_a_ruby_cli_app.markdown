---
layout: post
title:      "auction_crawler: A Ruby CLI app"
date:       2020-04-18 19:22:46 +0000
permalink:  auction_crawler_a_ruby_cli_app
---


    I started this course 4 weeks ago with next to no knowledge about Ruby, but I had a fair knowledge of programming in general. I was feeling very confident in my ability to get through this course at full pace even though I'm still working a full time job. Then came the week of our first project and I thought great I'll do this just as easy as I've been getting through everything else so I came up with a project design to challenge myself.

    Starting this project I knew I had given myself a huge chore. I had to learn first which pieces of the Blizzard api would return relavent information. Once I thought I had that figured out I had the pleasure of learning omniauth so I could get an authorization token which I had to supply with every api call. Once I had that token that's when I realized that all the information I wanted wasn't in just one call that I could piece it out of. No that would have been easy. Instead I had to chunk out each item and then take it's unique identifier and supply that back to the api with a separate call in order to get all the information I wanted about each item.
		
		The main intention of the application was for people to be able to check what auctions were currently available on the World of Warcraft auction house without having to log in. It's relatively simple in layout but follows a belongs to/has many through relationship.
		
1. 		The app initiates communication with the api and gets an auth token
2. 		The app pulls a list of all current auctions for one of the servers
3. 		The auction class trys to display 10 auction items but first checks to see if they exhist
4. 		If they don't exhist auction uses the info runner to get item information by id supplied and then build the item
5. 		Once it has a list of 10 items to display the user can interact by typing one of several commands or the number of the item to get more details on it.

    It ended up being a very fun challenge, and I didn't have enough time to get everything in it that I wanted so I'm going to keep it as an open project on my github. If you're interested in taking a look and watching the evolution of it later on you can check it out here => [auction_crawler](https://github.com/creinken/auction_crawler)
