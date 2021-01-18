---
title: "pgxdb_biosamples_extract_biocharacteristics_mappings.pl Perl Code Documentation"
layout: default
www_link: 
excerpt_separator: <!--more-->
date: 2021-01-18
category:
  - howto
tags:
  - code
  - documentation
  - Perl
  - ProgenetixTemplate
---

## {{ page.title }}

<!--more-->


The "pgxdb_biosamples_extract_biocharacteristics_mappings.pl" script is a helper
for getting an overview map of all combinations of icdom :: icdot :: NCIT
diagnostic codes. It parses over all biosamples in progenetix and arraymap, and
maps out all code combinations through the use of a key concatenated from the
icdom::icdot::NCIT codes of each sample.

Cave: A possible incomplete mapping could result from multiple codes of the same
prefix type being assigned to the same sample - this is neither probable nor
highly relevant but should be checked through some other annotation QC script.

