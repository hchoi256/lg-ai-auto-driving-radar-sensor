
****
### Terms
- Learning rate
- Batch gradient descent
- Stochastic gradient descent (SGD)
- Avoid local minimum
  - Momentum
    - SGD w/ momentum
    - Nesterov momentum
  - Adaptive learning rate
    - AdaGrad
    - RMSProp
    - Adam
- Avoid overfitting
  - Reduce number of features
  - Regularization

![image](https://user-images.githubusercontent.com/39285147/182006560-b09a3593-7253-44b7-9bde-dd6a76715d49.png)

# Gradient Discent
![image](https://user-images.githubusercontent.com/39285147/178204718-740c117e-9d6b-42d5-b8b3-d6fca3a11539.png)

함수의 기울기(경사)를 구하여 기울기가 낮은 쪽으로 계속 이동시켜 극값(최적값)에 이를 때까지 반복하는 것이다.

## α 분석
![image](https://user-images.githubusercontent.com/39285147/178205637-d9eb211b-7446-47e1-b8ac-80517a48e97e.png)
![image](https://user-images.githubusercontent.com/39285147/178215771-05118421-8003-41c3-b31a-a45d3d221b38.png)
![image](https://user-images.githubusercontent.com/39285147/178207012-14d61f86-9ce7-4729-95f0-59391bfd5c58.png)
- If α is too small, gradient descent can be slow.
- If α is too large, gradient descent can overshoot the minimum. It may fail to converge, or even diverge.

# Batch gradient descent
![image](https://user-images.githubusercontent.com/39285147/178205619-416efefb-c227-4bfc-9744-fb8a32b89fb6.png)

적절한 크기의 α을 사용한 것과 같은 효과

## BGD 한계와 해결
데이터가 1000개 있을 때 모든 데이터에 대하여 각각 Loss function을 계산하고, 그들의 기댓값을 오차(ε)로 하고, 그 오차를 최소화시키는 방향으로 weight들을 업데이트한다.
- 피라미터 한 번 업데이트 하기 위해서 전체 데이터 참조해야 함.
  - **SGD*
- 여전히 Local optimum 취약
  - **담금질 기법*

# Stochastic gradient descent(SGD)
데이터가 1000개가 있을 때 무작위로  데이터에 대하여 Loss function을 계산하고, 그 함수를 최소화하는 방향으로 W를 업데이트한다.

## SGD 한계와 해결
BGD에 비해서 빠르게 반복을 수행하지만, 각 샘플 하나씩 연산을 하므로 noise 발생 염려가 있다.

# Local Optimum
![image](https://user-images.githubusercontent.com/39285147/178206735-ddc68470-1777-4070-941d-a36515d94e4b.png)

Cannot guarantee global minimum but attempt to find a good local minimum

# BGD vs. SGD
![image](https://user-images.githubusercontent.com/39285147/178208693-eedf1b4f-7ddd-49b9-9314-6c3a12b407da.png)

**BGD**
- 정확도 ↑, 성능 ↓
  - Optimal 수렴 안정적
- Local optima 빠질 가능성 ↑
- GPU 활용 병렬처리 유용, 메모리 多

**SGD**
- 정확도 ↓, 성능 ↑ (*속도때문에 사람들이 선호함*)
  - 경우에 따라 Optimal 수렴 안 됨
- Local optima 빠질 가능성 ↓ (BGD에 비해 상대적으로)
  - Shooting(요동치는 것) 때문에 local optima에 잘 안 걸려든다.
- GPU 전부 활용 X

# Avoid local minimum
## 1. Momentum - 속도를 최대한 빠르게 한다.

### *Exponentially Weighted Moving Average (low pass filtering)*
![image](https://user-images.githubusercontent.com/39285147/178209601-d13783cc-f1e9-4a6c-bfb2-0e87bf1a7c45.png)

과거에 Gradient가 업데이트 되어오던 방향 및 속도를 어느 정도 반영해서 현재 포인트에서 Gradient가 0이 되더라도 계속해서 학습을 진행할 수 있는 동력을 제공하게 되는 것
- 0 < p < 1 이므로, p를 지수 형태로 표현하면서 과거 gradient일수록 더 적은 velocity 작용을 하게 만든다.

### 1-2) SGD w/ Momentum
![image](https://user-images.githubusercontent.com/39285147/178211019-b114666e-6ccb-46a6-85e5-8f2f8d8a7ce8.png)
![image](https://user-images.githubusercontent.com/39285147/178210873-6a8d7eba-75c0-4721-a9b5-b93c9021b56a.png)

![image](https://user-images.githubusercontent.com/39285147/178211458-56b05f61-6bcb-4594-a19a-8b0deba10dea.png)

모멘텀 SGD는 경사 하강법에 관성을 더해 준다.
- Use a velocity as a weighted moving average of previous gradients

### 1-2) Nesterov Momentum
![image](https://user-images.githubusercontent.com/39285147/178213239-b701b895-8edb-4814-b511-8c596611d83a.png)

"lookahead" gradient step
- 현재 위치에서 momentum step을 이동한 위치에서 구한 gradient 값
- 어떤 방식으로 이동할지를 결정하므로 유동적인 이동이 가능 (> Momentum)

## 2. Adaptive learning rate - 방향을 최대한 일직선으로
### 2-1) AdaGrad
![image](https://user-images.githubusercontent.com/39285147/178212884-ffb13162-271f-483d-bb8d-6846dff8f323.png)

각 방향으로의 learning rate를 적응적으로 조절하여 학습 효율 ↑
- Slow down the learning rate when an accumulated gradient is large
- Speed up the learning rate when an accumulated gradient is small

#### AdaGrad 단점
누적에 따라 learning rate 값이 작아지게 된다.
- 학습이 발생하지 않음

### 2-2) RMSProp
RMSProp attempts to fix the drawbacks of AdaGrad, in which the learning rate becomes infinitesimally small and the algorithm is no longer able learning when the accumulated gradient is large.

![image](https://user-images.githubusercontent.com/39285147/178213603-081c4d32-b90c-43c6-b09c-fcb9c7ca92d6.png)
- r의 값을 과거에 r만큼의 p factor를 곱해서 어느 정도 조절하는 과정을 통하여 AdaGrad에 비해 더 천천히 학습 속도가 줄어드는 효과를 볼 수 있다.

### 2-3) Adam (adaptive moment estimation) : RMSProp + momentum
![image](https://user-images.githubusercontent.com/39285147/178214234-b3e71ec1-3f7b-473b-bcbc-fe1a88ec53ba.png)

> [Comaprison animation: gradient descent algorithms](https://miro.medium.com/max/1240/1*XVFmo9NxLnwDr3SxzKy-rA.gif)

****
# [Avoid Overfitting](https://github.com/hchoi256/ai-terms/blob/main/overfitting.md)
![image](https://user-images.githubusercontent.com/39285147/178215927-55946b76-6d10-43cd-b716-c2030e4a66dc.png)

More features → more parameters →need more data ; (in practice) less data → overfitting → MSE is sensitive to outliers

# Quiz
![image](https://user-images.githubusercontent.com/39285147/178216852-933cd1f7-f509-4f07-b446-e03a24e3de7c.png)

# Note
Optimization in general ML/DL
- Mostly SGD used in general ML/DL
  - Several limitations..
- **Adam** is a good default choice in most cases
