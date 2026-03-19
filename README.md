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

### 🤖 AI Models & Frameworks
* **Pose Estimation:** `OpenPose` (사용자의 정밀한 관절 및 키포인트 추출)
* **Human Parsing:** `SCHP (Self-Correction-Human-Parsing)` (의류 및 신체 부위 분할)
* **Object Detection:** `Detectron2` (이미지 내 의류 및 객체 인식)
* **Background Removal:** `Carvekit` (고정밀 누끼 작업 및 데이터 전처리)
* **Virtual Try-on:** `StableVITON` (Stable Diffusion 기반 고해상도 가상 피팅 구현)

### 🌐 Backend & Serving
* **Framework:** `FastAPI` (비동기 처리를 통한 고성능 추론 API 서버 구축)

### 💻 Infrastructure
* **OS:** Ubuntu 22.04 LTS (Native Dual-Boot)
* **GPU:** NVIDIA GeForce RTX 4070 SUPER (CUDA 12.x)

## 📂 프로젝트 구조 (Project Structure)

* `src/`: 메인 소스 코드 (Inference, FastAPI Server, Core Logic)
* `scripts/`: 데이터 전처리 및 자동화 스크립트 (Image Resizing, File Naming)
* `data/HR-VITON/custom/`: **[Dataset Root]** 가상 피팅 학습 및 테스트 데이터
    * `train/`, `test/`: (학습 및 검증 세트 분할)
        * `cloth/`: 배경이 제거된 상의/의류 이미지
        * `cloth-mask/`: 의류의 바이너리 마스크 (Binary Mask)
        * `image/`: 768x1024 고해상도 사용자/모델 이미지
        * `image-densepose/`: Detectron2 기반의 DensePose 추출 결과
        * `image-parse-v3/`: SCHP 기반의 신체 영역 분할 맵 (Human Parsing)
        * `image-parse-agnostic-v3.2/`: 의류 영역이 지워진 Agnostic Map (Fitting 핵심 데이터)
        * `openpose_img/`, `openpose_json/`: OpenPose 기반의 관절 키포인트 시각화 및 좌표 데이터

## 🔧 트러블슈팅 (Troubleshooting)
### 1. Mixed Precision (FP16) 학습 오류
* **문제:** 학습 중 `RuntimeError: Found dtype Half but expected Float` 발생.
* **해결:** 모델 학습 스크립트 실행 시 정밀도 설정을 명시적으로 조정하여 데이터 타입 불일치 해결.

---
© 2026 Hyunwoo. All rights reserved.
