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

{::comment}
## Fingerprint

|---------------------------+----------------|
| **Wide** fingerprint      | control groups |
|---------------------------| -------------: |
| **Up to 35 GSM channels** | 6-strongest GSM cells    | Single-strongest GSM cell |

Two **narrow** and one **wide** kind of fingerprint.
- Single-strongest GSM cell
- 6-strongest GSM cells: used in the GSM standard.
- The **wide**: includes readings from additional cells that are strong enough to be detected.

**Note:** Instead of *channel* or *frequency*, [article](article_link) uses *cell*, although the later makes less sense. I could not verify that GSM standard is using 6-strongest cells as mentioned.
{: .notice}
{:/comment}

## Localization
K-nearest neighbors for fingerprint matching.

[article_link]: https://www.computer.org/csdl/proceedings/infcom/2000/5880/02/00832252.pdf

*[RSS]: Received Signal Strength
*[GSM]: Global System for Mobile communications