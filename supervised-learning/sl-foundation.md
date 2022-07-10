# SL Foundation
### Terms
- Train/Validation/Test set
- Target Function
- Hypothesis H
- Learning Model
- Overfitting/Underfitting
- Bias-Variance Trade-off
- Avoid Overfitting
- Model Generalization
- Cross-Validation (CV)

## 특징
 - Data Label 존재
 - 들어온 인풋에 대하여 category label을 맞추는 함수(h)를 학습
 
## 종류
- **Regression** (연속 변수)
- **Classification** (이산 변수)

# Learning Pipeline
![image](https://user-images.githubusercontent.com/39285147/178139121-56fc8108-9459-4d01-b591-9cdd7eae8bd9.png)
## Training 단계
- Model output과 정답과의 차이인 error를 줄여가는 방향으로 모델 사전학습 (**label**이 주어져서 가능한 일)
## Test 단계
- Training 단계에서 학습된 모델을 사용하여 실제 환경에 적용 (**이 단계 검증 결과가 모델의 최종 성능**)

## 예시
![image](https://user-images.githubusercontent.com/39285147/178139268-7558ef94-806a-45cc-9253-371ea7f972d0.png)
![image](https://user-images.githubusercontent.com/39285147/178139386-35699b72-d212-499b-ad0d-3de608d0a9d3.png)
- 데이터 입력 표현(= Feature; 도메인지식 수반)
  - 차량의 가격
  - 차량의 엔진 파워

*DL는 Feature 스스로 학습하여 도메인지식에서 자유로움*

## Target Function
![image](https://user-images.githubusercontent.com/39285147/178139459-85abf7ae-627a-413b-b67d-9e889dd47326.png)

입력값을 출력(y)로 변환하는 함수

### Hypothesis H
이상적인 Target Function에 근사한 함수

## Learning Model
![image](https://user-images.githubusercontent.com/39285147/178139561-57635f09-6e64-449f-b407-398080ea50cf.png)

Hypothesis H에 도달하기 위한 방법론

### Model Selection
풀고자 하는 문제에 가장 적합한 model을 선택하는 과정

# Overfitting VS Underfitting (Bias-Variance Trade-Off)
## Underfitting
![image](https://user-images.githubusercontent.com/39285147/178140447-30660140-2d0c-4400-9c41-7e57bb3301ba.png)

## Overfitting
![image](https://user-images.githubusercontent.com/39285147/178140458-0350db01-23e1-4b44-bdaa-379a78bbe0bf.png)

### [Avoid Overfitting](https://github.com/EricChoii/ai-terms/blob/main/overfitting.md)

## Bias-Variance Trade-off
![image](https://user-images.githubusercontent.com/39285147/178140622-63c18b99-1905-44fd-9e65-6b768ca2fd87.png)
![image](https://user-images.githubusercontent.com/39285147/178151883-e8373347-12f0-4f03-be51-60db99e1e3f0.png)
- Total Loss(= generalization error) = Bias + Variance (+ noise)

# Model Generalization
## Generalization
![image](https://user-images.githubusercontent.com/39285147/178139695-ee43a743-1b78-42d7-bb96-17a5a0bd3ebc.png)
- 모델이 학습과정에서 관찰하지 못한 셈플에 대해서도 우수한 성능을 제공할 수 있어야 함.
- Generalization error E을 0으로 만들기는 **불가능**하므로, **Training/Validation/Test set** 구분으로 error *최소화*하려는 노력.

![image](https://user-images.githubusercontent.com/39285147/178139844-e35c7ed4-2c36-4e9a-b3bd-a804e794bc46.png)
- Overall Errors(= **cost/loss function**)
- **E_train** measured on a training set, which may or may not represent E_gen; used for fitting a model
- **E_test**(not used in training), which can be used for a proxy of E_gen

![image](https://user-images.githubusercontent.com/39285147/178140021-2ee36cec-aa7a-4cde-97e9-5910ca406a65.png)
- **Objective 1**: 일반적인 모델 성능을 갖도록 함(= 분산이 작음)
- **Objective 2**: 모델이 학습이 잘 되어짐(= 편차가 낮아짐)

## [Avoid Overfitting](https://github.com/EricChoii/ai-terms/blob/main/overfitting.md)

## Cross-validation (CV)
![image](https://user-images.githubusercontent.com/39285147/178140726-ea0190aa-54f9-4096-90fb-8574d11981cf.png)
- Test set으로만 검증하면 Test set 과적화가 발생한다. 이를 방지하고자, Training dataset 안에 하나의 Validation set을 포함한 k개를 한 묶음(*Data Augmentation*)으로 총 다섯 번의 검증 과정을 거쳐서 모델 일반화를 통한 최적화를 이루어 낸다. 최종적으로 Test set에서 모델 성능을 검증한다.

# Quiz
![image](https://user-images.githubusercontent.com/39285147/178150892-dd2786cd-2bfb-467e-998a-e921ed5d687f.png)
- **A**: Binary Classification
- **B**: Multi-class classification
- C: Regression (X)

![image](https://user-images.githubusercontent.com/39285147/178150921-784febbf-d95f-4d9b-83f0-05be85002e8d.png)
