# Dynamic Periocular Data Generation (DPDG) Environment

This directory documents the Unreal Engine component of DeepMetricEye. The DPDG environment uses Unreal Engine 5.2 and MetaHuman avatars to synthesize paired periocular RGB images and ground-truth depth maps for VR eye-region depth-estimation research.

## Overview

- **Engine:** Unreal Engine 5.2
- **Avatar system:** UE MetaHuman
- **Output:** synchronized periocular RGB images and depth maps
- **Purpose:** generate diverse training samples from limited real facial scans while reducing the burden of sensitive participant-data collection

## Setup

1. Install Unreal Engine 5.2.
2. Download the environment package:
   <https://drive.google.com/file/d/1DDyOThmrLEkm6d67v70p_Sb_0alSmXqN/view?usp=sharing>
3. Unzip the package.
4. Open `HumanDataset.uproject` in Unreal Engine 5.2.
5. Confirm that required MetaHuman assets, camera components, lighting, and export directories are loaded correctly.

## Typical Workflow

1. Import or select a MetaHuman identity.
2. Configure headset geometry and eye-oriented camera placement.
3. Adjust lighting and camera parameters to match the target headset condition.
4. Render periocular RGB images.
5. Export the corresponding depth maps.
6. Use the generated pairs with the model pipeline in [`../DepthEstimationModel/`](../DepthEstimationModel/).

## Notes

- The environment is intended for research reproduction and synthetic-data generation.
- Raw participant scans are sensitive and are not distributed through this repository.
- If you use the environment in research, cite the DeepMetricEye paper listed in the root README.
