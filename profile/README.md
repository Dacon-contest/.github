<h1 align="center">🏆 Dacon Contest</h1>

<p align="center">
  <b>DACON 구조물 안정성 추론 공모전 팀 아카이브</b><br />
  Computer Vision · Dual-View Classification · Large Vision Backbone · Model Calibration
</p>

<p align="center">
  <img src="https://img.shields.io/badge/DACON-구조물%20안정성%20추론-2563EB?style=for-the-badge" />
  <img src="https://img.shields.io/badge/최종%20순위-16등-16A34A?style=for-the-badge" />
  <img src="https://img.shields.io/badge/상위-4%25-F97316?style=for-the-badge" />
  <img src="https://img.shields.io/badge/대표%20제출%20LogLoss-0.01903-7C3AED?style=for-the-badge" />
  <img src="https://img.shields.io/badge/팀%20베스트%20LogLoss-0.01756-DC2626?style=for-the-badge" />
</p>

<br />

## 대표 공모전

### 구조물 안정성 추론 공모전

front / top 두 시점 이미지를 기반으로 구조물의 안정·붕괴 확률을 예측하는 비전 분류 공모전입니다.  
단순 이미지 분류가 아니라, 구조물의 형태·기울기·배치 정보를 바탕으로 물리적 안정성을 추론하는 문제로 접근했습니다.

<br />

## 성과

| 항목 | 내용 |
|---|---|
| 최종 순위 | 16등 |
| 전체 성과 | 상위 4% |
| 리더보드 대표 제출 점수 | Private LogLoss 0.01903 |
| 팀 내 베스트 모델 점수 | Private LogLoss 0.01756 |
| 팀 구성 | 5인 팀 |
| 진행 기간 | 2026.03.03 ~ 2026.03.30 |

<br />

## Best Pipeline

팀 내에서 가장 좋은 성능을 낸 학습 방향은 [`dacon-structural-stability`](https://github.com/Dacon-contest/dacon-structural-stability) 레포에 정리된 대규모 Vision Backbone 기반 파이프라인입니다.

- EVA-Giant / DINOv2 / EVA02 계열 대형 Vision Backbone 실험
- front / top 이미지를 같은 백본으로 인코딩하는 Shared Backbone Dual-View 구조
- 두 시점 특징을 결합하는 Attention Gate Fusion 구조
- Focal Loss + Label Smoothing 조합
- ShapeStacks 사전학습 후 DACON train + dev 기반 5-Fold Finetune
- RandomResizedCrop, Affine, Perspective, ColorJitter, Blur, Noise, Shadow 등 강한 증강 적용
- CutMix / Mixup / Clean 샘플을 섞는 배치 단위 학습 전략
- TTA, Temperature Scaling, Prediction Clipping 기반 LogLoss 개선

<br />

## 전처리 및 실험 방향

- 구조물 영역에 집중하기 위한 Segmentation 전처리 파이프라인 설계
- SAM 2, Depth-Anything-v2, SAM 2 + Depth Hybrid 방식 비교
- HSV Smart Box + SAM 2 하이브리드 방식으로 구조물 마스크 추출 실험
- RGB 입력과 RGB + Mask 4채널 입력 방식 비교
- ConvNeXt, Swin Transformer 기반 Dual-View Fusion 실험
- 배경 노이즈, 체커보드 바닥, 그림자 영향을 줄이기 위한 마스크 기반 학습 실험
- LogLoss 기준에서 과도한 확신을 줄이기 위한 확률 보정 적용

<br />

## 저장소 구성

| Repository | 설명 |
|---|---|
| [dacon-structural-stability](https://github.com/Dacon-contest/dacon-structural-stability) | 팀 내 최고 성능 방향의 대규모 Vision Backbone 학습·추론 파이프라인 |
| [dacon-data-segmentation_and_train](https://github.com/Dacon-contest/dacon-data-segmentation_and_train) | Segmentation 전처리 및 구조물 마스크 기반 학습 실험 |
| [dual-view-stability-classifier](https://github.com/Dacon-contest/dual-view-stability-classifier) | front / top Dual-View 구조물 안정성 분류 모델 실험 |
| [dacon-structure-stability-ai](https://github.com/Dacon-contest/dacon-structure-stability-ai) | 초기 베이스라인 및 실험 아카이브 |

<br />

## 사용 기술

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square" />
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square" />
  <img src="https://img.shields.io/badge/timm-111827?style=flat-square" />
  <img src="https://img.shields.io/badge/Albumentations-0F766E?style=flat-square" />
  <img src="https://img.shields.io/badge/ConvNeXt-2563EB?style=flat-square" />
  <img src="https://img.shields.io/badge/Swin_Transformer-7C3AED?style=flat-square" />
  <img src="https://img.shields.io/badge/EVA--Giant-7C2D12?style=flat-square" />
  <img src="https://img.shields.io/badge/DINOv2-111827?style=flat-square" />
  <img src="https://img.shields.io/badge/SAM2-111827?style=flat-square" />
  <img src="https://img.shields.io/badge/Depth--Anything--v2-0F766E?style=flat-square" />
</p>

<br />

## 소개

이 조직은 DACON 구조물 안정성 추론 공모전에서 사용한 코드, 데이터 전처리 실험, 모델 학습 파이프라인, 후처리 및 결과 분석 과정을 정리하기 위한 팀 아카이브입니다.
