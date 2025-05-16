# Heatmap_Badminton

# 🏸 Badminton Player Heatmap from Video

## 📌 Objective
This project aims to identify the location of badminton players in a video and generate a **heatmap of their foot positions** over a 10-minute match. Due to the common angled position of cameras, a **homography transformation** is applied to accurately map foot coordinates to real-world positions on the court.

## 👥 Team Members
- Student 1 - Pham Ngoc Hieu - 2430904
- Student 2 - Nguyen Nhat Phap - 2430911

## 🔍 Methodology

### 1. Person Detection using CNN (Fast-RCNN)
- A custom Convolutional Neural Network (CNN) was trained on the [INRIA Person Dataset]. (https://www.kaggle.com/datasets/jcoral02/inriaperson)
- The model detects the player and outputs bounding boxes per frame.

### 2. Pose Estimation using MediaPipe
- We use **Google MediaPipe Pose** to extract body landmarks.
- Landmarks 29 and 30 (left and right heel) are used to locate foot positions.

### 3. Homography Transformation
- Court boundary lines are detected via **Hough Transform** or manually selected.
- A homography matrix is computed to map foot coordinates from image space to a top-down court view.
- This transformation improves positional accuracy despite angled camera views.

### 4. Heatmap Generation
- Foot positions are collected from each video frame over ~10 minutes.
- A heatmap is generated using `matplotlib` or `seaborn` to visualize activity concentration on the court.


