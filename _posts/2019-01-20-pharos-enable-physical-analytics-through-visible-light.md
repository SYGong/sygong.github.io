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

### BFSK
To beaconing LED light bulb's
- Position.
-  $$\alpha$$.

### Optical channel model
Given RSS, estimate distance from receiver to LED lights.

#### Assumptions
- Lambertian radiation pattern.
- All LED lights facing downward.
- Light sensor facing squarely upward.

**Note:** Estimating the overall RSS with some component of RSS and duty cycle of PWM $$\alpha$$ (also beaconed by BFSK).
{: .notice}

### Localization
Need to observe 3 or more LED lights.
- Newton's method for 3 
- LMS for overdetermined

[article_link]: https://conferences.sigcomm.org/hotnets/2013/papers/hotnets-final100.pdf

*[LED]: Light-emitting Diode
*[PWM]: Light-emitting Diode
*[RSS]: Cumulative Distribution Function