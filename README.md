# Lightweight-U-Net-for-Multi-class-Aerial-Segmentation

## Project Overview
This repository contains a **patch-based semantic segmentation** project using a **lightweight U-Net** model for aerial images.  
The model segments images into multiple classes such as **buildings, roads, vegetation, water, land, and unlabeled areas**, enabling pixel-level analysis for remote sensing applications.

---

## Dataset
- **Dataset Name**: `semantic-segmentation-of-aerial-imagery` (Kaggle dataset)  
- **Number of Images**: ~180 images (patches are extracted for training efficiency)  
- **Classes**:
  - `0 → Building`
  - `1 → Land`
  - `2 → Road`
  - `3 → Vegetation`
  - `4 → Water`
  - `5 → Unlabeled`  

> **Note**: Patches are created to improve training speed and memory efficiency. Default patch size is 256×256 pixels.

---

## Workflow
1. **Data Preparation**
   - Split images and masks into patches.  
   - Convert RGB masks to integer labels (0–5).  
   - One-hot encode masks for multi-class segmentation.  

2. **Model Architecture**
   - Lightweight **U-Net** with reduced filters (32-64-128-256-512).  
   - Encoder-decoder architecture with skip connections.  
   - Softmax output layer for multi-class segmentation.

3. **Training**
   - Optimizer: Adam  
   - Loss: Categorical Cross-Entropy  
   - Batch size: 32  
   - Epochs: 50 (adjustable based on dataset and GPU)  

4. **Evaluation**
   - Training and validation loss/accuracy curves.  
   - Visual comparison of predicted masks vs. ground truth masks.

---

## Results
- Successfully segmented buildings, roads, vegetation, water, land, and unlabeled regions.  
- Training and validation curves show model convergence.  
- Sample predictions visualize the model's segmentation performance.

---

## Requirements
```bash
pip install tensorflow matplotlib scikit-learn opencv-python
