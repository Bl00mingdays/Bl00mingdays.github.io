# Bl00mingdays.github.io

# 👕 실시간 포즈 인식 기반 가상 피팅 시스템
> **Real-time Human Pose Estimation & Virtual Try-on Project**

MediaPipe를 활용하여 실시간으로 인체의 관절 포인트를 추출하고, 이를 기반으로 가상 의류 피팅(Virtual Fitting)을 구현하는 프로젝트입니다.

---

## 🚀 주요 기능 (Key Features)
* **Real-time Pose Estimation:** MediaPipe를 활용한 저지연 관절 인식.
* **Fashion-tech Integration:** HR-VITON 모델 기반의 고해상도 가상 피팅.
* **Custom Dataset:** 무신사 등에서 크롤링한 의류 이미지 및 팀원 사진을 활용한 맞춤형 데이터셋 구축.

## 🛠 기술 스택 (Tech Stack)
* **OS:** Ubuntu 22.04 LTS (WSL2 / Dual-Boot)
* **Hardware:** NVIDIA GeForce RTX 4070 SUPER
* **Language:** Python 3.x
* **AI/ML:** PyTorch, MediaPipe, OpenCV, SCHP

## 📂 프로젝트 구조 (Structure)
* `src/`: 메인 소스 코드 (Pose extraction, Inference)
* `scripts/`: 데이터 전처리 및 이미지 리사이징(768x1024) 스크립트
* `data/`: 샘플 데이터셋 (260318 폴더 등)

## 🔧 트러블슈팅 (Troubleshooting)
### 1. Mixed Precision (FP16) 학습 오류
* **문제:** 학습 중 `RuntimeError: Found dtype Half but expected Float` 발생.
* **해결:** 모델 학습 스크립트 실행 시 정밀도 설정을 명시적으로 조정하여 데이터 타입 불일치 해결.

---
© 2026 Hyunwoo. All rights reserved.
