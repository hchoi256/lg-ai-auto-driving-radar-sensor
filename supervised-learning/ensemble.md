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

Predict class label for unseen data by aggregating a set of predictions : different classifiers (experts) learned from the training data

Make a decision with a voting

## Ensemble Intuition

Build different experts, and let them vote.

### Advantages & Disadvantage
Advantages
- Improve predictive performance
- Other types of classifiers can be directly included
- Easy to implement
- No too much parameter tuning

Disadvantage
- Not a compact representation

### Bagging
![image](https://user-images.githubusercontent.com/39285147/178803258-d14bb90b-4c7b-4138-8b75-3cca6d72823b.png)

- **Boostrapping* + aggregating (for more robust performance; lower variance)
  - 높은 bias의 underfitting 문제나, 높은 variance로 인한 overfitting 문제를 해결하는데 도움을 준다

<details markdown="1">
<summary>Boostrapping(접기/펼치기)</summary>

![image](https://user-images.githubusercontent.com/39285147/178803397-7a47d4ff-2002-484b-a548-bf09de099279.png)

</details>

- Train several models in parallel (병렬 처리)
  - Usually, the more classifiers the better
- Improving Decision Tree
  - **Random forest** (inherently boosting)

### Boosting
![image](https://user-images.githubusercontent.com/39285147/178803534-0fe8851c-2cd4-4b7c-a527-25cc9f241268.png)

- **Sequencial** cascading of weak classifiers
  - **Adaboost*

<details markdown="1">
<summary>Adaboost(접기/펼치기)</summary>

![image](https://user-images.githubusercontent.com/39285147/178804663-a6d3c98e-82cb-42c8-9cdb-85b7e59722d9.png)

</details>

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
