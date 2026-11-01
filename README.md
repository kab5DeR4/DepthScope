# 🔭 DepthScope: Monocular Depth Estimation

A beginner-friendly computer vision experiment that predicts dense relative depth maps from a single 2D RGB photograph using the pretrained **Depth Anything V2 Small** model.

---

## 📌 Project Overview

- **Project Name:** DepthScope
- **Task:** Monocular Depth Estimation (MDE)
- **Model:** [`depth-anything/Depth-Anything-V2-Small-hf`](https://huggingface.co/depth-anything/Depth-Anything-V2-Small-hf)
- **Core Stack:** Python, PyTorch, Hugging Face Transformers, Pillow, NumPy, Matplotlib
- **Target Platform:** Google Colab (with CPU/GPU support)

DepthScope takes a single 2D photograph (JPG, JPEG, or PNG) and produces:
1. The original photograph with dimensions.
2. A normalized grayscale relative depth map.
3. A colourised relative depth map (Inferno colormap) with an informative colourbar.
4. An exported PNG depth map file ready to download.

---

## 🚀 Quickstart: Running in Google Colab

The easiest way to run DepthScope is via Google Colab with a free GPU:

1. **Open Google Colab:** Navigate to [colab.research.google.com](https://colab.research.google.com/).
2. **Upload Notebook:** Click **File** > **Upload notebook** and select `DepthScope.ipynb`.
3. **Enable GPU (Recommended):**
   - Click **Runtime** > **Change runtime type**.
   - Under **Hardware accelerator**, select **T4 GPU** (or standard CPU fallback).
   - Click **Save**.
4. **Run Cells Sequentially:**
   - Run cells from top to bottom (`Shift + Enter` or **Runtime** > **Run all**).
   - When you reach the **Image Upload** cell, click the **Choose Files** button to upload any JPG, JPEG, or PNG image from your computer.
   - Observe inference timing, view side-by-side visualizations, and download the resulting depth map PNG.

---

## 💻 Optional: Running Locally in Jupyter

If you wish to run DepthScope on your local machine:

1. **Clone or navigate to the directory:**
   ```bash
   cd depth
   ```

2. **Create and activate a virtual environment (optional but recommended):**
   ```bash
   python -m venv venv
   # Windows:
   venv\Scripts\activate
   # macOS/Linux:
   source venv/bin/activate
   ```

3. **Install dependencies:**
   ```bash
   pip install torch torchvision transformers accelerate pillow numpy matplotlib
   ```

4. **Launch Jupyter:**
   ```bash
   jupyter notebook DepthScope.ipynb
   ```

---

## 🧭 Understanding Relative Depth vs. Metric Depth

- **Relative Depth (Disparity):** DepthScope predicts the *relative* order of objects in a scene (which elements are closer vs. farther). Brighter/warmer pixels indicate closer foreground objects; darker pixels indicate distant background elements.
- **Metric Depth:** Represents true physical distance in meters or centimeters (requiring camera calibration, stereo vision, or LiDAR sensors). Relative depth values do **not** represent physical meters.

---

## 📁 Repository Structure

```text
├── DepthScope.ipynb   # Complete, runnable Google Colab Jupyter Notebook (11 cells)
└── README.md          # Project documentation and execution guide
```

---

## 🔬 Experiment Ideas

Try uploading different types of images to explore the model's capabilities and failure modes:
- **Indoor rooms:** Check object segmentation around chairs, desks, and monitors.
- **Outdoor streets:** Observe perspective convergence along roads and depth handling of the sky.
- **Reflective & transparent objects:** Test mirrors and windows to observe how specularity challenges monocular depth priors.
