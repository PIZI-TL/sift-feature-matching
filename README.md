# Feature Matching and Object Localization using SIFT

This repository demonstrates a classic, robust computer vision pipeline for **Feature Matching** and **Object Localization** using the **SIFT (Scale-Invariant Feature Transform)** algorithm and **FLANN-based** feature matching. 

Unlike modern deep learning approaches, this method relies on local invariant features, making it highly efficient and mathematically interpretable for identifying specific objects (such as a unique banknote, a logo, or a book cover) within complex or cluttered scenes.

## 📌 Project Overview
The pipeline executes the following computer vision operations:
1. **Keypoint Extraction:** Uses SIFT to identify scale and rotation-invariant keypoints and descriptors in both the target object image and the scene image.
2. **Fast Feature Matching:** Utilizes **FLANN (Fast Library for Approximate Nearest Neighbors)** with KD-Tree indexing to perform accelerated $k$-NN matching ($k=2$).
3. **Ambiguity Filtering:** Applies **Lowe's Ratio Test** (threshold set to `0.7`) to eliminate weak and ambiguous cross-matches.
4. **Geometric Verification (Homography):** Computes a perspective transformation matrix using **RANSAC** to separate valid geometric inliers from background noise.
5. **Bounding Box Drawing:** Dynamically projects the target object's boundaries onto the scene using perspective transformation (`cv2.perspectiveTransform`).

## 🛠️ Tech Stack & Requirements
The codebase is written in Python 3 and depends on the following libraries:
- **OpenCV (`opencv-python`):** For SIFT implementation, FLANN matching, and image drawing tools.
- **NumPy:** For advanced matrix operations, coordinate reshaping, and data type casting.
- **Matplotlib:** For rendering and visualizing the final subplots of side-by-side matches.

