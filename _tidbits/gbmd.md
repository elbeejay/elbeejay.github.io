---
title: "Surface Water Detection"
permalink: /tidbits/surfwater/
excerpt: "Remote sensing to objectively identify surface water."
header:
    #image: /assets/images/construction.png
    teaser: /assets/images/gbmd/logo.png
---

The [Landsat](https://landsat.gsfc.nasa.gov/) mission has been collecting
imagery of the Earth's surface for over 3 decades now.
To analyze these images, many many different methods have been developed.

| ![RGB Landsat Images](/assets/images/gbmd/GBMD_RGB_animation_smaller.gif) |
|:--:|
| Animation of composite Landsat imagery |

Below, an example of the convolutional deep learning neural network
[DeepWaterMap](https://github.com/isikdogan/deepwatermap) applied to Landsat
imagery of the Ganges-Brahmaputra-Meghna River Delta is shown.
DeepWaterMap performs objective surface water detection, a prerequisite for
many different temporal analyses of river systems.

DeepWaterMap was created by [Leo Isikdogan](https://www.isikdogan.com/), to
read more about it, check out one of the journal articles describing the
algorithm and its development
([2017 paper](https://ieeexplore.ieee.org/document/8013683),
[2019 paper](https://ieeexplore.ieee.org/document/8913594)).

| ![Water Maps](/assets/images/gbmd/GBMD_animation_smaller.gif) |
|:--:|
| Animation of surface water extents as identified by DeepWaterMap |

Landsat imagery and DeepWaterMap results were manipulated and animated using
the open-source tools [GDAL](https://gdal.org/),
[pillow](https://python-pillow.org/),
[imageio](https://imageio.github.io/),
and [pygifsicle](https://github.com/LucaCappelletti94/pygifsicle).
