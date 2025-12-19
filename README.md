Pill Instance Segmentation 

Course: CSE438 (Digital Image Processing)

Semester: Fall 2025 | Section: 3

This repository contains our semester project for CSE438. Our work focuses on the Instance Segmentation of individual pills from a Roboflow dataset. We investigate the performance of state-of-the-art YOLO models and evaluate how semi-supervised methods—Standard Pseudo-Labeling, MixMatch, and FixMatch—can improve segmentation accuracy when labeled data is limited.

Team Members

Name

Student and ID

Nafisa Saiyara Aranti

2022-1-60-060

Sumaiya Tabassum

2022-1-60-168

Nishat Lubna

2020-2-60-053

S M Sazzad Hossain

2022-1-60-136


Project Objective: Instance Segmentation

The goal of this project is to precisely isolate and segment each pill instance in an image. Unlike standard detection, which only provides bounding boxes, our approach generates pixel-level masks for every pill.
Pixel-Level Accuracy: Defining the exact boundary of each pill to handle overlaps and clusters.
Label Efficiency: Implementing semi-supervised learning to leverage unlabeled data, reducing the reliance on manual pixel-wise annotations.
Model Implementations


1. Baseline Models (Supervised)
2. 
We established our initial performance metrics using three generations of segmentation-specific YOLO models:

YOLOv8-seg
YOLOv11-seg
YOLOv12-seg

4. Semi-Supervised Learning (SSL) Frameworks
5. 
To enhance the segmentation masks using unlabeled data, we implemented:
Standard Pseudo-Labeling: An iterative approach where the model generates masks for unlabeled images, which are then added to the training set as ground truth for the next round.
MixMatch: A method that blends unlabeled samples with labeled ones using MixUp and ensures the model produces low-entropy (confident) predictions across different image views.
FixMatch: A consistency-based framework where the model is trained to predict the same mask for a "weakly augmented" version of a pill image and a "strongly augmented" version, using the weak prediction as a reliable target.


Repository Structure

├── segment_baselines/  # Configurations for YOLOv8, v11, and v12-seg

├── ssl_implementations/# Modules for Pseudo-labeling, MixMatch, and FixMatch

├── data/               # Scripts for loading the Roboflow pill dataset

├── results/            # Comparison of segmentation masks and mAP scores

└── README.md           # Project documentation

Requirements

Python 3.9+

Ultralytics (for YOLO segmentation backbones)
OpenCV (for image processing and mask visualization)
Roboflow SDK (for dataset management)

