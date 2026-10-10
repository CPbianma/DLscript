---
type: graded-quiz
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 2
section: "Practice quiz: Multiclass Classification"
item_title: "Practice quiz: Multiclass Classification"
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/assignment-submission/d9Buy/practice-quiz-multiclass-classification
language: en
extracted_at: 2026-10-08T22:52:07+08:00
grade: 100%
status: success
---
# Practice quiz: Multiclass Classification

**Grade: 100%**

## Question 1 (GradedMultipleChoiceQuestion)

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/f38d2d9d-5e70-4900-bd84-baf812439294image2.png?expiry=1791556379828&hmac=mFO1aruu9Bxmzxw9Edwwp4zAf10dJGx1cE76WCLLGaM)

For a multiclass classification task that has 4 possible outputs, the sum of all the activations adds up to 1. For a multiclass classification task that has 3 possible outputs, the sum of all the activations should add up to ….

- [ ] It will vary, depending on the input x.
- [ ] More than 1
- [x] 1
- [ ] Less than 1

*Points: 1.1 / 1*

## Question 2 (GradedMultipleChoiceQuestion)

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/f38d2d9d-5e70-4900-bd84-baf812439294image4.png?expiry=1791556379847&hmac=tkxAAMy-obEYpNh2qRA2Ez4VbbZ-7DFUdgovPgb8sHo)

For multiclass classification, the cross entropy loss is used for training the model. If there are 4 possible classes for the output, and for a particular training example, the true class of the example is class 3 (y=3), then what does the cross entropy loss simplify to? [Hint: This loss should get smaller when a3a\_3a3​a, start subscript, 3, end subscript gets larger.]

- [x] −log(a3)-log(a\_3)−log(a3​)minus, l, o, g, left parenthesis, a, start subscript, 3, end subscript, right parenthesis
- [ ] z\_3/(z\_1+z\_2+z\_3+z\_4)
- [ ] z\_3
- [ ] −log(a1)+−log(a2)+−log(a3)+−log(a4)4\frac{-log(a\_1) + -log(a\_2) + -log(a\_3) + -log(a\_4) }{4}4−log(a1​)+−log(a2​)+−log(a3​)+−log(a4​)​start fraction, minus, l, o, g, left parenthesis, a, start subscript, 1, end subscript, right parenthesis, plus, minus, l, o, g, left parenthesis, a, start subscript, 2, end subscript, right parenthesis, plus, minus, l, o, g, left parenthesis, a, start subscript, 3, end subscript, right parenthesis, plus, minus, l, o, g, left parenthesis, a, start subscript, 4, end subscript, right parenthesis, divided by, 4, end fraction

*Points: 1 / 1*

## Question 3 (GradedMultipleChoiceQuestion)

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/f38d2d9d-5e70-4900-bd84-baf812439294image5.png?expiry=1791556379865&hmac=bf9G7NY2sTxHMSgPpH15svked08FVTEsFfw_39rVwOo)

For multiclass classification, the recommended way to implement softmax regression is to set from\_logits=True in the loss function, and also to define the model's output layer with…

- [ ] a 'softmax' activation
- [x] a 'linear' activation

*Points: 1 / 1*

