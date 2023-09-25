# Projects and Open Positions

The _Theoretical Cytogenetics and Oncogenomics_ group is always open for
candidates with a good mix of strong interest and background in (genome-) bioinformatics,
medical genomics and cytogenetics or classifications, ontologies and semantic analytics.

Especially, provide a welcoming environment for guiest scientists and junior academics
in search for projects as part of their BSc and MSc studies.

At this time we do not advertise any funded openings.

## Some Projects

Ongoing software and service projects can be visited at our Github organizations ([progenetix](https://github.com/progenetix) and [baudisgroup](https://github.com/baudisgroup)) and when looking at individual contributions to e.g. GA4GH and ELIXIR.

* [bycon](https://github.com/progenetix/bycon) at Github in __Progenetix__ - Python based implementation of a [GA4GH Beacon](http://beacon-project.org)
* [pgxRpi](https://github.com/progenetix/pgxRpi) at Github in __Progenetix__ - An API wrapper package in R for loading & displaying data from Progenetix 
* [segment-liftover](https://github.com/baudisgroup/segment-liftover) at Github __baudisgroup__
    * [publication](http://info.baudisgroup.org/publications/2018/03/14/segment_liftover.html)
* [SNP2pop](https://github.com/baudisgroup/snp2pop) at Github __baudisgroup__
    * [publication at ScientificReports](https://www.nature.com/articles/s41598-020-61854-x)
* [ICDOntologies](https://github.com/progenetix/ICDOntologies) at Github in __Progenetix__ - mapping disease concepts

## Support or Contact

For requests & support, please use standard Github procedures such as pull
requests or issues on our project repositories, or [contact us](mailto:contact@progenetix.org).

---

## MSc Projects in Bioinformatics & Computational "Bio"

Our group offers positions for graduated studies (MSc), e.g. as part of the CBB
program of ETHZ, UZH and Basel University. Examples are given below; however, 
new/modified projects may come up (or be suggested).

----

### Beyond CNVs - Exploring compound mutational hits in reference datasets

Traditionally the focus of the Progenetix resource - and our data analysis strategies -
has been in the representation and analysis of somatic copy number variations
(CNV) in cancer samples. This has been complementary to many studies of the last
decade which focussed on the exploration of sequence modifications (e.g. SNVs)
detected through NGS techniques.

#### Datasets for collection of compond variant data

* TCGA
    - an ubiquitous collection of ~11k cancer samples with several layers of -omics data
    - CNV data represented in Progenetix
* cancer cell lines
    - CNV and annotated variants integrated in Progeneix' [`cancercelllines.org`](http://cancercelllines.org)
    - additional mutation data may exist in publications, repositories

#### Expected outcomes

* comprehensive integration of non-CNV genomic variation data into Progenetix
* creation of a relevant cancer genome beacon w/ the primary target of a deep
  representation of TCGA (an cell line) data
* development and testing of _beaconplus_ query modalities for compund (_cis_ and _trans_)
  genomic variations
* data delivery (genomic variants, phenotypic, clinical and procedural data...)
  through a "Phenopackets over Beacon" concept
* analysis of compound or alternative variant events (e.g. deletion & inactivating mutation,
  amplification OR activating SNV ...) in the TCGA dataset

