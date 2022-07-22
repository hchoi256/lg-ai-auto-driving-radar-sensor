# Radar 제품 이해

# 학습목표
- Radar의 기본이론과 특장점
- 어플리케이션 별 사용되는 레이더 종류와 레이더 필요 기술이 무엇인지 학습

# Radar 이해
## Radar란?
- Radar 는 **Ra**dio **D**etection **A**nd **R**anging 의 약어이며 *Radio Wave* 를 이용한 사물 감지하는 기술
- 차량 Radar 는 차량 보행자 도로 인프라를 인식하여 차량과의 거리 , 상대속도 , 각도 , 높이 등의 정보를 수집

> *군사용 레이더*: 사격통제 장치에서 10GB Hz 엑스밴드 주파수를 사용하고 있었지만, 점차 주파수 버뮈를 높고 낮게 사용하는 기술로 발전

> *IoT 레이더*: 주로 24GB, 60GB 주파수를 사용한 보안용 침입감지, 독거노인 움직임, 심호흡 감지, 낙상감지, 재실감지 등 헬스케어용으로 사용

> *자동차용 레이더*: 주로 77GB~79GB의 주파수를 사용하고, 최근 카메라 라이다 등과 함께 자율주행의 핵심 부품으로 자리매김 했다.

> *ADAS용 레이더*: 차량 앞뒤 범퍼에 설치되어 차량, 보행자, 도로 인프라를 인식한다.

## 거리 측정
![image](https://user-images.githubusercontent.com/39285147/180578765-e556095b-90e6-424f-8cb6-9cc1ed3b6144.png)

> *ToF*: 타겟을 맞고 반사되어 돌아온 수신 전자파 신호의 시간 차

![image](https://user-images.githubusercontent.com/39285147/180579019-936333ba-3e02-41c9-94f6-c732597be22d.png)

> *Pulsed radar*: 진폭을 높여서 신호를 멀리 보내는 군사용으로 많이 사용한다.
>
> *FMCW*: 시간에 따라 선형적으로 변하는 삼각파 형태의 Chirp 신호를 내보내고 상대물에 반사되어 돌아오는 신호를 받는다. 이론적으로 사각지대가 없고, 낮은 출력 전력, 낮은 하드웨어 복잡성, 저렴한 제조 비용으로 상업용으로 많이 사용한다.

## 속도 측정
![image](https://user-images.githubusercontent.com/39285147/180578820-e880f4fa-c668-45dc-a671-380faa7aba76.png)

**도플러 주파수**란 반사되어 돌아오는 신호의 주파수를 분석해보면 기존 송신 주파수와 차이가 발생하는데 이를 도플러 주파수이고, 도플러 효과라 지칭한다 (FMCW).
- 상대물이 다가오면 도플러 주파수가 높아지고, 멀어지면 낮아진다.
- 상대물의 속도가 늦으면 도플러 주파수는 작아진다.

> *ToF*: 타겟을 맞고 반사되어 돌아온 수신 전자파 신호의 시간 차

## 각도 측정
![image](https://user-images.githubusercontent.com/39285147/180579198-64773973-f47f-4114-af35-d72211510698.png)

Array 안테나로 송수신되는 신호의 **위상차**를 이용해 상대물의 각도나 위치 정보를 알 수 있다.
- 레이더 안테나는 주로 Array 배열 구조를 사용하는데, 안테나 배열 수가 많을수록 빔 폭이 sharp 해져서 상대물의 각도 정보를 확인 가능하다 (= **각 해상도가 높다**).

## 레이더 핵심 기술
![image](https://user-images.githubusercontent.com/39285147/180579463-aca8e3cc-6fd8-4824-b753-1cd22c2f2aa0.png)

안테나, mmWave회로, 신호처리, 후처리 판별 알고리즘 PCB, 제조공정 Clibration SW 기술

> *Adaptive Cruise Control*: 주로 고속도로에서 Smart Cruise에 사용

> *Automatic Emergency Breaking*: 충돌 방지를 위해 사용된다.

# Radar 종류
![image](https://user-images.githubusercontent.com/39285147/180579563-7de16e11-cacc-48a2-9142-03f24e70a8f4.png)

# Radar 기술 동향
![image](https://user-images.githubusercontent.com/39285147/180579588-9758638f-94b2-489e-964d-50fa049a8b7c.png)

레이더 기술은 2022년 현재 2D/3D에서 4D로 진화중이다.
- 현재 차량에는 주로 2D 레이더가 장착되고, 거리 속도를 측정한다.
- 3D 레이더는 거리, 속도, 각도를 측정한다.
- 4D 레이더는 거리, 속도, 높이까지 측정하여 **사물의 형체 파악**이 가능하다 (자율주행 Lv. 4에 필수적이다).


# Radar 칩셋
![image](https://user-images.githubusercontent.com/39285147/180579638-9389f849-3b29-4a0d-9428-34aca833a59c.png)

# Radar 시장 동향
[*시장 규모*]

![image](https://user-images.githubusercontent.com/39285147/180579708-7fc50202-c844-4bd2-8275-e0d9486eae21.png)

- 차량 제어를 위해 AEB 기능 채용 확대
  - 일본 `20 년 / EU `22 년 이후 신차 AEB 의무 장착
  - 북미 `22 년 부터 OEM 의 신차 AEB 장착 합의
- Front Radar 의 고해상도化로 채용률 성장
- Corner Radar 의 Low Cost 化
  - 차량당 4 개 이상 적용되어 360 도 서라운드 센싱
- 안전과 편의 기능으로 강화를 위한 In Cabin 용 신규 Application 개화

# Summary
1. Radar 이해에서 거리 , 속도 , 각도 측정 방법
2. Radar 필요기술은 안테나 , mmWave 회로 , SW, 기구 , PCB, 공정설계
3. Radar 종류는 SRR, MRR, LRR 이고 향후 4D Imaging Radar 로 고도화
4. 차량용 Radar 는 Infineon, TI, NXP 가 주로 사용
