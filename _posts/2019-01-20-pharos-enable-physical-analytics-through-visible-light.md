---
title: "Pharos: Enable Physical Analytics through Visible Light based Indoor Localization (2013)"
tags: []
categories: "position"
---

## Published in
- HotNets-XII Proceedings of the Twelfth ACM Workshop on Hot Topics in Networks

### Online copies
[Article][article_link]
/
[Slides](https://pdfs.semanticscholar.org/6272/602dba3a4fc36c58a94a3bd9b3a6fd140100.pdf)

## Synopsis
**[Localization](#localization-algorithm) with LED bulbs**. Each bulb use **[BFSK to broadcasting](#broadcast)** its own postion to a receiver, who will estimate its distance to each bulb with **[optical channel model](#optical-channel-model)**. 

## Optical channel model
Given RSS, estimate distance between a receiver's light sensor and the bulb.

**Note:** Overall RSS is estimated, given some components of RSS and the [broadcasted](#broadcast) duty cycle of PWM.
{: .notice}

### Assumptions of model
- Lambertian radiation pattern.
- All bulbs facing downward.
- Light sensor facing squarely upward.

## Broadcast
Use BFSK for modulation to broadcast each LED bulb's
- position
- duty cycle of PWM

### Mitigate collisions
Random channel hopping.

#### Channelization
Whole available spectrum is bounded by 
- minimum frequency to prevent human perceivable flickering 
- minimum of LED bulb’s On/Off speed 
- response speed of the light sensor on the receiver

## Localization algorithm
- Newton's method, when $$n = 3$$
- LMS method, when $$n > 3$$

where $$n$$ is number LED bulbs observed.

## Evaluation

- Compared to two LED based algorithm 
   - Locates a receiver to the position of the light source with the highest RSS.
   - Locates a receiver as the weighted average of the locations of the observed bulbs, using their RSS as weights.

- Compared to Wi-Fi based systems in terms of
   - Accuracy
   - Database usage
   - Overhead

[article_link]: https://conferences.sigcomm.org/hotnets/2013/papers/hotnets-final100.pdf

*[LED]: Light-emitting Diode
*[PWM]: Pulse Width Modulation
*[RSS]: Received Signal Strength
*[BFSK]: Binary Frequency Shift Keying