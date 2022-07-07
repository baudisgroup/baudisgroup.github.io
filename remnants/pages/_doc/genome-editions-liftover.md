---
title: "Genome editions and liftover"
date: 2018-07-20
layout: default
author: Michael
excerpt_separator: <!--more-->
pdf_file_name:
pdf_file_type:    # slides poster article
www_link:
www_links_formatted:   # use this for a quoted, complete HTML link with label '<a href="http://" target="_blank">...</a>'
category:
  - howto      # publication howto presentation
tags:
  - code          # article talk poster slides
---

## {{ page.title }}


Since the first release in 2000, the human reference genome is continuously being worked on. While the most recent major release (GRCh38) dates back to 2013, minor releases (GRCh38.pX) are issued more frequently and can be downloaded from the official NCBI Genome Reference Consortium website.

<!--more-->


<table> <tbody> <tr bgcolor='#0099ff'> <td>RELEASE DATE</td> <td>RELEASE NAME</td> <td>UCSC VERSION</td> <td>STATUS</td> </tr> <tr> <td>Dec. 2013</td> <td>Genome Reference Consortium GRCh38</td> <td>hg38</td> <td>Available</td> </tr> <tr> <td>Feb. 2009</td> <td>Genome Reference Consortium GRCh37</td> <td>hg19</td> <td>Available</td> </tr> <tr> <td>Mar. 2006</td> <td>NCBI Build 36.1</td> <td>hg18</td> <td>Available</td> </tr> <tr> <td>May 2004</td> <td>NCBI Build 35</td> <td>hg17</td> <td>Available</td> </tr> <tr> <td>Jul. 2003</td> <td>NCBI Build 34</td> <td>hg16</td> <td>Available</td> </tr> <tr> <td>Apr. 2003</td> <td>NCBI Build 33</td> <td>hg15</td> <td>Archived</td> </tr> <tr> <td>Nov. 2002</td> <td>NCBI Build 31</td> <td>hg13</td> <td>Archived</td> </tr> <tr> <td>Jun. 2002</td> <td>NCBI Build 30</td> <td>hg12</td> <td>Archived</td> </tr> <tr> <td>Apr. 2002</td> <td>NCBI Build 29</td> <td>hg11</td> <td>Archived (data only)</td> </tr> <tr> <td>Dec. 2001</td> <td>NCBI Build 28</td> <td>hg10</td> <td>Archived (data only)</td> </tr> <tr> <td>Aug. 2001</td> <td>UCSC-assembled</td> <td>hg8</td> <td>Archived (data only)</td> </tr> <tr> <td>Apr. 2001</td> <td>UCSC-assembled</td> <td>hg7</td> <td>Archived (data only)</td> </tr> <tr> <td>Dec. 2000</td> <td>UCSC-assembled</td> <td>hg6</td> <td>Archived (data only)</td> </tr> <tr> <td>Oct. 2000</td> <td>UCSC-assembled</td> <td>hg5</td> <td>Archived (data only)</td> </tr> <tr> <td>Sep. 2000</td> <td>UCSC-assembled</td> <td>hg4</td> <td>Archived (data only)</td> </tr> <tr> <td>Jul. 2000</td> <td>UCSC-assembled</td> <td>hg3</td> <td>Archived (data only)</td> </tr> <tr> <td>Jun. 2000</td> <td>UCSC-assembled</td> <td>hg2</td> <td>Archived (data only)</td> </tr> <tr> <td>May 2000</td> <td>UCSC-assembled</td> <td>hg1</td> <td>Archived (data only)</td> </tr> </tbody> </table>


Even though multiple names can exist for one build (e.g. hg18 and NCBI Build 36.1), both refer to the same assembly and are therefore interchangeable.

New versions of the human reference genome contain updates for genome mapping coordinates. While most changes are minor position corrections, some elements, e.g. single nucleotide polymorphisms (SNP), may be remapped to another chromosome. Both UCSC and NCBI offer tools to convert annotations from one build to another (referred to as liftover) which can be found on their respective websites (or see links below).

Since 2018, our group offers the [__segment_liftover__ tool](https://github.com/baudisgroup/segment-liftover), improving the re-mapping of segmented genome data, and batch processing of liftover tasks in general.

#### Links

* Human Genome Overview on Genome Reference Consortium website
    * http://www.ncbi.nlm.nih.gov/projects/genome/assembly/grc/human/
* UCSC LiftOver tool
    * http://genome.ucsc.edu/cgi-bin/hgLiftOver
* NCBI Remapping service:
    * http://www.ncbi.nlm.nih.gov/genome/tools/remap
