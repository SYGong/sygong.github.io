---
title: "Indoor Location Sensing Using Geo-Magnetism (2011)"
tags: [fingerprint]
categories: "position"
---

## Published in
MobiSys '11 Proceedings of the 9th international conference on Mobile systems, applications, and services

## Digest
**Positioning system** using **disturbances of the earth's magnetic field caused by structural steel elements** as **fingerprints** that are **spatially varying** but **temporally stable**.

## Fingerprint

### Collection
At each location, rotate the 3 axes magnetic sensor in a 5 cm diameter circle by a stepper motor with 100 steps per rotation to get $$\mathbf{m}_1,...,\mathbf{m}_{100}$$, where each $$\mathbf{m}$$ is a 3 dimensional vector.

Simulate $$k$$ sensors evenly spaced in circumference, where $$k$$ is an divisor of 100, e.g. 50, 20, 5, 4.

**Note:** [Paper](article_link) let $$k$$ denotes common denominator, which does not make sense.
{: .notice}

### Predict position and orientation
Least RMS based Nearest Neighborhood.

**Note:** [Paper](article_link) uses RMS a lot, however it does not calculate arithmetic mean of the squares (refer to Equation 1).
{: .notice}

{::comment}
Essentially just least squares of each axes? From equation 1 we can tell they don't average k nor 3 (axes)
{:/comment}

## Evaluation of

### Location error

{::comment}
These two are for corridor, where data collected in a line
- Confusion matrix of RMS errors (ground truth postiion vs. predicted position)
- Least RMS errors (ground truth postiion vs. predicted position)
{:/comment}
- Histogram (proportion vs. distance error) 
- CDF of distance error

### Number of sensors
- RMS error vs fingerprint feature numbers

### Temporally stablility
- Cosine similarity

{::comment}
$$\mathit(CosineSimilarity)(A, B) = \frac{1}{n} \sum_{i=1}{n} \frac{A_i B_i}{\left\Vert A_i \right\Vert \left\Vert B_i \right\Vert}$$, where ... 

This is a average cosine similarity of each pair of vector, can we use $$\mathit(CosineSimilarity)(A, B) = <A, B>_F{\left\Vert A \right\Vert_F \left\Vert B \right\Vert_F}$$ where $$<A, B>_F$$ is Frobenius norm? 
{:/comment}
- Magnitude

### Effect of moving objects
- RMSE vs. distance to object (e.g. elevator, laptop)

{::comment}
Not sure details of RMSE
{:/comment}

## Links
- [Article][article_link]
- [Slides](https://sigmobile.org/mobisys/2011/slides/magnetism.pdf)

[article_link]: https://www.media.mit.edu/speech/papers/2011/positioning.systems.pdf

*[RMS]: Root Mean Square
*[CDF]: Cumulative Distribution Function