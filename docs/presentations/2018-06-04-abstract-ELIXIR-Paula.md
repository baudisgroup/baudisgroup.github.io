---
title: 'Biocuration for cancer genome databases: arrayMap and Progenetix'
template: blog_post.html 
date: 2018-06-04
---

#### Abstract: [ELIXIR All Hands 2018](https://www.elixir-europe.org/events/elixir-all-hands-2018)
### Paula Carrio Cordo and Michael Baudis

Screening for somatic mutations in cancer has become integral to diagnostic and target evaluation for personalized therapeutic approaches. [*arrayMap*](http://arraymap.org) is a curated oncogenomic resource, focusing on copy number aberration (CNA) profiles derived from genomic arrays. The information has been processed from data accessed through NCBI’s Gene Expression Omnibus (GEO), EBI’s ArrayExpress, and, importantly, through targeted mining of publication data. Whereas this database is based on raw probe data sets, the parental project, [*Progenetix*](http://progenetix.org), allows for genome variant analysis from additional sources and serves as metadata reference.<!--more-->

*arrayMap* underwent improvements to facilitate meta-analysis of cancer related genome data and clinical use, such as the adoption of a hierarchical schema representation and expansion of the data. The resulting, comprehensive resource consisting of *Progenetix* and arrayMap contains information for more than 400 ICD-O entities and 63'000 genomic array profiles. For interoperability of clinical data efforts are done inn data standardization. Existing standards such as ICD-O have proven to give a good description of a cancer entity based on the morphology and topography of the sample, but of interested is to move into ontology codes that provide hierarchical reference terminology such as NCIt neoplasm core.

For the integrative analysis of distributed data resources necessary for precision oncology research, translation between different standards used in local and external resources is needed, using ontology mappings to allow for different vocabularies. Our work contributes to cross-resource mapping of cancer classifications, providing both suitable input for mapping services as well as testing new paradigms for data integration in biomedical settings. However, further curation of vocabularies is needed, for instance using mapping concepts beyond single point-to-point assertions.
