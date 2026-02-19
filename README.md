# Harmful-content-blocking
AI YOLO 객체 감지 기술을 활용한 유해 콘텐츠 사전 차단 및 보호자 보고 채팅 애플리케이션 

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


# 요약
-실시간 유해요소 탐지
-메신저 앱 내 자동 필터링

{앱 채팅방 사진}
<채팅 중 동영상 전송>

![image](https://github.com/user-attachments/assets/9d804b2b-1148-403c-9d55-ef8186fee6e4) 
<유해 요소 탐지>

![image](https://github.com/user-attachments/assets/105c5e8f-982b-47a4-89cb-ce0d4508fdf0) 
<보고서 링크 접속>

# 주요 기능
1. 실시간 유해요소 탐지 (YOLOv5)

   객체 탐지 모델 : YOLOv5 커스텀 모델
   탐지 가능한 유해요소 : [칼, 담배, 총기]
   실시간 처리 지원

2. 메신저 앱 연동
   동영상 전송 시 필터링 수행
   - 전송 전 서버에서 실시간 프레임 분석
   - 유해 요소 탐지 시 즉시 차단

3. 보고서 생성

   발견된 유해요소 종류 및 정확도 제공

# 기술 스택

# 데이터 셋

# 성능 및 평가

# 개선 사항
