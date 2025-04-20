# 👕 Clustering & Classification on Fashion MNIST and Overhead MNIST

This repository contains an unsupervised-to-supervised learning pipeline for the **Fashion MNIST** and **Overhead MNIST** datasets. The project combines **K-Means clustering** with a **Multi-Layer Perceptron (MLP)** classifier to efficiently label and classify handwritten and fashion-related images.

---

## 👩‍🏫 Submitted By

- **Esha Bhattacharya** (MDS202324)  
- **Malde Dharmi** (MDS202333)  
**Course:** DMML Assignment 3

---

## 📚 Project Overview

### 🔹 Goal

To reduce manual labeling effort by clustering unlabeled images and assigning cluster-level labels using nearest neighbors. These labeled clusters are then used to train a classification model (MLP), transforming an unsupervised problem into a supervised one.

---

## 🗂️ Datasets Used

### 1. **Fashion MNIST**
- 60,000 grayscale images (28x28)
- 10 categories: `T-shirt/top`, `Trouser`, `Pullover`, `Dress`, `Coat`, `Sandal`, `Shirt`, `Sneaker`, `Bag`, `Ankle boot`

### 2. **Overhead MNIST**
- Custom/variant MNIST-style dataset
- Each image is 28x28, labels denote classes (0–9)

---

## 🧠 Methodology

### 🔸 Clustering with K-Means

- **Preprocessing**: Normalization of pixel values from 0–255 to 0–1
- **Clustering**: Images are grouped using **K-means**
- **Cluster Labeling**:
  - For each cluster, find 10 nearest data points to the centroid
  - Assign the **mode** of their labels to the whole cluster

### 🔸 Classification with MLP

**Model Architecture:**
```text
Input Layer: 28x28 flattened → 784
Hidden Layer 1: Dense(100, ReLU)
Hidden Layer 2: Dense(50, ReLU)
Output Layer: Dense(10, Softmax)
