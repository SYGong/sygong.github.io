---
title: "Indoor Localization System using RSSI Measurement of Wireless Sensor Network based on ZigBee Standard (2006)"
tags: []
categories: "position"
---

## Published in
- International Journal on Wireless & Optical Communications    
January 2006

### Online copies
[Article][article_link]

## Synopsis
Indoor [localization](#localization) technique **using RSSI** in a ZigBee sensor network to **[estimates the distance](#distance)** between sensor nodes.

## Distance
RSSI $$p$$ (in $$\mathit{dB}m$$) is a function of distance $$d$$:

$$\mathit{p} = \alpha\ln{d} + \beta$$.

**Note:** Not sure ZigBee RSSI is in $$\mathit{dB}m$$.
{: .notice}
**Note:** $$\alpha$$ and $$\beta$$ are computed by empirical RSSI and distance data using least-squares method.
{: .notice}
**Note:** $$\alpha$$ and $$\beta$$ vary in different place. No model fits all situation.
{: .notice}

## Localization
- Maximum likelihood
- MMSE

{::comment}
minimizing the differences between model estimated and  distances.
{:/comment}

**Note:** implicit assumption of normal distribution.
{: .notice}



[article_link]: http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.105.4355&rep=rep1&type=pdf

*[MMSE]: Minimum Mean Square Error
*[RSSI]: Received Signal Strength Indicator