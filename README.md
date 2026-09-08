# Gene Expression Analysis: PCA and Sparse PCA and Classification

## Overview
This project applies dimensionality reduction (PCA) and classification techniques to a gene expression dataset from the ALL/AML (Acute Lymphoblastic Leukemia / Acute Myeloid Leukemia) dataset. The goal was to identify key genes and reduce the high-dimensional data (7,129 genes expressions). 

## Dataset
- **Training samples:** 38 patients (27 ALL, 11 AML)
- **Gene features:** 7,129 expression values per sample

## Methods

### 1. Principal Component Analysis (PCA)
A PCA was applied to identify principal components. 
- **PCA (38 components):** ~95% of variance explained by first 30 components
- **First 5 components:** ~52% explained variance
- **First 3 components:** ~39% explained variance

**Finding:** Most variation is concentrated in early principal components.

### 2. Sparse PCA
L1 regularization to enforce feature selection:
- **3 components:** 42.1% sparsity, 30.0% explained variance
- **5 components:** 50.2% sparsity, 36.9% explained variance  
- **10 components:** 60.5% sparsity, 47.9% explained variance

**Finding:** Sparsity increases with more components. Trade off between interpretability and explained variance.

### 3. Sparse Logistic Regression
L1-regularized logistic regression to identify a small set of genes for classification:
- **Selected genes:** 3 features (out of 7,129)
- **Training accuracy:** 71.1% accuracy on a 5-Fold Cross-Validation
- **ROC-AUC:** Computed both on training and CV folds
- **Convergence:** Achieved at 2,546 iterations (max: 10,000)


## Files Included

- **sparse_pca.ipynb**: Complete PCA and Sparse PCA analysis with all visualizations and improvements
- **sparse_logreg.ipynb**: L1-regularized logistic regression with cross-validation, evaluation metrics, and ROC curves

