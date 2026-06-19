# DeepMetricEye / DPDG-Env

中文 | [English](README.md)

[![License: GPL-3.0](https://img.shields.io/badge/License-GPLv3-blue.svg)](LICENSE)
[![Paper](https://img.shields.io/badge/Paper-ISMAR%202023-8A2BE2)](https://doi.org/10.1109/ISMAR59233.2023.00058)
[![arXiv](https://img.shields.io/badge/arXiv-2311.07235-b31b1b)](https://arxiv.org/abs/2311.07235)
[![Unreal Engine](https://img.shields.io/badge/Unreal%20Engine-5.2-0E1128)](DPDG_Environment/)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.x-EE4C2C)](DepthEstimationModel/)

这是论文 **DeepMetricEye: Metric Depth Estimation in Periocular VR Imagery** 的研究代码与数据生成仓库。仓库包含 Dynamic Periocular Data Generation (DPDG) 合成环境，以及用于从 VR 头显单目眼部相机图像估计眼周 metric depth 的模型代码。

![DeepMetricEye pipeline](docs/assets/deepmetriceye-pipeline.png)

上图截取自论文 PDF，用作仓库展示首图。

## 项目价值

现代 VR 头显中的眼部相机通常可以获取瞳孔、眼周轮廓与 gaze 相关的 2D 信息，但这些相对二维特征无法直接支持瞳孔直径、眼周形变或光刺激标准计算等 metric measurement。DeepMetricEye 的目标是用单目图像重建可测量的眼周深度图，并用 UE MetaHuman 环境缓解真实人脸数据采集困难。

核心内容包括：

- 面向 VR 眼部相机的轻量级眼周深度估计模型；
- 基于 Unreal Engine 5.2 与 MetaHuman 的 DPDG 合成数据环境；
- RGB/depth 训练样例，用于快速验证训练和推理流程；
- 面向 VR 眼健康、XR sensing 与人机交互研究的可复现实验入口。

## 仓库结构

| 路径 | 说明 |
| --- | --- |
| [`DPDG_Environment/`](DPDG_Environment/) | Unreal Engine 5.2 MetaHuman 合成环境，用于生成眼周 RGB 图像与深度图。 |
| [`DepthEstimationModel/`](DepthEstimationModel/) | PyTorch/Jupyter 模型实现与最小示例数据集。 |
| [`docs/data-access.md`](docs/data-access.md) | 数据公开范围、敏感数据说明和受限数据申请方式。 |
| [`CITATION.cff`](CITATION.cff) | GitHub 和文献管理器可识别的引用元数据。 |

## 快速开始

### 深度估计模型

```bash
cd DepthEstimationModel
python -m venv .venv
source .venv/bin/activate
pip install torch torchvision pillow matplotlib scipy tqdm numpy
jupyter notebook model.ipynb
```

`train_data_minimal/` 只用于快速验证流程，并不是完整研究数据集。

### DPDG 合成环境

1. 安装 Unreal Engine 5.2。
2. 按 [`DPDG_Environment/README.md`](DPDG_Environment/README.md) 中的链接下载 DPDG 工程包。
3. 打开 `HumanDataset.uproject`。
4. 配置 MetaHuman 身份、VR 头显几何、相机位姿、灯光与导出目录。
5. 导出同步的眼周 RGB 图像与 ground-truth depth map。

## 论文链接

- 项目页：<https://yitongsun.com/deepmetriceye>
- DOI：<https://doi.org/10.1109/ISMAR59233.2023.00058>
- arXiv：<https://arxiv.org/abs/2311.07235>
- 仓库：<https://github.com/sunyitong/DPDG-Env>

## 数据访问

完整实验数据包含敏感人脸信息，因此不直接通过 GitHub 分发。公开样例、受限数据政策和联系流程见 [`docs/data-access.md`](docs/data-access.md)。

## 引用

如果本仓库对你的研究有帮助，请引用：

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

## 贡献

欢迎提交 issue 或 pull request，尤其是复现实验修复、文档补充、数据加载流程整理和更多 VR 头显标定说明。较大改动请先阅读 [`CONTRIBUTING.md`](CONTRIBUTING.md)。

## 许可证

本仓库采用 [GNU General Public License v3.0](LICENSE)。
