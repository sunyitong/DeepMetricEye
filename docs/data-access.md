# Data Access

This repository includes a minimal RGB/depth sample under `DepthEstimationModel/train_data_minimal/` so that researchers can verify the training and inference workflow.

## Public Sample

The minimal sample is intended for:

- checking data loaders,
- validating tensor shapes,
- testing the notebook end to end,
- illustrating the RGB/depth pairing used by the model.

It is not the complete dataset used in the paper.

## Restricted Data

The full experimental data includes sensitive facial information and participant-derived scans. To protect participant privacy, raw data is not distributed directly through GitHub.

Researchers who need access to restricted data should contact the authors and be prepared to discuss research purpose, data-handling safeguards, institutional affiliation, and non-disclosure requirements.

Contact: <yitong.sun@network.rca.ac.uk>

## Recommended Citation

Please cite the associated paper when using the public sample, DPDG environment, or model code:

```bibtex
@inproceedings{Sun_2023,
  title={DeepMetricEye: Metric Depth Estimation in Periocular VR Imagery},
  DOI={10.1109/ISMAR59233.2023.00058},
  booktitle={2023 IEEE International Symposium on Mixed and Augmented Reality (ISMAR)},
  publisher={IEEE},
  author={Sun, Yitong and Zhou, Zijian and Diels, Cyriel and Asadipour, Ali},
  year={2023},
  pages={434--443}
}
```
