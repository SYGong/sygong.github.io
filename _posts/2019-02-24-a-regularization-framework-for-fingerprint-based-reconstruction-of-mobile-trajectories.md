---
title: "A Regularization Framework for Fingerprint-based Reconstruction of Mobile Trajectories (2016)"
tags: []
categories: "position"
---

## Published in
- Journal  
International Journal of Parallel, Emergent and Distributed Systems  
Volume 31 Issue 3, May 2016 

### Online copies
[Article][article_link]

## Synopsis

be reconstructed from the real-time fingerprint
data that are obtained by the sensors built in the device.

spatiotemporal properties regarding the fingerprint space in
relation to the location space

Our goal is to investigate the effectiveness of a solution
framework based on formulating the fingerprint-based trajectory
reconstruction problem as a regularization problem where
the regularizers are to enforce two properties regarding the
fingerprint space in relation to the location space and natural
mobility:
 (P1) spatial smoothness: two fingerprints similar in value
should correspond to nearby locations.
 (P2) temporal smoothness: the trajectory of a moving
device in the real world should exhibit some degree of
position smoothness over time.

## Assumptions

Fingerprints of a trajectory. Some labeled, (assume that a
small portion of these fingerprints are obtained with respective
location information and this is the only training data that we
have.) others need to be located.


it is possible to improve over earlier approaches that are designed for non-trajectory fingerprint localization.





in comparison
with earlier fingerprint techniques based on kNN and manifold
regularization.

## Fingerprint
at a specific location is a vector of location-sensitive measurements
observed about the mobile device at this particular
location

## Objectives

### Label error

minimize the estimation error with respect to the labeled fingerprints. 
MSE


### spatial smoothness in the fingerprint space


### temporal smoothness
valid locations is given, the reconstructed trajectory should
be restricted to only these locations.



[article_link]: https://www.researchgate.net/profile/Ting_Zhang12/publication/283172835_A_regularization_framework_for_fingerprint-based_reconstruction_of_mobile_trajectories/links/5a56e11445851547b1bf2ebb/A-regularization-framework-for-fingerprint-based-reconstruction-of-mobile-trajectories.pdf

*[RSS]: Received Signal Strength
*[GSM]: Global System for Mobile communications
*[SLAM]: Simultaneous Localization and Mapping
*[MDS]: Multidimensional Scaling