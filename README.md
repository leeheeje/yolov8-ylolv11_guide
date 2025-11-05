# 🧠 YOLOv11 모델 다운로드 및 사용 가이드

## 📦 지원되는 모델 및 작업 모드

YOLOv11은 다양한 크기의 모델(`n`, `s`, `m`, `l`, `x`)과 여러 작업(Task)에 대해 사전 학습된 가중치를 제공합니다.  
아래 표에서 원하는 모델을 클릭하면 바로 다운로드할 수 있습니다.

| 모델 | 파일 이름 | 작업(Task) | 다운로드 | 설명 |
|------|------------|-------------|-----------|------|
| **YOLO11** | `yolo11n.pt`, `yolo11s.pt`, `yolo11m.pt`, `yolo11l.pt`, `yolo11x.pt` | 객체 탐지 (Object Detection) | 🔽 [yolo11n.pt](https://github.com/ultralytics/assets/releases/download/v0.0.0/yolo11n.pt)  <br> 🔽 [yolo11s.pt](https://github.com/ultralytics/assets/releases/download/v0.0.0/yolo11s.pt)  <br> 🔽 [yolo11m.pt](https://github.com/ultralytics/assets/releases/download/v0.0.0/yolo11m.pt)  <br> 🔽 [yolo11l.pt](https://github.com/ultralytics/assets/releases/download/v0.0.0/yolo11l.pt)  <br> 🔽 [yolo11x.pt](https://github.com/ultralytics/assets/releases/download/v0.0.0/yolo11x.pt) | 기본 객체 탐지용 모델 |
| **YOLO11-seg** | `yolo11n-seg.pt`, `yolo11s-seg.pt`, ... | 인스턴스 분할 (Segmentation) | 🔽 [yolo11n-seg.pt](https://github.com/ultralytics/assets/releases/download/v0.0.0/yolo11n-seg.pt) | 객체 마스크 생성 가능 |
| **YOLO11-pose** | `yolo11n-pose.pt`, `yolo11s-pose.pt`, ... | 포즈/키포인트 감지 | 🔽 [yolo11n-pose.pt](https://github.com/ultralytics/assets/releases/download/v0.0.0/yolo11n-pose.pt) | 인체 포즈 감지 |
| **YOLO11-obb** | `yolo11n-obb.pt`, `yolo11s-obb.pt`, ... | 방향 감지 (Oriented Bounding Box) | 🔽 [yolo11n-obb.pt](https://github.com/ultralytics/assets/releases/download/v0.0.0/yolo11n-obb.pt) | 회전된 물체 탐지 |
| **YOLO11-cls** | `yolo11n-cls.pt`, `yolo11s-cls.pt`, ... | 이미지 분류 (Classification) | 🔽 [yolo11n-cls.pt](https://github.com/ultralytics/assets/releases/download/v0.0.0/yolo11n-cls.pt) | 단일 객체 분류 |

> 💡 **참고:** 위 링크들은 예시이며, 실제 다운로드 링크는 Ultralytics의 공식 [YOLO11 Releases 페이지](https://github.com/ultralytics/assets/releases)에서 최신 버전으로 교체하면 됩니다.

---

## 📘 사용 예시

```bash
# 객체 탐지 예시
yolo predict model=yolo11n.pt source=./images/example.jpg

# 인스턴스 분할 예시
yolo predict model=yolo11n-seg.pt source=./images/example.jpg

# 포즈 감지 예시
yolo predict model=yolo11n-pose.pt source=./images/person.jpg


