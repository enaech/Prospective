# MRI-Based Tumor Habitat Predicts Glioblastoma Outcomes  
Prospective Longitudinal Analysis of Physiologic MRI-based Tumor Habitat Predicts Short-term Patient Outcomes in IDH-wildtype Glioblastoma   

## Summary statement  
Spatial heterogeneity in glioblastoma indicates a poor prognosis and contributes to treatment resistance. This study prospectively validates the clinical utility of physiologic MRI-based tumor habitat analysis in predicting time-to-progression (TTP) and progression sites in isocitrate dehydrogenase (IDH)-wildtype glioblastoma patients post concurrent chemoradiotherapy (CCRT). An increase in the hypovascular cellular habitat, characterized by both low apparent diffusion coefficient and cerebral blood volume values, showed the most significant association with shorter TTP and predicted the site of progression. Notably, the habitat risk score outperformed traditional tumor volume assessments in predicting short-term outcomes, offering a valuable tool for patient risk stratification. Our results underscore the potential of multiparametric physiologic MRI-derived spatiotemporal tumor habitat and habitat risk score as useful biomarkers for early tumor progression and clinical outcomes, assisting in patient risk assessment and treatment decision-making in glioblastoma management.  

## Key point  
1. Hypovascular cellular habitat and habitat risk score were predictors of time-to-progression.  
2. Habitat risk score outperformed tumor volume in predicting time-to-progression.   
3. An increase in hypovascular cellular habitat predicted tumor progression sites.  

## MRI aqcusition  
The brain tumor imaging protocol was acquired on a **3-T scanner (Ingenia 3.0 CX, Philips Healthcare)** and included both conventional and advanced sequences: T2-weighted imaging (**T2WI**), fluid-attenuated inversion recovery (**FLAIR**) imaging, T1-weighted imaging (**T1WI**), diffusion-weighted imaging (**DWI**), dynamic susceptibility contrast (**DSC**) perfusion imaging, and contrast-enhanced **(CE) T1WI**.    
- The **DWI** parameters were as follows: repetition time (TR)/echo time (TE) 3000/56 ms, diffusion gradient encoding with b values of 0 and 1000 s/mm2, field of view (FOV) of 250 × 250 mm, matrix dimensions of 256 × 256, and slice thickness/gap of 5/2 mm.   
  **ADC** images were calculated from the DWI images acquired with b values of 1000 and 0 s/mm2.   
- **DSC** imaging was conducted using a gradient-echo echo-planar imaging protocol. A preload of 0.1 mmol/kg gadoterate meglumine (Dotarem; Guerbet) was administered, followed by a dynamic bolus of a standard dose of 0.1 mmol/kg gadoterate meglumine delivered at a rate of 4 mL/s using an MRI-compatible power injector (Spectris; Medrad). Subsequently, 20 mL of saline was injected at the same rate.
  The DSC imaging parameters were as follows: TR/TE of 1808/40 ms, flip angle of 35°, FOV of 24 × 24 cm, slice thickness/gap of 5/2 mm, matrix dimensions of 128 × 128, and a total acquisition time of 1 minute and 54 s. The dynamic acquisition was performed with a temporal resolution of 1.5 s, capturing a total of 60 dynamics. The DSC imaging covered the entire tumor volume with the same section orientation as the conventional MRI.  

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

