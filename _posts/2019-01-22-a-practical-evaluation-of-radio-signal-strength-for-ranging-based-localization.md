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

- **effective range**: Integral over the probability of making a RSS measurement at a particular distance $$p(measurement|d)$$ weighted by the probability of finding a neighbor at that distance $$\Pi d^2$$



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

**Note:** Overall RSS is estimated, given some components of RSS and the [broadcasted](#broadcast) duty cycle of PWM.
{: .notice}

### Assumptions of model
- Lambertian radiation pattern.
- All bulbs facing downward.
- Light sensor facing squarely upward.

## Broadcast
Use BFSK for modulation to broadcast each LED bulb's
- position, and
- duty cycle of PWM.

### Mitigate collisions
Random channel hopping.

#### Channelization
Whole available spectrum is bounded by 
- minimum frequency to prevent human perceivable flickering, 
- minimum of LED bulb’s On/Off speed, and
- response speed of the light sensor on the receiver.

## Localization algorithm
Let $$n$$ denotes number LED bulbs observed. Use
- Newton's method, when $$n = 3$$;
- LMS method, when $$n > 3$$.

## Evaluation

- Compared to LED based algorithms that locate receiver to
   - position of the light source with the highest RSS, or
   - weighted average of the locations of the observed bulbs, using their RSS as weights.

- Compared to Wi-Fi based systems in terms of
   - accuracy,
   - database usage, and
   - overhead.

[article_link]: http://www.chriskarlof.com/papers/whitehouse07practical.pdf

*[LED]: Light-emitting Diode
*[PWM]: Pulse Width Modulation
*[RSS]: Received Signal Strength
*[BFSK]: Binary Frequency Shift Keying