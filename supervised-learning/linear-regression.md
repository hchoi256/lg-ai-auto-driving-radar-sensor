****
### Terms
- Linear regression
- Parameter optimization
  - Normal Equation
  - Gradient descent
    - Greedy algorithm

# Linear Regression
![image](https://user-images.githubusercontent.com/39285147/178196382-56e8a8fd-093e-4632-9213-13f6f4ebe595.png)

연속되는 출력을 예측을 하고 추론하기 위한 방법

## Linear Models
![image](https://user-images.githubusercontent.com/39285147/178196415-38fd2c92-35ea-4e1a-896e-e1735c78019d.png)
![image](https://user-images.githubusercontent.com/39285147/178196701-ce862dc2-fa03-4c3f-a99c-bd71596d1655.png)
- 모델 함수(h)에 대해 피라미터(세타)가 선형적인 관계에 있다.
  - 선형 모델이라고 해서 반드시 입력 변수(x)에 선형일 필요는 없다

## Example
![image](https://user-images.githubusercontent.com/39285147/178196746-f5335637-1b0b-42db-83cb-fd118eb65786.png)
- **Univariate Problem**(단변량)
- **Multivariate Problem**(다변량)

## Linear regression framework
![image](https://user-images.githubusercontent.com/39285147/178196979-fc670ef5-27ba-4492-b1e6-83199c0b4c75.png)
- **단변량인가?**
  - If yes, univariate linear model
- **Predictor Loss 평가**
  - MSE 최소화
- **Optimization**
  - Gradient descent algorithm
  - Normal equation

****
# 피라미터(세타) 최적화
![image](https://user-images.githubusercontent.com/39285147/178197289-7fc887bf-df07-435c-88e6-b7170f719e4e.png)
![image](https://user-images.githubusercontent.com/39285147/178197351-fd667f82-cb93-4099-867b-83de0bc62b75.png)
- 세타 값에 따라, fitted line과 등고선이 변한다; 등고선에서 손실 함수(J)가 가장 **최소**가 되는 지점을 찾는 것이 목표.
  - 최적화 피라미터는 cost function을 가장 최소화 하는 것에 목표가 있다.

![image](https://user-images.githubusercontent.com/39285147/178197438-e087d643-4d00-418f-9d55-0f245fca7ca7.png)
![image](https://user-images.githubusercontent.com/39285147/178197453-f78b90b1-1cda-4a17-bda1-8aac60f1bec6.png)
- 피라미터(세타) 값을 조정하며 가장 fit이 잘 되었을 때 등고선의 정중앙에 최소 지점에 도달하는 것을 확인할 수 있다.

## 피라미터-입력피처의 관계
![image](https://user-images.githubusercontent.com/39285147/178197965-dddabfee-38bb-4b38-89a4-2f1103915f90.png)

피라미터(= 가중치)는 입력 피처가 최종 출력에 끼치는 영향력을 조절한다.
- **score*(=모델출력): ![image](https://user-images.githubusercontent.com/39285147/178202928-b38b1b04-f842-4ac1-8053-dfc9791dda50.png)
- **MSE*: ![image](https://user-images.githubusercontent.com/39285147/178202939-068fed18-542f-4e13-9dc3-430b244c81ee.png)

## 1. Getting a solution 𝜽: *Normal Equation (Least Square)*
![image](https://user-images.githubusercontent.com/39285147/178198986-a37ff222-2855-4be6-8692-cea698ad4545.png)
![image](https://user-images.githubusercontent.com/39285147/178199510-7833b730-c9b1-47d9-9460-6081fb205534.png)
<details markdown="1">
<summary>유도과정(접기/펼치기)</summary>

![image](https://user-images.githubusercontent.com/39285147/178199284-1f7c237b-2917-4c42-a3e6-be51920e63af.png)

</details>

- **Normal Equation*: 네모박스 방정식
- **Least Square*: 추론 과정
  - 피라미터를 포함한 수식의 미분값이 0이 되는 지점(= 최소 손실)의 피라미터 값을 구하는 방법
  - Assuming that 𝑬 is **continuous, differentiable, and convex**

### Normal Equation 한계점
- **데이터 샘플 숫자가 늘어나는 경우 비효율적이다.**
  - N(샘플 개수)가 늘어나면 역함수 연산 과정이 매우 복잡해지기 때문이다.
- **역행렬이 존재하지 않는 경우**
  - *Iterative algorithm (Gradient descent)* 로 해결

## 2. Getting a solution 𝜽: Gradient descent
![image](https://user-images.githubusercontent.com/39285147/178201137-419c43bf-b1bb-46f2-be40-72bc3545b194.png)

Error surface에서 최소의 에러 포인트(*gradient = 0*)를 찾아가는 과정
- Gradient(함수 변화도)가 가장 큰 방향으로 이동 (산 정상에서 가장 빠르게 하산하려면 가장 큰 폭으로 내려오는 것과 같은 이치)

## Gradient descent algorithm
![image](https://user-images.githubusercontent.com/39285147/178201002-c7ddd4cb-91d9-474e-9b6b-5d5160154221.png)

초기 피라미터에서 시작하여 목적함수(J)가 수렴할 때까지 Iterative하게 피라미터를 바꿔가면서 최적 피라미터를 찾는다.
- 𝛼 ↓: 최적 피라미터 찾는 과정 오래 걸림
- 𝛼 ↑: 최적 피라미터(gradient = 0) 놓칠 가능성 多 

#### Formular
![image](https://user-images.githubusercontent.com/39285147/178201318-f613c2e7-318b-4f74-b3b5-e160c2bf7b01.png)

<details markdown="1">
<summary>피라미터 업데이트 과정(접기/펼치기)</summary>

![image](https://user-images.githubusercontent.com/39285147/178202131-0583c718-48a0-4cbf-b112-68b4c0ce4ce0.png)
![image](https://user-images.githubusercontent.com/39285147/178202146-5409a272-42a9-49a5-80e7-8711bc189ff8.png)

</details>

- *Hyper parameter*: 사전에 설정된 값들(i.e., 𝛼)로 항상 양수이다.
- *Learnable parameter*: GD를 통해 학습하고자 하는 것(i.e., 피라미터)

### Greedy algorithm
Gradient descent algorithm에서 경우에 따라 Local optimum에 도달할 가능성 존재
- **Local optimum*
- **Global optimum*

## Gradient descent algorithm vs. Normal equation
![image](https://user-images.githubusercontent.com/39285147/178202658-345986db-2484-42e5-be37-c63ed9993736.png)

### Gradient descent 한계
![image](https://user-images.githubusercontent.com/39285147/178202611-07ed6ee4-54ce-49b2-8d60-6f15d75dfff2.png)
1. Local minima
2. Saddle points

### Gradient descent 해결
4. Stochastic gradient descent(SGD)
5. Mini batch

****
# Quiz
![image](https://user-images.githubusercontent.com/39285147/178202712-138468c8-3593-452e-8b5d-dce64e2d6656.png)
