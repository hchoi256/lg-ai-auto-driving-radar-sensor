****
### Terms
- Linear Classification
  - Zero-one loss
  - Hinge loss
  - Cross-entropy loss
- Score and Margin
- Multiclass classification

![image](https://user-images.githubusercontent.com/39285147/178240098-fcfabcdd-b93e-40a8-8271-f5665bb66e7e.png)

# Linear Classification
[*Linear Model*]

![image](https://user-images.githubusercontent.com/39285147/178746386-b49e5341-3b58-406e-9161-44d66d6e4da8.png)

Linear Classification은 decision boundary를 찾아내어 주어진 분류 문제를 해결하는 방법이다.
- Discrete output
- Use **labeled** dataset
  - Correct label is ready for a training set

## Advantage of linear classification
- Simple
- Interpretability (예측 결과에 더해서 사람이 이해할 수 있는 형태로 추가적인 정보를 제공)

<details markdown="1">
<summary>Interpretability(접기/펼치기)</summary>

![image](https://user-images.githubusercontent.com/39285147/178757022-bec942b7-6c75-415a-8c11-89d56c68f1c4.png)

</details>

## Goal: Find Target Function 𝑓 (𝑓:𝑿→𝒀)
Hypothesis 𝑔:𝑿→𝒀(ML model to approximate 𝑓) : 𝑔∈𝑯

<details markdown="1">
<summary>𝑔∈𝑯(접기/펼치기)</summary>

![image](https://user-images.githubusercontent.com/39285147/178739687-257c8740-fa15-46bc-bf10-052e3f505b87.png)- w 
![image](https://user-images.githubusercontent.com/39285147/178739877-de2f076b-afd9-463b-a548-6e93714a715f.png)

</details>

> Score 값이 커질수록 결정경계(h(x))로 부터 멀리 떨어진다.

<details markdown="1">
<summary>Score & Margin이란?(접기/펼치기)</summary>

![image](https://user-images.githubusercontent.com/39285147/178741007-f2bb6a08-104f-4825-89ec-a5b961b3ba2d.png)

</details>

> Margin:  score * y(실제값) (= 모델이 정답을 잘 맞추고 있는가)
>> 음의 값: model prediction 실패

>> 양의 값: model prediction 성공

# Linear classification framework
![image](https://user-images.githubusercontent.com/39285147/178739145-94d4e15f-295e-4689-84b0-dadfaaae74aa.png)

## Zero-one loss
![image](https://user-images.githubusercontent.com/39285147/178741814-48468556-579e-4296-bfd9-79502b4f6d89.png)

내부의 logic을 판별하여 맞으면 0 틀리면 1을 출력하는 함수.

### 한계와 해결점
Zero-one loss에 gradient descent 알고리즘을 적용하려면 partial derivative term을 적용해야하나, 기울기가 모두 0이 되버린다. 이를 해결하고자, Hinge loss가 사용된다.

## Hinge loss
![image](https://user-images.githubusercontent.com/39285147/178741882-f726f06b-73e6-4b67-9483-78caed18459d.png)
 
모델이 예측을 잘 하고 있다면(= Margin이 1보다 크다면), 수식에 의해 hinge loss는 0이 된다, vice versa.

## [Cross-entropy loss](https://github.com/EricChoii/ai-terms/blob/main/entropy.md)
> *Classification model 학습에 가장 많이 사용된다*

![image](https://user-images.githubusercontent.com/39285147/178741907-3154da2e-6d7b-413a-94bf-7b766beedd57.png)

엔트로피 값(H(p))는 고정값이므로, 실질적으로 Cross entropy는 KL divergence 값에 의해 조절된다. 여기서 KL divergence는 p와 q의 유사도에 따라 값이 정해진다.
- p와 q가 다르다면 cross entropy loss는 증가한다.

### Score(실수값)을 확률값으로 Mapping하기
우리가 fitting을 하고자 하는 label은 1 or 0인데, 실수값인 score를 어떻게 확률 함수를 통해 매핑하는 방법으로 **Sigmoid function*가 사용된다.

<details markdown="1">
<summary>Sigmoid function(접기/펼치기)</summary>

![image](https://user-images.githubusercontent.com/39285147/178742116-8c589c94-5a4e-4603-bdb2-46d12e1f51d8.png)

(+)값으로 커지게 된다면 확률 값 1에 근사하게 된다, vice versa.

</details>

[*Logistic model*]

![image](https://user-images.githubusercontent.com/39285147/178741943-bc16c4b0-037f-4737-a878-4d16b6e5f614.png)

실수값인 Score를 Sigmoid Function에 대입하여 [0, 1] 확률 범위로 리턴한다.

### Cross-entropy loss: Gradient Descent Method
![image](https://user-images.githubusercontent.com/39285147/178742070-8a89f201-3c40-43be-abc7-4b703a7c974e.png)

Loss가 발생할 때, Gradient Descent 방법을 활용하여 가중치를 업데이트한다.

# How to Train Linear Classifier - Gradient Descent
![image](https://user-images.githubusercontent.com/39285147/178742255-c2149c2c-75f0-489d-a93d-1a8572af4bdb.png)
- Gradient descent = Cross Entropy Loss의 미분값(= ![image](https://user-images.githubusercontent.com/39285147/178755058-37f42ba7-9b79-463c-9685-73f88b77f557.png))

Iterative optimization using gradient descent

1. Initialize weights at time step 𝒕= 0
2. Compute the gradients
3. Set the direction to move :
4. Update weights
5. Iterate to next step until converging

# Multiclass classification
![image](https://user-images.githubusercontent.com/39285147/178756035-e4294c2f-1fe7-4c35-b579-03b84b1dc377.png)
- Not all classification predictive models support multi class classification.
- split the multi class classification dataset into multiple binary classification datasets and fit a binary classification model on each.

### Example: Image Recognition
![image](https://user-images.githubusercontent.com/39285147/178746614-5194aebe-4686-4240-a22b-bb09402ef55f.png)

## Multiclass Classification One vs All
![image](https://user-images.githubusercontent.com/39285147/178742628-dfc16fb8-6ebb-4bdf-a048-f592cbd470c9.png)
![image](https://user-images.githubusercontent.com/39285147/178742769-142ac214-f9b8-49b1-83da-f7eb82d86d97.png)

One vs All은 binary classification에서 multiclass classification으로 확장하는 문제이다. 각 학습 모델에 대한 Score값에 Sigmoid Function을 취하여 확률값으로 매핑하고, 이를 **One Hot Encoding*으로 label화 된 값들과 비교하여 error를 계산한다.

> One Hot Encoding: 두 개의 서로 다른 표 사이에 거리를 가깝게 하면서 학습

# Quiz
![image](https://user-images.githubusercontent.com/39285147/178743210-3c64eba8-bca0-4188-9dd1-50f35c8878aa.png)
![image](https://user-images.githubusercontent.com/39285147/178743234-891e5dfc-4840-4dad-85c5-a4a934f66407.png)
![image](https://user-images.githubusercontent.com/39285147/178743256-f44bdbab-b7a4-4b2f-bf6b-19c215583724.png)

# Reference
- Book: Pattern Recognition and Machine Learning (by Christopher M. Bishop)
- Book: Machine Learning: a Probabilistic Perspective (by Kevin P. Murphy)
- https://www.andrewng.org/courses/

