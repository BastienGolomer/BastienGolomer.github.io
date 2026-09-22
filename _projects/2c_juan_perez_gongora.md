---
layout: page
title: "Habitat Imaging for Local Failure Prediction after Proton Therapy"
description: Master Semester Project, supervised (May 2026)
importance: 2
category: research
tags: [Student project, Master Semester Project]
---

**Master Semester Project — Juan Perez Gongora (May 2026).**

## Abstract

Background and Motivation: Accurate modelling of treatment response in proton therapy is challenging due to inter-patient variability and tumour heterogeneity, which can lead to local tumour control failure. While quantitative imaging biomarkers hold promise for predicting outcomes, standard radiomics approaches often fail to account for spatial intra-tumoural heterogeneity, which is increasingly recognized as important for modelling tissue-level effects. To address this, habitat imaging partitions tumours into spatially distinct subregions (habitats) with homogeneous multimodal imaging properties. This approach aims to better capture the spatial distribution and prevalence of complex biological phenotypes for predictive modelling. In this project, it is applied to survival analysis and the prediction of local failure after proton therapy.

Materials and Methods: Habitat imaging analysis was performed in a cohort of 38 skull-base cancer patients treated with proton therapy, of whom 7 experienced tumour recurrence, defined as local failure. Baseline multi-modal imaging consisting of CT and MRI sequences including T1, FLAIR, DWI/ADC and contrast-enhanced GADO-T1, was collected consistently across the cohort. After pre-processing, the soft-tissue component of the gross tumour volumes (GTV) was analysed using six algorithms for clustering of MR image intensities into high- and low-intensity sub-regions, yielding 16 habitats. Clustering alternatives went from standard K-Means to advanced spatially aware techniques. The prognostic relevance of individual habitat volume fractions and their presence within the GTV was assessed using a bootstrap procedure with an L1-penalized Cox proportional hazards model. Decisive factors included selection frequency, consistent weight sign and model concordance index (C-index).

Results: Although individual habitat volume fractions did not reach statistical significance in corrected univariate tests, multivariate survival models demonstrated predictive performance for local failures. K-Means and Otsu clustering algorithms yielded the highest concordance indices, outperforming spatially aware algorithms. Specific habitats were consistently selected across clustering methods: the habitat with high GADO-T1 intensities acted as a robust hazard-increasing predictor, whereas habitats with hyperintense FLAIR or combined high ADC and FLAIR consistently demonstrated hazard-decreasing effects.

Conclusion: A structured approach for generating and analysing tumour habitats from multi-modal MR images was developed. The identified habitats highlight the potential of spatial intra-tumour heterogeneity to serve as a predictive signature for local failure. External validation in larger cohorts and combination with dosimetric data are necessary to translate these findings into personalized treatment optimizations in a clinical context.

Supervised at the Center for Proton Therapy, Paul Scherrer Institut.

## Documents

- [Full report (PDF)](/assets/pdf/students/Juan_Perez_Gongora_Semester_Project_Report.pdf)
- [Presentation (PDF)](/assets/pdf/students/Juan_Perez_Gongora_Semester_Project_Presentation.pdf)
