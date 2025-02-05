---
title: "USGS Groundwater Analysis in R"
permalink: /projects/gwatlas/
excerpt: "Drought analysis based on groundwater data"
header:
    #image: /assets/images/usgs/gw_logo.png
    teaser: /assets/images/usgs/gw_logo.png
---

Following the [decommissioning of Groundwater Watch](https://waterdata.usgs.gov/blog/gww/), the USGS lacked a user-friendly map interface to view current groundwater conditions.
I was asked to develop an R Shiny app that could act as a stop-gap to allow users to view and interact with groundwater data while a new enterprise-level web application was being developed.

## Shiny Application

The Shiny app (fashioned as an R package, [gwatlas2](https://rconnect.usgs.gov/gwatlas2-docs/)) can be accessed [here](https://rconnect.usgs.gov/gwapp/). This map makes use of a number of other computational and visualization tools to calculate the groundwater statistics and visualize the site-level data.

| ![gwatlas2 Shiny app](/assets/images/usgs/gwatlas.png) |
|:--:|
| Screenshot of the *gwatlas2* Shiny app. |

For the "Climate Response Network" (CRN) I was asked to create a [similar application](https://rconnect.usgs.gov/crn-map/CRNmap.html) that could be used to view the CRN groundwater sites specifically ([source code](https://code.usgs.gov/water/computational-tools/shinyapps/crnmaprmd)).

## Computational Methods

To calculate the basic, national-level statistics for each site, I developed the [precompute R package](https://rconnect.usgs.gov/precompute-docs/) which is run on a daily basis to precompute the statistics for all of the groundwater sites.
When a user clicks on a site to view more detailed information, data is fetched on the fly using the [R dataRetrieval package]({% link _projects/dataretrieval.md %}), that data is then processed using the [R HASP](https://github.com/DOI-USGS/HASP) package.

| ![Site page example](/assets/images/usgs/site_page.png) |
|:--:|
| Example of a single groundwater site page. |

## Deployment Strategy

While the enterprise-level solution is being developed, the Shiny application is currently deployed via Posit Connect.
The individual site pages themselves are actually generated via an [R plumber Swagger API](https://rconnect.usgs.gov/GWsitereport/__docs__/) that I wrote and deployed via Posit Connect.

| ![Site Page API](/assets/images/usgs/gw_api.png) |
|:--:|
| The site page Swagger API page. |

To help others create similar groundwater monitoring applications, I also created a ["regionaldemo" R package](https://rconnect.usgs.gov/regionalapp-docs/) that includes setup instructions and customization information.