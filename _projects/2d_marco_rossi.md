---
layout: page
title: "Time-Resolved Dose and LET for Voxel-Wise Prediction of Radiation-Induced Brain Toxicity"
description: MSc Thesis, co-supervised, Politecnico di Milano
importance: 2
category: research
tags: [Student project, Co-supervised]
---

**MSc Thesis — Marco Rossi, Politecnico di Milano.**

Main advisor: Prof.ssa Chiara Paganelli, Dipartimento di Elettronica, Informazione e Bioingegneria (DEIB), Politecnico di Milano.

## Abstract

Radiotherapy aims to to achieve local tumour control by depositing ionizing radiation in the target volume, while sparing surrounding normal tissues as much as possible. High-precision techniques such as proton therapy are promising in this regard; however, despite their favorable dose conformality, late adverse effects, including brain toxicity in head tumours, remain clinically reported complications. Previous studies have primarily focused on aggregated dosimetric and clinical risk factors, whereas the temporal structure of treatment delivery has largely been overlooked. In this work, we investigate whether the temporal structure of pencil beam scanning proton delivery is associated with subsequent radiological brain toxicity, quantified by regions of radiation-induced contrast enhancement (RICE). Using machine log records acquired during beam delivery, we reconstruct voxel-level, time-resolved dose and Linear Energy Transfer (LET) deposition and integrate these data into a deep learning model for voxel-wise RICE risk prediction. The architecture combines a bidirectional Long Short-Term Memory (bi-LSTM) to encode sequences of individual dose-spot events, a Multi Layer Perceptron (MLP) to encode per-voxel treatment summary features, and a classification head to merge both representations. The model was trained on 78,976 voxels from 17 skull-base chordoma patients with radiographic evidence of RICE on post-contrast T1-weighted MR imaging. On an independent test set of two patients (11,392 voxels), the model achieved fair performance (balanced accuracy 73.51%; recall 64.10%; precision 48.70%), with reduced calibration on unseen data contributing to the observed drop in precision. Explainability analyses identified clinically plausible drivers: higher LETd and cumulative dose, together with fewer delivered fractions, increased predicted risk in the summary encoder, while instantaneous dose, LET, and beam-on duration contributed most strongly in the event encoder. Overall, these findings suggest that time-resolved delivery information contains signal relevant to voxel-level RICE risk, but further work is required to improve robustness, particularly calibration and generalization under distribution shift, and to enhance interpretability before clinical translation.

Co-supervised at the Center for Proton Therapy, Paul Scherrer Institut.

## Links

- [Marco Rossi — Politecnico di Milano profile](https://www.deib.polimi.it/eng/people/details/1492196)
- [Thesis archive (Politesi)](https://www.politesi.polimi.it/handle/10589/250643)
