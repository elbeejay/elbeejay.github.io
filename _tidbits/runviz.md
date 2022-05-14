---
title: "Visualizing My Runs"
permalink: /tidbits/run-viz/
excerpt: "Animating the 31 runs I took in Jan. 2022"
header:
    #image: /assets/images/construction.png
    teaser: /assets/images/runs/logo.png
---

In January 2022 I went for a run every day and I tracked these runs using
[Strava](https://www.strava.com/dashboard).
At the end of the month, I wanted a unique graphic displaying my efforts, so I
decided to download my Strava data and figure out how parse, analyze, and
visualize the runs I took in January.

Long story short, I was able to produce the animation shown below.
Data parsing and visualization took place using
[Python](https://www.python.org/), and relied heavily
on the [matplotlib](https://matplotlib.org/), [numpy](https://numpy.org/),
[pandas](https://pandas.pydata.org/),
[gpxpy](https://github.com/tkrajina/gpxpy), and
[cartopy](https://scitools.org.uk/cartopy/docs/latest/) libraries.
At the end of the Python processing, the individual frames for the animation
were turned into a gif using [ffmpeg](https://ffmpeg.org/).
The codes used to generate this visualization are available on GitHub in the
[StravaActivityVisualizer](https://github.com/elbeejay/StravaActivityVisualizer) repository.

| ![Jan. Runs](/assets/images/runs/janruns.gif) |
|:--:|
| Animation of all 31 of my runs in January 2022 if they began simultaneously. |
