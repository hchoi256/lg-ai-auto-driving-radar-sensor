# Radar 제조 공정 (*LG 해커톤 과제*)

# 학습목표
- 자사(LG) 레이더 제품 소개 및 제조 공정 이헤
- 해커톤 과제 관련, **공정 인자와 수율의 관계**

> *공정 인자*: 제품이나 제조공정에 영향을 미치는 변수이다

> *수율*: 생산 과정을 통해서 제조된 제품들 중 합격품의 비율을 뜻합니다. 


# Radar 제품 소개
## In-Cabin 레이더 - 현대 자동차 ROA(Read Occupant Alert) 레이더

![image](https://user-images.githubusercontent.com/39285147/180612058-6356f98c-564a-41c7-a230-21ac0684a909.png)
![image](https://user-images.githubusercontent.com/39285147/180612067-455cf8db-4314-4e48-af9d-dcf918ec29c3.png)

In-Cabin 모니터링 시스템에서 카메라, 압력 센서, 초음파, 레이더 등 여러 가지 센서 기술들이 사용되고 있다.

> **ROA**: 차량 내에 장착하여 후석 승객 유무 감지

> SBR: 탑승자 위치를 정확하게 파악하는 기술
> ![image](https://user-images.githubusercontent.com/39285147/180612381-30f54750-1a56-4425-a243-45d78a09dc65.png)

### 각 센서 단점
**카메라**: 이불을 덮었을 때 보이지 않으며, 야간 탐지 능력이 저조하다. 또한, Privacy 문제가 존재한다.

**초음파**: 멀티 타겟 측정이 어렵다.

**압력센서**: 사람, 사물 구분없이 모든 물체의 무게를 감지한다.

> 이러한 각 센서들의 단점으로 레이더 센서의 개발 효용성에 관심이 쏠리고 있다.

# Process Flow (레이더 제품 조립 공정도 예시)
![image](https://user-images.githubusercontent.com/39285147/180612093-361d7ddb-824a-4446-9161-fe3f2fef45ce.png)

**ICT(In-Circuit Test)**: PCB의 테스트 포인트를 통해 SMT(Surface Mount Technology)된 각 부품의 RLC 값을 확인하여 불량을 검출한다.
- SMT 시 발생하는 Chip 누락, 용량 값이 다른 경우 불량을 잡아낼 수 있는 중요한 공정이다.

**F/W Down(펌웨어 다운로드)**: 레이더 제품 메모리에 펌웨어를 넣는 공정

**DC Test 공정**: 모듈이 제대로 동작하는지 입력 전원을 넣어 기본 기능을 확인

**PCB 분리(Routing)**: 커팅 방법에 따라 레이저/브레이드 방식이 존재한다.
- *레이저 공정* - 정밀한 가공 이물질 유입 방지 IC의 데미지를 주는 공정
- *브레이드 공정* - 그렇지 않은 경우 저렴한 브레이드 커팅 사용

> Printed Circuit Board (PCB): 회로기판
> ![image](https://user-images.githubusercontent.com/39285147/180612595-91cf105b-4062-4b43-8cee-d9ff70d0e06b.png)

**TIM(Thermal Interface Material) 공정**: 도포 면적, 도포량에 따라 발열 성능에 영향을 미치는 주요 공정

**Press-Fit**: 케이스 혹은 커넥터에 있는 PIN과 PCB를 연결하는 공정이다.

**Screw 체결 공정**: 주요 관리포인트 (Screw 높이, 토크)

**Sealant 도포**: 케이스 밀폐를 위해 진행하는 공

**Calibration EOL**: 공정 및 부품 특성을 반영하여 제품 성능에 영향이 없는지 최종 점검

**Labeling**: 제품 추적 관리를 위해 라벨 부착

# 가인자 공정
Clibration 공정 수율에 영향을 미친다

## TIM Dispensing
![image](https://user-images.githubusercontent.com/39285147/180612107-56e93652-38ca-439a-99ce-8a9a1a9b9ac0.png)

일부 부품의 발열을 확산시켜 열을 낮추고자 하는 목적으로 사용한다. 따라서, TIM 재질은 **열 전달률이 높을수록 좋으나** 가격이 높아 발열원에 따라 시뮬레이션을 통해 최적의 재료 선정이 중요하다!

TIM 재질은 실리콘과 같은 액상의 GAP Filler 또는 고체 시트 타입을 이용한다.

### TIM 직관
- 도포량 ↑ --> 제품 두께 ↑
- 일부면에만 도포량 ↑ --> 조립시 평판도 ↓ --> 제품 성능 ↓
- 필드에서 장시간 사용 ↑ --> TIM 내부 휘발성 기화 --> PCB 오염률 ↑

## Press-Fit
![image](https://user-images.githubusercontent.com/39285147/180612887-af79172f-0beb-49d2-b2c8-dccc03c8b3e4.png)

케이스에 있는 PIN과 PCB를 연결하는 공정으로 체결 압력에 따라 PCB 평탄도에 영향을 준다.

PCB 체결 시 평행하게 안착하는 기술이 핵심이다.
- 평행하게 안착되지 않으면 PIN이 휘거나 손상된다.

## Screw 체결
![image](https://user-images.githubusercontent.com/39285147/180612929-64f68dbc-052f-468b-81cf-c4b48b9b0568.png)

PCB가 평행하지 않으면 성능에 문제가 발생하기 때문에 적당한 압력으로 평평하게 Screw를 심을 필요가 있다.

> *LVDT*: 코일의 상호 유도 작용을 이용하여 직선 변위를 그것에 비례하는 전기 신호로 변환하는 센서

## Randome Assembly
![image](https://user-images.githubusercontent.com/39285147/180613008-575dfa12-5773-409d-acc9-73def6be332b.png)

Randome이 평행하게 조립되었는지 점검해야 한다.

## Calibration 공정
![image](https://user-images.githubusercontent.com/39285147/180613041-20a967ac-d4eb-4772-9c63-8f7ffbc3e50d.png)

Calibration 공정은 RFIC칩, PCB, 안테나 조립 과정의 오차 등에 의해 조금씩 다른 RF(전파) 성능이 편차가 없도록 목표한 값으로 동일하게 맞춰주는 과정이다.

> ![image](https://user-images.githubusercontent.com/39285147/180613171-19cf982f-d116-49ea-982b-89f5c04f511b.png)

### Calibration의 주요 RF 항목
- 각도 별
- 안테나 별 RF 신호 크기의 이상
- 각도 별 안테나 방사 패턴
- 국가 규격 항목
- etc.

## Test 공정

불량 확인 시 폐기하게 되므로 이 Test 공정의 수율이 가장 비용에 영향을 미친다.

실제 100~200 미터 떨어진 타깃으로 시험할 수 없어서, 레이더 타겟 시뮬레이터라고 하는 계측기를 이용하여 레이더에서 방사된 신호를 실제 100미터, 200미터 떨어진 거라에서 반사된 신호처럼 반사하여 이를 검사한다.

**RF 항목*들을 Chamber 내에서 레이더를 회전하면서 측정하게 된다.

## Test 주요 RF 항목
- 여러 개의 타깃들의 각도 및 거리 탐지 성능
- 움직이는 타깃에 대한 위치 및 속도

> Calibration & Test
> ![image](https://user-images.githubusercontent.com/39285147/180613414-27496f62-ee35-45fb-b080-c5a5fcb5785d.png)
>
> 로봇 arm을 활용한 방식을 최초로 LG가 고안하여 사용하고 있다. 로봇 사용 시 정밀하고 빠른 이동과 보정이 가능하다.

# 해커톤 과제
**Cal 공정 불량 자동화 시스템**을 DX(Digital Transformation) 과제로 추진하고 있고, 이번 해커톤과 연계하여 추가적인 아이디어를 발굴하고자 한다.

기본 목표는 **조립 공정에서 세팅한 값 X 인자에 따른 최종 RF 성능의 결과값 Y 인자를 분석하는 것**이다 (*회귀-->예측?*)

이를 통해서 **입력 데이터와 출력 데이터 사이의 관계**를 모델을 사용하여 추론하고, **특정 기간 동안의 성능의 불량이 상승하거나 이상 발생 시 공정 데이터의 변화를 같이 분석하여 불량의 원인이 되는 공정을 같이 분석하여 불량의 원인이 되는 공정을 빠른 시간 내에 개선하는 것**이 최종 목표이다.


## Cal 공정 불량 자동분석 시스템
![image](https://user-images.githubusercontent.com/39285147/180613463-7647b78c-a1d0-4fe0-8bce-d4d789d2f46e.png)

Ass`y 공정의 X 인자의 개수는 18개이고, CAL/EOL(Calibration) 공정의 성능인 Y값의 개수는 1727개이다.

생산 시 서버의 X,Y 값을 활용하여 그 상관관계를 분석하고, 회귀식과 같은 상관관계 모델식을 도출하여 Y항목이 불량치를 상하한치 범위를 넘어가기 전에 불량 공정을 미리 차단할 수 있다.

궁극적으로, Cal 공정 시스템이 구축되면 불량을 0로 관리하여 cost를 줄일 수 있다. 또한, 신규모델 셋업시간이 단축되고 초기 불량률 관리가 가능하다.

# Summary
1. LG이노텍 Radar 제품 소개
2. Radar 수율에 영향을 미치는 가인자 공정
3. Cal 공정 불량 자동분석 시스템 이해 (해커톤 과제 연계)
