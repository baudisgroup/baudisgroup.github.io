---
title: "Ontology Term Contributions"
date: 2021-01-14
permalink: /howto/ontology-term-contributions/
excerpt_link: http://info.baudisgroup.org/howto/ontology-term-contributions/
layout: default
author: '@mbaudis'
excerpt_separator: <!--more-->
pdf_file_name:
pdf_file_type:    # slides poster article
www_link:
www_links_formatted:   # use this for a quoted, complete HTML link with label '<a href="http://" target="_blank">...</a>'
category:
  - howto      # publication howto presentation
  - news
tags:
  - code
  - ontologies
  - EFO
---

## {{ page.title }}

The group is an active contributor to several public ontologies, both through mapping efforts
([ICDOntologies](https://github.com/progenetix/ICDOntologies), [icdot2uberon](https://github.com/progenetix/icdot2uberon)) and
by requesting terms relevant for genomic and metadata e.g. for [EFO](https://www.ebi.ac.uk/ols/ontologies/efo).

<!--more-->

### EFO Terms for cancer sample material

#### Reference Sample ([EFO:0009654](http://www.ebi.ac.uk/efo/EFO_0009654))

* **Preferred term label**: reference sample
* **Synonyms**
  - germline reference sample
  - baseline reference sample
  - non-neoplastic sample
  - inherited reference sample
  - native sample
* **Textual definition**: A material sample derived from cells or tissue representing a physiologically or phenotypically normal state.
* **Parent term**: [OBI:0000747](http://purl.obolibrary.org/obo/OBI_0000747) material sample
* submitted 2019-02-08 <https://github.com/EBISPOT/efo/issues/365>
* live 2019-02-013

#### Abnormal Sample ([EFO:0009655](http://www.ebi.ac.uk/efo/EFO_0009655))

* **Preferred term label**: abnormal sample
* **Synonyms**
  - abnormal tissue sample
  - altered sample
* **Textual definition**: A material sample derived from cells or tissue representing an observed or suspected physiologically, genomically or phenotypically abnormal state
* **Parent term**: [OBI:0000747](http://purl.obolibrary.org/obo/OBI_0000747) material sample
* submitted 2019-02-08 <https://github.com/EBISPOT/efo/issues/365>
* live 2019-02-013

#### Neoplastic Sample ([EFO:0009656](http://www.ebi.ac.uk/efo/EFO_0009656))

* **Preferred term label**: neoplastic sample
* **Synonyms**
  - tumor sample
* **Textual definition**: A material sample derived from neoplastic cells or tissue.
* **Parent term**: [EFO:0009655](http://www.ebi.ac.uk/efo/EFO_0009655) abnormal sample
* submitted 2019-02-08 <https://github.com/EBISPOT/efo/issues/365>
* live 2019-02-013

#### Metastasis Sample ([EFO:0010941](http://www.ebi.ac.uk/efo/EFO_0010941))

* **Preferred term label**: metastasis sample
* **Synonyms**
  - metastasis
* **Textual definition**: A neoplastic sample derived from a cancer metastasis (not from a primary tumor).
* **Parent term**: [EFO:0009656](http://www.ebi.ac.uk/efo/EFO_0009656) neoplastic sample
* submitted 2020-12-16 <https://github.com/EBISPOT/efo/issues/917>
* live 2021-01-18

#### Primary Tumor Sample ([EFO:0010942](http://www.ebi.ac.uk/efo/EFO_0010942))

* **Preferred term label**: primary tumor sample
* **Synonyms**
  - primary tumor
  - primary neoplasia
  - primary tumour sample
  - primary neoplasia sample
* **Textual definition**: A neoplastic sample derived from a primary tumor (not from a cancer metastasis).
* **Parent term**: [EFO:0009656](http://www.ebi.ac.uk/efo/EFO_0009656) neoplastic sample
* submitted 2020-12-16 <https://github.com/EBISPOT/efo/issues/918>
* live 2021-01-18

#### Recurrent Tumor Sample ([EFO:0010943](http://www.ebi.ac.uk/efo/EFO_0010943))

* **Preferred term label**: recurrent tumor sample
* **Synonyms**
  - recurrent tumor
  - recurrent neoplasia
  - recurrent tumour sample
  - recurrent neoplasia sample
* **Textual definition**: A neoplastic sample derived from a recurrent tumor (not from a primary occurrence of a neoplasm).
* **Parent term**: [EFO:0009656](http://www.ebi.ac.uk/efo/EFO_0009656) neoplastic sample
* submitted 2020-12-16 <https://github.com/EBISPOT/efo/issues/919>
* live 2021-01-18


### EFO Terms for molecular-cytogenetic technologies

#### Comparative Genomic Hybridization (CGH) ([EFO:0010937](http://www.ebi.ac.uk/efo/EFO_0010937))

* **Preferred term label**: comparative genomic hybridization (CGH)
* **Synonyms**
  - chromosomal Comparative Genomic Hybridization
* **Textual definition**: Comparative Genomic Hybridization is an in-situ hybridization method for the analysis of regional genomic copy number imbalances (CNA / CNV), based on the hybridization of test (e.g. tumor) and reference DNA to chromosomal metaphase preparations from healthy donors.
* **Parent terms**:
  - [EFO:0001456](http://www.ebi.ac.uk/efo/EFO_0001456) DNA assay
  - [OBI:0001686](http://purl.obolibrary.org/obo/OBI_0001686) in-situ hybridization assay
* submitted 2020-12-09 <https://github.com/EBISPOT/efo/issues/909>
* live 2020-12-14

#### Large-Insert Clone DNA Microarray ([EFO:0010938](http://www.ebi.ac.uk/efo/EFO_0010938))

* **Preferred term label**: large-insert clone DNA microarray
* **Synonyms**
  - spotted DNA microarray
* **Textual definition**: Large-Insert Clone DNA Microarrays consist of usually several thousands of spots of DNA from bacterial artificial chromosome (BAC) and P1 artificial chromosome (PAC) clones. The main application of those arrays is for array Comparative Genomic Hybridization (aCGH) experiments.
* **Parent terms**:
  - [EFO:0002701](http://www.ebi.ac.uk/efo/EFO_0002701) DNA array
* submitted 2020-12-09 <https://github.com/EBISPOT/efo/issues/910>
* live 2020-12-14

#### Oligonucleotide DNA Microarray ([EFO:0010939](http://www.ebi.ac.uk/efo/EFO_0010939))

* **Preferred term label**: oligonucleotide DNA microarray
* **Synonyms**
  - chromosomal Comparative Genomic Hybridization
* **Textual definition**: Oligonucleotide DNA Microarrays consist of usually thousands to many hundreds of thousands spots of DNA oligonucleotides (25- to 60 bases) which have been created by either in situ synthesis or deposition of presynthesized oligonucleotides on a carrier substrate. Applications for those arrays are in the detection of copy number variations or small structural changes as well as in genotyping (if oligonucleotides have been designed for SNP detection).
* **Parent terms**:
  - [EFO:0002701](http://www.ebi.ac.uk/efo/EFO_0002701) DNA array
* submitted 2020-12-09 <https://github.com/EBISPOT/efo/issues/911>
* live 2020-12-14
