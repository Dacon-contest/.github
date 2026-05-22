<h1 align="center">🏆 Dacon Contest</h1>

<p align="center">
  <b>AI Competition Team Archive</b><br />
  Computer Vision · Dual-View Classification · Segmentation · Model Calibration
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Competition-DACON-2563EB?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Final%20Rank-16th-16A34A?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Top-4%25-F97316?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Private%20LogLoss-0.01903-7C3AED?style=for-the-badge" />
</p>

<br />

## Main Competition

### 구조물 안정성 추론 공모전

front / top 두 시점 이미지를 기반으로 구조물의 안정·붕괴 확률을 예측하는 비전 분류 공모전입니다.  
단순 이미지 분류가 아니라 구조물의 형태, 기울기, 배치 정보를 바탕으로 물리적 안정성을 추론하는 문제로 접근했습니다.

<br />

## Result

| Item | Description |
|---|---|
| Final Rank | 16th |
| Percentile | Top 4% |
| Private LogLoss | 0.01903 |
| Team Size | 5 members |
| Period | 2026.03.03 ~ 2026.03.30 |

<br />

## Experiment Focus

- Dual-view image classification using front / top structure images
- Segmentation preprocessing pipeline for extracting structure regions
- SAM 2, Depth-Anything-v2, SAM 2 + Depth Hybrid comparison
- HSV Smart Box + SAM 2 hybrid segmentation strategy
- ConvNeXt and Swin Transformer based classification experiments
- RGB image input vs. RGB + Mask 4-channel input comparison
- TTA, Temperature Scaling, and Prediction Clipping for LogLoss improvement

<br />

## Repositories

| Repository | Purpose |
|---|---|
| dacon-structure-stability-ai | Main experiment archive and modeling workflow |
| dacon-data-segmentation_and_train | Segmentation preprocessing and training experiments |
| dual-view-stability-classifier | Dual-view structure stability classifier |
| dacon-structural-stability | Additional experiment and result archive |

<br />

## Tech Stack

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square" />
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square" />
  <img src="https://img.shields.io/badge/timm-111827?style=flat-square" />
  <img src="https://img.shields.io/badge/Albumentations-0F766E?style=flat-square" />
  <img src="https://img.shields.io/badge/ConvNeXt-2563EB?style=flat-square" />
  <img src="https://img.shields.io/badge/Swin_Transformer-7C3AED?style=flat-square" />
  <img src="https://img.shields.io/badge/SAM2-111827?style=flat-square" />
  <img src="https://img.shields.io/badge/Depth--Anything--v2-0F766E?style=flat-square" />
</p>

<br />

## Notes

This organization stores competition code, preprocessing experiments, model training pipelines, and result analysis used during the DACON structure stability prediction competition.
