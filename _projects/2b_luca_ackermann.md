---
layout: page
title: "Radiomics and Survival Analysis of Local Treatment Failure in Skull-Base Tumours"
description: Master Semester Project, supervised (October 2025)
importance: 2
category: research
tags: [Student project, Master Semester Project]
---

**Master Semester Project — Luca Ackermann (October 2025).**

## Abstract

Background and Motivation: Accurate prediction of radiation therapy response remains difficult due to inter-patient variability and tumor heterogeneity. Identification of quantitative imaging biomarkers that can characterize these differences and improve outcome prediction is needed.

Materials and Methods: This study investigated the association between radiomics features, clinical parameters and local treatment failure in patients with skull base chordoma and chondrosarcoma cancers treated with proton therapy. The final cohort consisted of 31 patients, of whom 6 experienced local treatment failure. Baseline diffusion weighted, T1-weighted and FLAIR-weighted magnetic resonance images, together with clinical parameters, were collected for all patients. A pipeline was developed for multimodal image registration, intensity normalization, and radiomics feature extraction. After removing highly correlated features, 50 radiomics features and one clinical parameter were included in a survival analysis. Feature robustness was evaluated using bootstrap resampling and a Cox proportional hazards model was fitted. Model performance was determined using the concordance index, the integrated Brier score, and Kaplan-Meier analysis.

Results: The discriminative performance of the model plateaued after the inclusion of the five most robust features. Calibration performance was highest using the two most robust features, but remained comparably stable for five. The final Cox model incorporating five features achieved good risk stratification, as confirmed by Kaplan-Meier analysis.

Conclusion: The presented pipeline provides a reproducible framework to extract radiomics features from multimodal MRI data and perform survival analysis in combination with clinical parameters. The features identified in this study show potential to capture valuable biological information associated with treatment outcome. Future studies with a larger dataset are needed to confirm these findings and to reliably identify imaging biomarkers to help make clinical decisions.

Supervised at the Center for Proton Therapy, Paul Scherrer Institut.

## Documents

- [Full report (PDF)](/assets/pdf/students/Luca_Ackermann_Semester_Project_Report.pdf)
- [Presentation (PDF)](/assets/pdf/students/Luca_Ackermann_Semester_Project_Presentation.pdf)
