****
### Terms
- Advanced Classification
  - SVM
  - NN

# ANN
![image](https://user-images.githubusercontent.com/39285147/178767972-0c4f50b4-fe8b-410c-b0e2-991b81e40c9c.png)

# Problem Domain
![image](https://user-images.githubusercontent.com/39285147/178758777-4a467cce-9d42-485d-8068-096dc94d5ec1.png)

서로 다른 분류선들을 학습데이터에 대하여 훌륭하게 분류를 해냈지만, 실샐활에 적용했을 때는 다양한 종류의 sample들이 해당 분류선들로 하여금 다른 성능을 끌어낸다.

# Support Vector Machine (SVM)
![image](https://user-images.githubusercontent.com/39285147/178759917-17b6d70d-5c49-45ff-a13b-e3a24e494d39.png)

Maximum margin hyperplane with support vectors
- Robust to outliers

> **Support vector*: an instance with the minimum margin, which will be the most sensible data points to affect the performance

## Margin
![image](https://user-images.githubusercontent.com/39285147/178760628-3ff33e56-e93a-4c7c-b309-e5ee7425c1c7.png)
![image](https://user-images.githubusercontent.com/39285147/178760767-9915ecd4-9605-4569-91cf-33e9bd7ea98e.png)

Twice the distance from the hyperplane to the nearest instance on either side

𝑤 is orthogonal to the hyperplane

<details markdown="1">
<summary>Margin Distance(접기/펼치기)</summary>

![image](https://user-images.githubusercontent.com/39285147/178761055-d0eaaf0f-f7d9-48a1-8d1d-49959d0a59a2.png)

</details>

## Optimization
### 1. Hard margin SVM
![image](https://user-images.githubusercontent.com/39285147/178762447-30739e0a-ad58-46f7-a985-0b7ed11763bb.png)

Assumes linear separability

#### Constraints
![image](https://user-images.githubusercontent.com/39285147/178762996-62a0fcd6-ee7f-4960-aef9-7f083ca91f21.png)

### 2. Soft margin SVM
![image](https://user-images.githubusercontent.com/39285147/178763343-61e4ee2e-6ff6-4270-85d7-fb24c8e8b768.png)

Extends to non-separable cases

### 3. Nonlinear transform & kernel trick
![image](https://user-images.githubusercontent.com/39285147/178763530-2e4b28b7-b553-4bec-9a42-670a5b10f11d.png)

Linearly sepable하지 않은 data sample들이 있다고 할 때, 그 차수를 높여 linearly sepable하게 만드는 과정.

#### Types of Kernels
![image](https://user-images.githubusercontent.com/39285147/178763662-4a870457-2ed7-4a06-a6ab-bae89e0a8d71.png)

<details markdown="1">
<summary>RBF(접기/펼치기)</summary>

![image](https://user-images.githubusercontent.com/39285147/178763860-50afdbe6-c92a-4316-8775-fac71ed76379.png)

</details>

# Artificial Neural Network (NN)
![image](https://user-images.githubusercontent.com/39285147/178764237-7dbf7df9-5de8-40be-8a8a-2b7d4d45a650.png)

결이 다른 Classifier (Nonlinear Classification Model)

Deep Neural Network (DNN)의 기본

### Activation Function
![image](https://user-images.githubusercontent.com/39285147/178764776-60aad5a1-f818-4d7a-8154-427e18a5a73a.png)

Score값을 Sigmoid와 같은 함수에 넣어 Nonlinear 연산을 수행하는 함수

> *ReLU*: 학습을 수행함에 따라 Gradient 값이 0으로 수렴하는 Sigmoid와 달리 미분값이 1로 고정되어 꾸준히 학습이 가능한 ReLU

## Deep Neural Network (DNN)
![image](https://user-images.githubusercontent.com/39285147/178765564-08e48085-8e5f-48eb-9d98-6d16053c357d.png)

상기 ANN에 계층을 깊게 쌓으면 DNN이 된다. DNN는 각각의 계층에 따라서 학습을 하게 되는 feature의 형태가 달라진다.

이러한 Nonlinear 함수들이 계층적으로 쌓여가면서 signal spade와 같은 복잡한 신호들의 패턴들을 조금 더 정확하게 분류 가능하다.

## Multilayer Perceptron (MLP)
![image](https://user-images.githubusercontent.com/39285147/178765768-20a0994b-2e3c-4fde-9473-ee22fd4cfc6d.png)
![image](https://user-images.githubusercontent.com/39285147/178766731-66568a7a-2dea-43bf-b886-42ea03100d77.png)

Neural Network를 여러 개의 층으로 쌓은 것이 Multilayer Perceptron Model이다.

그전까지 선형 모델로는 풀 수 없었던 XOR와 같은 문제들을 Multilayer Perceptron 계층들을 쌓아가면서 더 복잡한 형태의 hyperplane 형성이 가능하다.

<details markdown="1">
<summary>XOR 문제(접기/펼치기)</summary>

![image](https://user-images.githubusercontent.com/39285147/178766379-1c19213d-5193-4faf-877e-88fab16b84eb.png)
![image](https://user-images.githubusercontent.com/39285147/178766401-602caf14-f64b-4764-a367-e2f2ccf324f5.png)
![image](https://user-images.githubusercontent.com/39285147/178766422-c5c72322-bb45-4103-baf5-252c30e0ba13.png)
![image](https://user-images.githubusercontent.com/39285147/178766447-3911e480-e575-4baf-99a1-a5f52318ae1f.png)

</details>

### Example: MNIST data recognition
![image](https://user-images.githubusercontent.com/39285147/178766549-4cc2f940-d7ef-4743-9400-9e44e7e10ded.png)

이미지 patch가 들어올 때, 각 이미지 숫자를 0부터 9까지의 숫자로 알맞게 분류를 하는 문제이다.

## 한계점
### *Gradient Vanishing Problem*
![image](https://user-images.githubusercontent.com/39285147/178768444-6808fe2b-010b-43da-a5ec-123468d57e22.png)

The numerous multiplication of this result converges to near zero (= 신경망 깊어질수록 학습이 진행되지 않는 현상). 

## 해결점
- Backpropagation (BP)
- Pre training+ fine tuning
- *Convolutional neural networks (CNN)* for reducing redundant parameters.
- Rectified linear unit (constant gradient propagation)
- Dropout

## Convolutional neural networks (CNN)
![image](https://user-images.githubusercontent.com/39285147/178769285-615d4e95-245c-4910-9cd7-0c126faeaf8b.png)

State of the art classification model for high dimensional data (image, video, etc.)

# Quiz
![image](https://user-images.githubusercontent.com/39285147/178769502-e82d38c8-0cc0-48de-a978-7447bb85e4e2.png)
![image](https://user-images.githubusercontent.com/39285147/178769525-5fdc0788-d746-4d84-ac2e-51039ae3febf.png)

# References
- I. Goodfellow , et. al., “Deep Learning”, [online avaliable](http://www.deeplearningbook.org/)
- CS231n: Deep Learning for Computer Vision (http://cs231n.stanford.edu/)
