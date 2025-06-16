
# 🚀 Google Colab → GitHub 아카이브 매뉴얼

이 가이드는 **Google Colab**에서 작업한 코드, 결과 파일, 이미지 등을  
**GitHub 저장소에 직접 업로드(아카이브)** 하는 전체 과정을 초보자도 쉽게 따라할 수 있도록 설명합니다.

---

## ✅ 사전 준비

### 1. GitHub 저장소 만들기
- https://github.com → 로그인 → 우측 상단 `+` 클릭 → **New repository**
- Repository name: 예) `capstone-object-detection`
- **README 생성하지 않기** (Colab에서 직접 파일 올릴 예정)

---

## ✅ 1단계: Colab에서 Git 설치 및 GitHub 연동

### 🔹 GitHub 사용자 정보 설정 (최초 1회)

```bash
!git config --global user.email "your_email@example.com"
!git config --global user.name "your_github_username"
```

예:
```bash
!git config --global user.email "solucionemoscorea@gmail.com"
!git config --global user.name "yongcito"
```

---

## ✅ 2단계: GitHub 저장소 클론

```bash
!git clone https://github.com/사용자명/저장소명.git
```

예:
```bash
!git clone https://github.com/yongcito/CBNU_AI.git
```

---

## ✅ 3단계: 내 파일을 저장소 폴더로 복사

예:
```bash
!cp /content/my_notebook.ipynb CBNU_AI/폴더명/
!cp -r /content/runs/detect/predict CBNU_AI/폴더명/
```

---

## ✅ 4단계: GitHub에 커밋 & 푸시

```bash
%cd CBNU_AI/폴더명/

!git add .
!git commit -m "Add 프로젝트 파일"
!git push origin main
```

---

## 🛑 오류 발생: `could not read Username`

Colab에서는 GitHub 로그인 창이 뜨지 않기 때문에,  
**Personal Access Token (PAT)** 을 발급받아 아래처럼 설정해야 합니다.

---

## ✅ 5단계: GitHub Token 연동 방법

### 1. [토큰 생성 링크](https://github.com/settings/tokens?type=beta) 접속
- 토큰 이름: capstone-push
- 권한: `repo`, 또는 `Contents (Read/Write)`
- 저장소 선택: 해당 repo
- 생성 후 나오는 토큰 복사

### 2. Colab에서 토큰 포함 URL로 원격 설정 변경

```bash
!git remote set-url origin https://ghp_토큰내용@github.com/사용자명/저장소명.git
```

예:
```bash
!git remote set-url origin https://ghp_xxxxxx@github.com/yongcito/CBNU_AI.git
```

---

## ✅ 6단계: 다시 푸시 실행

```bash
!git push origin main
```

---

## 🎉 아카이브 완료 후 확인

GitHub 웹페이지에 접속하여,  
추론 결과 폴더, 소스코드, 리포트 파일 등이 정상적으로 올라갔는지 확인합니다.

---
