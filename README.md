# DepthScope

A simple project that predicts depth from 2D photos using the Depth Anything V2 model.

## What it does
- Takes an image (.jpg or .png)
- Runs depth estimation with Hugging Face transformers
- Shows a side-by-side comparison (original, grayscale depth, color depth)
- Downloads the output depth map

## Quickstart: Running in Google Colab
1. Open [Google Colab](https://colab.research.google.com/).
2. Upload `DepthScope.ipynb`.
3. Set runtime to T4 GPU.
4. Run all cells and upload your photo.
