---
title: "Combining Model Meshes"
permalink: /art/mesh/
excerpt: "Coupling mesh generators and Landlab"
header:
    #image: /assets/images/construction.png
    teaser: /assets/images/mesh/logo.png
---

I've had fun messing with the popular (and open-source!) landscape evolution
model, [Landlab](http://landlab.github.io). Landlab itself comes packaged with
a ton of different modules and components allowing one to conduct a variety of
numerical experiments.

I wanted to see if other mesh generators could be coupled to the Landlab
interface. This would enable testing a variety of mesh schemes that go beyond
the scope of the Landlab project itself. My driving question was:
**can we see the effects of local grid resolution in Landlab?**

To answer this question, I turned to the mesh generator
[dmsh](https://github.com/nschloe/dmsh), and the C-package *triangle* embedded
within the hydrodynamic model [anuga](https://anuga.anu.edu.au/).

This little project has turned into a "lab" component in the [CSDMS suite of
educational lab exercises](https://csdms.colorado.edu/wiki/Lab-0020).
Additional information and notebooks are available in the project
[documentation](https://elbeejay.github.io/meshing-with-landlab/).

A short set of images showcasing some of these results using Landlab's
[flow accumulator](https://landlab.readthedocs.io/en/master/reference/components/flow_accum.html)
are shown below:

| ![Mesh from Smooth Topography](/assets/images/mesh/mesh_process.png) |
|:--:|
| A mesh with variable resolution (left), and the source smooth topography (right) |

&nbsp;

| ![Mesh without outlines](/assets/images/mesh/meshed_topo.png) |
|:--:|
| The variable resolution mesh without cell outlines. |

&nbsp;

| ![Flow accumulation](/assets/images/mesh/flow_accumulation.png) |
|:--:|
| Flow accumulation on the variable resolution mesh. Resolution differences make the top and bottom halves of the image look quite different! |
