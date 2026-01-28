# 🔮 Visual Field Prediction Using Multimodal Deep Learning


### 📝 Project Overview

This project focuses on predicting visual field (VF) sensitivities in glaucoma patients using a multimodal deep learning framework. Glaucoma causes progressive vision loss, and structural cues in Color Fundus Photographs (CFP), optic nerve head regions, and clinical features can be used to estimate functional decline.
Our approach integrates deep learning, segmentation-derived features, and clinical data fusion to accurately predict both pointwise VF values and mean sensitivity.

---


### 👁️ Input Modalities Used

To model both structure and function, the following visual and clinical features are utilized:
* Optic Disc Mask
* Optic Cup Mask
* Clinical Features: Age, Gender, IOP, CDR, CCT
* Visual Field Ground Truth: 59 pointwise sensitivities + mean sensitivity

---

### 📊 Dataset Used

#### 📌 GRAPE Dataset (Glaucoma Research and Progression Evaluation Dataset)

The dataset includes CFP images, segmented OD/OC boundaries, longitudinal clinical measurements, and Humphrey 24-2 VF tests.

**Data Split:**

* Training: 80%
* Testing: 20%

**Data Types Included:**

* ROI crops
* LabelMe-based OD/OC annotations
* Clinical CSV files
* VF sensitivity values (59 points + mean)

---

### ⚙️ Methodology

#### **1. Data Preprocessing**

* ROI extraction using optic nerve head localization
* Parsing LabelMe JSONs to generate OD/OC masks
* Clinical feature normalization
* Image resizing and augmentation
* Building multimodal fusion datasets (3-channel and 5-channel)

#### **2. Model Training**

* Implemented fully in PyTorch
* Trained on Kaggle Notebooks using NVIDIA Tesla T4 GPU
* Early stopping and checkpointing
* Separate pipelines for pointwise and mean sensitivity prediction

#### **3. Evaluation Metrics**

* Mean Absolute Error (MAE)
* Root Mean Squared Error (RMSE)
* Coefficient of Determination (R²)

---


### 🚀 Future Enhancements

* Use of self-supervised pretraining for fundus images
* Exploration of diffusion-based image augmentations
* Multi-dataset generalization (GRAPE + REFUGE + ORIGA)
* Graph-based structure modeling of OD–cup relationship



