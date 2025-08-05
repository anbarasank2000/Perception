# Perception Foundations

This repository contains implementations of five computer vision problems involving object tracking, edge detection, image stitching, camera calibration, and stereo depth estimation using OpenCV and NumPy. Each task demonstrates hands-on understanding of core vision techniques, designed without using high-level abstraction functions for key computations.

---

## 📌 Object Tracking
<p align="center">
  <img src="https://github.com/anbarasank2000/Perception/blob/main/Object%20Tracking/Object_tracking-ezgif.com-video-to-gif-converter.gif" width="45%" />
  <img src="https://github.com/anbarasank2000/Perception/blob/main/Object%20Tracking/download.png" width="45%" />
</p>
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
<p align="center">
  <img src="https://github.com/anbarasank2000/Perception/blob/main/Edge%20Detection%20and%20Image%20Stitching/output_video3-ezgif.com-crop.gif" width="70%" />
</p>

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
<p align="center">
  <img src="https://github.com/anbarasank2000/Perception/blob/main/Edge%20Detection%20and%20Image%20Stitching/Stich%20out.png" width="70%" />
</p>

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
<p align="center">
  <img src="https://github.com/anbarasank2000/Perception/blob/main/Cam%20Calibration%20and%20Depth%20Estimate/download.png" width="45%" />
  <img src="https://github.com/anbarasank2000/Perception/blob/main/Cam%20Calibration%20and%20Depth%20Estimate/download%20(1).png" width="45%" />
</p>
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
<p align="center">
  <img src="https://github.com/anbarasank2000/Perception/blob/main/Cam%20Calibration%20and%20Depth%20Estimate/Depth%20Map.png" width="70%" />
</p>
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


