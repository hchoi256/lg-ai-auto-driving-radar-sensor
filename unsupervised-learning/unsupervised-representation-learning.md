****
### Terms
- Unsupervised Representation Learning
- Pretext Learning
- Mutual Information
- Self-Supervised Learning
- Instance discrimination
- Constrastive loss

# Unsupervised Representation Learning
'제한된 조건 안에서 만든 문제'에서는 엄청난 좋은 성능을 내는 결과

## Pretext Learning - Representation Learning Driven by Task Design
![image](https://user-images.githubusercontent.com/39285147/179062286-209bfb6f-1b52-4da2-b477-fdc7b04d4611.png)

어떻게 Unsupervised Learning을 활용하여 데이터를 분석하고 잘 정리된 Representation, 유용한 정보를 만들기 위한 학습 Task

> Self-Supervised Learning
>> 스크립트 하나만으로 Supervised Dataset을 만들어 문제를 푸는 것 (*인간이 인풋을 주지 않는다*)
>>
>> Unsupervised Learning이지만 unlabeled 데이터를 labeled data로 보이게 만든다.

## Variational Mutual Informartion Estimation
![image](https://user-images.githubusercontent.com/39285147/179063615-05e013a9-b704-4fa1-ab20-83c809c246f9.png)

> Mutual Information
>> 어떻게 하면 여기 있는 이 Variable과 저 Variable 사이에 공유하는 정보의 양이 얼만큼인지 숫자로 계산해낼 수 있을까?

> Multiview Coding
>> 같은 콘셉트라면 어느 방향에서 찍은 사진이여도 결국은 같은 정보를 담고 있다. 따라서, 해당 사지을 뉴럴 네트워크를 통과시켜서 정보를 정리한 Activation 벡터가 비슷하게 생겨야 된다.

### SimCLR
![image](https://user-images.githubusercontent.com/39285147/179064246-93cd5b96-2818-4f93-9d1d-a30d4af60d7b.png)

데이터 증식을 통하여 학습을 수행하였을 때(Unsupervised), 전부 다 비슷한 벡터를 뱉어내야 된다는 것을 학습시킨다.

Unlabeled 데이터만 가지고 정보를 너무 잘 정리하다 보니, 그 위에다가 Supervised로 아주 간단한 Linear network만 살짝 튜닝을 해줘도 정보를 별로 안쓰고도 상당히 좋은 성능이 나온다.

After SimCLR, many MI variants by tweaking architecture and loss function…

# Key Concepts
## Instance discrimination
- 개별적 이미지 (an instance)를 하나의 class 로 정의
- An instance --> multiple augmentations
- Positive pair vs. negative pair

## Constrastive loss (InfoNCE loss)
![image](https://user-images.githubusercontent.com/39285147/179070630-1ee95fbf-b998-40ef-bfeb-795f9b9ee91c.png)


