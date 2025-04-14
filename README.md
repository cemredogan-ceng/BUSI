#  BUSI – Breast Ultrasound Image Segmentation Using Deep Learning

This project aims to detect and segment tumor regions in breast ultrasound images using various deep learning models. By utilizing the BUSI dataset and multiple CNN architectures, the goal is to improve breast cancer diagnosis through medical image segmentation.

---

# Project Summary

We implemented several CNN-based encoder-decoder segmentation architectures, including ResNet, UNet, AlexNet, GoogleNet, InceptionV3, and a hybrid CNN-RNN model. Each model was evaluated in terms of segmentation performance using standard metrics such as F1 Score and IoU (Jaccard Index).

---

# Dataset: BUSI

- **Name:** Breast Ultrasound Images Dataset (BUSI)
- **Source:** Mendeley Data
- **Classes:**
  - Benign: 437 images
  - Malignant: 210 images
  - Normal: 133 images
- **Includes:** Segmentation masks for each image
- **Challenges:** Class imbalance, noise in ultrasound images

---

## Applied Models

### CNN-RNN (ResNet34 + LSTM)
- Encoder: ResNet34
- Context modeling with RNN (LSTM)
- Output: Tumor segmentation masks
- Loss: Binary Cross-Entropy
- Accuracy: 94.99%, F1 Score: 71.08%, IoU: 55.13%

---

### AlexNet
- Pretrained encoder
- Custom decoder for segmentation
- Loss: Focal Loss
- Accuracy: 95.11%, F1 Score: 65.70%, IoU: 48.92%

---

### ResNet50
- Best overall performer
- Accuracy: 95.74%, F1 Score: 72.33%, IoU: 56.65%

---

### GoogleNet
- Lightweight encoder with segmentation head
- Accuracy: 94.34%, F1 Score: 66.76%, IoU: 50.11%

---

### InceptionV3
- High feature extraction capability
- Accuracy: 95.33%, F1 Score: 71.45%, IoU: 55.58%

---

### UNet (with ResNet34 encoder)
- Combined BCE + Dice loss
- Best balance between precision and recall
- Accuracy: 95.89%, F1 Score: 75.82%, IoU: 61.06%

---

## Model Comparison

| Model      | Accuracy | F1 Score | IoU     |
|------------|----------|----------|---------|
| **UNet**       | 95.89%   | **75.82%** | **61.06%** |
| ResNet50   | 95.74%   | 72.33%   | 56.65% |
| InceptionV3| 95.33%   | 71.45%   | 55.58% |
| CNN-RNN    | 94.99%   | 71.08%   | 55.13% |
| GoogleNet  | 94.34%   | 66.76%   | 50.11% |
| AlexNet    | 95.11%   | 65.70%   | 48.92% |

---

## Implementation Details

- Image resizing: 256x256 (or 299x299 for Inception)
- Data split: 70% train, 15% validation, 15% test
- Data Augmentation: horizontal flip, contrast adjustment, rotation
- Optimizer: Adam
- Epochs: 20
- Losses: Binary Cross Entropy, BCEWithLogitsLoss, Focal Loss, Dice Loss

---

## Tools & Libraries

- Python, PyTorch  
- torchvision, albumentations  
- matplotlib, pandas, numpy  
- Jupyter Notebook / Google Colab  

---

##  Future Improvements

- Integrate attention-based mechanisms (e.g., Attention UNet)  
- Train models with Dice + IoU combined loss  
- Apply post-processing to enhance mask quality  
- Deploy best model as a web application for clinical use  

---

## Authors

- Developed by Cemre Doğan and Buket Uğurlu


---

> “This project showcases deep learning’s potential to support early and accurate diagnosis of breast cancer using ultrasound imaging.”

