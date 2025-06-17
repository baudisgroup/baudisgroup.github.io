---
title: 'Transfer Learning for Large-Scale Genomic AI in Cancer Genomics'
description: 'AI in Healthcare Conference – Legal, Ethical &amp; Implementation Challenges</br>June 2025 – Zurich, Switzerland'
template: post.html 
authors:
  - '@good-teeth-otter'
date: 2025-06-13
pdf_file_name: 2025-06-13___Jiahui__Transfer-learning-for-large-scale-genomic-AI-in-cancer-Genomics__AI-in-healthcare-conference.pdf
links: []
  # - "[Jiahui's slides - Transfer Learning for Large-Scale Genomic AI in Cancer Genomics](__pdf_repo_url__/2025-06-13___Jiahui__Transfer-learning-for-large-scale-genomic-AI-in-cancer-Genomics__AI-in-healthcare-conference.pdf)"
---

#### Jiahui Yu

**Summary** Recent advances in large-scale AI models adapted for genomic analysis – including DNA-BERT, Evo, and Nucleotide Transformer – have demonstrated promising capabilities in end-to-end prediction of functional genomic elements without relying on handcrafted features. However, as these models transition from analyzing population-scale germline data to the more complex landscape of tumor genomes, two critical concerns emerge: whether their learned representations can maintain accuracy across diverse sequencing technologies, and whether clinicians can develop sufficient trust in the latent patterns driving the model predictions.

Our ongoing research addresses these challenges through a transfer learning approach, adapting existing genomic language models using whole genome sequencing (WGS) data from the ICGC Pan-Cancer cohort. <!--more-->Instead of using pre-processed variant calls, we train models directly on raw sequencing data containing both somatic and germline variations, forcing the architecture to develop its own representations of complex genomic alterations, including single nucleotide variations (SNVs), structural rearrangements (SVs), large-scale insertions/deletions (indels), and copy-number variations (CNVs). 

To validate our approach, we focus on two key aspects: first, evaluating model generalization by testing fine-tuned versions across multiple independent WGS cancer cohorts with varying technical characteristics; and second, implementing explainability techniques that combine attention mechanisms with feature occlusion tests to identify which genomic segments most influence tumor classification predictions. These model-derived insights are then compared against established driver-gene databases and clinical annotations to assess biological plausibility and clinical relevance.

Clinical translation of genomic AI requires both robust multi-dataset validation and biologically interpretable predictions to realize its potential for analyzing complex sequencing data. By addressing these challenges, we aim to bridge the gap between computational innovation and clinically practical insights, paving the way for more trustworthy and generalizable AI applications in precision oncology.