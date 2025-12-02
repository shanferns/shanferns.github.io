---
title: "Projects"
layout: archive
sitemap: true
author_profile: true
permalink: /Projects/
---

[Physics-based Pipeline & 3D U-Net for Stomach Segmentation from MRI](https://github.com/shanferns/Image-processing-stomach-using-physics-based-pipeline-and-AI-methods.git).

<object data="https://github.com/shanferns/Image-processing-stomach-using-physics-based-pipeline-and-AI-methods.git" type="application/pdf" width="100%" height="70px"> 
  <p>It appears you don't have a PDF plugin for this browser.
  You can <a href="https://github.com/shanferns/Image-processing-stomach-using-physics-based-pipeline-and-AI-methods.git">click here to view the GitHub repository</a>.</p>  
</object>

Built a traditional image-processing workflow—denoising, rigid registration, binary Otsu thresholding, and morphological refinement—to generate high-quality stomach masks from 4D MRI datasets. Using these curated masks, designed and trained a modified 3D U-Net with organ-specific enhancements: class-imbalance handling using <code>BCEWithLogitsLoss</code>, BatchNorm in all convolutional blocks for MRI intensity stabilization, a lightweight architecture with only two downsampling stages to reduce GPU memory while preserving organ structure, and full skip connections to maintain spatial detail. Applied sigmoid and thresholding at inference to produce binary masks and validated the model on unseen MRI volumes to assess segmentation generalization and robustness.

[Image Processing & Data Science for Studying Vagal Nerve Stimulation (VNS) Effects on Gastric Motility](/Project_document/Data_science_presentation_Shannon.pdf).

<object data="/Project_document/Data_science_presentation_Shannon.pdf" type="application/pdf" width="100%" height="70px"> 
  <p>It appears you don't have a pdf plugin for this browser.
  You can <a href="/Project_document/Data_science_presentation_Shannon.pdf">click here to
  download the pdf file.</a></p>  
</object>

Using image-processing techniques—including motion correction, segmentation, Otsu thresholding, and spatiotemporal imaging—to extract quantitative data, followed by applying data-science methods such as logistic regression, LDA, QDA, and KNN to evaluate which data-science approach best predicts the effects of VNS on gastric motility.

[Modeling the afferent vagal nerve of a rat and the action potential propagation](/Project_document/Neural_ppt.pdf).

<object data="/Project_document/Neural_ppt.pdf" type="application/pdf" width="100%" height="70px"> 
  <p>It appears you don't have a pdf plugin for this browser.
  You can <a href="/Project_document/Neural_ppt.pdf">click here to
  download the pdf file.</a></p>  
</object>

Extending the existing Hodgkin–Huxley model to represent the afferent vagal nerve in rats, and using cable theory to model action potential propagation along the nerve.

[A Comparative Study of Armchair Carbon Nanotubes under Shear Deformation using Molecular Dynamics Simulation](/Project_document/Carbon_nanotube.pdf).

<object data="/Project_document/Carbon_nanotube.pdf" type="application/pdf" width="100%" height="70px"> 
  <p>It appears you don't have a pdf plugin for this browser.
  You can <a href="/Project_document/Carbon_nanotube.pdf">click here to
  download the pdf file.</a></p>  
</object>

A comparative study of carbon nanotube (CNT) shear deformation—across chirality, temperature, strain rates, and double-walled structures—showed that CNTs fracture only under very high stress, with double-walled CNTs displaying greater mechanical strength. All simulations used the AIREBO potential, which models covalent bonding and long-range van der Waals interactions.

[Modeling of a reactor for Methanol Synthesis using Cu/ZnO/Al2O3 catalyst](/Project_document/Presentation_project_methanol.pdf).

<object data="/Project_document/Presentation_project_methanol.pdf" type="application/pdf" width="100%" height="70px"> 
  <p>It appears you don't have a pdf plugin for this browser.
  You can <a href="/Project_document/Presentation_project_methanol.pdf">click here to
  download the pdf file.</a></p>  
</object>

Methanol synthesis—an exothermic hydrogenation of CO2 over a Cu/ZnO/Al2O3 catalyst—proceeds primarily through two rate-determining steps: CO2 dissociative adsorption and formate hydrogenation, with formate as the dominant intermediate. A 1D pseudo-homogeneous reactor model using the Vanden Bussche–Froment kinetics best matches industrial data (error <1%) and remains the most accurate for commercial multi-tubular reactor conditions.

