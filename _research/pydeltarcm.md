---
title:  "Modernizing DeltaRCM"
permalink: /research/pydeltarcm/
excerpt: "Making DeltaRCM modern and modular"
header:
    #image: /assets/images/pydeltarcm/logo.png
    teaser: /assets/images/pydeltarcm/logo.png
---

| ![Example Model](/assets/images/pydeltarcm/logo.png) |
|:--:|
| Example model topography with overlaid reduced-complexity "parcels" paths |

*pyDeltaRCM* is a documented, tested, and modular version of the popular
*DeltaRCM* model [[1](https://esurf.copernicus.org/articles/3/67/2015/),
[2](https://esurf.copernicus.org/articles/3/87/2015/)].
*pyDeltaRCM* is currently under development, but greatly speeds up the
reduced-complexity approach to river delta modeling established in the
original *DeltaRCM*. This speed-up is made possible through the use of
"jitted" methods. *pyDeltaRCM* also enables reproducibility with methods to
record and maintain the random-seed used for a given model.
Furthermore, the use of Python makes this new model open-source and accessible.
Splitting the model into different components in an object-oriented framework
makes the model makes customization easy via subclasses and hooks.

For more about this project, refer to the
[documentation](https://deltarcm.org/pyDeltaRCM/) or the
[source code](https://github.com/DeltaRCM/pyDeltaRCM) itself.
*pyDeltaRCM* is an open-source project and we welcome any new developers and
contributors to this effort.
Currently the project is being developed by
[Andrew Moodie](https://andrewjmoodie.com/),
[Eric Barefoot](http://ericbarefoot.com/), and me.
