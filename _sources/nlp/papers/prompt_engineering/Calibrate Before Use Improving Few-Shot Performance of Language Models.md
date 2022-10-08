# Calibrate Before Use: Improving Few-Shot Performance of Language Models

Tony Z. Zhao, Eric Wallace, Shi Feng, Dan Klein, Sameer Singh  
[Paper](http://proceedings.mlr.press/v139/zhao21c.html)  
[Github](https://github.com/tonyzhaozh/few-shot-learning)  

## Abstract

- Shows that few-shot prompting for large language models like GPT-3 can be unstable
- Demonstrate that this instability arises from the bias of language models towards predicting certain answers
- Mitigate model biases by first estimating the model's bias towards each answer by asking for its prediction when given the training prompt and a content-free test input (e.g. "N/A")
- Then fit calibration parameters that cause the prediction for this input to be uniform across answers

## Introduction

### Few-shot learning

- Ability to learn tasks with limited examples
- Few-shot "in-context" learning shows that model can learn without parameter updates
- Example:

```text
Input: Subpar acting.  Sentiment: Negative
Input: Beautiful film. Sentiment: Positive
Input: Amazing.        Sentiment:
```

### Instability

- Shows GPT-3 accuracy can be highly unstable across different prompts
- Causes of instability:
  - Majority label bias
  - Recency bias
  - Common token bias
