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
Quantify the effects of various environmental factors to RSS. localization RSS ranging-based  multi-hop sensor network in special environment and device setup.

## Multi-hop
in which nodes use RSS to estimate distances to other nodes and can
localize themselves even while being multiple hops
from the nearest anchor node.

## Quantities
Quantify the effects of environmental factors on RSS.
- **noise**: Standard deviation of all RSS values that may be observed at a particular distance in a given environment.

- **attenuation rate**: Rate of decrease of RSS respect to distance.

- **effective range**: Integral over the probability of making a RSS measurement at a particular distance 
$$p(\mathit{measurement}| d)$$ weighted by the probability of finding a neighbor at that distance $$\Pi * d^2$$.

**Note:** [Article](article_link) does not explain what $$\Pi$$ is. They are probably assuming nodes' projection onto 2D plane follows uniform distribution so that the probability of finding a neighbor is proportional to the area of circle with radius $$d$$, i.e. proportional to $$\pi d^2$$. However this is not 
{: .notice}

 However, we also show that this result is highly sensitive to subtle environmental factors such as the grass height, radio enclosure, and elevation of the nodes from the ground.


[article_link]: http://www.chriskarlof.com/papers/whitehouse07practical.pdf

*[RSS]: Received Signal Strength