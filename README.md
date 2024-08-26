# MRI-Based Tumor Habitat Predicts Glioblastoma Outcomes
Prospective CCRT
Prospective Longitudinal Analysis of Physiologic MRI-based Tumor Habitat Predicts Short-term Patient Outcomes in IDH-wildtype Glioblastoma 

## Summary statement
Spatial heterogeneity in glioblastoma indicates a poor prognosis and contributes to treatment resistance. This study prospectively validates the clinical utility of physiologic MRI-based tumor habitat analysis in predicting time-to-progression (TTP) and progression sites in isocitrate dehydrogenase (IDH)-wildtype glioblastoma patients post concurrent chemoradiotherapy (CCRT). An increase in the hypovascular cellular habitat, characterized by both low apparent diffusion coefficient and cerebral blood volume values, showed the most significant association with shorter TTP and predicted the site of progression. Notably, the habitat risk score outperformed traditional tumor volume assessments in predicting short-term outcomes, offering a valuable tool for patient risk stratification. Our results underscore the potential of multiparametric physiologic MRI-derived spatiotemporal tumor habitat and habitat risk score as useful biomarkers for early tumor progression and clinical outcomes, assisting in patient risk assessment and treatment decision-making in glioblastoma management.  

## Key point
Hypovascular cellular habitat and habitat risk score were predictors of time-to-progression.  
Habitat risk score outperformed tumor volume in predicting time-to-progression.   
An increase in hypovascular cellular habitat predicted tumor progression sites.  

## Keywords
Tumor habitat; glioma; isocitrate dehydrogenase; magnetic resonance imaging; outcome


## Citation
_Public data with a comprehensive pathology-molecular map of glioblastoma with en bloc resection is available in the Ivy Glioblastoma Atlas (http://glioblastoma.alleninstitute.org/).
This provides an en-block specimen, comprehensive pathologic map supplied by pathologists, RNA sequencing, and multiparametric MRI of diffusion-weighted and dynamic susceptibility contrast imaging._

## Dataset
This folder contains co-registered MRI, habitat and pathology data.  
MRI data includes Nifti.gunzip format of contrast-enhanced T1 (pid_tp_t1ce_coreg.nii.gz) and FLAIR (pid_tp_flair_coreg.nii).  
MRI habitat data includes results of tumor habitat analysis (voxel-wised clustering of ADC and CBV maps) as Nifti.gunzip format per patient.
If this file is overlayed to anatomical image files (load as segmentation), the tumor habitats will be shown.  
Pathology data includes co-registered pathologic slides per patient as Nifti.gunzip format.
If this file is overlayed to anatomical image files (load as segmentation), the co-registered results will be shown.  
