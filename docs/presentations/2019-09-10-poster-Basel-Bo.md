---
title: "Minimum Error Calibration and Normalization for Genomic Copy Number Analysis"
template: blog_post.html 
date: 2019-09-10
pdf_file_name: 2019-09-10___Bo-Gao__Minimum-Error-Calibration-and-Normalization-for-Genomic-Copy-Number-Analysis__BC2_Basel_poster.pdf
---

#### BC2 2019, Basel
### Bo Gao

#### Abstract

**Background**:  
Copy number variations (CNV) are regional deviations from thenormal autosomal bi-allelic DNA content. While germline CNVs are a majorcontributor to genomic syndromes and inherited diseases, the majority of cancersaccumulate extensive ”somatic” CNV (sCNV or CNA) during the process ofoncogenetic transformation and progression. While specific sCNV have closelybeen associated with tumorigenesis, intriguingly many neoplasias exhibitrecurrent sCNV patterns beyond the involvement of a few cancer driver genes.Currently, CNV profiles of tumor samples are generated using genomicmicro-arrays or high-throughput DNA sequencing. Regardless of the underlyingtechnology, genomic copy number data is derived from the relative assessmentand integration of multiple signals, with the data generation process being proneto contamination from several sources. Estimated copy number values have noabsolute and linear correlation to their corresponding DNA levels, and the extentof deviation differs between sample profiles which poses a great challenge fordata integration and comparison in large scale genome analysis.

**Results**:  
In this study, we present a novel method named Minimum ErrorCalibration and Normalization of Copy Numbers Analysis (Mecan4CNA). Foreach sCNV profile,Mecan4CNAreduces the noise level, calculates valuesrepresenting the normal DNA copies (baseline) and the change of one copy (leveldistance), and finally normalizes all values. Experiments ofMecan4CNAonsimulated data showed an overall accuracy of 93% and 91% in determining thebaseline and level distance, respectively. Comparison of baseline and level distanceestimation with existing methods and karyotyping data on the NCI-60 tumor cellline produced coherent results. To estimate the method’s impact on downstreamanalyses we performed GISTIC analyses on original andMecan4CNAdata fromthe Cancer Genome Atlas (TCGA) where the normalized data showed prominentimprovements of both sensitivity and specificity in detecting focal regions.

**Conclusions**: 
In general,Mecan4CNAprovides an advanced method for CNAdata normalization especially in research involving data of high volume andheterogeneous quality. With its informative output and visualization, it can alsofacilitate analysis of individual CNA profiles.Mecan4CNAis freely available as aPython package and through Github.




