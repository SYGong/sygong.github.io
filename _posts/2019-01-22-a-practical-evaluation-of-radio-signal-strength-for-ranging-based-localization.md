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
Radio signal strength (RSS) is notorious for being a noisy signal that is difficult to use for
ranging-based localization. In this study, we demonstrate that RSS can be used to localize
a multi-hop sensor network. quantify the effects of various environmental factors. However, we also show that
this result is highly sensitive to subtle environmental factors such as the grass height, radio
enclosure, and elevation of the nodes from the ground.

## Quantities
Quantify the effects of environmental factors on RSS.
- **noise**: Standard deviation of all RSS values that may be observed at a particular distance in a given environment.

- **attenuation rate**: Rate of decrease of RSS respect to distance.

- **effective range**: Integral over the probability of making a RSS measurement at a particular distance 
$$p(\mathit{measurement}| d)$$ weighted by the probability of finding a neighbor at that distance $$\Pi * d^2$$.

**Note:** [Article](article_link) does not explain what $$\Pi$$ is. They are probably assuming nodes' projection onto 2D plane follows uniform distribution so that the probability of finding a neighbor is proportional to the area of circle with radius $$d$$, i.e. proportional to $$\pi d^2$$.
{: .notice}

Noise is the standard deviation σ of all RSS values that may be observed at a particular distance in a
Mobile Computing and Communications Review, Volume 1, Number 2 2
given environment. 

Much greater variation can be observed by
placing a single pair of nodes in more than one location, due to the effects of changing environmental factors such as trees or walls. 

. Finally, individual radios
can vary significantly in both transmission strength
and receptivity, especially in cheap, low-power radios

We collected the RSS data in this study using a
novel data collection technique that we presented in
[35], which uses a specially generated 2D topology
of 30 nodes where each pair of nodes in the topology
measure a different distance.

three characteristics


[article_link]: http://www.chriskarlof.com/papers/whitehouse07practical.pdf

*[RSS]: Received Signal Strength