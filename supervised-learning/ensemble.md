****
### Terms
- Ensemble
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

### Bagging
![image](https://user-images.githubusercontent.com/39285147/178803258-d14bb90b-4c7b-4138-8b75-3cca6d72823b.png)

- **Boostrapping* + aggregating (for more robust performance; lower variance)
  - 높은 variance로 인한 overfitting 문제를 해결하는데 도움을 준다

<details markdown="1">
<summary>Boostrapping(접기/펼치기)</summary>

![image](https://user-images.githubusercontent.com/39285147/178803397-7a47d4ff-2002-484b-a548-bf09de099279.png)

</details>

> Bagging: 학습 과정에서 training sample을 랜덤하게 나누어 선택해 학습한다.
>> 같은 데이터셋을 다른 모델 M개로 학습하기에 다른 데이터셋 M개를 사용하는 효과가 있다.

- Train several models in parallel (병렬 처리)
  - Usually, the more classifiers the better
- Improving Decision Tree
  - **Random forest** (inherently boosting)

### Boosting
![image](https://user-images.githubusercontent.com/39285147/178803534-0fe8851c-2cd4-4b7c-a527-25cc9f241268.png)

- **Sequencial** cascading of **weak classifiers*
  - **Adaboost*

<details markdown="1">
<summary>Adaboost(접기/펼치기)</summary>

![image](https://user-images.githubusercontent.com/39285147/178804663-a6d3c98e-82cb-42c8-9cdb-85b7e59722d9.png)

</details>

<details markdown="1">
<summary>Weak/Strong Classifier(접기/펼치기)</summary>

Weak: Bias가 높은 Classifier (단순한 모델)
Strong: Variance가 높은 Classifier (복잡한 모델)

</details>

> Cascading을 적용하여 weak classifier를 순차적으로 학습하여 모델 복잡도를 높인다.


- Assign a larger weight for misclassified points by one of the base classifiers, when training the next classifier in the sequence (combat to lower bias)
- Improving Decision Tree
  - Gradient boosting machine (GBM) as **generalized Adaboost**
    - Very popular machine learning algorithm
    - One of leading methods for winning many Kaggle competition

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
