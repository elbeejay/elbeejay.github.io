---
title: "Austin Prop. B Election Map"
permalink: /art/atx-map/
excerpt: "Semi-Automated Mapping"
header:
    #image: /assets/images/construction.png
    teaser: /assets/images/atxmap/logo.png
---

The 2021 local election in Austin has generated a [lot](https://www.usatoday.com/story/news/2021/05/17/austin-homeless-camping-ban-law-elite-funded-campaign-reinstate/5074550001/) [of](https://www.kxan.com/news/local/austin/prop-b-as-austin-heads-to-polls-may-1-polarizing-homeless-camping-ban-takes-center-stage/) [buzz](https://www.youtube.com/watch?v=5az_EKGYOeE) largely due to
[Proposition B](https://www.austintexas.gov/news/council-orders-elections-eight-propositions-may-1-2021).

I saw [this map](https://twitter.com/elium2/status/1388724608224923650?s=20)
on Twitter shortly after the election and was inspired to create my own
version of the map using Python to automate data scraping, and GMT to script
the mapping process.

| ![Final Map](/assets/images/atxmap/plot_shaded.png) |
|:--:|
| Map of 2021 Prop. B Election Results per Precinct |

In this map the color of the precincts depicts the percentage of the vote
"For" Prop. B in the 2021 election.
The gray polygons are regions where the automated scraping was unable to
associate any voting information to the precinct.
From the north-west running to the south-east the Lower Colorado River
is shown in light black.
Even lighter still, the railroad lines are shown as faint dot-dash lines
that can be seen running north-south through the city.

The data scraping process and map generation is all done programmatically via
scripts, making this workflow flexible and extendable to different election
results within the City of Austin.
This workflow is open-source and available
[on GitHub](https://github.com/elbeejay/ATX_PropB_Map) with specifications
about the software used and instructions for re-creating this map.
