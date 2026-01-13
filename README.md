# Visualizations of Lipid Metabolism
## Overview
The analysis applies principal component analysis (PCA) and univariate statistical methods to lipidomic datasets, providing insights into how ad libitum feeding and doxorubicin treatment influence lipid metabolism in rat jejunum and liver tissues.

* This project reproduces selected figures from the study:

    Balgoma D, Kullenberg F, Peters K, Dahlgren D, Heindryckx F, Lennernäs H, Hedeland M. (2022). Orthogonality in Principal Component Analysis Allows the Discovery of Lipids in the Jejunum That Are Independent of Ad Libitum Feeding. Metabolites, 12(9):866. https://doi.org/10.3390/metabo12090866
  
The primary objective of this project was to practice data analysis in Python by recreating figures using statistical and machine learning approaches. Specifically, I reproducing Figure 2B (PCA loadings of jejunal and hepatic lipidomes) and Figures 4A & 4B (bar plots showing treatment effects on lipid families).

## Data
The dataset is available in the supplementary material of the original publication:
* Supplementary Material 1: _Processed lipidomic data_ (Excel)
  * Variables sheet: metadata on lipid species (tissue origin, lipid family)
  * Signal sheet: processed intensity values for lipid species across experimental conditions
    
This repository does not host the raw or processed data directly. Please download the Excel file from the study above and place it in your working directory as <ins>Balgoma_data.xlsx</ins>.

## Methods
* All plots were generated using matplotlib and seaborn.
* Each figure section in the notebook includes clear variable initialization, processing steps, and visualization code.
  
### 1. Data Loading & Preprocessing
* Imported lipidomic data from the Excel supplementary file.
* Separated metadata (tissue type, lipid family) from signal data.
* Standardized signal intensities before multivariate analysis.

### 2. PCA (Figure 2B)
* Performed PCA on standardized lipidomic data.
* Visualized loadings for jejunal and liver lipids.
* Highlighted key lipid families (TG and FA) to illustrate opposing loadings along the first principal component.

### 3. Bar Plots (Figures 4A & 4B)
* Figure 4A: Computed a lipidomics-based fasting score (log(TG/FA) ratio) to reflect feeding frequency across treatment conditions.
* Figure 4B: Summed signal intensities for etherPE lipids containing polyunsaturated fatty acids (PUFAs), visualizing treatment effects.
* Error bars represent the standard error of the mean (SEM).

## Results
### 1. PCA (Figure 2B):
* Liver lipids are distributed strongly along PC1, reflecting variability driven by digestion status under ad libitum feeding.
* Jejunal TGs and FAs displayed opposing loadings, confirming an anticorrelated relationship tied to feeding state.

### 2. Fasting Score (Figure 4A):
* Doxorubicin treatment reduced feeding frequency, as indicated by decreasing TG/FA ratios across stronger/longer treatments.

### 3. etherPE-PUFAs (Figure 4B):
* Doxorubicin treatments increased PUFA-containing etherPEs in jejunal tissue, with effects scaling by treatment strength and duration.

These results are consistent with the original study, demonstrating that ad libitum feeding introduces significant confounding effects in lipidomics analyses. The findings also show that PCA can reveal lipid families independent of feeding status, enhancing the reliability of metabolic studies conducted under drug treatment conditions.

## Requirements
This project was built in Python 3.9 using the following packages:
* pandas
* numpy
* scikit-learn
* matplotlib
* seaborn
* scipy

## Usage
* Download the supplementary dataset from the paper and save it as Balgoma_data.xlsx.
* Open the notebook:
```
jupyter notebook main.ipynb
```
* Run all cells to reproduce Figures 2B, 4A, and 4B.
  
## Aknowledgements
* Data from
  
    Balgoma D, Kullenberg F, Peters K, Dahlgren D, Heindryckx F, Lennernäs H, Hedeland M. Orthogonality in Principal Component Analysis Allows the Discovery of Lipids in the Jejunum That Are Independent of Ad Libitum Feeding. Metabolites. 2022; 12(9):866. https://doi.org/10.3390/metabo12090866

## Author
Mabel Chang

Developed as the final project for BF550: Foundations of Programming, Data Analytics, and Machine Learning in Python at Boston University (F23), instructed by Dr. Ilija Dukovski
