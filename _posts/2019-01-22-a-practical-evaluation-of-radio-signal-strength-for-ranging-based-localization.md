---
title: "A Practical Evaluation of Radio Signal Strength for Ranging-based Localization (2007)"
tags: []
categories: "position"
---

## Published in
- Newsletter  
ACM SIGMOBILE Mobile Computing and Communications 

### Online copies
[Article][article_link]

## Synopsis
Use [**RSS and multilateration to locate**](#localization) nodes in multi-hop sensor network under some conditions. [**Quantify**](#quantities) the effects of [**various environmental factors**](#environmental-factors).

## Localization
Each node use **linear RSS-to-distance model** to estimate distances to other nodes, find [shortest path](shortest-path) to each anchor whose position is given. Shortest path distances are then used for **multilateration**.

### Shortest path
- distance: DV-distance algorithm
- APS

## Quantities
Quantify the effects of environmental factors on RSS.
- **noise**: Standard deviation of all RSS values that may be observed at a particular distance in a given environment.
- **attenuation rate**: Rate of decrease of RSS respect to distance.
- **effective range**: Integral over the probability of making a RSS measurement at a particular distance 
$$p(\mathit{measurement} | d)$$ weighted by the probability of finding a neighbor at that distance $$\Pi * d^2$$.

**Note:** [Article](article_link) does not explain what $$\Pi$$ is. It is probably assuming nodes' projection onto 2D plane follows uniform distribution so that the probability of finding a neighbor is proportional to the area of circle with radius $$d$$, i.e. proportional to $$\pi d^2$$.
{: .notice}

## Environmental factors
- Time
- Elevation
- Vegetation
- Transmission power
- Packaging
- Indoor environment

[article_link]: http://www.chriskarlof.com/papers/whitehouse07practical.pdf

*[RSS]: Received Signal Strength