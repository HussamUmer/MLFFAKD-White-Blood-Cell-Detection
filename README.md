# 🩸 MLFFAKD – Optimizing White Blast Cell Detection

[![Paper](https://img.shields.io/badge/📄%20Research%20Paper-PDF-blue)](paper.pdf)
[![Dataset](https://img.shields.io/badge/Dataset-Figshare-orange)](https://springernature.figshare.com/articles/dataset/A_large-scale_high-resolution_WBC_image_dataset/22680517)
[![Accuracy](https://img.shields.io/badge/Accuracy-98.33%25-brightgreen)](#-results-vs-state-of-the-art)
[![License](https://img.shields.io/badge/License-MIT-purple)](LICENSE)

> **Multi-Layer Feature Fusion & Attention-Based Knowledge Distillation (MLFFAKD)**  
> Lightweight yet high-accuracy deep learning for **White Blood Cell (WBC) classification** from blood smear images.

---

## 📌 Overview

Detecting immature blast cells in blood smear images is critical for diagnosing hematological diseases like leukemia.  
Manual inspection is **slow, labor-intensive, and prone to human error**.  

Our **MLFFAKD framework**:
- Transfers rich knowledge from **EfficientNet (teacher)** → **TinyResNet (student)**
- Uses **Multi-Layer Feature Fusion** + **Attention Mechanisms**
- Achieves **98.33% accuracy** with **60% faster inference**
- Ideal for **real-time clinical & portable AI devices**

---

## ✨ Key Features

✅ **High Accuracy** – Matches teacher model performance  
✅ **Lightweight** – Faster inference for real-time use  
✅ **Attention-Enhanced** – Focuses on important image regions  
✅ **Multi-Layer Fusion** – Captures both low & high-level features  
✅ **Clinically Applicable** – Suitable for low-resource hospitals  

---

## 📊 Performance Summary

| Model               | Accuracy | Precision | Recall  | F1-Score |
|---------------------|----------|-----------|---------|----------|
| Teacher (EfficientNet) | 98.61%  | 98.39%    | 98.33% | 98.44%   |
| Student (TinyResNet)   | 98.33%  | 98.39%    | 98.33% | 98.44%   |

---

## 🖼 Visual Results

| Teacher Model CM | Student Model CM |
|------------------|------------------|
| ![Confusion Matrix](Sample%20Outputs/download3.png) | ![Student Confusion Matrix](Sample%20Outputs/download2.png) |

---

## 🧠 Methodology

### 1️⃣ Data

We used the **High-Resolution, Large-Scale White Blood Cell (WBC) Image Dataset**, published on Figshare.  
This comprehensive dataset includes:

- **16,027** single-cell WBC images, both normal and pathological  
- Covers **nine classes**: neutrophil segments, neutrophil bands, eosinophils, basophils, lymphocytes, monocytes, normoblasts (nucleated red blood cells), myeloblasts (referred to as “myeloid” on the webpage), and lymphoblasts  
- **Dataset Link**: [🔗 Figshare – High-Resolution WBC Dataset](https://springernature.figshare.com/articles/dataset/A_large-scale_high-resolution_WBC_image_dataset/22680517)


For training and evaluation, we structured the dataset as follows:

| Dataset Split       | Number of Samples |
|---------------------|-------------------|
| **Training**        | 2,880             |
| **Validation**      | 360               |
| **Testing**         | 360               |

Data augmentation techniques such as rotation, brightness adjustment, horizontal/vertical flips, and zoom were applied to enrich the training set and improve model generalization.

### 2️⃣ Teacher–Student Training
- **Teacher**: EfficientNet (pre-trained)
- **Student**: TinyResNet (lightweight)
- **Knowledge Distillation**: Soft targets + multi-layer feature alignment

### 3️⃣ Multi-Layer Feature Fusion + Attention
- Extract features from multiple teacher layers  
- Fuse + align with student features  
- Apply attention for relevant region emphasis

---

## ⚙️ Installation & Usage

```bash
# Clone repo
git clone https://github.com/your-username/MLFFAKD-White-Blood-Cell-Detection.git
cd MLFFAKD-White-Blood-Cell-Detection

# Install dependencies
pip install -r requirements.txt

# Run Jupyter Notebook
jupyter notebook MFFAKD_final_notebook.ipynb
```
## 📈 Results vs State-of-the-Art

| Model                    | Accuracy   | Precision  | Recall     | F1-Score   |
| ------------------------ | ---------- | ---------- | ---------- | ---------- |
| DenseNet + Random Search | 97.3%      | 96.5%      | 96.8%      | 96.6%      |
| Y-YOLO v10               | 96.8%      | 95.9%      | 96.2%      | 96.0%      |
| Vision Transformer (ViT) | 96.5%      | 95.7%      | 96.0%      | 95.8%      |
| DeepLeuk CNN             | 97.1%      | 96.3%      | 96.6%      | 96.4%      |
| **Proposed MLFFAKD**     | **98.33%** | **98.37%** | **98.36%** | **98.34%** |

## 📧 Contact

- **Sana Ullah Khan** – [sana.ullah@kust.edu.pk](mailto:sana.ullah@kust.edu.pk)  
- **Hussam Umer** – [hussamumer28092000@gmail.com](mailto:hussamumer28092000@gmail.com)

