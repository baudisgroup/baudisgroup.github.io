---
title: "ELIXIR All Hands 2018 - arrayMap"
template: blog_post.html 
date: 2018-06-04
---

#### Abstract: [ELIXIR All Hands 2018](https://www.elixir-europe.org/events/elixir-all-hands-2018)
## Update on arrayMap Cancer Genome Resource
### Qingyao Huang and Michael Baudis

arrayMap is a cancer-related genome profile database, curated from public data repositories. The resources’s data processing pipelines handle the homogeneous conversion of available raw data from various genomic array platforms (e.g. cCGH, SNP) and represents pre-computed copy number variation (CNV) profiles, allowing the evaluation of target gene involvement as well as the comparative analysis of whole-genome CNV patterns, e.g. for assessing between-sample CNV heterogeneity and associate sets of similar patterns with metadata qualifiers such as diagnostic classifications. In addition to the representation of cancer-related samples, we also plan to generate copy number profiles from non-cancer samples, in an effort to represent population-related CNV patterns.

Last year, we updated the arrayMap database with new samples from NCBI’s Gene Expression Omnibus (GEO: 24k), EBI’s ArrayExpress (15k) and the Cancer Genome Atlas (TCGA: 22k). The genome version of all genomics data has been lifted to the latest GRCh38 with our batch-processing segment_liftover tool. CNVs are assessed, evaluated and visualized for all these cancer-related genomics single profiles as well as with summary histograms on selected sample groups (e.g. cancer entities, experimental series). 

In the newest edition of the database, we also introduced allele-specific representation of SNP-array based data, allowing for better evaluation of segmental copy number status, the detection of coy number neutral LOH regions, as well as providing support for ploidy estimation. Furthermore, we performed a pilot study aimed at data-driven assessment of the population background for these samples taking 1000 Genomes project as reference.

The updated data repository is accessible through the arraymap.org website as well as through the [beacon+ API](http://beacon.progenetix.org/). Software tools are available as Docker image "baudisgroup/tum2pop" on [Docker Hub](https://hub.docker.com/) and provided through the ["baudisgroup" organisation on Github](http://github.com/baudisgroup/). 

