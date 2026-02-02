# Land Cover Classification using Stochastic Modeling and Bag of Visual Words (EuroSAT)

## Executive Summary
This project addresses the problem of land cover classification using satellite imagery from the EuroSAT dataset. The approach combines statistical image analysis, stochastic modeling concepts, and classical machine learning techniques.

Feature extraction is performed using color statistics and Local Binary Patterns (LBP), followed by a Bag of Visual Words (BoVW) representation. Classification is carried out using distance-based and margin-based classifiers, with performance evaluated using standard multi-class metrics.

---

## Project Objectives
- Perform statistical analysis of satellite images (histograms, PDFs, covariance)
- Extract texture-based features using Local Binary Patterns (LBP)
- Build a Bag of Visual Words (BoVW) representation using clustering
- Train and evaluate classical machine learning classifiers
- Analyze classification performance per land cover class

---

## Dataset
- Name: EuroSAT
- Source: Sentinel-2 satellite imagery
- Number of classes: 10
- Image type: RGB satellite images
- Task: Multi-class land cover classification

Classes include:
AnnualCrop, Forest, Residential, Industrial, River, Highway, Pasture, SeaLake, HerbaceousVegetation, PermanentCrop

---

## Methodology

### 1. Exploratory Data Analysis
- Visualization of sample images per class
- RGB color histograms for each class
- Probability Density Function (PDF) estimation
- Covariance analysis between color channels (R, G, B)

These steps provide statistical insight into inter-class variability.

---

### 2. Feature Extraction

#### Local Binary Patterns (LBP)
- Texture descriptors extracted from grayscale images
- Uniform LBP configuration
- Patch-based histogram extraction
- Normalization of local histograms

#### Bag of Visual Words (BoVW)
- LBP descriptors clustered using K-Means
- Codebook size: k = 200 visual words
- Each image represented as a normalized histogram of visual words

---

### 3. Classification
The BoVW feature vectors are classified using classical machine learning models.

Primary configuration:
- Normalization: L2 Normalizer
- Classifier: k-Nearest Neighbors (k = 15)

Alternative classifiers (tested or configurable):
- Linear SVM
- RBF SVM

---

## Experimental Setup
- Train/Test split: 80% / 20%
- Stratified sampling across classes
- Feature normalization applied before classification
- Evaluation on held-out test set

---

## Results

### Overall Performance
- Accuracy: ~0.80
- Macro-average F1-score: ~0.79

### Observations
- High performance for classes such as Forest, SeaLake, and Residential
- Confusion observed between visually similar classes (e.g. AnnualCrop vs PermanentCrop)
- Texture-based BoVW representation captures land cover patterns effectively

---

## Visual Outputs
The notebook includes:
- Sample images per class
- RGB histograms and PDFs
- Covariance matrices per class
- BoVW histograms (per image and per class)
- Confusion matrix visualization
- Classification report (precision, recall, F1-score)

---

## Tech Stack
- Python 3
- NumPy, Pandas
- OpenCV
- scikit-learn
- scikit-image
- Matplotlib
- Jupyter Notebook (Google Colab compatible)

---

## How to Run
```bash
pip install numpy pandas matplotlib scikit-learn scikit-image opencv-python

