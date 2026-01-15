---
title: "CNAttention: an attention-based deep multiple-instanc method for uncovering copy number aberratio signatures across cancers"
template: post.html 
authors:
 - '@mbaudis'
date: 2026-01-15
pdf_file_name: 2026-01-15___Yang-and-Baudis__CNAttention__Briefings-in-Bioinformatics.pdf
links:
  - '[github.com/baudisgroup/CNAttention](https://github.com/baudisgroup/CNAttention)'
---

#### Ziying Yang and Michael Baudis
##### Briefings in Bioinformatics, 2026, 27(1), bbaf696, 2026-01-15
* doi: [10.1093/bib/bbaf696](https://doi.org/10.1093/bib/bbaf696)

**Abstract**: Somatic copy number aberrations (CNAs) represent a distinct class of genomic mutations associated with oncogenetic effects. Over
the past three decades, significant volumes of CNA data have been generated through molecular-cytogenetic and genome sequencing-
based techniques. These data have been pivotal in identifying cancer-related genes and advancing research on the relationship between
CNAs and histopathologically defined cancer types. However, comprehensive studies of CNA landscapes and disease parameters are
challenging due to the vast diagnostic and genomic heterogeneity encountered in ”pan-cancer” approaches. In this study, we introduce
CNAttention, an attention-based deep multiple instance learning method designed to comprehensively analyze CNAs across different
cancers and uncover specific CNA patterns within integrated gene-level CNA profiles of 30 cancer types. CNAttention effectively learns
CNA features unique to each cancer type and generates CNA signatures for 30 cancer types using attention mechanisms, highlighting
the distinctiveness of their CNA landscapes. CNAttention demonstrates high accuracy and exhibits stable performance even with
the incorporation of external datasets or parameter adjustments, underscoring its effectiveness in tumor identification. Expanding
these signatures to cancer classification trees reveals common patterns not only among physiologically related cancer types but
also among clinico-pathologically distant types, such as different cancers originating from neural crest derived cells. Additionally,
detected signatures also uncover genomic heterogeneity in individual cancer types, for instance in brain lower grade glioma. Additional
experiments with classification models underscore the efficacy of these signatures in representing various cancer types and their
potential utility in clinical diagnosis.
