****
### Terms
- Causality
- Structural Causal Model (SCM)
  - Observational 
  - Interventional
  - Counterfactual distributions
- Conditional independencies
- Causal effect

# Causality(인과성, 인과율)
Causality란 하나의 어떤 무엇인가가 다른 무엇을 생성함에 있어 영향을 미치는 것으로, 원인과 결과 사이 관계는 필요조건이나 충분조건일 필요는 없다 (i.e., 버스를 놓쳐서 지각을 했다).

> 관련/연관이 있다
>> 상관성의 정보 제시 (인과 X)

> Causal Inference
>> 인과적인 통찰을 이용해서 하는 그 모든 추론이라는 넓은 개념

### How is Causality related to & {AI, ML, & DS}?
Artificial Intelligence
- 어떤 에이전트(소프트웨어, 로봇)가 목표를 성취하기 위해 합리적인 액션을 취하는 것

Machine Learning
- Currently focused on learning correlations (데이터 상관성 학습)

Data Science
- Capture, Process, Analyze (e.g., Stat, ML), Communicate with Data

### Pearl’s Causal Hierarchy
▶ **Level 1**: Associational or Observational (관찰/단순비교)
- 사람들이 아스피린 약을 언제 먹는지 등을 *관찰*한다.

▶ **Level 2**: Interventional or Experimental (실험 계층/중재)
- *실험* 계층이 서로 다른 아스피린 약을 복용했을 때 나타나는 결과에 주목한다.

▶ **Level 3**: Counterfactual (관측/실험 값 동시 고려하는 반사실적 계층)
- 아스피린 약을 복용하지 *않았다면* 어땠을까?

### Simpson’s Paradox
![image](https://user-images.githubusercontent.com/39285147/179286008-13299b1e-3cba-464a-bb0c-a3634af0865e.png)

각각의 변수에 대한 가중치나 특성을 고려하지 않고 전체 통계 결과를 유추하다 보면 발생할 수 있는 오류이다.

> 가상의 무작위  실험
>> 인과 효과를 계산할 수 있다.

### 데이터 분석할 때 고려할 점
![image](https://user-images.githubusercontent.com/39285147/179286653-d13cde9a-bd3d-4e01-8eb4-a81333036c30.png)

1. 주어진 데이터가 상관성을 띄는지 인과성을 띄는지
2. 알고자 하는 질문이 조건부 확률같은 상관성에 관한 것인지, 인과성에 관한 것인지

## Formalizing Causality
### Observation & Intervention (Experiments)
![image](https://user-images.githubusercontent.com/39285147/179287137-a021f63a-2280-48cf-a145-5445dc6eb1ef.png)

**[Black box](https://github.com/EricChoii/ai-terms/blob/main/README.md)*

### Causal Framework: Structural Causal Model
![image](https://user-images.githubusercontent.com/39285147/179287565-4b21f326-8ac0-44c6-a9d7-8845d2e06124.png)
![image](https://user-images.githubusercontent.com/39285147/179287235-098cf491-9e62-455e-8950-3ee316388863.png)

> Causal diagram
>> 연구자가 시스템이 어떠할지 인과적인 가정을 하는 부분으로, 전문가들의 상식, 지식 혹은 가정에 의거한다.

Structural Causal Model is a **formal framework to study causality**.

#### Example: Causal diagram vs. Causal Model
![image](https://user-images.githubusercontent.com/39285147/179287850-195372a8-5d93-4c59-8f9c-15de88f8b42e.png)
![image](https://user-images.githubusercontent.com/39285147/179287861-c7f36343-d6f9-4d3c-b66b-e8404e58522e.png)

#### Intervention(중재) — do(·) operator
![image](https://user-images.githubusercontent.com/39285147/179288066-02f548b0-d1df-4cd1-a51e-60e1b5d5facf.png)

> x를 상수로 중재(고정)하면서 더 이상 x는 영향력을 행사하지 않아 가지가 끊어졌다.

- Given a model M the action of fixing any observable variable X ∈ V to a constant value x is denoted using the do(·) operator as do(X = x).
- This operation gives birth to a **submodel** M_x that looks exactly like M but with functions where f_x has been replaced with a constant x.
- These two graphs represent the world before and after an intervention do(X = x).

#### Intervention — Causal Effects
![image](https://user-images.githubusercontent.com/39285147/179288459-2e2acbb2-151f-4ddf-8a38-47d435a0029a.png)

> *Expectation*: E[Y|do(x)]
>
> *Difference*: E[Y|do(X = 1)]−E[Y|do(X = 0)] (Average Treatment Effect, ATE)
> 
> *Conditional*: E[Y|do(X = 1),Z]−E[Y|do(X = 0),Z] (Conditional ATE)

### Conditional Independence(조건부 독립성) from Causal Diagram
[*causal graph*]
![image](https://user-images.githubusercontent.com/39285147/179288715-02623456-cbea-44ce-a9dd-ff55c646ca5b.png)
![image](https://user-images.githubusercontent.com/39285147/179288637-37cec2cd-dc91-4829-80b4-ecf015233985.png)

> Causal graph
>> Implies conditional independencies testable via d-separation (blockage).

# Summary
![image](https://user-images.githubusercontent.com/39285147/179288795-c15c5478-62e1-403c-a9aa-43b05a52bd92.png)
