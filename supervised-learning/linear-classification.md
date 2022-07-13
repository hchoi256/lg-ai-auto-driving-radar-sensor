****
### Terms
- Linear Classification

![image](https://user-images.githubusercontent.com/39285147/178240098-fcfabcdd-b93e-40a8-8271-f5665bb66e7e.png)

# Linear Classification
![image](https://user-images.githubusercontent.com/39285147/178738475-c74b8b40-f4c8-484b-baae-833d622749d2.png)

Uses a hyperplane as a decision boundary to classify samples based on a linear combination of its explanatory variables

### Example
- Image recognition

## Advantage of linear classification
- Simple
- Interpretability (예측 결과에 더해서 사람이 이해할 수 있는 형태로 추가적인 정보를 제공)

## Target function 𝑓 (𝑓:𝑿→𝒀)
- Correct label is ready for a training set
- Hypothesis 𝑔:𝑿→𝒀(ML model to approximate 𝑓) : 𝑔∈𝑯

<details markdown="1">
<summary>𝑔∈𝑯(접기/펼치기)</summary>

![image](https://user-images.githubusercontent.com/39285147/178739687-257c8740-fa15-46bc-bf10-052e3f505b87.png)
![image](https://user-images.githubusercontent.com/39285147/178739877-de2f076b-afd9-463b-a548-6e93714a715f.png)

</details>

## Linear classification framework
![image](https://user-images.githubusercontent.com/39285147/178739145-94d4e15f-295e-4689-84b0-dadfaaae74aa.png)

### Score and Margin
![image](https://user-images.githubusercontent.com/39285147/178741007-f2bb6a08-104f-4825-89ec-a5b961b3ba2d.png)

### Zero-one loss
![image](https://user-images.githubusercontent.com/39285147/178741814-48468556-579e-4296-bfd9-79502b4f6d89.png)

### Hinge loss
![image](https://user-images.githubusercontent.com/39285147/178741882-f726f06b-73e6-4b67-9483-78caed18459d.png)

### Cross-entropy loss
![image](https://user-images.githubusercontent.com/39285147/178741907-3154da2e-6d7b-413a-94bf-7b766beedd57.png)
![image](https://user-images.githubusercontent.com/39285147/178741943-bc16c4b0-037f-4737-a878-4d16b6e5f614.png)
![image](https://user-images.githubusercontent.com/39285147/178742070-8a89f201-3c40-43be-abc7-4b703a7c974e.png)

**Sigmoid function* is used to map a score value into a probability value.

<details markdown="1">
<summary>Sigmoid function(접기/펼치기)</summary>

![image](https://user-images.githubusercontent.com/39285147/178742116-8c589c94-5a4e-4603-bdb2-46d12e1f51d8.png)

</details>

## How to Train Linear Classifier
![image](https://user-images.githubusercontent.com/39285147/178742255-c2149c2c-75f0-489d-a93d-1a8572af4bdb.png)

Iterative optimization using gradient descent

1. Initialize weights at time step 𝒕= 0
2. Compute the gradients
3. Set the direction to move :
4. Update weights
5. Iterate to next step until converging

# Multiclass classification (one vs all)
![image](https://user-images.githubusercontent.com/39285147/178742628-dfc16fb8-6ebb-4bdf-a048-f592cbd470c9.png)
![image](https://user-images.githubusercontent.com/39285147/178742769-142ac214-f9b8-49b1-83da-f7eb82d86d97.png)

- Not all classification predictive models support multi class classification.
- split the multi class classification dataset into multiple binary classification datasets and fit a binary classification model on each.

# Quiz
![image](https://user-images.githubusercontent.com/39285147/178743210-3c64eba8-bca0-4188-9dd1-50f35c8878aa.png)
![image](https://user-images.githubusercontent.com/39285147/178743234-891e5dfc-4840-4dad-85c5-a4a934f66407.png)
![image](https://user-images.githubusercontent.com/39285147/178743256-f44bdbab-b7a4-4b2f-bf6b-19c215583724.png)

# Reference
- Book: Pattern Recognition and Machine Learning (by Christopher M. Bishop)
- Book: Machine Learning: a Probabilistic Perspective (by Kevin P. Murphy)
- https://www.andrewng.org/courses/

