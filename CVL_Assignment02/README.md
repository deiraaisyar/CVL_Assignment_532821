# CVL Assignment 02: Object Detection

**Name:** Deira Aisya Refani  
**NIM:** 24/532821/PA/22539  
**Class:** CS

## Overview

This assignment implements a pedestrian detection system from scratch using the Penn-Fudan Pedestrian Database. The pipeline follows a classical object detection approach using HOG features, SVM classification, and sliding window search without relying on high-level detection libraries. The complete implementation is available in `CVL_Assignment02.ipynb`.

## Techniques Implemented

### 1. Dataset Parsing
Processes the Penn-Fudan dataset by extracting bounding box coordinates from plain-text annotation files using regular expressions. The data is partitioned into training and testing sets to evaluate model performance of unseen images.

### 2. HOG Feature Extraction
Manually implements Histogram of Oriented Gradients (HOG) to capture the local gradient structure and silhouettes of pedestrians. This involves gradient computation, cell-based orientation histogramming, and block normalization.

### 3. SVM Classification
Trains a Linear Support Vector Machine (SVM) classifier to distinguish between positive patches (pedestrians) and negative patches (background). Features are standardized using a scalar transformation for optimal classifier performance.

### 4. Sliding Window Search
Implements a multi-scale sliding window search to scan test images. The classifier evaluates each window to determine the presence of a pedestrian, generating initial detection candidates.

### 5. Non-Maximum Suppression (NMS)
An essential post-processing step to filter redundant and overlapping bounding boxes. It ensures that each pedestrian is represented by a single, most confident detection based on overlap thresholds.

### 6. Performance Evaluation
Computes quantitative metrics to assess the detection accuracy. This includes calculating Intersection over Union (IoU) for bounding box overlap, as well as Precision, Recall, and Accuracy.

## Accuracy and IoU Analysis

The following analysis is based on the inference results obtained from the test images:

### 1. Detection Accuracy
The model achieved a perfect accuracy of 1.000 (100%) across most test images (Images 1, 2, 3, and 5). This indicates that every ground-truth pedestrian was successfully covered by at least one prediction candidate. However, Image 4 presented an outlier with an accuracy of 0.667, where the model failed to detect one out of the three pedestrians present.

### 2. IoU (Intersection over Union)
While detection accuracy was high, the quality of the bounding box fit (IoU) ranged between 0.459 and 0.586. Since an IoU of 0.5 is the typical threshold for a successful detection, these scores are considered mediocre. The analysis reveals that predicted boxes are often slightly shifted, too large, or too small compared to the ground truth, highlighting the limitations of the fixed-scale sliding window and manual HOG approach in achieving precise localization.

## Libraries Used

- **OpenCV (cv2):** Image loading, resizing, and drawing detections
- **NumPy:** Numerical computations and HOG feature vector manipulation
- **Matplotlib:** Visualization of datasets, HOG features, and final detection results
- **Scikit-learn (sklearn):** Linear SVM implementation and performance metrics
- **Tqdm:** Progress bars for monitoring dataset processing and sliding window loops