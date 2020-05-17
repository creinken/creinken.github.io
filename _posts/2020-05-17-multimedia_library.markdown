---
layout: post
title:      "Multimedia Library"
date:       2020-05-17 22:40:58 +0000
permalink:  multimedia_library
---


    Going into second project week was rather stressful at first. A week before I was almost a week ahead of schedule, and then closing day for my new house happened.  All in all I didn't end up even starting on the project until just before I had to go to work on Tuesday of project week. I thought for sure I was going to fall even more behind because I didn't even know what I wanted to do for the project yet.
		I ended up comming up with a multimedia library idea pretty quickly because the first thing I thought of when I read that there was to be a collections aspect was a library. After that I thought, "Well a library is all well and good but a library of what?" I'm big into gaming and movies so I decided to have it be a library of movies and games.
		The main groundwork was fairly easy and straight forward. I wanted the user to be able to select from already exhisting movies or games when adding to their collection or be able to create a movie or game if it didn't already exist so I set up a many-to-many relationship between users and movies through a joins table and the same for games. I didn't want them to be able to delete the original as other users were potentially referencing it in their collections as well so I had to do a little google searching to find the right method that would allow the original to persist while removing the item from the collection. A little view logic as it wouldn't work right in the controller and I was able to allow user's to view other users' collections without being allowed to edit their collections.
		My biggest challenge came when I decided I wanted it to function somewhat like an actual library where you can go and checkout or borrow books from the library. I wanted the users to be able to borrow a movie or game from another user, but I also wanted the user, and only the user who borrowed it, to be able to return it to only the user they borrowed it from. I finally figured out that I could set another many-to-many relationship through a new joins table user to borrowed joins table to movies/games collection joins tables. As of the writing of this blog though I have yet to get it working all the way.
		All in all this was a very fun project that helped me understand and solidify many important concepts that I'm sure are going to play a big part in the upcoming Rails section.
