---
title: "The Horus WLAN Location Determination System (2000)"
tags: []
categories: "position"
---

## Published in
- Journal  
Wireless Networks archive  
Volume 14 Issue 3, June 2008 

### Online copies
[Article][article_link]
/
[Slides](http://www0.cs.ucl.ac.uk/staff/B.Karp/gz06/s2009/gz06_s2009_groupA.pdf)

## Synopsis

identifies different causes for the wireless channel variations and addresses them to achieve its high accuracy. It
uses location-clustering techniques to reduce the computational requirements of the algorithm.

## Variations

### Temporal variations


### Spatial characteristics


|---------------------+---------------------|
| Wave                | Speed in air (m/ms) |
|---------------------| ------------------: |
| sound               | 0.34    |
| radio               | 299700  |


Medium Speed

$$\tao << c$$, where $$\tao$$ and $$c$$ is speed of sound and light in air, re


## Features
- Decentralized
- User privacy preserved

Cricket is the result of several design goals, including
user privacy, decentralized administration, network heterogeneity,
and low cost. We describe
the randomized algorithm used by beacons to transmit information,

We achieve this by measuring the one-way propagation
time of the ultrasonic signals emitted by a beacon, taking advantage
of the fact that the speed of sound in air (about 1.13 ft/ms at
room temperature) is much smaller than the speed of light (RF) in
air. On each transmission, a beacon concurrently sends information
about the space over RF, together with an ultrasonic pulse.

**Note:** *radio map* are fingerprints with their locations.
{: .notice}

{::comment}
## Training
puts real locations in a floor plan into a high dimension space by MDS , such that the geometrical distances between the points in the high dimension space reflect
their real walking distances. , MDS is used to create a high dimension space, in which fingerprints are represented by points,
and their mutual distances are preserved.In traditional approaches, fingerprints are geographically unrelated, losing
the possibility of building fingerprint space.

## Fingerprint

## Collision handle
randomization.
The choice of random interval
is governed by the number of beacons we typically expect
will be within range of each other and the time it takes for the
transmitted information to reach the listeners, which depends on
the message size and link bandwidth.

We minimize errors due to RF and ultrasonic interference among
beacons by two methods: (i) proper selection of system parameters
to reduce the chance of false correlations, and (ii) listener inference
algorithms based on statistical analysis of correlated 􀀀 RF,US

samples.

The precision of the system
is determined by how well the listener can detect the boundary between
two spaces, while the granularity of the system is the smallest
possible size for a geographic space such that boundaries can be
detected with a high degree of precision. A third metric, accuracy is
used to calibrate individual beacons and listeners; it is the degree to
which the distance from a beacon, estimated by a listener, matches
the true distance.

The listeners implement a decoding
algorithm to overcome the effects of ultrasound multipath
and RF interference. We investigate the performance of three decoding
algorithms and find that picking the location corresponding
to the beacon with minimum statistical mode performs the best,

## Fingerprint matching
nearest neighbor algorithm
{:/comment}

[article_link]: http://nms.lcs.mit.edu/papers/cricket.pdf

*[RSS]: Received Signal Strength
*[GSM]: Global System for Mobile communications
*[SLAM]: Simultaneous Localization and Mapping
*[MDS]: Multidimensional Scaling