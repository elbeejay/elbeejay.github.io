---
title: "Ticket to Ride: DC"
permalink: /tidbits/ttr-dc/
excerpt: "Creating a custom Ticket to Ride map"
header:
    #image: /assets/images/construction.png
    teaser: /assets/images/ttrdc/logo.png
---

I am a big fan of the [Ticket to Ride](https://www.daysofwonder.com/tickettoride/en/) board game, and wanted to try my hand at creating a custom board to play on.
I was able to do so, and created a custom map of the Washington, DC metro area, as shown below.

| ![TTR-DC](/assets/images/ttrdc/ttrdc_map.png) |
|:--:|
| The Ticket to Ride: District of Columbia map |

It turns out a number of fan-made boards and "how-to" guides exist.
A few of the ones I found helpful include [this guide](https://thequantumdice.wordpress.com/2017/09/10/ticket-to-ride-county-durham-coal-mining-country/) by Robet Bettles, as well as these [two](http://www.davidmillard.org/2009/01/ticket-to-ride-uk-map/) [guides](https://ttrboards.wordpress.com/ticket-to-ride-uk-version-2-1/) on making UK maps.
A number of other fan-made boards served as inspiration as well, several lists with links to these boards exist, such as [this one](https://ttrboards.wordpress.com/), [this one](https://boardgamegeek.com/geeksearch.php?action=search&objecttype=boardgame&q=ticket%20to%20ride%20fan&B1=Go), and the [official Days of Wonder fan contributions list](https://www.daysofwonder.com/tickettoride/en/fans/).

I ended up getting my board printed by [Print & Play](https://www.printplaygames.com/), which provided me with a surprisingly high-quality print for the price.

Below I will describe the process I followed to create this map.
The map itself, as well as code I used to generate the individual route cards, is available on GitHub in the [TTRDC repository](https://github.com/elbeejay/TTRDC).


## Creating the game

I started by searching for relatively clean maps of the DC region that outlined the borders, as well as the major waterways.
I used [Inkscape](https://inkscape.org/) to do my line work, and began with a blank document 20.8 inches wide, and 31.2 inches tall, as that was what I measured the official Ticket to Ride board to be.


I created a border that was 25.4 mm wide around all sides, as that was roughly what I measured the size of the scoring numbers to be on the official board.
Then I imported the clean maps of the DC region, and scaled them to fit within my bordered region.
Using these maps, I traced the edges of the states, as well as the waterways.


Next, I searched for maps of the DC Metro lines, as well as bus routes.
It helped to have familiarity with the region, as I was able to know a priori that the Metro lines themselves would not be enough to create a good game, as they radiate outward from the city center, and do not form a well connected network along the edges of the map.
Once I had a few maps with Metro stations and bus stops, I imported them into Inkscape and scaled them to approximately fit my previously drawn borders and boundaries.


From there, I placed circles with radii of about 10.5 mm at each potential station location.
Then I placed generic gray rectangles approximately 10 x 25 mm in size between the stations to begin to roughly define the routes themselves.
The next steps became iterative, as I started to rotate the rectangles to form the routes, and would have to slightly adjust station locations to make the routes fit.
Eventually, I had a skeleton map with my stations and routes defined in gray.


Next I made very subjective decisions and decided which routes would be come double routes, and which would stay single routes.
This again required manipulation of the stations and board to accommodate the width of the doubled routes.
The next step was to color the routes, to do this I started a spreadsheet where I tracked the number of individual train car slots that were in each color.
This way I was able to aim for some balance between all of the colors and the gray routes.


Via visual inspection I also tried to balance the location of various colors to avoid making one section of the map entirely red, for example.
Once the map was defined and routes were colored, I added the scoring numbers, city names, and filled in the point values around the outside border.


Then I moved into Python, and defined my station names in a CSV, and the routes between stations in a separate CSV.
Using these CSV files, I wrote a script to generate a `networkx` graph representation of my map.
From this graph, it became possible to automate the creation of unique routes between two stations, the basis for the "tickets" or "route cards" needed to play the game.
I wrote a script to generate these unique routes such that a set of routes would be randomly created ensuring that the start and end point of a route was not the same, or adjacent stations.
Furthermore, the set of routes would be unique; no two routes would have the same start-end or end-start points.
The script also automatically created the point values to be attributed to each route by finding the minimum number of trains required to connect the two cities, which is how I believe the official game does it.
That was about it, I didn't write code to create the cards themselves, and ended up writing them out on blank cards based on the CSV output of my script.