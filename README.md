# 🧠 Gabor Wavelet-based Image Classification using Convolutional Neural Networks (CNNs)

This repository presents a deep learning-based approach to improve image classification performance by leveraging **Gabor wavelet representations** of images. The core idea is to train multiple CNN models using both original and Gabor-transformed images and perform **ensemble decision fusion** to enhance classification accuracy.

---

## 📌 Project Summary

We apply this approach to classify **chest X-ray images** for **pneumonia detection**, combining traditional CNN architectures with **directionally localized features** extracted via Gabor filters.

### 🔍 Motivation

- Improving diagnostic tools for pneumonia detection using X-rays.
- Exploiting the spatial-frequency sensitivity of Gabor wavelets.
- Combining signal processing and deep learning to improve generalization.

---

## 🌐 Methodology

### 🌀 Gabor Wavelets & Filters

- Gabor wavelets are **complex exponentials modulated by Gaussians**, sensitive to frequency and orientation.
- Gabor filters act as **localized, orientation-tuned edge detectors**.

### 🔄 Image Transformation Pipeline

- For each input image:
  1. Apply Gabor filters at **8 different orientations**.
  2. Generate **8 Gabor-transformed images**.
  3. Train **9 CNNs** (1 with the original image + 8 with Gabor-transformed variants).

### 🧮 Decision Fusion

- Final prediction is made by aggregating the output probabilities from all CNNs using the **Sum of Probabilities (SMP) Rule**:
- A custom threshold of **0.4** is used for final classification.

---

## 📊 Dataset

- **Source**: Pediatric chest X-ray dataset from Guangzhou Women and Children’s Medical Center.
- **Size**: 5,856 JPEG images
  - Training: 5,216
  - Validation: 16
  - Testing: 624
- **Classes**: `Pneumonia`, `Normal`

---

## 🏗️ CNN Architecture

> Standard convolutional architecture with ReLU activations and max-pooling. Each CNN is trained independently on either the raw image or a specific Gabor-transformed version.

---

## 📈 Results

| Model              | Accuracy | Precision | Recall | F1-Score |
|--------------------|----------|-----------|--------|----------|
| Single CNN (Raw)   | 90.06%   | 92.27%    | 91.79% | 0.92     |
| **Ensemble (Fused)** | **92.47%**   | **90.73%**    | **97.94%** | **0.94**     |

> The ensemble model significantly improves recall while maintaining high precision.

---

## 🔭 Future Work

- Try alternative **wavelet families** for image decomposition.
- Explore **other CNN variants** (e.g., ResNet, EfficientNet).
- Investigate **wavelet packet decomposition** for richer representations.

---

## 📚 References

1. Granlund, G. H. (1978). *In Search of a General Picture Processing Operator*. Computer Graphics and Image Processing, 8(2), 155–173. [https://doi.org/10.1016/0146-664X(78)90047-3](https://doi.org/10.1016/0146-664X(78)90047-3)

2. Serte, S., & Demirel, H. (2019). *Gabor wavelet-based deep learning for skin lesion classification*. Computers in Biology and Medicine, 113, 103423. [https://doi.org/10.1016/j.compbiomed.2019.103423](https://doi.org/10.1016/j.compbiomed.2019.103423)

---

## 👨‍🎓 Author

**Rajdeep Pathak**  
Department of Mathematics,  
Indian Institute of Technology Hyderabad  
📅 May 6, 2025

