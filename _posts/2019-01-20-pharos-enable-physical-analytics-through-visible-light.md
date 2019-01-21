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
Localization through multilateration with LED lights. Each LED light bulb uses BFSK modulation to beaconing its position. Optical channel model estimates distance between a light sensor and LED lights.

### Optical channel model
Given RSS, estimate distance from receiver to LED lights.

**Note:** Estimating the overall RSS from one LED bulb with some component of RSS and $$\alpha$$, where $$\alpha$$ is the bulb's duty cycle of PWM and beaconed by BFSK.
{: .notice}

#### Assumptions
- Lambertian radiation pattern.
- All LED lights facing downward.
- Light sensor facing squarely upward.

### Multilateration
A light sensor needs to observe $$k$$ LED lights, where $$k \ge 3$$
- Newton's method, when $$k = 3$$
- LMS, when $$k > 3$$

[article_link]: https://conferences.sigcomm.org/hotnets/2013/papers/hotnets-final100.pdf

*[LED]: Light-emitting Diode
*[PWM]: Pulse Width Modulation
*[RSS]: Cumulative Distribution Function