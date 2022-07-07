---
date: 2017-09-13
category:
  - presentations
tags:
  - talk
  - presentation
pdf_file_name: 2017-09-13_BC2_Michael_Baudis_GA4GH_Beacon.pdf
pdf_file_type: slides
---

#### [BC]2 2017 - [Basel Computational Biology Conference](https://www.bc2.ch/2017/)
## Advancing the Global Alliance for Genomics and Health data schemas through data-driven implementations
### Michael Baudis

##### Abstract

The core mission of the Global Alliance for Genomics and Health (GA4GH) is to advance the utility of biomedical data through facilitating of federated analyses, across geographic, regulatory and technical boundaries. A central component is the development of standardised data schemas and application programming interfaces (APIs), for molecular screening data as well as biological and technical metadata.

In addition to direct schema development, demonstration projects explore strategies and limitations of federated data access and attempt to engage active participants from different areas of biomedical research and clinical practice as well as experts from areas such as computer and network security, law and ethics. One of the main demonstrators has been the “Beacon” project, which through a lightweight “beacon-network” registry and API allows the querying for specific genome sequence variants at resources from all over the world.

Early on, the main focus of GA4GH was on demonstrating functionality and to engage participants through through low-complexity scenarios. However, increased utility of GA4GH schemas requires representation of common biological, health specific and technical metadata.

The Metadata Task Team (MTT) of the GA4GH Data Working Group (DWG) has been working on defining the part of the schema representation which not primarily addresses primary or derived “omics” (e.g. sequences, variants) data. Core principles of schema development have been the restriction of schema complexity, the use of standardised data formats (e.g. ISO time), and the prominent use of ontologies as externally maintained value descriptors.

An important benchmark for a given data schema is the successful projection of reference datasets. However, so far the mapping of rich metadata attributes and structures into the GA4GH schema has not been explored for large, real world datasets or reference repositories.

As part of an ELIXIR “human data implementation study”, we have started to implement datasets as schema-compatible resources, and to explore linking these to external reference services for biomedical ontologies. At the core of this project, we are using the arraymap.org reference database for molecular genomic profiling data in cancer, which contains data from oncogenomic copy number analyses and curated metadata. The study has been directed at testing the GA4GH object model, with a focus on metadata, and at using this experience to guide schema development efforts of the GA4GH MTT. 

Additionally, as part of a parallel ELIXIR study, our GA4GH conform representation arrayMap data tests forward looking developments of genomic "Beacons", with focus on structural genome variants, the inclusion of metadata parameters for data queries, and the development of query interfaces and informative Beacon response formats.

At the present time, our test implementation represents >55’000 genomic call sets and allows the direct use of variant and metadata queries against a set of database collections implemented in MongoDB. A first API implementation provides responses to Beacon-style queries, e.g. the frequency of a variant for a tumor type specified through an ontology term.

Ongoing efforts aim to promote rapid evolution of the GA4GH metadata schema for a variety of data types and proposed use cases, such as geolocation data, metagenomic applications and temporal relations. On the implementation side, next steps include the integration of ontology services for data query and ingestion scenarios, as well as the extension of the demonstrator API for rich metadata query scenarios. An important part of current and future developments will be the use of additional data resources for demonstration projects.

Example datasets as well as tools and documentation are made available through the [“arraymap2ga4gh” project on Github](http://github.com/progenetix/).

##### Highlights

This presentation will be aimed at reporting the current status of the GA4GH schema development with focus on the lessons learned from the data implementation studies, as well as the challenges from design and implementation of data concepts centred around modern object based biodata data standards with heavy dependency on ontologies. We hope to excite the audience about the ongoing developments at GA4GH, with emphasis on increased engagement in data sharing activities.
