# 🖼️ Image Filtering & Spatial Domain Processing Tutorial

Welcome to the **Image Filtering & Spatial Domain Processing** tutorial repository! This repository is designed as a practical, hands-on guide for computer vision enthusiasts, students, and developers interested in mastering fundamental digital image processing techniques.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/cmu-own/cmu-own/blob/main/ImageFiltering/image_filtering.ipynb)

---

## 📌 Comprehensive Overview

Image filtering is one of the most critical foundational building blocks in Computer Vision and Digital Image Processing. It acts as an indispensable pre-processing step for advanced tasks such as object recognition, image segmentation, feature extraction, autonomous driving perception, and medical image analysis.

In spatial domain filtering, pixel values are directly manipulated based on their local neighborhood using mathematical 2D matrices known as **Kernels** or **Convolution Filters**. Through convolution, we can perform diverse tasks:

- 🧹 **Denoising & Smoothing:** Eliminating camera sensor grain, salt-and-pepper noise, and high-frequency disturbances.
- 📐 **Edge & Feature Detection:** Identifying object boundaries, structural lines, and sharp intensity transitions.
- 🔍 **Image Enhancement & Sharpening:** Accentuation of fine details and high-contrast features for improved clarity.

This repository provides a self-contained, interactive Jupyter Notebook (`image_filtering.ipynb`) packed with executable Python code leveraging industry-standard libraries: **OpenCV**, **NumPy**, and **Matplotlib**.

---

## 📂 Project Structure

```
ImageFiltering/
├── image_filtering.ipynb   # Complete step-by-step tutorial notebook with code & visual outputs
└── README.md               # Detailed project documentation & guide
```

---

## 🚀 Topics Covered in the Tutorial

1. **Synthetic Image Generation:**
   - Programmatically constructing test targets with geometric shapes, gradients, and text overlays using OpenCV without external asset dependencies.

2. **Smoothing & Blurring Filters (Linear Filtering):**
   - **Box Filter (Averaging):** Equal weighting kernel for general smoothing.
   - **Gaussian Blur:** Weighted Gaussian distribution kernel for natural detail smoothing.

3. **Noise Reduction (Non-Linear Filtering):**
   - **Salt & Pepper Noise Simulation:** Synthetic creation of random impulse noise.
   - **Median Filter:** Non-linear sorting filter that eliminates extreme noise outliers while preserving boundary shapes.
   - **Bilateral Filter:** Edge-preserving smoothing filter considering both spatial distance and pixel color similarity.

4. **Edge Detection & Gradient Operators:**
   - **Sobel Operator:** Computing first-order image intensity derivatives along X and Y axes.
   - **Laplacian Filter:** Second-order derivative filter for isotropic edge response.
   - **Canny Edge Detector:** Multi-stage optimal edge detection algorithm incorporating hysteresis thresholding.

5. **Custom 2D Convolution & Sharpening:**
   - Building custom transformation matrices and applying them using `cv2.filter2D()`.

---

## 🛠️ Prerequisites & Installation

To run this tutorial on your local machine, ensure Python 3.8+ is installed along with the required libraries:

```bash
pip install numpy opencv-python matplotlib jupyter
```

---

## 💻 How to Run

### Option 1: Run Online in Google Colab 🚀
Launch the notebook directly in your browser without installing anything locally:  
👉 [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/cmu-own/cmu-own/blob/main/ImageFiltering/image_filtering.ipynb)

### Option 2: Run Locally
1. Clone the repository:
   ```bash
   git clone https://github.com/cmu-own/cmu-own.git
   ```
2. Navigate to the `ImageFiltering` directory:
   ```bash
   cd cmu-own/ImageFiltering
   ```
3. Open the notebook in Jupyter:
   ```bash
   jupyter notebook image_filtering.ipynb
   ```

---

## 🤝 Contributing & Usage

Feel free to fork this repository, experiment with different kernel parameters, and use these code snippets in your computer vision assignments, projects, or research!

---

## 📝 License

This project is open-source and released under the MIT License for educational and tutorial purposes.
