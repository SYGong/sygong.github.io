---
title: "The Cricket Location-Support System (2000)"
tags: []
categories: "position"
---

## Published in
- Proceeding  
MobiCom '00 Proceedings of the 6th annual international conference on Mobile computing and networking

### Online copies
[Article][article_link]
/
[Slides](http://www0.cs.ucl.ac.uk/staff/B.Karp/gz06/s2009/gz06_s2009_groupA.pdf)

## Synopsis
Combination of [**RF and ultrasound**](#speed-of-signals) to enable a listener to [determine the distance](#distance-measurement) to beacons.

## Localization

### Speed of signals

|---------------------+---------------------+----------|
|                     | Denote speed of     | Approximate value in air $$(m/ms)$$ |
|---------------------| ------------------: |--------: |
| $$v_s$$             | ultrasound          | 0.34     |
| $$v_r$$             | RF                  | 299700   |

### Distance measurement 
Distance between beacon and listener  
$$d =  \frac{v_rv_s(t_s - t_r)}{v_r - v_s} \approx v_s(t_s - t_r)$$,  
where $$t_s$$ and $$t_r$$ are the time listener receives of RF and ultrasound signal, respectively.

## Features
- Decentralized, and
- User privacy preserved, a listener is completely passive. 

{::comment}
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

On each transmission, a beacon concurrently sends information
about the space over RF, together with an ultrasonic pulse.
Use concurrent radio and ultrasonic signals to infer distance, the listener inference algorithms to overcome multipath and interference, and practical beacon configuration and positioning techniques that improve accuracy.

**Note:** *radio map* are fingerprints with their locations.
{: .notice}

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

The only configuration required in Cricket is setting the string for
a space that is disseminated by a beacon. The specific string is a
function of the resource discovery protocol being used, and Cricket
allows any one of several possibilities (in Section 5 we describe our
implementation platform and integration with INS). Cricket also
provides a way by which the owner of a room can securely set and
change the space identifier that is sent in the advertisements. This is
done by sending a special message over the same RF channel that
is used for the advertisements, after authenticating the user via a
password. At this stage, we have chosen to allow this change only
from within physical proximity of the room or location where the
beacon is located. This makes the system somewhat more secure
than if we allowed this to be done from afar.

## Fingerprint matching
nearest neighbor algorithm
{:/comment}

[article_link]: http://nms.lcs.mit.edu/papers/cricket.pdf

*[RF]: Radio Frequency