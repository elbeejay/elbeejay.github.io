---
title: "Synthesizing SWIR Data with *SynthSWIR*"
permalink: /projects/synthswir/
excerpt: "Basic ML model to infer SWIR bands from RGB+NIR data"
header:
    # image: /assets/images/synthswir/logo.png
    teaser: /assets/images/synthswir/logo.png
---

While developing water masks to extract graphs for the [graph flux estimation project]({% link _projects/graphflux.md %}), I was using *deepwatermap* to identify surface water from Landsat and Sentinel-2 imagery.
Through the Planet [Education and Research Program](https://www.planet.com/industries/education-and-research/), I also had access to some PlanetScope imagery, which was at a much higher spatial resolution and therefore resolved smaller channels, critical for the characterization of smaller river deltas.
Unfortunately, the PlanetScope imagery lacked the same spectral bands as the Landsat and Sentinel-2 imagery, and thus was incompatible with the *deepwatermap* package.

To address this incompatibility, I developed a basic ML model, *SynthSWIR*, to infer SWIR bands from RGB+NIR data.
The premise is that the information encoded in the SWIR bands is highly correlated with the information encoded in the other available spectral bands to an extent that is sufficient enough to apply *deepwatermap* and extract water masks.
Furthermore, when processing the higher-resolution Planet imagery through the *deepwatermap* model, we have some confidence that the model can identify surface water on imagery at a higher resolution than it was trained on because natural water bodies are highly fractal and thus self-similar across scales.
While re-training *deepwatermap* with RGB+NIR data would have been the ideal solution, this would have required re-creating the training dataset, and obtaining access to a sufficiently large computer cluster to train the model.
By developing a small "auxiliary" model that attempts to alter the input data such that it is compatible with the pre-trained *deepwatermap* model, the expense of re-training the larger model is avoided.

The *SynthSWIR* model I developed does not account for the spatial arrangement of the pixels, but rather just attempts to infer the SWIR bands from the RGB+NIR data on a per-pixel basis.

| ![Model Architecture](/assets/images/synthswir/ModelSchematic.png) |
|:--:|
| Neural network architecture for the *SynthSWIR* model |

The results were promising, as we found that the results from the PlanetScope imagery resolved the smaller channels that were missed in the Landsat imagery.

| ![Imagery comparison](/assets/images/synthswir/LandsatPlanetComparison_01.png) |
|:--:|
| Comparison between PlanetScope and Landsat imagery |

When we quantified the "distance from water" in wetland imagery taken nearly coincidentally by Landsat and PlanetScope, we found that the median distance to a water body was about 50 meters closer in the Planet imagery.

| ![Wetland comparison](/assets/images/synthswir/WetlandsFig01.png) |
|:--:|
| Comparison in wetland imagery between Landsat and PlanetScope |

To evaluate the ability of the *SynthSWIR* model to estimate the Landsat SWIR-1 and SWIR-2 bands, I used Landsat imagery with the SWIR bands removed and compared the results to the "true" SWIR band data.
The resulting errors in the estimates were small and unbiased, suggesting that this model was able to infer the SWIR bands from the RGB+NIR data.

| ![Model evaluation](/assets/images/synthswir/LandsatSWIRComparison_alt.png) |
|:--:|
| *SynthSWIR* model evaluation on Landsat imagery with SWIR bands removed |

I also compared the performance of this bespoke *SynthSWIR* model to a simpler Random Forest model, as well as naive substitution of the SWIR bands with the RGB or NIR bands before processing with *deepwatermap*, and consistently found that the *SynthSWIR* substituted SWIR bands resulted in better surface water identification results.
