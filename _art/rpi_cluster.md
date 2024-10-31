---
title: "A Bramble of Raspberry Pis"
permalink: /art/rpibramble/
excerpt: "Distributed computing with Raspberry Pis"
header:
    #image: /assets/images/construction.png
    teaser: /assets/images/rpi/logo.png
---

The availability of relatively cheap computing resources via
[Raspberry Pis](https://www.raspberrypi.org/), combined with the faster,
flexible, and open-source version of DeltaRCM that we'd just developed
([*pyDeltaRCM*]({% link _projects/pydeltarcm.md %})) piqued my curiosity
about networking and managing a small cluster of computing resources.

I ended up acquiring a set of Raspberry Pi 4s; my current set up is below.
This became an interesting learning experience about networking and
head-less ssh connections.

| ![Example Landsat Mosaic](/assets/images/rpi/pi_cluster.jpg) |
|:--:|
| 4 RasberryPis (right) connected via an ethernet switch (bottom right). Powered via USB power hub (bottom left) with a shared 256GB SSD NFS drive (center left).|

Ultimately, this little project of mine has been a success. By running
64-bit Ubuntu Server on each of the Pis, I have been able to successfully
install pyDeltaRCM and simulate river delta evolution on these little
devices. Each Pi has 4 CPU cores, and since pyDeltaRCM enables easy
parallelization, I am able to comfortably run 3 simultaneous simulations
per Pi, so 12 in total. While the CPUs themselves are not wildly fast or
powerful, for model domain sizes and durations similar to those in the
[early](https://doi.org/10.5194/esurf-3-67-2015)
[DeltaRCM](https://doi.org/10.1002/2015JF003653)
[publications](https://doi.org/10.1002/2016GL070519),
each run completes in 2 days.
This means that every 2 days, a set of 12 simulations of a reasonable domain
size, simulating about 150 years of time, can be completed.
Extrapolating to a month, that is 180 model runs!
This volume of output opens up many possibilities for model experimentation,
all while not requiring CPU resources from my primary workstation.

The Pis are connected to a common
[NFS drive](https://www.minitool.com/lib/what-is-nfs.html),
which I can access from my
desktop. This connectivity means I do not have to individually `ssh` into each
Pi to transfer model outputs via `scp`. Instead, I can mount the NFS drive
on my primary computer and pull the model outputs from there. At this time I
have yet to turn the set of 4 Pis into a single coherent "cluster" that accepts
jobs and distributes them. So figuring out how to do that is the next step for
me, right now I have to `ssh` into each Pi individually to start any set of
model runs.
