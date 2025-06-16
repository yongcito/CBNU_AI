 🗂️ Dataset Overview

본 폴더는 캡스톤 프로젝트에서 사용된 식품 제조 작업자 위생복/위생모 감지 데이터셋의 구조 및 통계, 예시 분석 자료를 포함한다.

---

 📦 폴더 구조
 
```
dataset/
├── dataset_overview.ipynb  📊 데이터 분포·샘플·통계 분석 노트북
└── README.md  📑 데이터셋 설명 파일(본 문서)
```

---

 🧮 데이터셋 통계

- Train: 1,189장 (74%)
- Validation: 237장 (15%)
- Test: 160장 (10%)
- 클래스:  
  - 🦺 gown_on  
  - 👒 hairnet_on  
  - 👤 person

상세 분포/시각화/어노테이션 예시:  
→ `dataset_overview.ipynb`에서 직접 확인

---

 🧑‍🔬 데이터 특징

- Roboflow 기반 분할 및 증강
- 실제 식품공장 CCTV 환경 촬영 이미지
- 증강: 🔄 flip, 🔍 zoom, 💧 blur, 🔊 noise 등
- 클래스별 균형/분포 유지


