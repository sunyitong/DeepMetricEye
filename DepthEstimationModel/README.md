# Depth Estimation Model

This directory contains the PyTorch/Jupyter implementation used for periocular depth estimation in DeepMetricEye.

## Overview

- **Task:** estimate periocular depth maps from monocular VR eye-camera imagery
- **Backbone:** optimized U-Net 3+ style encoder-decoder architecture
- **Input:** preprocessed single-channel periocular image
- **Output:** predicted periocular depth map
- **Sample data:** minimal public RGB/depth pairs under `train_data_minimal/`

## Quick Start

```bash
python -m venv .venv
source .venv/bin/activate
pip install torch torchvision pillow matplotlib scipy tqdm numpy jupyter
jupyter notebook model.ipynb
```

Open `model.ipynb` and run the cells in order. The notebook includes model definition, data loading, training, and evaluation utilities.

## Minimal Dataset

`train_data_minimal/` contains a small public sample for checking the training and inference pipeline. It is not the full research dataset.

Expected structure:

```text
train_data_minimal/
  train/
    rgb/
    depth/
  val/
    rgb/
    depth/
  test/
    rgb/
    depth/
```

## Inference Note

`use_model.py` is an early inference script and may require path updates before use. For reproducible experiments, prefer the notebook workflow until the script is refactored into a stable CLI.

## Citation

If you use this model or the accompanying sample data, please cite the DeepMetricEye paper listed in the root README.
