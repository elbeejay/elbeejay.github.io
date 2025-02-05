---
title: "Estimating River Depth"
permalink: /projects/riverdepth/
excerpt: "Web-tool to measure river width and estimate depth"
header:
    # image: /assets/images/riverwidth/logo.png
    teaser: /assets/images/riverwidth/logo.png
---

| ![Tool Interface](/assets/images/riverwidth/01.png) |
|:--:|
| Initial tool interface |

To learn a bit of JavaScript, I decided to write a simple tool that would allow users to measure the width of a river and estimate the depth with some uncertainty.
The webpage itself is a static HTML file that is hosted on GitHub Pages and available [here](https://jayaramhariharan.com/river-width-depth-calculator/).

To use the tool the user can either enter river width measurements, or make measurements on the map by hand.
For convenience, the ESRI World Imagery basemap is also available to help make the measurements.
Once a number of width measurements have been made, the user can click the "Calculate Depth" button to estimate the depth.

| ![Tool Output](/assets/images/riverwidth/02.png) |
|:--:|
| Example tool usage and output |

The calculations are based off of functional relationships between river width, depth, and discharge as they were first described by Leopold and Maddock in 1953 ([Link](https://semspub.epa.gov/work/01/554357.pdf)).
Coefficients for the relationships, as well as the coefficients for the 95% confidence intervals were obtained from a more recent study by Moody and Troutman in 2002 ([Link](https://onlinelibrary.wiley.com/doi/pdf/10.1002/esp.403?casa_token=Za3AyMwoQtgAAAAA:mqentCE1utPtdvX5HqJKC2WEZQ9Qa3JAtMZUoVkSwGVgLmEYi6myaSXUaWZ9NpnK8yTrAOB6EX8D4w)).

Naturally, this is more of a toy tool than a serious model for estimating river depth from width, but was a good exercise in web development and JavaScript.