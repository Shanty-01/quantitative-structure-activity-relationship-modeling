# Quantitative Structure-Activity Relationship (QSAR) Modeling for Glycogen Synthase Kinase-3 Beta (GSK-3β)
[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Shanty-01/quantitative-structure-activity-relationship-modeling/blob/main/chEMBL_Alzheimer_Glycogen_synthase_kinase_3_beta.ipynb)



This project aims to create a Quantitative Structure-Activity Relationship (QSAR) model for glycogen synthase kinase-3 Beta (GSK-3β), 
which is a target molecule for Alzheimer's disease. The model will predict the activity of chemical compounds against GSK-3β, 
supporting drug discovery efforts for Alzheimer's disease.

## About
* Research has shown that increased activity of glycogen synthase kinase-3 beta (GSK-3β) is strongly linked to the development of Alzheimer's disease. This is due to its contribution in the hyperphosphorylation of tau protein, the main component of neurofibrillary tangles (NFTs), one of the hallmarks of Alzheimer's disease. Thus GSK-3β inhibition could reduce neurodegeneration caused by tau phosphorylation[1].  

* IC50 (Half-maximal Inhibitory Concentration) is a measure of the concentration of a drug or compound required to inhibit a particular biological or biochemical process by 50%. If a molecule has a low IC50 in respect to GSK-3β, the molecule has the potential to be a GSK-3β inhibitor.

* chEMBL is a publicly available relational database containing bioactive molecules with drug-like properties along with their 2-D structures, calculated properties (e.g. logP, Molecular Weight, Lipinski Parameters, etc.) and abstracted bioactivities (e.g. binding constants, pharmacology and ADMET data).

 * The dataset includes the 2D structure (SMILES) and IC50 values for molecules targeting GSK-3β, which can be used as the training data to build a model for predicting the IC50 of molecules to inhibit GSK-3β. The model that predicts IC50 values is an example of a Quantitative Structure-Activity Relationship (QSAR) model.
## Result
In this project, we have:  

* Extracted molecules that could inhibit GSK-3β from the chEMBL dataset.
* Classify molecules to active and inactive groups by the threshold of :
 - Active (strongly potent): IC50 < 1000 nM
 - Inactive : IC50 > 10000 nM .

* Conducted the Mann–Whitney test for the Lipinski descriptor between active and inactive groups. With p-value < 0.05, the labelled active and inactive molecules differ significantly in their Lipinski descriptor values, therefore validating the threshold used value.
* Trained an XGBRegressor model to map SMILE Fingerprint of a molecule to its IC50 value to inhibit GSK-3β. The model evaluation shows:  
   - Validatiion RMSE: 0.856
   - Test RMSE: 0.876
### References
[1] C. L. Sayas and J. Ávila, “GSK-3 and Tau: A Key Duet in Alzheimer’s Disease,” Cells, vol. 10, no. 4, p. 721, Mar. 2021, doi: https://doi.org/10.3390/cells10040721.
