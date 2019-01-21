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
Localization through multilateration with LED bulbs. Each bulb broadcasting its own postion to receiver, who will estimate distance to each bulb by optical channel model. 

### Optical channel model
Given RSS, estimate distance between reciever's light sensor and LED bulb.

**Note:** Estimating the overall RSS with some components of RSS and the bulb's duty cycle of PWM.
{: .notice}

#### Assumptions
- Lambertian radiation pattern.
- All LED lights facing downward.
- Light sensor facing squarely upward.

[article_link]: https://conferences.sigcomm.org/hotnets/2013/papers/hotnets-final100.pdf

*[LED]: Light-emitting Diode
*[PWM]: Pulse Width Modulation
*[RSS]: Cumulative Distribution Function