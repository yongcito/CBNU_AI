 🧠 지능화캡스톤프로젝트 10주차  
 Object Detection with Custom Datasets

 ✅ 과제 개요
본 프로젝트는 Roboflow와 Ultralytics YOLO를 활용하여 사용자 정의 객체 탐지(Object Detection) 모델을 구축하는 과제입니다.  
직접 구축한 데이터셋을 기반으로 YOLOv8~YOLOv11 중 하나를 선택하여 학습하고, Validation 및 Test 결과를 분석합니다.

---

 📁 데이터셋 구성
- Roboflow를 이용하여 총 1,586장의 이미지를 수집 및 라벨링
- 클래스: `person`, `gown_on`, `hairnet_on`
- 데이터 분할:
  - Train Set: 1,359장
  - Validation Set: 132장
  - Test Set: 95장
- 전처리:
  - 이미지 자동 회전 보정, Grayscale 변환, Adaptive Contrast 적용
- 증강 기법:
  - 수평 뒤집기, 랜덤 줌, 노이즈, 블러 등

---

 🧪 모델 학습
- 사용 모델: YOLOv8l (YOLOv8 Large)
- 프레임워크: [Ultralytics YOLO 8.3.143](https://github.com/ultralytics/ultralytics)
- 학습 환경:
  - Google Colab Pro+
  - GPU: NVIDIA A100 (40GB)
  - Python 3.11.12, Torch 2.6.0 + CUDA 12.4
- 학습 조건:
  - Epochs: 100
  - Batch size: 16
  - Image size: 960
- 학습 소스코드:  
  [`yolov8l_250524_ep100_bs16_sz960_1.ipynb`](./yolov8l_250524_ep100_bs16_sz960_1.ipynb)

---

 📊 성능 평가

📍 Validation 결과 (132장 기준)

| 지표        | 값     |
|-------------|--------|
| mAP@0.5     | 0.9562 |
| mAP@0.5:0.95| 0.6163 |

📍 클래스별 성능

| 클래스       | Precision | Recall | mAP@0.5 | mAP@0.5:0.95 |
|--------------|-----------|--------|---------|---------------|
| gown_on      | 0.917     | 0.928  | 0.950   | 0.528         |
| hairnet_on   | 0.953     | 0.943  | 0.963   | 0.655         |
| person       | 0.947     | 0.935  | 0.956   | 0.666         |

---

 🖼️ Test 결과 이미지

- YOLOv8l 모델을 통해 추론한 Test 이미지 시각화
- 테스트 이미지 추론 결과 저장:  
  [`predict/`](./predict/)  
  (또는 [`yolo_predict.zip`](./yolo_predict.zip))

- 학습 전체 결과 폴더:
  [`yolov8l_ep100_bs16_img960`](./yolov8l_ep100_bs16_img960/)

```python
 예시 추론 코드
results = model.predict("/content/capstone_project-9/test/images", save=True)
