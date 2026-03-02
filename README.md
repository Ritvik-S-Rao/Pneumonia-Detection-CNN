## Performance & Benchmarking

The custom CNN significantly outperformed the VGG19 baseline in both accuracy and computational efficiency when restricted to roughly 30 minutes of total training time. 

By epoch 5, the custom model achieved superior validation accuracy while drastically reducing the epoch training time by 90%. Most importantly for medical diagnostics, the custom model achieved a **0.94 Recall for Pneumonia**, effectively minimizing dangerous false negatives compared to the heavier baseline model.

### Training Metrics & Efficiency
| Metric | Custom CNN (5th Epoch) | VGG19 Baseline (1st Epoch) |
| :--- | :--- | :--- |
| **Training Accuracy** | 95.16% | 90.27% |
| **Validation Accuracy** | 87.66% | 68.75% |
| **Training Loss** | 0.1379 | 0.2509 |
| **Validation Loss** | 0.3055 | 0.4479 |
| **Training Time / Epoch** | ~170 Seconds | ~1700 Seconds |

### Classification Report (Test Data)
| Metric | Custom CNN (5th Epoch) | VGG19 Baseline (1st Epoch) |
| :--- | :--- | :--- |
| **Overall Accuracy** | 0.88 | 0.86 |
| **Precision (Normal)** | 0.89 | 0.84 |
| **Recall (Normal)** | 0.77 | 0.79 |
| **F1-Score (Normal)** | 0.82 | 0.81 |
| **Precision (Pneumonia)** | 0.87 | 0.88 |
| **Recall (Pneumonia)** | **0.94** | 0.91 |
| **F1-Score (Pneumonia)** | 0.91 | 0.89 |

## Key Features
* **Custom Architecture:** Built from scratch to optimize feature extraction for X-ray imagery without the overhead of massive pre-trained networks.
* **Overfitting Prevention:** Utilized custom callbacks and loss function tuning to maintain strong validation performance.
* **Diagnostic Safety:** Explicitly optimized for high recall on the positive (Pneumonia) class to minimize false negatives.
* **High Efficiency:** Proved that a targeted, lightweight architecture can outperform heavy generalized models (like VGG19) when computational resources and training times are highly constrained.
