---
type: graded-quiz
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 3
section: "Practice quiz: Bias and variance"
item_title: "Practice quiz: Bias and variance"
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/assignment-submission/FakV2/practice-quiz-bias-and-variance
language: en
extracted_at: 2026-10-08T22:52:07+08:00
grade: 100%
status: success
---
# Practice quiz: Bias and variance

**Grade: 100%**

## Question 1 (GradedMultipleChoiceQuestion)

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/0597681e-6ccc-4f13-bd62-6c322925cf90image5.png?expiry=1791556467944&hmac=LUeN69yJPw-PKOZxqmX59AJ1ls18Mw9bwVGx74lQaZk)

If the model's cross validation error JcvJ\_{cv}Jcv​J, start subscript, c, v, end subscript is much higher than the training error JtrainJ\_{train}Jtrain​J, start subscript, t, r, a, i, n, end subscript, this is an indication that the model has…

- [ ] Low bias
- [ ] high bias
- [x] high variance
- [ ] Low variance

*Points: 1 / 1*

## Question 2 (GradedMultipleChoiceQuestion)

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/0597681e-6ccc-4f13-bd62-6c322925cf90image3.png?expiry=1791556467966&hmac=Up8taAioo5Ejxwu6v7CuWwiaZYGb4RulteGMm44fLsA)

Which of these is the best way to determine whether your model has high bias (has underfit the training data)?

- [x] Compare the training error to the baseline level of performance
- [ ] See if the training error is high (above 15% or so)
- [ ] See if the cross validation error is high compared to the baseline level of performance
- [ ] Compare the training error to the cross validation error.

*Points: 1 / 1*

## Question 3 (GradedCheckboxQuestion)

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/0597681e-6ccc-4f13-bd62-6c322925cf90image4.png?expiry=1791556467982&hmac=k02bSA5WKujQNmDHa1G5CbPkKXjmRFgZT8Y-tzaegdc)

You find that your algorithm has high bias. Which of these seem like good options for improving the algorithm’s performance? Hint: two of these are correct.

- [ ] Remove examples from the training set
- [x] Collect additional features or add polynomial features ✅correct
  > Feedback: Nice work Correct. More features could potentially help the model better fit the training examples.
- [ ] Collect more training examples
- [x] Decrease the regularization parameter λ\lambdaλlambda (lambda) ✅correct
  > Feedback: Nice work Correct. Decreasing regularization can help the model better fit the training data.

*Points: 1 / 1*

## Question 4 (GradedCheckboxQuestion)

You find that your algorithm has a training error of 2%, and a cross validation error of 20% (much higher than the training error). Based on the conclusion you would draw about whether the algorithm has a high bias or high variance problem, which of these seem like good options for improving the algorithm’s performance? Hint: two of these are correct.

- [x] Collect more training data ✅correct
  > Feedback: Nice work Yes, the model appears to have high variance (overfit), and collecting more training examples would help reduce high variance.
- [ ] Reduce the training set size
- [x] Increase the regularization parameter λ\lambdaλlambda ✅correct
  > Feedback: Nice work Yes, the model appears to have high variance (overfit), and increasing regularization would help reduce high variance.
- [ ] Decrease the regularization parameter λ\lambdaλlambda

*Points: 1 / 1*

