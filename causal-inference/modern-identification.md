****
### Terms
- Modern Identification
  - Generalized Identification
  - Transportability
  - Recovering from Selection Bias
  - Recovering from Missing Data

### Background
![image](https://user-images.githubusercontent.com/39285147/179339806-1cff2c4f-4b43-463b-a1eb-05cc92cda53d.png)

> Socioeconomic Status (SES)
>> 사회 경제적인 사람들의 상태에 따라서 데이터가 수집될 수 있다.

기존 인과효과 계산 방법은 한 도메인에 의존하여 추론하였지만, 여러 종류의 데이터를 한꺼번에 활용해서 우리가 원하는 인과효과를 계산하면 더 낫지 않을까?
- 이러한 데이터의 다양성을 베재하고 추론하면, 편향이 존재하는 값이 될 수도 있다.

# Modern Identification
## Modern Identification Tasks
1. Experimental conditions
- Generalized Identification

2. Environmental conditions
- **Transportabilit**

3. Sampling conditions
- **Recovering from Selection Bias**

4. Responding conditions
- **Recovering from Missingness**

## Generalized Identification
![image](https://user-images.githubusercontent.com/39285147/179341439-da02ee67-2fa3-4633-87d0-96cdbefa2808.png)
![image](https://user-images.githubusercontent.com/39285147/179341299-21322e40-6eff-4064-b35f-2191ef3b5a34.png)

여러 데이터가 한 도메인에 주어져 있을 때, 그것으 ㄹ활용해서 원하는 인과 효과를 계산한다

### Generalized Identifiability: Drug-Drug Interactions
![image](https://user-images.githubusercontent.com/39285147/179341349-cb1a96fc-e3b9-41a5-bb94-be89b1929c29.png)

두 개의 실험 데이터를 활용한 예제로, 각각의 약에 대해서 실험한 데이터가 있을 때, 두 약을 혼용하면 어떤 효과가 날지 이해한다.

## Transportability

주어져 있는 데이터의 소스와 우리가 인과 효과를 계산하고자 하는 타겟이 서로 다른 도메인일 때의 인과 추론을 다루는 단순한 인과 추론이 아닌 '통계적 추론'이다.

> ""External Validity"" asks the question of generalizability: To what populations, settings, treatment variables, and measurement variables can this effect be generalized?” (Shadish, Cook, and Campbell, 2002)
>
> “""Extrapolation"" across studies requires ‘some understanding of the reasonsfor the differences.’ ” (Cox, 1958)

실험이 일어난 모집단과 인과 효과를 적용하고자 하는 다른 집단 간의 차이가 존재한다면, 실험 데이터의 인과 효과를 그대로 타겟에 적용할 수 없다.
- i.e., 미국 법치를 한국에 곧바로 들여올 수 없는 것

## Recovering from Selection Bias
![image](https://user-images.githubusercontent.com/39285147/179341784-09a385a4-df49-4050-b77f-d994e5e50177.png)
![image](https://user-images.githubusercontent.com/39285147/179342477-b5cca6e1-0bcd-4927-a34e-ece1061fe72b.png)

> 선택편향 (Selection Bais)
>> 데이터의 샘플이 선택적으로 포함되는 경우에 발생되는 편향

### Selection Bias without External Information
![image](https://user-images.githubusercontent.com/39285147/179342489-6eeb9b06-15c7-44a4-a492-c19a0caaff55.png)

### Identification under Selection (with External Data)
![image](https://user-images.githubusercontent.com/39285147/179342542-cc8e1376-1655-4891-bd7c-2a314ec662a3.png)
![image](https://user-images.githubusercontent.com/39285147/179342549-15881b6b-c12b-401c-8728-eae738a1eaa8.png)

## Recovering from Missing Data
### Identification under Missing Data
![image](https://user-images.githubusercontent.com/39285147/179342682-3bc13277-f099-4d1d-bfd0-5f6cc2989b27.png)

*Missing data* present a challenge in many academic disciplines
- Sensors do not always work reliably.
- Respondents do not fill out every question in the questionnaire.
- Medical patients are often unable to recall treatments or outcomes

### 누락의 이유
![image](https://user-images.githubusercontent.com/39285147/179343494-7d26348f-b142-4d57-befd-050f333e1b43.png)

1. Missing Completely At Random (MCAR) 완전 무작위
2. Missing at Random (MAR) 메커니즘이 누락된 변수와 어떤 조건부 독립이 성립
3. Missing Not at Random (MNAR) 랜덤하지 않은 누락

> 누락된 정보가 있는 줄들을 삭제, 빈 값들을 채우는 알고리즘들 MCAR, MAR에 부분적을 ㅗ동작하지만 MNAR에는 동작하지 않음.
