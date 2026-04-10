# ai 유해 콘텐츠 차단 및 보고 채팅 애플리케이션

### Harmful-content-blocking

> AI YOLO 객체 감지 기술을 활용한 유해 콘텐츠 사전 차단 및 보호자 보고 채팅 애플리케이션 


<div align="center">

  **Backend**
  
[![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=flat&logo=python&logoColor=white)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-2.0+-000000?style=flat&logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![Twilio](https://img.shields.io/badge/Twilio_SDK-F22F46?style=flat&logo=twilio&logoColor=white)](https://www.twilio.com/)
[![YOLOv5](https://img.shields.io/badge/YOLOv5-PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)](https://github.com/ultralytics/yolov5)
[![OpenCV](https://img.shields.io/badge/OpenCV-4.5+-5C3EE8?style=flat&logo=opencv&logoColor=white)](https://opencv.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-1.10+-EE4C2C?style=flat&logo=pytorch&logoColor=white)](https://pytorch.org/)

  **Frontend (Android)**

[![Android Studio](https://img.shields.io/badge/Android_Studio-2021.1+-3DDC84?style=flat&logo=androidstudio&logoColor=white)](https://developer.android.com/studio)
[![Java](https://img.shields.io/badge/Java-8+-007396?style=flat&logo=java&logoColor=white)](https://www.oracle.com/java/)
[![Firebase](https://img.shields.io/badge/Firebase-9.0+-FFCA28?style=flat&logo=firebase&logoColor=black)](https://firebase.google.com/)
[![Retrofit](https://img.shields.io/badge/Retrofit-2.9+-48B983?style=flat)](https://square.github.io/retrofit/)
[![OkHttp](https://img.shields.io/badge/OkHttp-4.9+-4479A1?style=flat)](https://square.github.io/okhttp/)


   **Database & Services**
   
[![Firebase Realtime DB](https://img.shields.io/badge/Firebase_Realtime_DB-FFCA28?style=flat&logo=firebase&logoColor=black)](https://firebase.google.com/products/realtime-database)
[![Firebase Auth](https://img.shields.io/badge/Firebase_Auth-FFCA28?style=flat&logo=firebase&logoColor=black)](https://firebase.google.com/products/auth)
[![Twilio SMS API](https://img.shields.io/badge/Twilio_SMS_API-F22F46?style=flat&logo=twilio&logoColor=white)](https://www.twilio.com/en-us/messaging/channels/sms)

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
5. [프로젝트 결과](#프로젝트-결과)
6. [기술적 도전과 해결](#기술적-도전과-해결)
7. [팀 및 기여](#팀-및-기여)
8. [라이선스](#라이선스)


## 프로젝트 소개


### 📚 2024 종합설계

본 프로젝트는 **2024년 한국공학대학교 종합설계**의 일환으로 진행되었습니다.

- **프로그램**: 한국정보산업연합회 주관 산학 협력 프로젝트
- **프로젝트 기간**: 2024년 3월 ~ 11월 (9개월)
- **팀 구성**: 4인 (전자공학과 졸업생)

---

###  📑 배경 및 필요성


스마트폰 보급 확대와 함께 청소년들의 Social Network Service(또는 Social Networking Service) 이용이 보편화되면서 유해 콘텐츠에 노출될 위험이 증가 하였다. 

특히 동영상 공유 기능을 매개로 한 유해물 유포는 청소년 정서에 치명적인 영향을 미치고 있으나, 서버 우회 및 개인 정보 보호를 보장하는 메신저 앱의 특성상 가해자 추적과 실효성 있는 대응에 한계가 명확하다. 이에 따라 유해 환경으로부터 청소년을 선제적으로 보호할 수 있는 보안 솔루션을 구현하고자 한다.

---

###  🎯 프로젝트 목표


YOLOv5 딥러닝 모델을 활용하여 메신저 앱에서 공유되는 동영상 속 유해 콘텐츠를 실시간으로 사전 차단하고, 보호자에게 자동 보고하는 통합 시스템 개발

**1️⃣ 높은 탐지 정확도 확보**

- 신뢰도 90% 이상에서만 탐지 작동
- 3프레임 연속 탐지 조건으로 오탐지 최소화

**2️⃣ 실시간 처리 성능 구현**

- 프레임별 객체 인식 및 즉각 대응
- Threshold Exit(유해물 3회 탐지 시 즉시 종료) 알고리즘으로 효율적 처리

**3️⃣ 보호자 연동 시스템 구축**

- SMS 자동 알림 기능 (Twilio API)
- 탐지 프레임 이미지 자동 저장

**4️⃣ 사용자 경험 최적화**

- 안전한 콘텐츠는 자유롭게 공유 가능
- 차단 시 명확한 피드백 제공

---

### 💡 프로젝트 차별점


**선제적 방어** : 사후 대응이 아닌 사전 차단

**탐지 대상** : 텍스트가 아닌 동영상 프레임 탐지

**이중 검증** : 높은 신뢰도 (90%)와 연속 프레임 탐지 조건으로 오탐지 최소화

**처리 속도** : 유해요소 3프레임 연속 탐지 시 즉시 중단(Threshold Exit) 하여 효율적 처리

**보호자 연동** : 유해 요소 탐지 시 SMS 전송으로 위험 상황에 즉각 대응 가능

**통합 솔루션** : 탐지 + 차단 + 보고 + 데이터 보관을 하나의 시스템에서 처리하는 Full-Stack 관리

**확장 가능성**: 다양한 SNS 서비스로 확장 가능한 구조

---

### 🎓 학습 목표

####  기술적 역량 강화

**1️⃣ 딥러닝 모델 활용 능력**

- YOLOv5 모델 학습 및 파인튜닝 경험
- PyTorch 프레임워크 이해 및 커스텀 데이터셋 구축
- 객체 탐지 알고리즘 원리 습득 및 모델 경량화 경험

**2️⃣ 풀스택 개발 경험**

- Android 앱 개발 (Java) 및 사용자 경험 (UX) 설계
- Flask 웹 서버 구축 (Python)
- Firebase 실시간 데이터베이스 연동

---

####  문제 해결 능력 강화

**1️⃣ 성능 최적화**

- Threshold Exit 알고리즘 설계로 컴퓨팅 자원 효율화

**2️⃣ 정확도 향상**

- 신뢰도 임계값 조정을 통한 정확도 최적화
- 연속 프레임 교차 검증 알고리즘 설계를 통한 오탐지 최소화 전략 수립

**3️⃣ 실무 프로젝트 경험**

- 요구사항 분석 및 설계
- 팀 협업 및 버전 관리 (Git)
- 문서화 및 발표 자료 작성

**4️⃣ 사회적 가치 실현**

- 기술적 능력으로 취약 계층에게 실질적인 안전 장치 마련

---

## 주요 기능

본 프로젝트는 다음 3가지 핵심 기능으로 유해 콘텐츠 차단 애플리케이션을 구현

**1️⃣ 실시간 유해 콘텐츠 탐지**

YOLOv5 기반 프레임별 객체 탐지 및 이중 검증

**핵심 기능**

| 기술 | 기능 | 설명 |
|:---:|:---:|:---:|
|OpenCV|프레임별 분석|동영상을 프레임 단위로 분해하여 분석|
|YOLOv5|객체 탐지|3개의 클래스(담배,칼,권총) 실시간 인식|
|Confidence Threshold|신뢰도 검증|90% 이상만 탐지로 인정|
|Threshold Exit|성능 최적화|3프레임 연속 탐지 시 차단|

**탐지 알고리즘**
```
카메라 입력 → OpenCV 프레임 추출 → YOLOv5 추론 
→ 신뢰도 검증 (≥90%) → 연속 탐지 확인 (3회) → 차단 결정
```

**신뢰도 검증 및 성능 최적화**
```python
CONFIDENCE_THRESHOLD = 0.9  # 90% 이상만 탐지
detection_count = 0
detected_class_names = set()

while cap.isOpened() and detection_count < 3:
    ret, frame = cap.read()
    if not ret:
        break
    
    results = MODEL(frame)
    detections = results.pandas().xyxy[0]
    
    for _, detection in detections.iterrows():
        confidence = float(detection['confidence'])
        
        if confidence >= CONFIDENCE_THRESHOLD:
            class_id = int(detection['class'])
            class_name = class_names[class_id]
            
            detection_count += 1
            detected_class_names.add(class_name)
            
            # 탐지 프레임 저장
            save_detected_frame(frame, class_name)
    
    # 3회 탐지 시 즉시 중단 (Threshold Exit)
    if detection_count >= 3:
        return block_video(detected_class_names)
```
**❗차단 로직**
```python
# 예시: 유해물 탐지 시
if detection_count >= 3:
    return {
        'objectDetected': True,
        'message': f"{', '.join(detected_class_names)}가 탐지되었습니다",
        'detected_frames': detected_frames  # 증거 이미지 경로
    }

# 예시: 안전한 콘텐츠
else:
    video_url = f"http://server_ip/uploads/{filename}"
    return {
        'objectDetected': False,
        'videoUrl': video_url,
        'message': "객체 감지를 완료했습니다."
    }
```
---

#### 📊 특징

-  **이중 검증**: 신뢰도 90% + 3프레임 연속 조건

-  **Threshold Exit**: 3회 탐지 시 즉시 중단으로 효율화

-  **자동 증거 수집**: 탐지 프레임 이미지 자동 저장

-  **오탐지 최소화**: 일시적 오검출 무시

---

#### 결과 처리 시나리오


**🚫 유해 콘텐츠 탐지 시**
```
동영상 전송 차단 → 채팅방에 차단 메시지 표시 → 탐지 프레임 이미지 자동 저장 → 보고서 전송
```

**✅ 안전 확인 시**

```
동영상 URL 생성 → 채팅방에 링크 공유
```
---

### 2️⃣ 채팅 통합 시스템

**핵심 기능**

| 기술 | 기능 | 설명 |
|:---:|:---:|:---:|
|Firebase Realtime DB|사용자 채팅 DB|텍스트 메시지 즉시 동기화|
|Firebase Auth|사용자 인증|닉네임 연동 채팅|
|Retrofit + OkHttp|동영상 업로드|Multipart 형식 파일 전송|
|ChildEventListener|메모리 관리|최대 100개의 메세지 기록|

---

**📤 동영상 업로드 프로세스**
```
[1단계] 사용자 갤러리에서 동영상 선택 (Intent.ACTION_GET_CONTENT)
   ↓
[2단계] InputStream으로 동영상 읽기 + Byte 배열 변환
   ↓
[3단계] Multipart 형식으로 Flask 서버 전송 (Retrofit)
   ↓
[4단계] 서버에서 YOLOv5 분석
   ↓
[5단계] 결과 수신 (JSON)
   ├─ objectDetected: true  → 차단 메시지 전송
   └─ objectDetected: false → 동영상 URL 전송
```

**🔧 메시지 처리 로직**
```Java
// Firebase 실시간 리스너
databaseReference.addChildEventListener(new ChildEventListener() {
    @Override
    public void onChildAdded(DataSnapshot dataSnapshot, String s) {
        ChatMessage message = dataSnapshot.getValue(ChatMessage.class);
        chatMessages.add(message);
        chatAdapter.notifyDataSetChanged();
        recyclerView.scrollToPosition(chatMessages.size() - 1);
        
        // 메시지 수 제한 (메모리 최적화)
        if (chatMessages.size() > 100) {
            String oldestMessageKey = dataSnapshot.getKey();
            databaseReference.child(oldestMessageKey).removeValue();
            chatMessages.remove(0);
        }
    }
});
```

**🌐 네트워크 통신 설정**

```python
// OkHttp 클라이언트 - 대용량 파일 지원
OkHttpClient client = new OkHttpClient.Builder()
    .connectTimeout(60, TimeUnit.SECONDS)  // 연결 대기
    .writeTimeout(60, TimeUnit.SECONDS)    // 업로드 대기
    .readTimeout(60, TimeUnit.SECONDS)     // 응답 대기
    .build();

// Retrofit API 인터페이스
Retrofit retrofit = new Retrofit.Builder()
    .baseUrl("http://192.168.x.x:80/")  // Flask 서버 주소
    .client(client)
    .addConverterFactory(GsonConverterFactory.create())
    .build();
```

#### 특징

-  **비동기 처리**: 동영상 업로드 중에도 채팅 가능
-  **ProgressDialog**: 업로드 진행 상황 실시간 표시
-  **에러 핸들링**: 네트워크 오류 시 명확한 피드백 제공

---

####  사용자 피드백 시나리오

**업로드 중**
```
ProgressDialog 표시 → "동영상 업로드 중..." 메시지
```

**차단 시**
```
"유해물이 감지되어 동영상 전송이 취소되었습니다" → 채팅방에 자동 전송
```

**성공 시**
```
"동영상이 채팅방에 전송되었습니다" → 링크 클릭으로 시청 가능
```

**실패 시**
```
"업로드 실패: 연결을 확인해주세요" → Toast 메시지 표시
```


### 3️⃣ 보고서 전송 시스템

Twilio API 기반 SMS 자동 발송 및 차단 콘텐츠 자동 수집

**핵심 기능**

| 기술 | 기능 | 설명 |
|:---:|:---:|:---:|
|Twilio API|SMS 자동 발송|보호자에게 실시간 알림 전송|
|OpenCV|프레임 저장|탐지된 프레임 이미지 저장|
|Python File I/O|로그 기록|탐지 정보 텍스트 파일 생성|
|UNIX Timestamp|시간 추적|탐지 시각 기록|

**SMS 자동 알림**

```python
from twilio.rest import Client

def send_sms_alert(parent_phone, detected_object, confidence):
    client = Client(account_sid, auth_token)
    
    message_body = f"""
[유해물 탐지 알림]
탐지 유해물: {detected_object}
신뢰도: {confidence:.2%}
시간: {datetime.now().strftime('%Y-%m-%d %H:%M:%S')}
증거: http://server_ip/report/{video_id}
    """
    
    message = client.messages.create(
        body=message_body,
        from_=twilio_number,
        to=parent_phone
    )

```

**차단 콘텐츠 저장 로직**

```python
def save_detected_frame(frame, folder_path, class_name):
    """탐지된 프레임 이미지 저장"""
    output_filename = f"detected_{class_name}_frame.jpg"
    output_path = os.path.join(folder_path, output_filename)
    cv2.imwrite(output_path, frame)
    return output_path

def save_detection_info(video_folder, detection_number, class_name, confidence):
    """탐지 정보 텍스트 파일 생성"""
    info_path = os.path.join(video_folder, f"detected_video{detection_number}_txt")
    with open(info_path, 'w', encoding='utf-8') as f:
        f.write(f"Frame {detection_number}: {class_name}가 탐지되었습니다. ")
        f.write(f"(인식률: {confidence:.2%})\n")

```

####  특징

-  **자동 알림**: 유해물 탐지 즉시 보호자에게 SMS 발송
-  **증거 보관**: 탐지 프레임 + 상세 로그 자동 저장
-  **보안 처리**: 처리 완료 후 원본 동영상 자동 삭제
-  **추적 가능**: 시간, 유해물 종류, 신뢰도 기록

---

####  보고서 생성 프로세스

```
유해물 3회 탐지 확인
   ↓
탐지 프레임 이미지 저장 (JPG)
   ↓
탐지 정보 텍스트 파일 생성 (TXT)
   ↓
보호자에게 SMS 자동 발송 (Twilio)
   ↓
원본 동영상 삭제 (보안)
```

---


## 시스템 아키텍처

### 시스템 구상도

<p align="center">
<img width="565" height="405" alt="image" src="https://github.com/user-attachments/assets/ceb26d64-d95b-490e-b426-c00905fc7a91" /></p>

<p align="center">
<img width="229" height="365" alt="image" src="https://github.com/user-attachments/assets/0dcc8d39-59b4-4e57-9ef2-53efa80fe349" /></p>


본 시스템에서는 단말기 간 이미지, 영상, 문자 등의 전송 과정에서 Flask 서버를 중개로 활용하여, 전달되는 콘텐츠 내부에 유해 요소가 포함되어 있는지 YOLOv5 AI 모델로 검사한다. 유해물이 3회 이상 탐지되면 전송을 즉시 차단하고, 사전에 설정된 보호자에게 Twilio SMS로 실시간 알림을 발송한다. 안전이 확인된 영상만 Firebase를 통해 채팅방에 공유된다.


※ 모든 성능 테스트는 Samsung Galaxy Z Flip 3 실 단말기 환경에서 수행되었습니다.

---

### 🤖YOLO 학습 모델

#### YOLOv5 선정 이유

| 비교항목 | YOLOv3 |YOLOv5 | YOLOv8 |
|:---:|:---:|:---:|:---:|
|출시일자|2018|2020|2023|
|처리속도|느림|빠름|빠름|
|정확도|보통|높음|매우 높음|
|모델 크기|240MB|M-41MB|M-52MB|
|학습난이도|어려움|쉬움|보통|
|커뮤니티|보통|활성|성장 중|

---

**1️⃣ 속도와 정확도 그리고 안정성의 균형**

- 실시간 처리를 위해 **빠른 추론 속도** 필수
- YOLOv5 모델은 m모델 기준 mAP(정확도) ~45.4% ,처리 속도 약 4.5ms로 v3모델에 비해 각각 1.5배 , 4.4배 향상
- YOLOv8 모델은 성능은 뛰어나나 연산 자원을 더 많이 요구하고 업데이트로 인한 라이브러리 충돌 위험 존재

**2️⃣ PyTorch 기반 학습 편의성**
- PyTorch로 구현되어 기존 Python 라이브러리와의 원활한 연동 가능
- 복잡한 환경 설정 없이 YAML 파일 수정만으로 커스텀 데이터셋 학습
- Early Stopping 기법으로 학습 중 과적합 방지 및 자원 낭비 방지

**3️⃣ 활발한 커뮤니티 지원**
- 튜토리얼 및 문제 해결 자료 풍부함
- v5 모델은 이미 전 세계 수만 개의 프로젝트에서 검증됨
- 에러 발생 시 Stack Overflow 혹은 GitHub Issue를 통한 해결방안 확보로 개발 리소스 최소화

**4️⃣ 접근성 및 배포**
- 모델 크기가 세분화(n,s,m,l,x)되어 하드웨어 스펙에 맞춰 자유로운 선택 가능
- ONNX나 TensorRT로의 변환으로 Flask를 비롯한 다양한 서버환경에 즉시 통합 가능
- **Google Colab** 에서도 구동 가능 

---

#### 📦데이터 셋

**데이터 셋 구성**

본 프로젝트는 아동 청소년 보호를 위해 영상 매체에서 노출 빈도가 높은 총기, 도검류, 담배 3종을 유해물로 지정하여 탐지 대상으로 선정하였다.

초기모델 구축과정에서 인터넷에서 사진을 긁어 라벨링을 하며 진행하였으나 더 많은 데이터셋을 확보하기 위해 Roboflow의 데이터 셋과 직접 촬영한 사진 100장을 포함해 약 26000장의 사진으로 YOLO nano, small, medium 모델을 위주로 다양한 batch와 80~120번의 epochs의 조건을 변경하며 모델 학습을 수행하였다. 

하지만 학습된 모델은 목표하던 90% 이상의 정확도에 달하지 못하여 데이터셋의 사진을 약 4만 장으로 늘리고 custom 데이터 셋의 품질을 높이며 다양한 batch와 overfitting이 되지 않을 정도의 학습 수를 고려하여 진행 하였다. 

<p align="center">
<img width="513" height="301" alt="Image" src="https://github.com/user-attachments/assets/97b18563-6bdf-4d47-a03b-05879c1784c8" ></img></p>

YOLO 의 Pretrained Checkpoints를 기반으로 성능과 속도 사이의 Trade-off를 분석하였다.
640px 입력 이미지 환경에서 모델 규모에 따른 성능 테스트에 따라 실시간 추론 속도를 유지하면서도 높은 검출 정확도를 보장하는 Medium 모델을 선택하였다.

---

**성능 지표**

데이터 셋과 변수들을 바꿔가며 시행착오를 거친 끝에
최종 구현된 모델은 mAP@0.5 기준 93.94%의 높은 정확도를 기록하였으며, 각 클래스별 predicted가 균일하게 0.9에 달하는 수치를 기록했다.

<p align="center">
<img width="628" height="417" alt="Image" src="https://github.com/user-attachments/assets/7acdf3a2-3627-4c95-b6ac-6c53291c5cac" ></img></p>

---

### 📱애플리케이션 개발

※ 모든 성능 테스트는 Samsung Galaxy Z Flip 3 실 단말기 환경에서 수행되었습니다.

이번 프로젝트에서는 다음 3가지 요소를 고려하여 Android Studio를 애플리 케이션 개발에 이용하였다.

---

1️⃣ 접근성

- Android 공식 IDE로 최적화된 성능 보장
- 동영상 및 갤러리 접근 용이
- RecyclerView, ProgressDialog 등 네이티브 UI 활용

2️⃣ Firebase 완벽 연동

- Firebase Realtime Database 공식 SDK 제공
- Google 공식 문서 및 샘플 코드 풍부
- Authentication, Storage, Cloud Messaging 통합 관리

3️⃣ 팀 개발 경험

- 팀원 모두 Java 기반 안드로이드 개발 경험 보유
- 학교 교육과정에서 Android Studio 사용
- 빠른 프로토타이핑 및 디버깅 가능

---

**주요 라이브러리**

```gradle
dependencies {
    // Firebase
    implementation 'com.google.firebase:firebase-auth:21.0.1'
    implementation 'com.google.firebase:firebase-database:20.0.3'
    
    // 네트워크
    implementation 'com.squareup.retrofit2:retrofit:2.9.0'
    implementation 'com.squareup.retrofit2:converter-gson:2.9.0'
    implementation 'com.squareup.okhttp3:okhttp:4.9.0'
    
    // UI
    implementation 'androidx.recyclerview:recyclerview:1.2.1'
    implementation 'androidx.appcompat:appcompat:1.4.0'
}
```

---

## 기술 스택

<div align="center">

  **Backend**
  
[![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=flat&logo=python&logoColor=white)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-2.0+-000000?style=flat&logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![Twilio](https://img.shields.io/badge/Twilio_SDK-F22F46?style=flat&logo=twilio&logoColor=white)](https://www.twilio.com/)
[![YOLOv5](https://img.shields.io/badge/YOLOv5-PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)](https://github.com/ultralytics/yolov5)
[![OpenCV](https://img.shields.io/badge/OpenCV-4.5+-5C3EE8?style=flat&logo=opencv&logoColor=white)](https://opencv.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-1.10+-EE4C2C?style=flat&logo=pytorch&logoColor=white)](https://pytorch.org/)

  **Frontend (Android)**

[![Android Studio](https://img.shields.io/badge/Android_Studio-2021.1+-3DDC84?style=flat&logo=androidstudio&logoColor=white)](https://developer.android.com/studio)
[![Java](https://img.shields.io/badge/Java-8+-007396?style=flat&logo=java&logoColor=white)](https://www.oracle.com/java/)
[![Firebase](https://img.shields.io/badge/Firebase-9.0+-FFCA28?style=flat&logo=firebase&logoColor=black)](https://firebase.google.com/)
[![Retrofit](https://img.shields.io/badge/Retrofit-2.9+-48B983?style=flat)](https://square.github.io/retrofit/)
[![OkHttp](https://img.shields.io/badge/OkHttp-4.9+-4479A1?style=flat)](https://square.github.io/okhttp/)


   **Database & Services**
   
[![Firebase Realtime DB](https://img.shields.io/badge/Firebase_Realtime_DB-FFCA28?style=flat&logo=firebase&logoColor=black)](https://firebase.google.com/products/realtime-database)
[![Firebase Auth](https://img.shields.io/badge/Firebase_Auth-FFCA28?style=flat&logo=firebase&logoColor=black)](https://firebase.google.com/products/auth)
[![Twilio SMS API](https://img.shields.io/badge/Twilio_SMS_API-F22F46?style=flat&logo=twilio&logoColor=white)](https://www.twilio.com/en-us/messaging/channels/sms)

</div>

---

## 프로젝트 결과

### 📋개발 결과

- 통합 보안 솔루션 구축: Android(클라이언트) - Flask(서버) - YOLOv5(AI) - Twilio(SMS)를 잇는 Full-Stack 유해 콘텐츠 차단 시스템 구현 완료.

- 실시간 대응 체계: 유해 요소 감지 시 즉각적인 전송 차단 및 증거 프레임 수집, 보호자 보고서 전송 프로세스 확립.

- 데이터 보안: 분석 완료 후 서버 내 원본 영상을 즉시 삭제하여 개인정보 유출 위험 최소화

---

### ✨성능 지표
| 비교항목 | 지표 |비고 | 
|:---:|:---:|:---:|
|정확도|mAP@0.5: 93.94%|담배, 칼, 권총 탐지|
|분석 속도|약 10초|30초 분량 영상 기준 초기 모델 대비 18배 단축|
|탐지 신뢰도|90% 이상|90% 미만은 미탐지 처리|

---

### 활용 분야

1️⃣ **가정 내 자녀 보호**: 청소년의 스마트폰 메신저 내 유해 매체 노출 선제적 방지.

2️⃣ **교육 기관**: 학교 및 학원 내 태블릿 PC/학습용 단말기의 유해 콘텐츠 필터링 솔루션.

3️⃣ **기업 보안**: 업무용 협업 툴 내 부적절한 이미지/영상 공유 차단 및 관리.

4️⃣ **커뮤니티 플랫폼**: 사용자 간 신뢰를 높이고, 건강한 소통 환경 조성

---

## 기술적 도전과 해결

###  정확도 향상
```
#문제점: 초기 26,000장의 데이터셋으로는 특정 조도나 각도에서 '담배'와 '볼펜'을 오인식하는 등 정확도 한계 발생.

#해결 방안:

- Roboflow 및 직접 촬영한 실전 데이터 100여 장을 추가하여 총 40,000장의 고품질 데이터셋 구축.

- 다양한 Batch size(16, 32)와 Epoch(80~120) 실험을 통해 Overfitting을 방지하며 최적의 가중치 도출.

- 단순 1회 탐지가 아닌 '3프레임 연속 탐지' 로직을 설계하여 일시적인 오검출(Noise)을 효과적으로 제거.
```
---

###  성능 최적화

```
#문제점: 사용자 단말-서버-A.I.로 이어지는 3중 통신 구조로 인해 서버 통신 과정에서의 네트워크 오류 발생 시 감지 기능 장애 가능성 및 모바일 환경에서 과도한 시간 소요

#해결 방안:

- Threshold Exit 알고리즘: 전체 영상을 분석하지 않고, 유해 요소가 3회 확인되는 즉시 분석을 중단하고 차단 결과를 반환하여 프로세스 시간 단축.

- 데이터 셋 최적화 및 모델 경량화로 30초 분량 영상 기준 처리 시간을 약 180초에서 10초로(약 18배) 획기적으로 단축

- 서버가 직접 유해물을 탐지하여 통신 시간 단축 및 백업 서버를 도입하여 시스템 안정성 강화
```

---

###  사용자 수용성 저해
```
#문제점 1 (기획 차별성 부족): 초기 기획인 'Whisper 모델을 통합한 음성 및 이미지 검열'은 기존 서비스와의 차별성이 부족하다는 피드백 수령

#문제점 2 (과도한 검열 우려): 메신저 내 영상 전송을 강제로 차단하는 방식이 사용자의 소통 자유를 제한하여 사용자 경험(UX) 저하 우려

#해결 방안:

- 핵심 가치 재설정: 사회적 이슈인 '청소년 유해물 노출 방지'에 집중, '선제적 차단'과 '보호자 알림'이라는 명확한 차별점 확보.

- 유해물 탐지 시 사용자에게 "유해 요소 탐지"라는 명확한 피드백을 제공하고, 보호자에게 SMS를 발송하여 신속한 사후 지도가 가능하도록 UX 설계.

- 유해물 탐지 시 사용자에게 경고 발송 및 SMS 전송 선택권 제공
```

---

## 팀 및 기여
|     성명    |  역할 | 담당 업무                                         |
| :-------: | :-: | --------------------------------------------- |
|  **임재혁**  |  팀장 | Android 애플리케이션 프론트엔드 개발      |
|  **장민혁**  |  팀원 | Flask 기반 웹 서버 구축 및 AI 연동            |
|  **조수연**  |  팀원 | 보고서 생성 및 Twilio 알림 시스템 구축   |
|  **진우열**  |  팀원 | Firebase 실시간 데이터베이스 및 채팅 시스템 구축 |
| **공통 업무** |  -  | YOLO 데이터셋 제작 및 모델 학습                |

---

## 라이선스

MIT License

Copyright (c) 2025 wooyeolj

본 프로젝트는 2024년 한국공학대학교 종합설계의 일환으로 진행되었습니다.

⚠️
본 소프트웨어는 연구 목적으로 제작되었으며, 실제 시스템에 사용되어서는 안 됩니다.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
