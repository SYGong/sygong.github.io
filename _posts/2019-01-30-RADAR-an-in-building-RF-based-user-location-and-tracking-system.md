---
title: "RADAR: an in-building RF-based user location and tracking system (2000)"
tags: []
categories: "position"
---

## Published in
- Proceedings IEEE INFOCOM 2000.  
Conference on Computer Communications.  
Nineteenth Annual Joint Conference of the IEEE Computer and Communications Societies.

### Online copies
[Article][article_link]

## Synopsis
Combines empirical measurements with signal propagation modeling to determine user location.

**Note:** **empirical measurements** been referred by many other papers as **fingerprinting**.
{: .notice}

## Propagation
Wall Attenuation Factor model.

$$P(d_0)[\mathit{dB}m] = P(d)[\mathit{dB}m] - 10n\log{(\frac{d}{d_0})} - f(\mathit{nW}) * \mathit{WAF}$$


**Note:** Theoretically $$n = 2$$.
{: .notice}

## Localization
K-nearest neighbors for fingerprint matching.

[article_link]: https://www.computer.org/csdl/proceedings/infcom/2000/5880/02/00832252.pdf

*[RSS]: Received Signal Strength
*[GSM]: Global System for Mobile communications