---
title: "GSM Indoor Localization (2007)"
tags: []
categories: "position"
---

## Published in
- Pervasive and Mobile Computing

### Online copies
[Article][article_link]

## Synopsis
Indoor [localization](#localization) with **wide** GSM signal strength fingerprint.

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

[article_link]: http://sysweb.cs.toronto.edu/publication_files/0000/0017/varshavsky2007gsm.pdf

*[RSS]: Received Signal Strength
*[GSM]: Global System for Mobile communications