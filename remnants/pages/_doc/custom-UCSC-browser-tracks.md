---
title: "Progenetix data as custom tracks to UCSC genome browser"
date: 2019-08-30
layout: default
author: Bo Gao
permalink: /howto/custom-UCSC-browser-tracks.html
excerpt_link: https://info.baudisgroup.org/howto/custom-UCSC-browser-tracks.html
excerpt_separator: <!--more-->
category: 
  - howto
tags:
  - website
  - code
  - documentation
  - UCSC
  - API
---

## {{page.title}}

### Displaying copy number data in UCSC genome browser

To visualize genomic segments based data data (e.g. CNV calls), there are two kinds of plots we can produce in the UCSC genome browser.
 
<!--more-->
  
1. Show the raw data as bars

![](https://info.baudisgroup.org/assets/img/users/add_custom_tracks_to_ucsc_genome_browser/ucsc_bars.png)

2. Show raw data or pre-computed data as histogram

![](https://info.baudisgroup.org/assets/img/users/add_custom_tracks_to_ucsc_genome_browser/ucsc_hist.png)

<!--more-->

#### Data format

**Plot of bars:**

Segment data needs to be in a BED format like this:

````
#chrom chromStart chromEnd
chr22   20100000 20100100
chr22   20100011 20100200	
chr22   20100215 20100400
chr22   20100350 20100500
chr22   20100700 20100800
chr22   20100700 20100900
````

Details of BED format is [here](https://genome.ucsc.edu/FAQ/FAQformat.html#format1).

**Plot of histogram:**

Segment data needs to be in a bedGraph format like this:

```
#chrom chromStart chromEnd	dataValue
chr19 49302000 49302300 -1.0
chr19 49302300 49302600 -0.75
chr19 49302600 49302900 -0.20
chr19 49302900 49303200 -0.25
chr19 49303200 49303500 0.0
chr19 49303500 49303800 2.25
chr19 49303800 49304100 0.50
chr19 49304100 49304400 0.75
chr19 49304400 49304700 1.00
```

#### Plotting manually

To view a custom track, upload the data to the [Custom Tracks](http://genome.ucsc.edu/cgi-bin/hgCustom) page.

Configuration info needs to be specified:

1. Define the Genome Browser display characteristics:  

Add one or more optional [browser lines](https://genome.ucsc.edu/goldenPath/help/customTrack.html#lines) to the beginning of your formatted data file to configure the overall display of the Genome Browser when it initially shows your annotation data. Browser lines allow you to configure such things as the genome position that the Genome Browser will initially open to, the width of the display, and the configuration of the other annotation tracks that are shown (or hidden) in the initial display. NOTE: If the browser position is not explicitly set in the annotation file, the initial display will default to the position setting most recently used by the user, which may not be an appropriate position for viewing the annotation track.

2. Define the annotation track display characteristics:  

Following the browser lines -- and immediately preceding the formatted data -- 
add a [track line](https://genome.ucsc.edu/goldenPath/help/customTrack.html#TRACK) 
to define the display attributes for your annotation data set. Track lines 
enable you to define annotation track characteristics such as the name, description, colors, initial display mode, use score, etc. The track [type=\<track_type>](https://genome.ucsc.edu/goldenPath/help/customTrack.html#TRACK) attribute is required for some tracks. If you have included more than one data set in your annotation file, insert a track line at the beginning of each new set of data.

**An example of bars**

```
browser position chr22:20100000-20140000
track name=spacer description="Blue ticks every 10000 bases" color=0,0,255,
#chrom chromStart chromEnd
chr22   20100000 20100001
chr22   20110000 20110001
chr22   20120000 20120001
track name=even description="Red ticks every 100 bases, skip 100" color=255,0,0
#chrom chromStart chromEnd name
chr22   20100000 20100100	first
chr22   20100200 20100300	second
chr22   20100400 20100500	third
```

**An example of a histogram**

```
browser position chr19:49302001-49304701
browser hide all
browser pack refGene encodeRegions
browser full altGraph
#	300 base wide bar graph, autoScale is on by default == graphing
#	limits will dynamically change to always show full range of data
#	in viewing window, priority = 20 positions this as the second graph
#	Note, zero-relative, half-open coordinate system in use for bedGraph format
track type=bedGraph name="BedGraph Format" description="BedGraph format" visibility=full color=200,100,0 altColor=0,100,200 priority=20
chr19 49302000 49302300 -1.0
chr19 49302300 49302600 -0.75
chr19 49302600 49302900 -0.50
chr19 49302900 49303200 -0.25
chr19 49303200 49303500 0.0
chr19 49303500 49303800 0.25
chr19 49303800 49304100 0.50
chr19 49304100 49304400 0.75
chr19 49304400 49304700 1.00
```

#### Customizing pages for tracks

You can add a link from a details page to an external web page containing additional information about the feature by using the track line *url* attribute. In the annotation file, set the *url* attribute in the track line to point to a publicly available page on a web server. The *url* attribute substitutes each occurrence of **'\$\$'** in the URL string with the name defined by the name attribute. You can take advantage of this feature to provide individualized information for each feature in your track by creating HTML anchors that correspond to the feature names in your web page.

**An example**: Here is an example of a file in which the url attribute has been set to point to the file [http://genome.ucsc.edu/goldenPath/help/clones.html](http://genome.ucsc.edu/goldenPath/help/clones.html). The '\#\$\$' appended to the end of the file name in the example points to the HTML NAME tag within the file that matches the name of the feature (cloneA, cloneB, etc.).

```
browser position chr22:10000000-10020000
browser hide all
track name=clones description="Clones" visibility=2 color=0,128,0 useScore=1 url="http://genome.ucsc.edu/goldenPath/help/clones.html#$$"
#chrom chromStart chromEnd name score
chr22 10000000 10004000 cloneA 960 
chr22 10002000 10006000 cloneB 200 
chr22 10005000 10009000 cloneC 700 
chr22 10006000 10010000 cloneD 600
chr22 10011000 10015000 cloneE 300
chr22 10012000 10017000 cloneF 100 
```

#### Plotting through URL

Construct a URL that will link an annotation file to the Genome Browser. The URL must contain 3 pieces of information specific to your annotation data:

1. The species or genome assembly on which your annotation data is based. To specify a particular genome assembly for an organism, use the db parameter, db=database_name, where database_name is the UCSC code for the genome assembly. Examples: db=hg16.
2. The genome position to which the Genome Browser should initially open. This information is of the form position=chr_position, where chr_position is a chromosome number, with or without a set of coordinates. Examples: position=chr22, position=chr22:15916196-31832390.
3. The URL of the annotation file on your web site. This information is of the form `hgt.customText=URL`, where URL points to the annotation file on your website. An example of an annotation file URL is [http://genome.ucsc.edu/goldenPath/help/test.bed](http://genome.ucsc.edu/goldenPath/help/test.bed).

The following URL will open up the Genome Browser window to display chr 22 of the latest human genome assembly and will show the annotation track pointed to by the URL http://genome.ucsc.edu/goldenPath/help/test.bed:  
[http://genome.ucsc.edu/cgi-bin/hgTracks?org=human&position=chr22&hgt.customText=http://genome.ucsc.edu/goldenPath/help/test.bed](http://genome.ucsc.edu/cgi-bin/hgTracks?org=human&position=chr22&hgt.customText=http://genome.ucsc.edu/goldenPath/help/test.bed)

#### Additional info

1. Optional parameters to the URL is [here](https://genome.ucsc.edu/goldenPath/help/customTrack.html#SHARE)
2. Reference pages:
	- [Displaying Your Own Annotations in the Genome Browser](https://genome.ucsc.edu/goldenPath/help/customTrack.html)
	- [BedGraph Track Format](https://genome.ucsc.edu/goldenPath/help/bedgraph.html)
