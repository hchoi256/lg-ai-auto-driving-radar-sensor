****
### Terms
- Representation DL

# Representation DL
![image](https://user-images.githubusercontent.com/39285147/178970367-8252ae9a-7cc5-4ba4-b226-d5a1b58b295c.png)

Deep Learning Representation is (Severly) Under Constrained
- Good news
  - Simple SGD can find one of the useful networks(countless)
  - Representation characteristics can be adjusted if needed
- Bad news
  - Learned representation becomes difficult to undertand

## Deep Learning
![image](https://user-images.githubusercontent.com/39285147/178969881-bf60b2ed-f6ce-4456-b17a-60491583aab9.png)

- Obviously, no “formal system with a specification”
- What properties need to be satisfied?
- Can we interpret a specific representation (or a neuron)

### Disentangled Representation
![image](https://user-images.githubusercontent.com/39285147/178970887-f58a74ea-690f-4e6a-8fc5-3cec60664edf.png)

- Aligned
- Independendent
- Subspaces
- Possible because “severaly underconstrained”

# Task and Representation
## A Well Defined Task
![image](https://user-images.githubusercontent.com/39285147/178970866-01019cc6-bcf8-43c6-a6e5-e3bea9025d38.png)

Typically, only one attribute of interest is considered as y
- Imagenet class
- y is well defined because it is simply defined as human selected label

## Good Representation A Vague Concept (*Supervised*)
![image](https://user-images.githubusercontent.com/39285147/178971042-a881d465-c512-403a-ae02-5cf2c4484fd2.png)

- Even when y is well defined, what do we want for h1 and h2
  - Simply say “representation learning successful” if good performance?
    - But then there is almost nothing we can say about h 1 and h 2
    - Other than saying “useful information has been well curated"
  - Is there anything we can say or pursue?

### Information Bottleneck
![image](https://user-images.githubusercontent.com/39285147/178971133-ad40085f-2f28-4303-b415-14531e5ddc5f.png)

- For a w ell defined supervised task
- What should h1 and h2 satisfy?

## Good Representation A Vague Concept (*Unsupervised*)
For a general purpose, what is a good representation?
- “general often defined as a list of downstream tasks?
- So, we go back to “good performance for the task(s) of interest?”

## Word Embedding - General Purpose?
![image](https://user-images.githubusercontent.com/39285147/178971701-69ebdde4-75be-4df4-bff0-f9994b82189d.png)

### Word2Vec
Word representation formed independent of the downstream task s
- But masking itself is a task
- Does it mean masking is a “general task”?
Linear relationship encouraged by linear skipgram
- Is “linear relationship” a universally desired representation property for NLP tasks?
Latest pre-trained language models
- Unsupervised (self supervised) objectives can be m a sking, denoising, etc.
- Embedding learned as a part of model
  - Linear relationship? (anyone knows the answer?)
- Can be fine tuned if needed


