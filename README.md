# Perception
# Computer Vision Projects 🚀

This repository contains implementations of five computer vision problems involving object tracking, edge detection, image stitching, camera calibration, and stereo depth estimation using OpenCV and NumPy. Each task demonstrates hands-on understanding of core vision techniques, designed without using high-level abstraction functions for key computations.

---

## 📌 Object Tracking

### 🎯 Goal:
Track a black object thrown in a video and fit its trajectory using standard least squares to obtain a parabolic motion curve.

### ✅ Pipeline:
- Extract frames from video using OpenCV.
- Isolate the moving object based on color thresholding.
- Compute object centroid in each frame using NumPy (no built-in centroid function).
- Fit a parabola to the motion path using least squares.
- Predict Y-coordinate when X=1000 using the fitted equation.
- Overlay the trajectory on a captured frame.

---

## 🧭 Edge Detection and Image Stitching

### Paper Edge Detection

#### 🎯 Goal:
Detect and highlight the four corners and edges of a paper in a video, while filtering out blurry frames.

### ✅ Pipeline:
- Blur detection using Variance of Laplacian (threshold < 150).
- Edge detection using Canny.
- Line detection via Hough Transform and filtering short lines.
- Intersection points as putative corners.
- Corner refinement using Harris Corner Detection.
- Final overlay of 4 corner points (red) and 4 boundary edges (blue).

---

### Image Stitching (Panorama)

#### 🎯 Goal:
Stitch four overlapping images of a distant building into a single panorama.

### ✅ Pipeline:
- Feature extraction using SIFT/ORB.
- Feature matching with RANSAC-based filtering.
- Homography estimation between consecutive pairs.
- Warping and blending images to form a panoramic view.
- Visualize and justify feature selection and matching quality.

---

## 🎥 Cam Calibration and Depth Estimate

### Single Camera Calibration

#### 🎯 Goal:
Calibrate a camera using a chessboard/circular pattern and visualize the reprojection errors and results.

### ✅ Pipeline:
- Capture and load 50 custom calibration images.
- Use OpenCV functions for corner detection and calibration.
- Plot reprojection error per image.
- Visual comparison of original and undistorted images.
- Overlay original and reprojected corners with distinct colors.

---

### Stereo Depth Estimation

#### 🎯 Goal:
Use stereo image pairs and calibration data to compute depth maps.

### ✅ Pipeline:
- Match features using ORB/SIFT and estimate Fundamental and Essential matrices.
- Decompose Essential matrix to extract rotation (R) and translation (T).
- Stereo rectification using homographies (H1, H2).
- Epipolar geometry visualization.
- Disparity map computation and conversion to depth image.
- Save both grayscale and color (heatmap) disparity/depth images.

---


