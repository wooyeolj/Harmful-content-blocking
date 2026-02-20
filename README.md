# ai 유해 콘텐츠 차단 및 보고 채팅 애플리케이션

### Harmful-content-blocking

> AI YOLO 객체 감지 기술을 활용한 유해 콘텐츠 사전 차단 및 보호자 보고 채팅 애플리케이션 


<div align="center">

  Backend
  
[![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=flat&logo=python&logoColor=white)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-2.0+-000000?style=flat&logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![YOLOv5](https://img.shields.io/badge/YOLOv5-PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)](https://github.com/ultralytics/yolov5)
[![OpenCV](https://img.shields.io/badge/OpenCV-4.5+-5C3EE8?style=flat&logo=opencv&logoColor=white)](https://opencv.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-1.10+-EE4C2C?style=flat&logo=pytorch&logoColor=white)](https://pytorch.org/)

  Frontend (Android)

[![Android Studio](https://img.shields.io/badge/Android_Studio-2021.1+-3DDC84?style=flat&logo=androidstudio&logoColor=white)](https://developer.android.com/studio)
[![Java](https://img.shields.io/badge/Java-8+-007396?style=flat&logo=java&logoColor=white)](https://www.oracle.com/java/)
[![Firebase](https://img.shields.io/badge/Firebase-9.0+-FFCA28?style=flat&logo=firebase&logoColor=black)](https://firebase.google.com/)
[![Retrofit](https://img.shields.io/badge/Retrofit-2.9+-48B983?style=flat)](https://square.github.io/retrofit/)
[![OkHttp](https://img.shields.io/badge/OkHttp-4.9+-4479A1?style=flat)](https://square.github.io/okhttp/)


   Database & Services
   
[![Firebase Realtime DB](https://img.shields.io/badge/Firebase_Realtime_DB-FFCA28?style=flat&logo=firebase&logoColor=black)](https://firebase.google.com/products/realtime-database)
[![Firebase Auth](https://img.shields.io/badge/Firebase_Auth-FFCA28?style=flat&logo=firebase&logoColor=black)](https://firebase.google.com/products/auth)</parameter></invoke>

</div>

<div align="center">


---
### 프로젝트 데모
-YOLOv5 AI 모델을 이용한 실시간 유해요소 탐지
-메신저 앱 내 자동 필터링

<p align="center">
  <table>
    <tr>
      <td align="center">
        <img src="https://github.com/user-attachments/assets/eabbf51b-a8de-47d8-a50e-87b52ff7507a" width="300"/><br>
        <b><채팅 중 동영상 전송></b>
      </td>
      <td align="center">
        <img src="https://github.com/user-attachments/assets/9d804b2b-1148-403c-9d55-ef8186fee6e4" width="300"/><br>
        <b><유해 요소 탐지></b>
      </td>
      <td align="center">
        <img src="https://github.com/user-attachments/assets/105c5e8f-982b-47a4-89cb-ce0d4508fdf0" width="300"/><br>
        <b><보고서></b>
      </td>
    </tr>
  </table>
</p>

</div>

---

## 목차
1. [프로젝트 소개](#프로젝트-소개)
2. [주요 기능](#주요-기능)
3. [시스템 아키텍처](#시스템-아키텍처)
4. [기술 스택](#기술-스택)
5. [설치 및 실행](#설치-및-실행)
6. [프로젝트 결과](#프로젝트-결과)
7. [기술적 도전과 해결](#기술적-도전과-해결)
8. [향후 개선 방향](#향후-개선-방향)
9. [팀 및 기여](#팀-및-기여)
10. [라이선스](#라이선스)


## 프로젝트 소개

### 📚 2024 종합설계

본 프로젝트는 **2024년 한국공학대학교 종합설계**의 일환으로 진행되었습니다.

- **프로그램**: 한국정보산업연합회 주관 산학 협력 프로젝트
- **프로젝트 기간**: 2024년 3월 ~ 11월 (9개월)
- **팀 구성**: 4인 (전자공학과 졸업생)

### 🚨 배경 및 필요성

스마트폰 보급 확대와 함께 청소년들의 Social Network Service(또는 Social Networking Service) 사용이 일상화되면서 유해 콘텐츠에 노출될 위험이 증가 하였다. 특히 동영상 공유 기능을 통해 이러한 요소가 포함된 영상이 무분별하게 유통되며 부정적 영향을 미치고 있으나, 메신저 앱의 특성상 서버를 옮기며 가해자의 추적이 어렵고 간단한 대응책조차 마련하기 힘들다.

### 🎯 프로젝트 목표

YOLOv5 딥러닝 모델을 활용하여 메신저 앱에서 공유되는 동영상 속 유해 콘텐츠를 실시간으로 사전 차단하고, 보호자에게 자동 보고하는 통합 시스템 개발

1️⃣ 높은 탐지 정확도 확보

- 신뢰도 90% 이상에서만 탐지 작동
- 3프레임 연속 탐지 조건으로 오탐지 최소화

2️⃣ 실시간 처리 성능 구현

- 프레임별 객체 인식 및 즉각 대응
- Early Stop 알고리즘으로 효율적 처리

3️⃣ 보호자 연동 시스템 구축

- SMS 자동 알림 기능 (Twilio API)
- 탐지 프레임 이미지 자동 저장

4️⃣ 사용자 경험 최적화

- 안전한 콘텐츠는 자유롭게 공유 가능
- 차단 시 명확한 피드백 제공

### 💡 프로젝트 차별점

🛡️ 선제적 방어 : 사후 대응이 아닌 사전 차단

👁️ 탐지 대상 : 텍스트가 아닌 동영상 프레임 탐지

⚖️ 이중 검증 : 높은 신뢰도 (90%)와 연속 프레임 탐지 조건으로 오탐지 최소화

⚡ 처리 속도 : 유해요소 3프레임 연속 탐지 시 즉시 중단(Early Stopping) 하여 효율적 처리

📲 보호자 연동 : 유해 요소 탐지 시 SMS 전송으로 위험 상황에 즉각 개

🔄 통합 솔루션 : 탐지 + 차단 + 보고 + 데이터 보관을 하나의 시스템에서 처리하는 Full-Stack 관리

🌍 확장 가능성: 다양한 SNS 서비스로 확장 가능한 구조


### 🎓 학습 목표

#### 🛠️ 기술적 역량 강화

1️⃣ 딥러닝 모델 활용 능력

- YOLOv5 모델 학습 및 파인튜닝 경험
- PyTorch 프레임워크 이해 및 커스텀 데이터셋 구축
- 객체 탐지 알고리즘 원리 습득 및 모델 경량화 경험

2️⃣ 풀스택 개발 경험

- Android 앱 개발 (Java) 및 사용자 경험 (UX) 설계
- Flask 웹 서버 구축 (Python)
- Firebase 실시간 데이터베이스 연동

#### 🧩 문제 해결 능력 강화

1️⃣ 성능 최적화

- Early Stop 알고리즘 설계로 컴퓨팅 자원 효율화

2️⃣ 정확도 향상

- 신뢰도 임계값 조정을 통한 정확도 최적화
- 연속 프레임 교차 검증 알고리즘 설계를 통한 오탐지 최소화 전략 수립

3️⃣ 실무 프로젝트 경험

- 요구사항 분석 및 설계
- 팀 협업 및 버전 관리 (Git)
- 문서화 및 발표 자료 작성

4️⃣ 사회적 가치 실현

- 기술적 능력으로 취약 계층에게 실질적인 안전 장치 마련

## 주요 기능

### 1️⃣ 실시간 유해 콘텐츠 탐지
### 2️⃣ 채팅 통합 시스템
### 3️⃣ 보고서 전송 시스템

## 시스템 아키텍처

### 🏗️시스템 구상도

<img width="565" height="405" alt="image" src="https://github.com/user-attachments/assets/ceb26d64-d95b-490e-b426-c00905fc7a91" />

본 시스템에서는 단말기 간 이미지, 영상, 문자 등의 전송 과정에서 Flask 서버를 중개로 활용하여, 전달되는 콘텐츠 내부에 유해 요소가 포함되어 있는지 YOLOv5 AI 모델로 검사한다. 만약 유해 요소가 발견되면, 전송을 즉시 중단하고, 사전에 설정된 보호자에게 실시간으로 해당 내용을 보고한다.


### 🤖YOLO 학습 모델

#### 📋선정 이유
#### 📦데이터 셋

### 📱애플리케이션 개발

#### 💻개발 환경
#### 🌐서버 통신


## 기술 스택
## 설치 및 실행

## 프로젝트 결과

### 📋개발 결과
### ✨성능 지표
### 🎯활용 분야

## 기술적 도전과 해결

### 🎯 정확도 향상
### ⚡ 성능 최적화
### 🌐 사용자 수용성 저해


## 팀 및 기여
## 라이선스
