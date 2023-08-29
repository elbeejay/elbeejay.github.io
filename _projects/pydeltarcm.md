---
title:  "Modernizing DeltaRCM"
permalink: /projects/pydeltarcm/
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
*pyDeltaRCM* implements a faster version of the reduced-complexity approach
to river delta modeling established in the original *DeltaRCM* model.
*pyDeltaRCM* also enables reproducibility by automatically recording the
random-seed used to generate a given model output.
Furthermore, the use of Python makes this new model open-source and accessible.
Splitting the model into different components in an object-oriented framework
has made the code customizable via subclasses and hooks.

For more about this project, refer to the
[documentation](https://deltarcm.org/pyDeltaRCM/) or the
[source code](https://github.com/DeltaRCM/pyDeltaRCM) itself.
*pyDeltaRCM* is an open-source project and we welcome any new developers and
contributors to this effort.
Currently the project is being developed by
[Andrew Moodie](https://andrewjmoodie.com/),
[Eric Barefoot](http://ericbarefoot.com/), and me.

### Publications
---

<font size="3">
Moodie, A. J., Hariharan, J., Barefoot, E., & Passalacqua, P. (2021). <i>pyDeltaRCM</i>: a flexible numerical delta model. Journal of Open Source Software, 6(64), 3398. <a href="https://doi.org/10.21105/joss.03398">https://doi.org/10.21105/joss.03398</a>
</font>

### In Other Media
---

<font size="3">
"Building Modern Tools for River Delta Simulation and Analysis," UTIG Discussion Hour, April 13, 2021. <a href="https://www.youtube.com/watch?v=wFDxGKvnxpo">https://www.youtube.com/watch?v=wFDxGKvnxpo</a>
</font>
