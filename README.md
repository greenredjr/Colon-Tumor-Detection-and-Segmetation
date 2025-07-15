🧬 Colon Tumor Detection and Segmentation using YOLOv8 + U-Net with Attention

📌 Overview

This project implements a two-stage deep learning pipeline for early detection and segmentation of colorectal tumors in colonoscopy images. It integrates YOLOv8 for object detection and a modified U-Net for attention-guided semantic segmentation.

The key goal is accurate pixel-wise segmentation of tumor regions, enhanced using:

Attention masks generated from YOLO detections

A custom weighted BCE loss function focusing on tumor regions



---

🧠 Model Pipeline

Colonoscopy Image
        ↓
YOLOv8 Detector → Bounding Boxes → Attention Mask
        ↓
Modified U-Net (RGB + Attention Input)
        ↓
Tumor Segmentation Mask


---

🚀 Features

✅ Real-time tumor localization using YOLOv8

✅ Attention-guided segmentation with modified U-Net

✅ Weighted BCE Loss to emphasize tumor pixels

✅ Extensive data augmentation using Albumentations

✅ Evaluated on Dice, IoU, Precision, Recall, Accuracy



---

🗂️ Dataset Structure

Balanced_Dataset/
├── WLI/
│   ├── images/
│   └── masks/
├── LCI/
│   └── ...
├── NBI/
│   └── ...
...

All images and binary masks are resized to 256×256.


---

⚙️ Requirements

Python ≥ 3.8

PyTorch

OpenCV

Albumentations

NumPy, Pandas

Ultralytics (for YOLOv8)


Install dependencies:


🛠️ How to Run

1. Train YOLOv8 Detector (optional if pre-trained weights are used)


2. Generate Attention Masks from YOLO Predictions


3. Train Modified U-Net with Attention Masks + Weighted BCE Loss


4. Evaluate Segmentation Performance:


---

📊 Sample Results

Metric	Value

Dice Score	0.7550
IoU	0.6900
Precision	0.7529
Recall	0.7882
Accuracy	0.9689



---

🧪 Innovations Introduced

YOLO-guided attention masks used as input to U-Net

Weighted BCE loss focusing on tumor regions based on attention intensity

Improved segmentation performance in complex and small tumor cases
