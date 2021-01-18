---
title: "pgxdb_get_geo_metadata.pl Perl Code Documentation"
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


This script creates (or updates) the hierarchical GEO metadata file structure
and parses the `geometa.soft` files for some core information (ids, contact
info, PMID ...).

* perl pgxdb_get_geo_metadata.pl -out /Volumes/arraymapIn/2019-04-08-not-in-arraymap/
* perl pgxdb_get_geo_metadata.pl -randpf 30 -randno 400 -out ~/Downloads/test

#### Comand line parameters

* `-forcegpl y`
    - refreshes the GPL files, thereby adding the latest GSMs from those
* `-forcegsm y`
* `-forcegse y`
    - forces re-download of the corresponding `geometa.soft` files, if existing
    - shouldn't be needed - if file structure changes it is probably best to
    re-download the whole tree
    - one reason may be the addition of PMIDs over time
* `-randpf`
    - random platform number (has to be given, e.g. 10), for testing
* `-randno`
    - random array number per platform (has to be given, e.g. 100), for testing
    - avoids getting stuck at the high-count platforms
    
The script provides feedback about the types and locations of the created files.

