---
title: "Pharos: Enable Physical Analytics through Visible Light based Indoor Localization (2013)"
tags: []
categories: "position"
---

## Links
[Article][article_link]
/
[Slides](https://pdfs.semanticscholar.org/6272/602dba3a4fc36c58a94a3bd9b3a6fd140100.pdf)

## Published in
- HotNets-XII Proceedings of the Twelfth ACM Workshop on Hot Topics in Networks

## Digest
Localization with LED bulbs. Each bulb broadcasting its own postion to receiver, who will estimate the distance to each bulb with [optical channel model](#optical-channel-model). 

### Optical channel model
Given received energy, estimate distance between receiver's light sensor and the LED bulb.

{::comment}
**Note:** Overall energy is estimated, given some components of energy and the bulb's duty cycle of PWM.
{: .notice}

{:/comment}

#### Assumptions
- Lambertian radiation pattern.
- All LED lights facing downward.
- Light sensor facing squarely upward.

{::comment}
### BFSK for beaconing
LED light bulb's
- Position.
- Duty cycle of PWM $$\alpha$$.

### Multilateration
Receiver needs to observe $$k$$ LED lights, where $$k \ge 3$$. Use
- Newton's method, when $$k = 3$$
- LMS method, when $$k > 3$$

{:/comment}

[article_link]: https://conferences.sigcomm.org/hotnets/2013/papers/hotnets-final100.pdf

*[LED]: Light-emitting Diode
*[PWM]: Pulse Width Modulation
*[RSS]: Received Signal Strength