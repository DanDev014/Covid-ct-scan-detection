#COVID-19 Lung CT Scan Classification using CNN

A deep learning-based medical imaging project that applies **Convolutional Neural Networks (CNNs)** to classify lung CT scan images into **COVID-19** and **Non-COVID-19** categories.

This project prioritizes **Recall (Sensitivity)** as the primary evaluation metric because, in healthcare, minimizing false negatives is critical.

---

## Project Overview

The COVID-19 pandemic increased the demand for fast and accurate diagnosis. While PCR testing remains standard, lung CT scans provide valuable imaging insights for detecting infection patterns.

Manual analysis of CT scans can be slow and resource-intensive. This project uses deep learning to automate COVID-19 detection and support faster clinical decision-making.

The model performs **binary image classification** on lung CT scans using a custom-built CNN.

---

## Problem Statement

Early detection of COVID-19 is essential for timely treatment and disease control. However, manual CT scan interpretation by radiologists can be time-consuming and subject to inconsistency.

This project addresses that challenge by building an AI-powered classification model capable of identifying COVID-19 from lung CT scan images.

---

## Objective

To develop and evaluate a Convolutional Neural Network (CNN) model that classifies lung CT scans into:

* COVID-19
* Non-COVID-19

---

## Dataset

**Source:** Kaggle
**Dataset:** COVID-19 Lung CT Scans
**Author:** Mehrad Aria

Dataset URL:
[https://www.kaggle.com/datasets/mehradaria/covid19-lung-ct-scans](https://www.kaggle.com/datasets/mehradaria/covid19-lung-ct-scans)

### Dataset Summary

* **Total Images:** 8,439
* **Classes:** 2
* **Image Format:** PNG
* **Original Resolution:** 512 × 512

### Folder Structure

COVID-19/
Non-COVID-19/

---

## Methodology

### 1. Data Preprocessing

The following preprocessing steps were performed:

* Loaded CT scan images from directory folders
* Resized all images to **64 × 64**
* Converted images into NumPy arrays
* Normalized pixel values from **0–255** to **0–1**
* Applied one-hot encoding for binary classification

---

### 2. Data Splitting

The dataset was split into:

* **70% Training**
* **15% Validation**
* **15% Testing**

This ensures:

* proper model training
* model tuning
* unbiased evaluation

---

### 3. Model Architecture

The CNN model consists of:

* 3 Convolutional layers
* 3 MaxPooling layers
* Flatten layer
* Dense hidden layer
* Dropout layer
* Softmax output layer

### Architecture Summary

| Layer        | Function                           |
| ------------ | ---------------------------------- |
| Conv2D       | Feature extraction                 |
| MaxPooling2D | Dimensionality reduction           |
| Flatten      | Converts feature maps into vectors |
| Dense        | Learns classification patterns     |
| Dropout      | Prevents overfitting               |
| Softmax      | Produces final class probabilities |

**Trainable Parameters:** 683,458

---

## Evaluation Strategy

Since this is a **medical classification problem**, the primary evaluation metric is **Recall**.

### Why Recall?

In healthcare:

A **false negative** means an infected patient is incorrectly classified as healthy.

This can lead to:

* delayed treatment
* increased transmission
* higher medical risk

For this reason:

> Recall is prioritized over Accuracy.

### Metrics Used

* Recall (Primary)
* Precision
* AUC
* Accuracy
* F1-score
* Confusion Matrix

---

## Model Training

Training configuration:

| Parameter     | Value                    |
| ------------- | ------------------------ |
| Epochs        | 20                       |
| Batch Size    | 16                       |
| Optimizer     | Adam                     |
| Loss Function | Categorical Crossentropy |

---

## Results

### Final Test Performance

| Metric    | Score      |
| --------- | ---------- |
| Recall    | **99.68%** |
| Precision | **99.68%** |
| AUC       | **99.76%** |
| Accuracy  | **99.68%** |

---

## Classification Report

| Class        | Precision | Recall | F1-score |
| ------------ | --------- | ------ | -------- |
| Non-COVID-19 | 1.00      | 1.00   | 1.00     |
| COVID-19     | 1.00      | 0.97   | 0.99     |

---

## Key Insights

* The CNN successfully learned relevant lung CT scan patterns
* High recall demonstrates strong COVID-19 detection capability
* Low false negatives improve screening reliability
* High AUC confirms strong class separation

---

## Tech Stack

* Python
* TensorFlow / Keras
* OpenCV
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook

---

## Repository Structure

COVID-CT-Scan-Detection/
│── covid.ipynb
│── README.md
│── .gitignore

**Note:** Raw CT scan image folders are excluded from version control using `.gitignore`.

---

## Future Improvements

Potential improvements:

* Transfer Learning (ResNet50, MobileNetV2, EfficientNet)
* Data augmentation
* Hyperparameter tuning
* Explainable AI (Grad-CAM)
* Streamlit deployment

---

## Conclusion

This project demonstrates the effectiveness of CNNs in medical image classification.

By prioritizing **Recall**, the model aligns with real-world healthcare requirements where missing positive cases is more critical than maximizing overall accuracy.

The results show strong potential for supporting clinical screening workflows.

---

## Author

**Daniel Njeru**
Data Scientist | Machine Learning | AI | Data Analytics

GitHub: [https://github.com/DanDev014](https://github.com/DanDev014)
