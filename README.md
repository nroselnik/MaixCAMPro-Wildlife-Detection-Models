# MaixCAM-Pro Small Mammal Detection Models  
### Supervised Machine Learning Models for Squirrel Detection Using Heterogeneous, Homogeneous, and Mixed Backgrounds  
*(Associated manuscript: see reference in repository)*  


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

## Repository Structure

