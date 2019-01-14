Location fingerprinting is a range-free approach
to GPS-free localization. Conventionally, the fingerprint
space is defined as a feature vector space where a
fingerprint is a vector of location-sensitive measurements
associated with a location. However, in practice, it is
hard to find a quality feature space that is robust to
device heterogeneity and environment and infrastructure
dynamics. This paper advocates a fundamentally different
model where a fingerprint is defined as a dissimilarity measurement
associated with a pair of locations and proposes
a localization approach based on geometric embedding.

Need to justify the quality feature space problem.
Geometric embedding

The feature-based framework
has the following limitations: (L1) features may not be
globally measurable, (L2) features may change due to
infrastructure update, (L3) feature measurements may
be inconsistent due to time-varying environment interference,
and (L4) feature measurements may be devicespecific.
As such, it is not always possible to obtain good
fingerprint features for accurate localization.

(L1) choose features that is 
globally measurable, (L2) choose features resist 
infrastructure update, (L3) feature measurements that is stable over time
 environment interference,
and (L4) feature measurements may be devicespecific.
As such, it is not always possible to obtain good
fingerprint features for accurate localization.
The p2p measurement is still a measurement and if those are different then we need to take care different measurement.

fresh challenges


Two group to compare
- Fingerprint Localization
- Dissimilarity geometric embedding


VI. CONCLUSIONS
Our evaluation study
has found this approach more accurate than graph-based KNN.
What is Graph-based kNN? ISOMAP, the performance of ISOMAP is actually better for short links