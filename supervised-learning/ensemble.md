****
### Terms
- Ensemble
  - Voting 
  - Bagging
    - Bootstrap
  - Boosting
    - Adaboost
- TN,FP,FN,TP
- Accuracy, Precision, Recall
- ROC Curve

# Performance Evaluation in SL
![image](https://user-images.githubusercontent.com/39285147/178784146-bc2562a6-86d4-4b9b-aa84-11269697c231.png)
![image](https://user-images.githubusercontent.com/39285147/178784704-26e846fd-2508-4165-9d46-e0b79e816699.png)

> Confusion Matrix: 각 경우에 대해 오차가 얼마 있었는지 표현하는 방법

<details markdown="1">
<summary>Error measure(접기/펼치기)</summary>

![image](https://user-images.githubusercontent.com/39285147/178790613-cfc3281d-7598-4be3-9026-f206f53cce11.png)

</details>

> The error measure should be specified by the user
>> Not always given but needs to be carefully considered

## ROC Curve
![image](https://user-images.githubusercontent.com/39285147/178790161-46714147-3b13-4e76-b324-32a9ec4b495b.png)

서로 다른 classifier의 성능을 측정하는데 사용하는 curve이다.

> FPR: 1 - TPR
> 
> Sensitivity: Recall

# Ensemble Methods
![image](https://user-images.githubusercontent.com/39285147/178795696-eb536d7f-8942-4e47-9dc6-3305fa255065.png)

Predict class label for unseen data by aggregating a set of predictions : different classifiers (**experts*) learned from the training data
- 같은 모델로 학습이 될 수 있기에, 같은 학습데이터로 학습하는 것을 지양해야한다.

> *expert*: 하나의 학습 모델 (i.e., SVM)

이미 사용하고 있거나 개발한 알고리즘의 간단한 확장 SL task에서 성능을 올릴 수 있는 방법
- ML에서 알고리즘의 종류에 상관 없이 서로 다르거나, 같은 메커니즘으로 동작하는 다양한 ML 모델을 묶어 함께 사용하는 방식
- 다양한 모델의 각 장점을 살려서 예측 성능을 향상시킨다.

## Ensemble Intuition

Build different experts, and let them vote.

### Advantages & Disadvantage
#### Advantages
- Improve predictive performance (예측 성능을 안정적으로 향상 가능)
- Other types of classifiers can be directly included (noise로 부터 안정적이다)
- Easy to implement
- No too much parameter tuning (각 모델이 독립적으로 동작하기 때문이다.)

#### Disadvantage
- Not a compact representation

### Voting
**서로 다른** 알고리즘을 가진 분류기를 결합한다.

#### Hard Voting
![image](https://user-images.githubusercontent.com/39285147/181841630-90e8b288-4501-42d5-ac47-7ce381b48987.png)

#### Soft Voting
![image](https://user-images.githubusercontent.com/39285147/181841647-48cfe381-dcd5-4997-a7c7-ed75fae789bb.png)

### Bagging
![image](https://user-images.githubusercontent.com/39285147/178803258-d14bb90b-4c7b-4138-8b75-3cca6d72823b.png)

**같은 유형의** 서로 다른 분류 모델을 여러 개 만들어서 서로 다른 학습 데이터로 학습시킨 후(*부트스트랩*), 동일한 테스트 데이터에 대한 서로 다른 예측값들을 투표를 통해(*어그리게이팅*) 가장 높은 예측값으로 최종 결론을 내리는 앙상블 기법이다.
- **Boostrapping* + aggregating (for more robust performance; lower variance)
  - 높은 variance로 인한 overfitting 문제를 해결하는데 도움을 준다

<details markdown="1">
<summary>Boostrapping(접기/펼치기)</summary>

![image](https://user-images.githubusercontent.com/39285147/178803397-7a47d4ff-2002-484b-a548-bf09de099279.png)

전체 데이터에서 일부가 중첩되게 샘플링해서 데이터 세트를 만드는 과정으로 학습 데이터 수를 늘린다.

</details>

> Bagging: 학습 과정에서 training sample을 랜덤하게 나누어 선택해 학습한다.
>> 같은 데이터셋을 다른 모델 M개로 학습하기에 다른 데이터셋 M개를 사용하는 효과가 있다.

- Train several models in parallel (병렬 처리)
  - Usually, the more classifiers the better
- Improving Decision Tree
  - **Random forest** (inherently boosting)

### Boosting
![image](https://user-images.githubusercontent.com/39285147/178803534-0fe8851c-2cd4-4b7c-a527-25cc9f241268.png)

여러 개의 동일한 알고리즘의 분류기가 순차적으로 학습을 수행하되, 예측이 틀린 데이터에 대해 올바르게 예측하도록 가중치를 부여하면서 학습과 예측을 진행한다.
- **Sequencial** cascading of **weak classifiers*
  - **Adaboost*
- 높은 bias를 낮추는 것 (학습이 덜 된 모델을 추가 학습을 통해 좀 더 좋은 모델로 만드는것)

<details markdown="1">
<summary>Adaboost(접기/펼치기)</summary>

![image](https://user-images.githubusercontent.com/39285147/178804663-a6d3c98e-82cb-42c8-9cdb-85b7e59722d9.png)

</details>

<details markdown="1">
<summary>Weak/Strong Classifier(접기/펼치기)</summary>

**Weak**: Bias가 높은 Classifier (단순한 모델)

**Strong**: Variance가 높은 Classifier (복잡한 모델)

</details>

> Cascading을 적용하여 weak classifier를 순차적으로 학습하여 모델 복잡도를 높인다.


- Assign a larger weight for misclassified points by one of the base classifiers, when training the next classifier in the sequence (combat to lower bias)
- Improving Decision Tree
  - Gradient boosting machine (GBM) as **generalized Adaboost**
    - Very popular machine learning algorithm
    - One of leading methods for winning many Kaggle competition

![image](https://user-images.githubusercontent.com/39285147/181843541-210e9d23-b846-4fe4-9a52-2cc9b9befc89.png)

#### Advantage of Boosting
- Simple and easy to implement
- Flexible : can combine with any learning algorithm
- No prior knowledge needed about weak learner
- Versatile : can be applied on a wide variety of problems
- Non parametric

# Applications using SL
- Object Detection/localization
- Image, language interdisciplinary studies (image/video captioning, question and answering, etc.)
- Semantic segmentation, face detection, pose estimation, super resolution

# Future Research topics
- SL is a baseline study on many recent AI tasks, owing to large scaled labeled datasets

# SL의 한계점
- Nevertheless, it relies on the sizes of datasets ; what if we have no sufficient data samples?
  - Data augmentation
  - Learning from insufficient labels (weak supervision, etc.)
- Furthermore, what if the data properties are different between datasets?
  - **Domain adaptation*, [transfer learning](https://github.com/EricChoii/ai-terms/blob/main/README.md), etc.

> *Domain adaptation*: 다른 도메인으로 부터 얻은 지식을 새로운 타겟 도메인에 재활용할 수 있는 방법

# Quiz
![image](https://user-images.githubusercontent.com/39285147/178806791-e2b78c49-749a-4913-bd9b-8494ce116642.png)

# Reference
- Book: Pattern Recognition and Machine Learning (by Christopher M. Bishop)
- Book: Machine Learning: a Probabilistic Perspective (by Kevin P. Murphy)
- https://www.andrewng.org/courses/
