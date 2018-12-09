---
title: 什么是RSS (Receive Signal Strength) ，以及与RSSI的区别
mathjax: true
header:
  image: /assets/images/Tower.jpeg
---
### RSS
$$\mathit{RSS}$$ (Received Signal Strength) 是接收到的信号的功率，通常是以 $$\mathit{dB}m$$ 或 $$mW$$ 为单位 [[1]]。假设我们有以 $$mW$$ 为单位的功率 $$p$$，换算成以 $$\mathit{dB}m$$ 为单位表示就是 $$10 log_{10} p$$。

### RSSI
IEEE 802.11 定义了`RSSI` (Received Signal Strength Indicator)，范围从`0`到`RSSI_Max`。`RSSI_Max`的值由厂商自己定义，`RSSI`每一个值对应的 $$\mathit{RSS}$$ 也由厂商自己定义 [[1]] [[2]]。[[2]] 中还有Atheros等不同厂商的 `RSSI` 计算方式。

### Reference
- [[1]] [A Survey of Indoor Localization Systems and Technologies][1]
- [[2]] [Converting Signal Strength Percentage to dBm Values][2]

[1]: https://arxiv.org/pdf/1709.01015.pdf
[2]: http://madwifi-project.org/attachment/wiki/UserDocs/RSSI/Converting_Signal_Strength.pdf?format=raw