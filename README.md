# Pneumonia Detection from Chest X-Rays: Custom CNN vs. VGG19

## Overview
This repository contains a custom Convolutional Neural Network (CNN) engineered from scratch to detect pneumonia from medical chest X-ray imagery. The primary objective of this project was to design a highly efficient model that prioritizes **Recall** (to minimize dangerous false negatives in a medical context) while operating under strict computational and time constraints ($\sim$30 minutes of training).

To validate the architecture, the custom model was benchmarked against a pre-trained VGG19 baseline under identical training time constraints. 

## Tech Stack
* **Language:** Python
* **Framework:** TensorFlow / Keras
* **Concepts:** Deep Learning, Convolutional Neural Networks, Callbacks, Loss Optimization

## Performance & Benchmarking
The custom CNN significantly outperformed the VGG19 baseline in both accuracy and computational efficiency when restricted to roughly 30 minutes of total training time. By epoch 5, the custom model achieved a validation accuracy of **87.66%**, while drastically reducing the epoch training time by ~90%.

| Metric | Custom CNN (5th Epoch) | VGG19 Baseline (1st Epoch) |
| :--- | :--- | :--- |
| **Training Accuracy** | 95.16% | 90.27% |
| **Validation Accuracy** | 87.66% | 68.75% |
| **Training Loss** | 0.1379 | 0.2509 |
| **Validation Loss** | 0.3055 | 0.4479 |
| **Training Time / Epoch** | ~170 Seconds | ~1700 Seconds |
| **Primary Metric (Recall)** | High (Prioritized) | Low (Initial Pass) |

## Key Features
* **Custom Architecture:** Built from scratch to optimize feature extraction for X-ray imagery without the overhead of massive pre-trained networks.
* **Overfitting Prevention:** Utilized custom callbacks and loss function tuning to maintain strong validation performance.
* **High Efficiency:** Proved that a targeted, lightweight architecture can outperform heavy generalized models (like VGG19) when computational resources and training times are highly constrained.
