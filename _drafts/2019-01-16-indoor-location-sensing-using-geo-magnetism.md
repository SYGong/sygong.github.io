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
- Cosine similarity, 

$$\mathit(CosineSimilarity)(A, B) = \frac{1}{n} \sum_{i=1}{n} \frac{A_i B_i}{\left\Vert A_i \right\Vert \left\Vert B_i \right\Vert}$$, where 

This is a average cosine similarity of each pair of vector, can we use $$\mathit(CosineSimilarity)(A, B) = <A, B>_F{\left\Vert A \right\Vert_F \left\Vert B \right\Vert_F}$$ where $$<A, B>_F$$ is Frobenius norm? 

- Magnitude 

## Links
- [Article][article_link]
- [Slides](https://sigmobile.org/mobisys/2011/slides/magnetism.pdf)

[article_link]: https://www.media.mit.edu/speech/papers/2011/positioning.systems.pdf