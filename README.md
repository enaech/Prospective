# MRI-Based Tumor Habitat Predicts Glioblastoma Outcomes  
Prospective Longitudinal Analysis of Physiologic MRI-based Tumor Habitat Predicts Short-term Patient Outcomes in IDH-wildtype Glioblastoma   

## Summary statement  
Spatial heterogeneity in glioblastoma indicates a poor prognosis and contributes to treatment resistance. This study prospectively validates the clinical utility of physiologic MRI-based tumor habitat analysis in predicting time-to-progression (TTP) and progression sites in isocitrate dehydrogenase (IDH)-wildtype glioblastoma patients post concurrent chemoradiotherapy (CCRT). An increase in the hypovascular cellular habitat, characterized by both low apparent diffusion coefficient and cerebral blood volume values, showed the most significant association with shorter TTP and predicted the site of progression. Notably, the habitat risk score outperformed traditional tumor volume assessments in predicting short-term outcomes, offering a valuable tool for patient risk stratification. Our results underscore the potential of multiparametric physiologic MRI-derived spatiotemporal tumor habitat and habitat risk score as useful biomarkers for early tumor progression and clinical outcomes, assisting in patient risk assessment and treatment decision-making in glioblastoma management.  

## Key point  
1. Hypovascular cellular habitat and habitat risk score were predictors of time-to-progression.  
2. Habitat risk score outperformed tumor volume in predicting time-to-progression.   
3. An increase in hypovascular cellular habitat predicted tumor progression sites.  

## MRI aqcusition  

## MRI Habitat  
The final voxel classifications based on nCBV and ADC values were implemented using a k-means clustering module in the scikit-learn python package.
By utilizing these two distinct feature maps, three clusters were established: 
- `cluster 1` represented **“hypervascular cellular tumor”** with high CBV values and low ADC values  
- `cluster 2` represented **“hypovascular cellular tumor”** with low CBV values and low ADC values
- `cluster 3` represented **“nonviable tissue”** with low CBV values and high ADC values.  

The ranges for the boundaries of the pre-trained and retrospectively validated spatial physiologic habitats were previously reported as 4.37–4.44 for nCBV and 150–187 (×10-6 mm2/s) for ADC in a study on 97 patients<sup>[1](https://doi.org/10.1158/1078-0432.CCR-20-2156)</sup>.   


## Dataset
This folder contains co-registered MRI and pathological slide data, organized into six sub-folders, which fall into two main categories: MRI and MRI_Habitat
The sub-folder names are as follows: T1ce, FLAIR, ADC, CBV, Tumor_mask, and Habitat.

### MRI  
The **MRI** category includes the `T1ce`, `FLAIR`, `ADC`, and `CBV` subfolders. MRI data is provided in Nifti.gunzip format. {PID}_{timepoint}_sequence_nii.gz  
For instance, the files for a patient with ID 1083, who underwent MRI on October 24, 2018, are named `H001_20181024_t1ce_coreg.nii.gz` and `H001_20181024_flair_coreg.nii.gz`.  
This naming convention is consistent across the entire dataset.  

### MRI_Habitat
The MRI habitat data provides results of tumor habitat analysis for each patient, stored in Nifti.gunzip format.   
The `Tumor_mask` folder contains segmented tumor mask, based on the T1ce and Flair images.  
The `Habitat` folder includes the final voxel classifications based on normalized CBV (nCBV) and ADC values, obtained using a k-means clustering method.   
When these files are overlaid onto anatomical image files (loaded as segmentation), the tumor habitats will be visualized.  

---  
<sup>[1]</sup>  Park JE, Kim HS, Kim N, Park SY, Kim YH, Kim JH. Spatiotemporal Heterogeneity in Multiparametric Physiologic MRI Is Associated with Patient Outcomes in IDH-Wildtype Glioblastoma. Clin Cancer Res. 2021 Jan 1;27(1):237-245. doi: 10.1158/1078-0432.CCR-20-2156. Epub 2020 Oct 7. PMID: 33028594.

