---
Title: 什么是RSS (Receive Signal Strength) ，以及与RSSI的区别
mathjax: true
---

$$\mathit{RSS}$$ (Received Signal Strength) 是接收到的信号的功率，通常是以 $$\mathit{dB}m$$ 或 $$mW$$ 为单位[1]。假设我们有以 $$mW$$ 为单位的功率 $$p$$，换算成以 $$\mathit{dB}m$$ 为单位表示就是 $$10 log_{10} p$$。不管哪种表示方式，一般人都不太好理解。

IEEE 802.11 定义了$$\mathit{RSSI}$$ (Received Signal Strength Indicator)。范围从`0`到`RSSI_Max`，每一个数值对应的 $$\mathit{RSS}$$ 由各家厂商自己定义[[1]] [2]。[2] 中还有不同厂商的 $$\mathit{RSSI}$$ 计算方式。

[1]: https://arxiv.org/pdf/1709.01015.pdf "A Survey of Indoor Localization Systems and Technologies"
[2]: http://madwifi-project.org/attachment/wiki/UserDocs/RSSI/Converting_Signal_Strength.pdf?format=raw "Converting Signal Strength Percentage to dBm Values"
