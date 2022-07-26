# PART 1: 차량용 센서 종류와 장단점
![image](https://user-images.githubusercontent.com/39285147/180980701-44d29fd3-f7f5-402a-8e5e-0d3d0770f510.png)

# PART 2: 레이더 기본 원리와 부품 구성
## 레이더 기본 원리
![image](https://user-images.githubusercontent.com/39285147/180981499-d1902966-a297-4e02-b1a7-2f300de95019.png)

*GPS*란 30개 안팎의 위성으로 구성되어 있다.

위성으로부터 신호를 받으면 신호가 도달하는 시간으로 거리를 알 수 있으며, 3개 이상의 위성으로부터 신호를 받으면 현재 수신기의 위치를 특정할 수 있다 (각도 등 계산).

GPS처럼 차량용 레이더는 전파를 쏘고 되돌아오는 신호를 통해 물체를 감지하여 대상의 거리, 각도 및 속도를 측정한다.

이때, 여러 개의 송신 안테나와 수신 안테나를 조합해서 사용하면 여러 개의 GPS 위성과 같은 효과를 끌어내 해상도가 향상된다.

> 그림에서 TX1-3은 송신 채널이고, RX1-4는 수신 채널이다. 이 방법을 통해 해상도 향상을 도모한다.

## 레이더 부품 구성
- **레이돔(Radome=Radar+Dome)**: 레이더를 보호하는 덮개 역할로, 전파의 투과 특성이 우수한 재질로 만들어야 한다.
- **Shielding**: 열이 많이 발생하는 RF PCB의 단점을 보완하고자 Shielding을 통해 열을 분산시킨다.

### RF PCB와 DSP PCB 기판을 분리
![image](https://user-images.githubusercontent.com/39285147/180981769-9761a8ea-de8c-4722-b670-9a06ef2ac090.png)

### RF PCB와 DSP PCB 기판 하나로 합치기
![image](https://user-images.githubusercontent.com/39285147/180981896-a51dcd17-6542-4da1-970c-b83964c72aec.png)

# PART 3: 일반적인 레이더 양산 공정 과정
## 1. TIM 도포 과정
![image](https://user-images.githubusercontent.com/39285147/180983152-1665f7e3-b723-436b-bb6c-60e5b79a5c7b.png)

열이 많이 나는 소자와 실딩 사이 TIM을 디스펜싱 머신으로 도포해주는 공정이다.

TIM 용액의 양과 도포된 면적을 관리한다.

## 2. PCB 얹기 과정
![image](https://user-images.githubusercontent.com/39285147/180983247-15733712-ca99-418c-b2ea-881d048a207f.png)

도포 후 PCB를 놓는 공정이다.

## 3. 프레스핏(Press-fit) 과정
![image](https://user-images.githubusercontent.com/39285147/180983355-1870ee03-cbcb-47f3-b38e-f04e991dd4ee.png)

PCB를 정해진 힘으로 눌러서 커넥터 Pin 삽입하는 공정이다.

커넥터와 같은 부품은 자동으로 납땜하는 과정이 힘들어서 해당 과정이 필수적이다.

## 4. 스크류 조립 과정
![image](https://user-images.githubusercontent.com/39285147/180983529-15868be1-7ab6-4fa9-b99b-f9dfd1a15c84.png)

PCB가 단단히 고정되도록 나사 체결하는 공정이다.

*체결토크*, *회전수*, *체결 시간*에 대해 확인 및 기록한다.

## 5. Sealant 도포 과정
![image](https://user-images.githubusercontent.com/39285147/180983738-934c57c2-77fd-415c-bc99-90e090dbf2dc.png)

방수 성능 만족을 위해 Sealant, 본드 성분으로 밀폐되도록 도포하는 공정이다.

## 6. 레이돔 조립 과정
![image](https://user-images.githubusercontent.com/39285147/180983905-e6ec54db-ffe5-49af-bf3d-ae62f42bce39.png)

레이돔을 조립하고 평탄도를 검사하는 공정이다.

레이돔은 레이더 전파 신호의 감쇄가 적으며 이물질이 잘 묻지 않는 특성을 가지면 좋다.

## 7. Calibration
![image](https://user-images.githubusercontent.com/39285147/180984168-f78fbe77-3282-4b22-bad9-70b1ce29fa33.png)

상기 6단계 공정 이후, PCB나 RF 부품, 하우징 조립 등에 의해 제품마다 일반적으로 큰 편차가 발생한다.

이러한 편차를 줄이는 방법으로 Calibration 과정을 거쳐서 레이더의 수평/수직 시야각 범위에서 안테나 성능을 균일하게 보정한다.

실제 상황에 대하여 테스트할 수 없기에, 로봇이 챔버(방)내에서 제품을 여러 방향으로 회전시키며 레이더와의 상호작용을 검사한다. 
