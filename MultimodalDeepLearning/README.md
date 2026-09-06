# 🧠 Multimodal Deep Learning Tutorial: Vision, Language & Multi-Fusion Architectures

Welcome to the **Multimodal Deep Learning** tutorial! This repository provides an end-to-end, beginner-friendly yet highly comprehensive guide to understanding, building, and training **Multimodal Neural Networks** in **PyTorch**.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/cmu-own/cmu-own/blob/main/MultimodalDeepLearning/multimodal_deep_learning.ipynb)

---

## 📖 Table of Contents
1. [What is Multimodal Deep Learning?](#-what-is-multimodal-deep-learning)
2. [Why Use Multimodal AI? (Real-World Analogies)](#-why-use-multimodal-ai-real-world-analogies)
3. [The 3 Core Fusion Strategies](#-the-3-core-fusion-strategies)
   - [1. Early Fusion (Feature-Level Integration)](#1-early-fusion-feature-level-integration)
   - [2. Late Fusion (Decision/Latent-Level Integration)](#2-late-fusion-decisionlatent-level-integration)
   - [3. Cross-Attention Fusion (Intermediate Transformer-Based Integration)](#3-cross-attention-fusion-intermediate-transformer-based-integration)
4. [Modern Real-World Multimodal Architectures](#-modern-real-world-multimodal-architectures)
5. [Quickstart PyTorch Code (5 Lines)](#-quickstart-pytorch-code-5-lines)
6. [Project Repository Structure](#-project-repository-structure)
7. [How to Run the Jupyter Notebook](#-how-to-run-the-jupyter-notebook)
8. [License & Citation](#-license--citation)

---

## 💡 What is Multimodal Deep Learning?

In traditional Machine Learning, models process a single data modality (unimodal)—such as predicting stock prices from numerical tables, classifying images using Convolutional Neural Networks (CNNs), or translating text using Transformers.

**Multimodal Deep Learning** processes and integrates information from **two or more distinct data modalities** (e.g., Vision + Language + Audio) within a unified neural network architecture to perform complex reasoning.

```
       ┌────────────────────────┐
       │   Image / Vision Stream │ ───┐
       └────────────────────────┘    │
                                     ├───►  [ Feature Fusion Layer ]  ───►  Unified Prediction / Action
       ┌────────────────────────┐    │
       │   Text / Language Stream│ ───┘
       └────────────────────────┘
```

---

## 🌟 Why Use Multimodal AI? (Real-World Analogies)

### 🧑‍⚕️ Medical Diagnosis Analogy
- **Single Modality (Unimodal):** A doctor looks ONLY at an X-ray image.
- **Multimodal:** A doctor looks at the **X-ray image** AND reads the patient's **medical history text report** AND checks **blood test values**. Combining these streams leads to far more accurate diagnoses.

### 🚗 Autonomous Vehicles
Self-driving cars combine:
- 📷 **Vision (Cameras):** Detecting traffic lights and pedestrians.
- 📡 **LiDAR / Radar (Point Clouds):** Measuring exact 3D distances.
- 🗺️ **GPS / Map Data (Text/Metadata):** Navigation and routing.

---

## 🔀 The 3 Core Fusion Strategies

Combining different data streams can happen at different stages of a neural network:

```
──────────────────────────────────────────────────────────────────────────────────────────
Strategy                  Where Fusion Happens?           Pros                     Cons
──────────────────────────────────────────────────────────────────────────────────────────
1. Early Fusion           At the raw input level          Simple, captures early   Prone to modality 
                          (Concatenation of raw features) cross-modal interactions imbalance & noise

2. Late Fusion            At the final latent vector level High modularity, each   Misses low-level
                          (Concatenation after encoders)  encoder specialized     cross-modal features

3. Cross-Attention Fusion At intermediate transformer     Dynamic alignment,      Higher compute cost
                          layers via attention queries    state-of-the-art accuracy
──────────────────────────────────────────────────────────────────────────────────────────
```

### 1. Early Fusion (Feature-Level Integration)
Raw feature vectors from all modalities are concatenated directly at the input stage and passed into a single deep neural network.

$$\mathbf{x}_{\text{fused}} = [\mathbf{x}_{\text{img}} \,||\, \mathbf{x}_{\text{text}}]$$

### 2. Late Fusion (Decision/Latent-Level Integration)
Each modality is processed by its own specialized sub-network encoder (e.g., ResNet for images, BERT for text). The resulting bottleneck feature embeddings are concatenated into a joint latent vector for classification:

$$\mathbf{z}_{\text{img}} = f_{\text{vision}}(\mathbf{x}_{\text{img}}), \quad \mathbf{z}_{\text{text}} = f_{\text{language}}(\mathbf{x}_{\text{text}})$$
$$\mathbf{z}_{\text{fused}} = [\mathbf{z}_{\text{img}} \,||\, \mathbf{z}_{\text{text}}]$$
$$\text{Output} = g_{\text{classifier}}(\mathbf{z}_{\text{fused}})$$

### 3. Cross-Attention Fusion (Intermediate Transformer-Based Integration)
Cross-Attention allows one modality to "query" key information from another modality using Multihead Attention (`nn.MultiheadAttention`):

$$\text{Attention}(Q, K, V) = \text{softmax}\left(\frac{Q K^T}{\sqrt{d_k}}\right) V$$
where Query ($Q$) comes from Language Embeddings, and Key ($K$) & Value ($V$) come from Vision Embeddings.

---

## 🤖 Modern Real-World Multimodal Architectures

1. **CLIP (Contrastive Language-Image Pretraining by OpenAI):**
   - Learns joint representations by aligning image and text embeddings in a shared metric space using contrastive loss ($N \times N$ cosine similarities).
2. **BLIP / BLIP-2 (Salesforce):**
   - Uses a Q-Former (Query Transformer) to bridge frozen Vision Encoders (ViT) with frozen Large Language Models (LLMs like Vicuna / Fl T5).
3. **Flamingo (DeepMind):**
   - Interleaves cross-attention layers into pre-trained LLMs to handle arbitrary sequences of images, videos, and text.
4. **Gemini / GPT-4V:**
   - Native multimodal foundation models trained natively across text, image, audio, and video inputs.

---

## 🚀 Quickstart PyTorch Code (5 Lines)

Here is how multimodal late fusion works in PyTorch in 5 simple lines:

```python
import torch

# Simulated modality feature representations (Batch size = 1)
image_features = torch.randn(1, 64)    # 64-dim Vision vector
text_features = torch.randn(1, 128)    # 128-dim Language vector

# Fuse modalities along feature dimension (dim=1)
fused_vector = torch.cat((image_features, text_features), dim=1)  # Shape: [1, 192]
print(f"Fused Vector Shape: {fused_vector.shape}")
```

---

## 📂 Project Repository Structure

```
MultimodalDeepLearning/
├── multimodal_deep_learning.ipynb   # Comprehensive step-by-step PyTorch Jupyter Notebook
└── README.md                        # Master guide documentation & theoretical foundations
```

---

## 💻 How to Run the Jupyter Notebook

### Option 1: Run Online in Google Colab 🚀
Click the badge at the top of this document or use this direct link:  
👉 [Open multimodal_deep_learning.ipynb in Google Colab](https://colab.research.google.com/github/cmu-own/cmu-own/blob/main/MultimodalDeepLearning/multimodal_deep_learning.ipynb)

### Option 2: Run Locally
1. Clone the repository:
   ```bash
   git clone https://github.com/cmu-own/cmu-own.git
   ```
2. Navigate to the `MultimodalDeepLearning` directory:
   ```bash
   cd cmu-own/MultimodalDeepLearning
   ```
3. Install dependencies:
   ```bash
   pip install torch numpy matplotlib jupyter
   ```
4. Launch Jupyter Notebook:
   ```bash
   jupyter notebook multimodal_deep_learning.ipynb
   ```

---

## 📝 License & Citation

This project is open-source and created under the MIT License for educational purposes. Feel free to use, modify, and build upon this code for research and learning!
