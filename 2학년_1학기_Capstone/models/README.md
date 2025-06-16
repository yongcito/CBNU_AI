# 🧩 모델 실험 결과 구조 안내

본 폴더는 캡스톤 프로젝트의 학습된 YOLOv5 및 YOLOv8 모델 실험 결과를 계층적으로 관리합니다.

## 📦 폴더 구조

```
models/
├── yolov5/ # YOLOv5 기반 실험별 하위 폴더
│ ├── yolov5n_ep50_bs16_img640/
│ ├── yolov5s_ep100_bs16_img960/
│ └── ...
├── yolov8/ # YOLOv8 기반 실험별 하위 폴더
│ ├── yolov8n_ep50_bs16_img640/
│ ├── yolov8s_ep100_bs16_img960/
│ └── ...
└── README.md
```


- 각 하위폴더명에는 실험 조건(variant, epoch, batch size, input size 등)이 포함됨.
- 각 폴더 내 best.pt, last.pt, 학습 로그, 실험 그래프 등 주요 산출물 관리.

## ⚠️ 관리 원칙

- yolov5/yolov8 대분류만 폴더 분리, n/s/m 등 variant는 폴더명 구분만 적용
- 대용량 압축본(zip)은 저장소가 아닌 외부(구글드라이브 등)로 관리 권장
- 모든 변경은 git commit-log로 추적 가능

