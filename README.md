# ECG Classification Using Machine Learning and Deep Learning

## Overview

This project focuses on the classification of ECG (Electrocardiogram) signals using both traditional machine learning methods and deep learning approaches. The dataset is sourced from Kaggle and contains ECG recordings labeled as **normal (0)** and **abnormal (1)**.

The main objective is to compare different feature extraction and classification techniques for ECG signal analysis.

---

## Dataset Description

The dataset consists of ECG signals where each sample represents a complete heartbeat signal.

### Data Structure:

* Each row = one ECG signal
* Columns 0–139 = ECG signal values (140 time points)
* Column 140 = class label:

  * **0 → Normal**
  * **1 → Abnormal**

---

## Methodology

Three different approaches were implemented:

---

## 1. PCA + SVM (Support Vector Machine)

### Feature Extraction:

* Principal Component Analysis (PCA) was used for dimensionality reduction.
* PCA helps preserve the most informative components of ECG signals while reducing noise and complexity.

### Classification:

* Support Vector Machine (SVM) was used for classification.

### Results:

* Accuracy: **97.87%**
* Sensitivity: **95.41%**
* Specificity: **99.65%**

Confusion Matrix:

```
[[603  29]
 [  3 865]]
```

---

## 2. PCA + MLP (Multilayer Perceptron)

### Feature Extraction:

* PCA was applied to reduce dimensionality and extract meaningful features.

### Classification:

* A Multilayer Perceptron (MLP) neural network was used.

### Results:

* Accuracy: **98.33%**
* Sensitivity: **96.83%**
* Specificity: **99.42%**

Confusion Matrix:

```
[[612  20]
 [  5 863]]
```

---

## 3. Convolutional Neural Network (CNN)

### Motivation:

ECG signals contain important temporal patterns that are not fully captured by statistical or PCA-based features. CNNs are well-suited to learn these patterns directly from raw signals.

### Model Architecture:

* Input: ECG signal (1 × 140)
* Conv1D:

  * kernel size = 5
  * padding = 2
  * input channels = 1
  * output channels = 10
* MaxPooling:

  * kernel size = 4
  * stride = 4
* Fully Connected Layers:

  * 120 → 80 → 1

### Results:

* Accuracy: **99.53%**
* Sensitivity: **99.36%**
* Specificity: **99.65%**

Confusion Matrix:

```
[[628   4]
 [  3 865]]
```

---

## Comparison of Methods

| Model     | Accuracy   | Sensitivity | Specificity |
| --------- | ---------- | ----------- | ----------- |
| SVM (PCA) | 97.87%     | 95.41%      | 99.65%      |
| MLP (PCA) | 98.33%     | 96.83%      | 99.42%      |
| CNN       | **99.53%** | **99.36%**  | **99.65%**  |

---

## Key Insights

* PCA effectively reduces dimensionality and improves classical ML performance.
* SVM and MLP perform well on extracted features.
* CNN outperforms traditional methods by learning temporal patterns directly from raw ECG signals.
* Deep learning provides the most robust performance for ECG classification.

---

## Technologies Used

* Python
* NumPy / Pandas
* Scikit-learn
* TensorFlow / PyTorch
* Matplotlib
* Seaborn

---

## Conclusion

This project demonstrates that while traditional machine learning methods (SVM, MLP) perform strongly with PCA features, Convolutional Neural Networks achieve the highest performance by effectively capturing temporal dependencies in ECG signals.

---

