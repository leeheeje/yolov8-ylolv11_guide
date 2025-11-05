# 🧠 YOLOv11 Object Detection 프로젝트

## 📘 소개
이 저장소는 **YOLOv11 (You Only Look Once version 11)**을 사용하여 객체 탐지(Object Detection)를 학습하고 실험한 내용을 정리한 프로젝트입니다.  
YOLO는 이미지나 비디오에서 실시간으로 객체를 탐지할 수 있는 딥러닝 모델입니다.

> 🔰 초보자용으로, 설치부터 데이터 학습, 추론까지 단계별로 정리되어 있습니다.

---

## 🧩 목차
1. [프로젝트 개요](#프로젝트-개요)
2. [YOLOv8 vs YOLOv11 비교](#yolov8-vs-yolov11-비교)
3. [YOLO 용어 정리](#yolo-용어-정리)
4. [환경 설정](#환경-설정)
5. [데이터 준비](#데이터-준비)
6. [학습 방법](#학습-방법)
7. [추론(Detection)](#추론detection)
8. [결과 예시](#결과-예시)
9. [참고 자료](#참고-자료)

---

## 📍 프로젝트 개요
- 모델: **YOLOv11 (Ultralytics)**
- 목적: 이미지/영상에서 객체를 탐지하는 방법 실습
- 주요 기능:
  - 데이터셋 로드 및 라벨링
  - 모델 학습
  - 학습된 모델로 객체 탐지 수행
  - 결과 시각화

---

## ⚔️ YOLOv8 vs YOLOv11 비교

| 항목 | YOLOv8 | YOLOv11 |
|------|--------|---------|
| **출시 시기** | 2023년 초 | 2024년 말 |
| **개발사** | Ultralytics | Ultralytics |
| **모델 구조** | CSP 기반 Backbone + PAN-FPN Neck | 개선된 **RepNCSPELAN** 구조로 효율성 향상 |
| **성능 (mAP)** | 높음, YOLOv5 대비 약 10~15% 개선 | YOLOv8 대비 추가 향상 (약 5~10%) |
| **추론 속도** | 빠름 | 더 빠르고, 경량화 모델에서 효율적 |
| **지원 태스크** | Detection, Segmentation, Pose, Classification | 동일하지만 더 높은 정확도와 FPS |
| **훈련 안정성** | 우수 | 향상된 학습 안정성 및 더 나은 Loss 함수 |
| **지원 프레임워크** | PyTorch, ONNX, TensorRT 등 | 동일 (호환성 강화) |
| **사용성 (CLI)** | `yolo` 명령어 지원 | 동일 (`yolo train/predict/val/export`) |
| **주요 개선점** | YOLOv5 → YOLOv8으로 구조 단순화 | **Backbone, Neck, Head 구조 전면 개선**, 더 빠른 convergence |
| **권장 용도** | 일반적인 Object Detection 실험 | 최신 연구/프로젝트 및 경량화 실시간 탐지 |

> 💡 간단히 말하면, YOLOv11은 YOLOv8의 **속도 + 정확도 + 효율성**을 한 단계 더 끌어올린 최신 버전입니다.

---

## 📘 YOLO 용어 정리

| 용어 | 풀네임 | 설명 |
|------|---------|------|
| **Bounding Box (BBox)** | 객체 경계 상자 | 모델이 탐지한 객체의 위치를 나타내는 사각형 |
| **Confidence Score** | 신뢰도 점수 | 탐지된 객체가 실제로 해당 클래스일 확률 |
| **IoU (Intersection over Union)** | 교집합/합집합 비율 | 예측 박스와 실제 박스의 겹치는 정도 (성능평가 지표) |
| **mAP (mean Average Precision)** | 평균 정밀도 | 객체 탐지 정확도를 평가하는 대표 지표 |
| **NMS (Non-Maximum Suppression)** | 비최대 억제 | 중복된 박스를 제거하고 가장 신뢰도 높은 박스만 남김 |
| **Anchor Box** | 기준 박스 | 다양한 크기/비율의 객체를 탐지하기 위한 사전 정의된 박스 |
| **Backbone** | 특징 추출기 | 이미지의 주요 특징(feature)을 추출하는 CNN 네트워크 부분 |
| **Neck** | 중간 연결부 | Backbone에서 추출된 특징을 여러 스케일로 통합 |
| **Head** | 출력부 | 탐지 결과(좌표, 클래스, 점수 등)를 예측하는 부분 |
| **Epoch** | 학습 반복 횟수 | 데이터셋을 한 번 모두 학습하는 주기 |
| **Batch Size** | 배치 크기 | 한 번에 학습하는 이미지 개수 |
| **Learning Rate (LR)** | 학습률 | 가중치가 업데이트되는 속도 |
| **Augmentation** | 데이터 증강 | 학습 데이터를 변형하여 모델의 일반화 성능 향상 |
| **Fine-tuning** | 미세 조정 | 사전 학습된 모델을 기반으로 특정 데이터에 맞게 재학습 |

> 📖 YOLO를 제대로 이해하려면, 위의 용어를 숙지하면 도움이 됩니다!

---

## ⚙️ 환경 설정
```bash
pip install ultralytics

