---
title: "Indoor Location Sensing Using Geo-Magnetism (2011)"
tags: [fingerprint]
categories: "position"
---

## Published in
MobiSys '11 Proceedings of the 9th international conference on Mobile systems, applications, and services

## Digest
**Positioning system** using **disturbances of the Earth's magnetic field caused by structural steel elements** as **fingerprints** that are **spatially varying** but **temporally stable**.

## Fingerprint

### Collection
At each location, rotate the 3 axes magnetic sensor in a 5 cm diameter circle by a stepper motor with 100 steps per rotation to get $$\mathbf{m}_1,...,\mathbf{m}_{100}$$, where each $$\mathbf{m}$$ is a 3 dimensional vector.

Simulate $$k$$ sensors evenly spaced in circumference, where $$k$$ is an divisor of 100, e.g. 50, 20, 4.

**Note:** [Original paper](article_link) let $$k$$ denotes common denominator, which does not make sense.
{: .notice}

### Positioning
Least root mean square (RMS).

## Evaluation of

### Number of sensors
- Location error vs fingerprint feature numbers

### Location error
- Histogram (proportion vs. error) 
- Cumulative distribution function

### Temporally stablility
- Cosine similarity
- Magnitude

## Links
- [Article][article_link]
- [Slides](https://sigmobile.org/mobisys/2011/slides/magnetism.pdf)

[article_link]: https://www.media.mit.edu/speech/papers/2011/positioning.systems.pdf