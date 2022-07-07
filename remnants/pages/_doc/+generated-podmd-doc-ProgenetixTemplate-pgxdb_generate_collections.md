---
title: "pgxdb_generate_collections.pl Perl Code Documentation"
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


The `pgxdb_generate_collections.pl` script performs aggregation functions on
databases, specifically the generation of collections for pre-calculated
CNV frequencies and other statistics for samples grouped by different
`biocharachteristics.type.id` or `external_references.type.id` values.

The script uses the `PGXDB` package and its configuration file.

#### Arguments

* `-scopes`
    - selects the attributes to evaluate
    - overrides the value from config's `aggregation_scopes` keys
    - determines which types of aggregation collections are being generated
    - multiple values can be provided as a comma-concatenated string
* `-datasets`
    - selects the databases
    - defaults to the databases from config's `databases` keys
    - multiple values can be provided as a comma-concatenated string
* `-randno`
    - if an integer is provided, this will process a random number of group
    values (for testing)
* `-path`
    - the output location for the JSON files of the aggregated data
    - defaults to `___here_path___/out`

#### Output

The script will generate the aggregation collections in the `-path` directory.
At the end of processing each collection, and at the end of the script, the
commands to update the corresponding MongoDB collection will be shown in the
terminal.

#### Examples

* `pgxdb_generate_collections.pl -datasets progenetix -scopes biocharacteristics`
* `pgxdb_generate_collections.pl`

