# 💎 Gemstone Image Classification using Deep Learning

> AI-powered computer vision system that classifies gemstone types from images using transfer learning, explainable AI, and a deployed Streamlit application.

---

# Business Problem / Motivation

Gemstone identification is important in jewelry retail, gemology labs, auctions, mining operations, and e-commerce platforms. Misidentifying gemstones can lead to pricing errors, fraud, customer dissatisfaction, and operational inefficiency.

This project builds an AI-powered image classification model capable of identifying gemstone types from uploaded images. The goal is to improve classification speed, consistency, and scalability.

---

# Project Overview

This project compares multiple transfer learning CNN architectures for multi-class gemstone image classification.

### Models Evaluated:
- MobileNetV2
- ResNet50
- DenseNet121
- ConvNeXtTiny --> Final Selected Model

The best-performing model was deployed in a Streamlit web application for real-time image predictions.

---

# Dataset

### Source:
Kaggle Gemstone Image Dataset  
https://www.kaggle.com/datasets/lsind18/gemstones-images/data

### Type:
Multi-class image dataset

### Size:
- 87 gemstone classes
- Training image folders
- Testing image folders

### Example Classes:
Ruby, Sapphire, Emerald, Citrine, Garnet Red, Amethyst, Tourmaline

---

# Data Preprocessing

The following preprocessing pipeline was applied:

- Image resizing
- Label encoding
- Train / Validation / Test split
- Pixel normalization
- Data augmentation:
  - Horizontal Flip
  - Rotation
  - Zoom
  - Contrast Adjustment

These steps helped improve model generalization and reduce overfitting.

---

# Exploratory Data Analysis

### Included Analysis:
- Class distribution
- Sample gemstone image review
- Image quality consistency checks
- Class imbalance inspection

### Key Findings:
- Some gemstone classes had fewer samples than others
- Several gemstones had similar colors and textures
- Augmentation was important for robustness

---

# Modeling Approach

## Baseline Model

### MobileNetV2
Used as a lightweight benchmark model with fast training speed.

## Advanced Models

- ResNet50
- DenseNet121
- ConvNeXtTiny

## Final Model Choice: ConvNeXtTiny

ConvNeXtTiny was selected because it delivered the strongest balance of:

- Accuracy
- Stability
- Generalization
- Modern feature extraction performance

---

# Model Training

### Tools Used

- Python
- TensorFlow / Keras
- Scikit-learn
- Google Colab
- Matplotlib
- Streamlit

### Hyperparameters

- Optimizer: Adam
- Learning Rate: 1e-4 / 1e-5 fine tuning
- Batch Size: 32
- EarlyStopping
- ReduceLROnPlateau

---

# Results

## Final ConvNeXtTiny Performance

| Metric | Score |
|--------|------|
| Accuracy | 70.8% |
| Balanced Accuracy | 70.7% |
| Macro F1 Score | 70.7% |
| Recall | 70.7% |

## Earlier Controlled Subset Performance

| Metric | Score |
|--------|------|
| Accuracy | 88.9% |

## Why These Metrics Matter

- **Accuracy:** Overall prediction correctness  
- **Balanced Accuracy:** Handles class imbalance fairly  
- **Macro F1:** Measures performance across all classes equally  

---

# Model Comparison

| Model | Summary |
|------|---------|
| MobileNetV2 | Strong baseline |
| ResNet50 | Good feature extraction |
| DenseNet121 | High-performing |
| ConvNeXtTiny | Best overall |

---

# Model Interpretation (Explainable AI)

Grad-CAM heatmaps were used to visualize what image regions influenced predictions.

### Insights:

- Model focused heavily on gemstone color regions
- Surface reflections impacted predictions
- Similar gemstones created confusion in some classes

---

# Key Insights

- Transfer learning significantly improved results
- Fine-tuning outperformed frozen backbones
- ConvNeXtTiny generalized best
- Certain gemstones remain visually difficult to separate

---

# Conclusion

This project successfully developed a real-world gemstone image classification system using deep learning. The final model demonstrates strong potential for practical use in jewelry, e-commerce, and gemology industries.

---

# Future Work

- Improve full 87-class accuracy
- Add Top-K predictions
- Confidence threshold filtering
- Increase dataset size
- Cloud deployment
- Mobile application version

---

# Streamlit App

Users can upload gemstone images and receive:

- Predicted gemstone class
- Confidence score
- Top-K predictions

*(Insert app screenshot here)*

---

# How to Run

```bash
git clone https://github.com/yourusername/gemstone-image-classification.git

cd gemstone-image-classification

pip install -r requirements.txt

streamlit run app.py
