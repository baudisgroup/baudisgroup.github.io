---
title: "ELIXIR All Hands 2018 - segment_liftover"
date: 2018-06-04
category:
  - presentations
tags:
  - poster
  - presentation
---

#### Abstract: [ELIXIR All Hands 2018](https://www.elixir-europe.org/events/elixir-all-hands-2018)
## segment_liftover : a Python tool to convert segments between genome assemblies
### Bo Gao, Qingyao Huang and Michael Baudis

The process of assembling a species’ reference genome may be performed in a number of iterations, with subsequent genome assemblies differing in the coordinates of mapped elements. The conversion of genome coordinates between different assemblies is required for many integrative and comparative studies. While currently a number of bioinformatics tools are available to accomplish this task, most of them are tailored towards the conversion of single genome coordinates. When converting the boundary positions of segments spanning larger genome regions, segments may be mapped into smaller sub-segments if the original segment’s continuity is disrupted in the target assembly. Such a conversion may lead to a relevant degree of data loss in some circumstances such as copy number variation (CNV) analysis, where the quantitative representation of a genomic region takes precedence over base-specific accuracy. segment_liftover aims at continuity-preserving remapping of genome segments between assemblies and provides features such as approximate locus conversion, automated batch processing and comprehensive logging to facilitate processing of datasets containing large numbers of structural genome variation data.

