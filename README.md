
### Supervised Machine Learning Models for Squirrel Detection Using Heterogeneous, Homogeneous, and Mixed Backgrounds  



---

## Overview

This repository contains the models, scripts, and deployment files generated for the study **“Smart Wildlife Camera Using MaixCAM-Pro: Effects of Background Consistency on Small Mammal Detection Accuracy.”**  
The models were trained to detect **squirrels** using datasets with different background characteristics:

- **Model A – Heterogeneous background images**  
- **Model B – Homogeneous background (plain white) images**  
- **Model C – Mixed background (heterogeneous + homogeneous)**  

Model C achieved the highest accuracy and F1 score during field deployment on the MaixCAM-Pro device.

All model training was conducted using **Roboflow** (dataset preparation and annotation) and **MaixHub** (YOLO-based training and quantization). Deployment scripts were implemented using **MaixVision**.

---
# MaixCAM-Pro Wildlife Detection Models

This repository contains the model training, evaluation, and deployment workflow used in the study:

**Comparative Evaluation of AI-Integrated and Conventional Camera Traps for Small Mammal Monitoring**

The repository supports the development and testing of supervised object detection models for small mammal species (rats and squirrels) deployed on the MaixCAM-Pro edge-AI camera platform.

## Scope of the Repository

This repository is intended to support methodological transparency and reproducibility for the accompanying publication. It includes example training notebooks, configuration files, and deployment scripts relevant to edge-AI wildlife monitoring.

## Roboflow Universe Links
The annotated image datasets used for training the three detection models are hosted on Roboflow Universe and are publicly accessible at: Model A (background-consistent dataset): https://universe.roboflow.com/smart-wildlife-camera/model-a-with-background-tu0jm/dataset/5; Model B (white-background dataset): https://universe.roboflow.com/smart-wildlife-camera/model-b-white-background-kr5pb/dataset/2; and Model C (mixed-background dataset): https://universe.roboflow.com/smart-wildlife-camera/model-c-mix-background-wsnhl/dataset/1. 



Full training datasets are not hosted in this repository due to data volume and ethical considerations related to wildlife monitoring.
---

## Model Description

| Model | Background Type | Dataset Size | Performance (F1 score) | Notes |
|------|------------------|--------------|-------------------------|-------|
| **Model A** | Heterogeneous | 660 images | 0.04 | High false positives due to background bias |
| **Model B** | Homogeneous | 660 images | 0.67 | Cleaner background → more stable detection |
| **Model C** | Mixed | 1320 images | 0.97 | Best generalization and field performance |

Model C is **recommended** for deployment.

---

## Deployment on MaixCAM-Pro

1. Open **MaixVision**  
2. Import the `.kmodel` file from `/models/`  
3. Load `app_main.py` from `/maixcam_app/`  
4. Package and upload to device  
5. Run real-time detection

---

## Python Scripts

Two Python utilities are provided:

- **evaluation_metrics.py**  
  - Computes Precision, Recall, F1 Score, mAP (if prediction logs are available)
- **confusion_matrix_plot.py**  
  - Generates confusion matrices for the three models

## Key Files Used in the Study

- `yolov5_rat_squirrel_training_fixed.ipynb`  
  Google Colab notebook used for supervised training and evaluation of detection models described in the manuscript.


