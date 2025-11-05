# 🧠 YOLOv11 Object Detection 프로젝트

## 📘 소개
이 저장소는 **YOLOv11 (You Only Look Once version 11)**을 사용하여 객체 탐지(Object Detection)를 학습하고 실험한 내용을 정리한 프로젝트입니다.  
YOLO는 이미지나 비디오에서 실시간으로 객체를 탐지할 수 있는 딥러닝 모델입니다.

> 🔰 초보자용으로, 설치부터 데이터 학습, 추론까지 단계별로 정리되어 있습니다.

---

## 🧩 목차
1. [프로젝트 개요](#프로젝트-개요)
2. [환경 설정](#환경-설정)
3. [데이터 준비](#데이터-준비)
4. [학습 방법](#학습-방법)
5. [추론(Detection)](#추론detection)
6. [결과 예시](#결과-예시)
7. [참고 자료](#참고-자료)

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

## ⚙️ 환경 설정

### 1. 필수 요구사항
- Python 3.8 이상
- PyTorch
- Ultralytics 라이브러리 (YOLOv11 포함)
- Jupyter Notebook (선택)

### 2. 설치 방법
```bash
# 가상환경 생성 (선택)
python -m venv yolov11-env
source yolov11-env/bin/activate   # (Windows는 yolov11-env\Scripts\activate)

# 라이브러리 설치
pip install ultralytics
