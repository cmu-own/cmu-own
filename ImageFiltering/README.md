# 🖼️ Image Filtering Tutorial

Welcome to the **Image Filtering** tutorial repository! This directory contains Jupyter Notebook implementations and step-by-step visual experiments for fundamental Image Processing and Computer Vision filtering techniques.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/cmu-own/cmu-own/blob/main/ImageFiltering/image_filtering.ipynb)

---

## 📌 Overview

Image filtering is a core spatial-domain technique in computer vision used for image enhancement, noise reduction, edge detection, and feature extraction. This tutorial demonstrates key OpenCV and NumPy filtering algorithms using Python.

---

## 📂 Project Structure

```
ImageFiltering/
├── image_filtering.ipynb   # Complete step-by-step tutorial notebook with code & visuals
└── README.md               # Project documentation
```

---

## 🚀 Topics Covered in the Tutorial

1. **Synthetic Sample Generation:** Creating geometric shapes & text with OpenCV.
2. **Smoothing & Blurring Filters (Linear Filtering):**
   - Box Filter (`cv2.blur`)
   - Gaussian Blur (`cv2.GaussianBlur`)
3. **Noise Reduction (Non-Linear Filtering):**
   - Salt & Pepper Noise generation
   - Median Filter (`cv2.medianBlur`)
   - Bilateral Filter (`cv2.bilateralFilter`)
4. **Edge Detection & Gradient Filters:**
   - Sobel Filter (X & Y gradients)
   - Laplacian Filter
   - Canny Edge Detection (`cv2.Canny`)
5. **Custom Kernel Convolution:**
   - Image Sharpening using `cv2.filter2D()`

---

## 🛠️ Prerequisites & Installation

To run the notebook locally, install the required packages:

```bash
pip install numpy opencv-python matplotlib jupyter
```

---

## 💻 How to Run

### Option 1: Run Online in Google Colab 🚀
Click the badge above or use this link:  
[Open image_filtering.ipynb in Google Colab](https://colab.research.google.com/github/cmu-own/cmu-own/blob/main/ImageFiltering/image_filtering.ipynb)

### Option 2: Run Locally
1. Clone the repository:
   ```bash
   git clone https://github.com/cmu-own/cmu-own.git
   ```
2. Navigate to the `ImageFiltering` directory:
   ```bash
   cd cmu-own/ImageFiltering
   ```
3. Launch Jupyter Notebook:
   ```bash
   jupyter notebook image_filtering.ipynb
   ```

---

## 📝 License

This project is open-source and created for educational purposes.
