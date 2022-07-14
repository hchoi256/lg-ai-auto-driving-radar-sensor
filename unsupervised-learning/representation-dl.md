****
### Terms
- Representation DL
  - Disentangled representation
  - Unsupervised learning
    - Word embedding
      - WordtoVec
        - Masking
-  Two Extreme Points of View

# Representation DL
![image](https://user-images.githubusercontent.com/39285147/178970367-8252ae9a-7cc5-4ba4-b226-d5a1b58b295c.png)

### Deep Learning Representation is (Severly) Under Constrained
Good news
- Simple SGD can find one of the useful networks(countless)
- Representation characteristics can be adjusted if needed

Bad news
- Learned representation becomes difficult to undertand

## Deep Learning
![image](https://user-images.githubusercontent.com/39285147/178969881-bf60b2ed-f6ce-4456-b17a-60491583aab9.png)

- Obviously, no “formal system with a specification”
- What properties need to be satisfied?
- Can we interpret a specific representation (or a neuron)

### Disentangled Representation
![image](https://user-images.githubusercontent.com/39285147/178970887-f58a74ea-690f-4e6a-8fc5-3cec60664edf.png)

Disentangled representation이란 어떤 이미지를 나타내는 latent variable이 여러 개로 분리 되어 각각 다른 이미지의 특성에 관한 정보를 담고 있는 것을 의미합니다. 
- Aligned
- Independendent
- Subspaces
- Possible because “severaly underconstrained”

6개의 가장 중요한 개념이 있는 데이터에 대해서 그걸 완전히 분리시킨다.
- Color, shape, rotation, size, posY, posX 값만 입력하면 output을 만들어낸다.

#### 한계점
여전히 실제 상황에서 적용하기 어려운 난제이다.

# Task
## A Well Defined Task
![image](https://user-images.githubusercontent.com/39285147/178970866-01019cc6-bcf8-43c6-a6e5-e3bea9025d38.png)

Typically, only one attribute of interest is considered as y
- Imagenet class
- y is well defined because it is simply defined as human selected label (supervised learning)

## Good Representation A Vague Concept (*Supervised*)
![image](https://user-images.githubusercontent.com/39285147/178971042-a881d465-c512-403a-ae02-5cf2c4484fd2.png)

- Even when y is well defined, what do we want for h1 and h2
  - Simply say “representation learning successful” if good performance?
    - But then there is almost nothing we can say about h1 and h2
    - Other than saying “useful information has been well curated"
  - Is there anything we can say or pursue?

### Information Bottleneck
![image](https://user-images.githubusercontent.com/39285147/178971133-ad40085f-2f28-4303-b415-14531e5ddc5f.png)

관심 있는 정보만 추출하고 나머지는 제거하는 정보이론 방법론에서 의거하여 DL을 설명하려 했으나 실패로 끝났다.
- For a well defined supervised task
- What should h1 and h2 satisfy?

## Good Representation A Vague Concept (*Unsupervised*)
For a general purpose, what is a good representation?
- “general often defined as a list of downstream tasks?
- So, we go back to “good performance for the task(s) of interest?”

> General purpose downstream task
>> 아직 무엇인지 모르는 여러 task를 차후 수행할건데 unsupervised learning을 사용해서 데이터를 잘 정리하면, 차후 구체적으로 풀고 싶은 문제들(downstream task)에서 다방면으로 좋은 성능을 보이도록 하는 것.

## Word Embedding
### General Purpose?
![image](https://user-images.githubusercontent.com/39285147/178971701-69ebdde4-75be-4df4-bff0-f9994b82189d.png)

**Word2Vec**

단어 하나를 숫자로 매핑하는 기법
- Word representation formed independent of the downstream task s
  - But masking itself is a task
  - Does it mean masking is a “general task”?
- Linear relationship encouraged by linear skipgram
  - Is “linear relationship” a universally desired representation property for NLP tasks?

Latest pre-trained language models
- Unsupervised (self supervised) objectives can be m a sking, denoising, etc.
- Embedding learned as a part of model
  - Linear relationship? (anyone knows the answer?)
- Can be fine tuned if needed

## Masking
General or task specific?
- Representation contains all the attributes that exist
- Representation contains all the attributes that are useful for THE downstream tasks

> Self-supervised learning
>> label이 없는 untagged data를 기반으로 한 학습이며 자기 스스로 학습을 수행한다.
>> 
>> NLP 부분에서 예기치 않은 좋은 성과를 끌어낸다.

# Representation
What we want:
- A formal definition and evaluation metrics for representation

Reality
- No definition
- Task dependent evaluation methods

## Two Extreme Points of View: #1 Interpretable & Explainable Representations
### Distributed Representation
*Hinton, 1986*

가계도에서 주어진 정보가 아닌 데이터를 추론하는 DL 모델을 설명한다. 이 모델은 스스로 학습하면서 성별로 사람을 구분하는 등 representation 규칙을 생성한다.

### Visualization
Mapping between a neuron and the input

Interpret a neuron’s representation through the input

Lower layer --> higher layer (model build-up)

#### Problem: Smashing Upper Layer?
상당히 많은 알고리즘들이 제대로 개념을 잡고 있는지에 주목한 것이 아니라 그저 **Edge Detector*의 역할을 하고 있었다.

> Edge detector
>> input이 들어오면 값이 심하게 변하는 부분들이 항상 그렇게 잡혀가지고 보여주고 있던 거지 실제로 개념을 모델이 이해한 것이 아니다.

#### Explanable AI
기본적으로 알고리즘이 왜 어느 부분을 보고 결론을 내렸는지 해석할 수 있다.

**Grad-cam* working well for explaining the relation between the image input and the class output

> Grad-cam: Visual explanations from deep networks via gradient-based localization

### Feature Visualization
![image](https://user-images.githubusercontent.com/39285147/178991519-4232b429-3da6-41ba-a8c0-fc99f3ea3a1b.png)
![image](https://user-images.githubusercontent.com/39285147/178991564-8ca1dfa4-c007-4a31-a711-e573112770de.png)

뉴런마다 실제로 어떠한 개념이 존재할 것이다.

## Two Extreme Points of View: #2 Intelligence Without Representation
*Rodney Brooks*

Perception과 reasoning을 분리시켜서 AI를 생각하는 것이 옳은 것인지에 대한 의문을 제기.
- Reasoning task를 수행하기도 전에 representation을 먼저 수행하는 것이 옳은 것인가?

Human interventions (pre processing)
- Ingenuity of human utilized
- But not good for long term AI research

인간이 직접 개입하여 feature engineering을 수행한 정형화된 데이터를 가지고 AI 성능이 좋게 나온 논문은 의미가 없다고 주장.

