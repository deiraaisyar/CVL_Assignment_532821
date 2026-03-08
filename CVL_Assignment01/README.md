# CVL Assignment 01: Image Enhancement

**Name:** Deira Aisya Refani  
**NIM:** 24/532821/PA/22539  
**Class:** CS

## Overview

This assignment implements various image enhancement techniques in Python using OpenCV, NumPy, and Matplotlib. Each technique addresses different image problems through mathematical transformations and filters.

## Techniques Implemented

### 1. Laplacian Sharpening
Enhances blurred images by applying a Laplacian filter to detect edges and high-frequency details. The Laplacian output is added back to the original image with a scaling factor to restore sharpness.

### 2. Median Filtering
Removes salt-and-pepper noise from images by replacing each pixel with the median value of neighboring pixels. Effective at preserving edges while eliminating noise.

### 3. Histogram Equalization
Improves contrast in dark images by redistributing pixel intensities across the full range. Computed using a cumulative distribution function to spread intensity values evenly.

### 4. Gamma Correction
Adjusts brightness in overly bright images using a nonlinear transformation. Higher gamma values compress bright intensities, reducing excessive brightness.

### 5. Image Negative
Reverses pixel intensities to enhance visibility of bright details on dark backgrounds. Useful for highlighting details not clearly visible in the original image.

### 6. Piecewise-Linear Transformation
Stretches contrast in low-contrast images by dividing the intensity range into segments with different linear mappings. Improves detail visibility while controlling brightness.

### 7. Gaussian Filtering
Smooths overly sharp images by applying weighted averaging of neighboring pixels. Reduces harsh edges and high-frequency noise for a more natural appearance.

## Libraries Used

- **OpenCV (cv2):** Image processing operations
- **NumPy:** Numerical computations and array manipulation
- **Matplotlib:** Image visualization and histogram display

