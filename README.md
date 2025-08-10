# Optimizing White Blast Cell Detection with Multi-Layer Feature Fusion & Attention-Based Knowledge Distillation (MLFFAKD)

This repository contains the implementation of our research paper:

> **"Optimizing White Blast Cell Detection in Blood Smear Images Using Multi-Layer Feature Fusion and Attention-Based Knowledge Distillation"**  
> Sana Ullah Khan, Bakht Azam, Hussam Umer, Hidayat Ullah Khan (2025)

## 📌 Overview
Accurate detection of white blood cells (WBCs) — especially immature blast cells — is crucial for diagnosing hematological diseases such as leukemia, anemia, lymphoma, and thalassemia. Manual microscopic analysis is time-consuming, labor-intensive, and prone to human error.  

Our work introduces **MLFFAKD**, a **lightweight yet high-performing deep learning framework** that combines:
- **Multi-Layer Feature Fusion**  
- **Attention Mechanisms**  
- **Knowledge Distillation (KD)**  

We transfer knowledge from a powerful **EfficientNet (teacher model)** to a compact **TinyResNet (student model)**, significantly **reducing computational cost** while maintaining **state-of-the-art accuracy**.

---

## 🚀 Key Contributions
- **Novel Knowledge Distillation Approach** — Efficiently transfers rich feature representations from teacher to student model.
- **Multi-Layer Feature Fusion** — Leverages information from multiple network layers for improved learning.
- **Attention Mechanisms** — Enhances relevant feature selection, reducing false positives.
- **Computational Efficiency** — ~60% faster inference time with minimal performance drop compared to the teacher.
- **Clinical Applicability** — Optimized for real-time detection, especially in resource-constrained environments.

---

## 📊 Performance Summary

| Model             | Accuracy | Precision | Recall  | F1-Score |
|-------------------|----------|-----------|---------|----------|
| Teacher (EfficientNet) | 98.61%  | 98.39%    | 98.33% | 98.44%   |
| Student (TinyResNet)   | 98.33%  | 98.39%    | 98.33% | 98.44%   |

Our **MLFFAKD** student model matches the teacher model's accuracy while being much faster and lighter — ideal for portable and edge AI diagnostic devices.

---

## 🧠 Methodology

### 1️⃣ Data Preparation & Augmentation
- Dataset: **16,027 high-resolution WBC images** (9 classes) from the [Figshare repository](https://doi.org/10.6084/m9.figshare.23532799).
- Augmentations: Rotation, brightness adjustment, horizontal/vertical flips, and zoom.
- Balanced dataset: 20,000 images per class after augmentation.

### 2️⃣ Teacher–Student Framework
- **Teacher Model:** Pre-trained EfficientNet for deep feature extraction.
- **Student Model:** Lightweight TinyResNet optimized for speed and efficiency.
- **Knowledge Distillation:** Transfers both low-level and high-level features from teacher to student.

### 3️⃣ Multi-Layer Feature Fusion with Attention
- Combines feature maps from different layers.
- Applies attention mechanism for better feature selection.
- Ensures dimensional compatibility between teacher and student features.

### 4️⃣ Loss Function
Total loss = Knowledge Distillation Loss + Feature Distillation Loss + Fusion Loss + Cross-Entropy Classification Loss.

---


---

## 🖼️ Sample Outputs
- **Confusion Matrices** for both teacher and student models.
- **Performance Comparisons** with DenseNet, YOLOv10, Vision Transformer, and DeepLeuk CNN.

---

## 📥 Dataset
The dataset is available on Figshare:  
[🔗 High-Resolution Pathological and Normal WBC Dataset](https://doi.org/10.6084/m9.figshare.23532799)

---

## ⚙️ Installation & Usage

### Clone the repository
```bash
git clone https://github.com/your-username/MLFFAKD-White-Blood-Cell-Detection.git
cd MLFFAKD-White-Blood-Cell-Detection

