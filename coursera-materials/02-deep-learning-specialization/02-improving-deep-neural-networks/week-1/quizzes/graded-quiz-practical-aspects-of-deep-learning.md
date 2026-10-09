---
type: graded-quiz
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 1
section: Quiz
item_title: Practical Aspects of Deep Learning   
source_url: https://www.coursera.org/learn/deep-neural-network/assignment-submission/yTz20/practical-aspects-of-deep-learning
language: en
extracted_at: 2026-10-08T22:59:23+08:00
grade: 93%
status: success
---
# Practical Aspects of Deep Learning   

**Grade: 93%**

## Question 1 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work

If you have 10,000,000 examples, how would you split the train/dev/test set?

- [ ] 60% train . 20% dev . 20% test
- [x] 98% train . 1% dev . 1% test
- [ ] 33% train . 33% dev . 33% test

*Points: 1 / 1*

## Question 2 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Yes. The quality and type of images are quite different thus we can't consider that the dev and the test sets came from the same distribution.

When designing a neural network to detect if a house cat is present in the picture, 500,000 pictures of cats were taken by their owners. **These are used to make the training, dev and test sets.** It is decided that to increase the size of the test set, 10,000 new images of cats taken from security cameras are going to be used in the test set. Which of the following is true?

- [ ] This will reduce the bias of the model and help improve it.
- [x] This will be harmful to the project since now dev and test sets have different distributions.
- [ ] This will increase the bias of the model so the new images shouldn't be used.

*Points: 1 / 1*

## Question 3 (GradedCheckboxQuestion)

If your Neural Network model seems to have high variance, what of the following would be promising things to try?

- [x] Get more training data ✅correct
  > Feedback: Nice work
- [x] Get more test data
  > Feedback: This should not be selected
- [ ] Make the Neural Network deeper
- [ ] Increase the number of units in each hidden layer
- [x] Add regularization ✅correct
  > Feedback: Nice work

*Points: 0.8 / 1*

## Question 4 (GradedCheckboxQuestion)

Your classifier for bananas and oranges gets a training set error of 0.1% and a development set error of 11%.

**Which of the following statements are true?** (Check all that apply.)

- [ ] The model is overfitting the training set.
- [x] The model has a high variance. ✅correct
  > Feedback: Nice work The large gap between training and development set errors is a hallmark of high variance.
- [ ] The model has a very high bias.
- [x] The model is overfitting the development set.
  > Feedback: This should not be selected Overfitting the development set would result in a very low error on it.

*Points: 0.5 / 1*

## Question 5 (GradedCheckboxQuestion)

Which of the following are regularization techniques?

- [x] Weight decay. ✅correct
  > Feedback: Nice work Correct. Weight decay is a form of regularization.
- [ ] Increase the number of layers of the network.
- [x] Dropout. ✅correct
  > Feedback: Nice work Correct. Using dropout layers is a regularization technique.
- [ ] Gradient Checking.

*Points: 1 / 1*

## Question 6 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work

What happens when you increase the regularization hyperparameter lambda?

- [x] Weights are pushed toward becoming smaller (closer to 0)
- [ ] Weights are pushed toward becoming bigger (further from 0)
- [ ] Doubling lambda should roughly result in doubling the weights
- [ ] Gradient descent taking bigger steps with each iteration (proportional to lambda)

*Points: 1 / 1*

## Question 7 (GradedCheckboxQuestion)

Which of the following are true about dropout?

- [x] In practice, it eliminates units of each layer with a probability of 1- keep\_prob. ✅correct
  > Feedback: Nice work Correct. The dropout is a regularization technique and thus helps to reduce the overfit.
- [x] It helps to reduce the variance of a model. ✅correct
  > Feedback: Nice work Correct. The dropout is a regularization technique and thus helps to reduce the variance.
- [ ] In practice, it eliminates units of each layer with a probability of keep\_prob.
- [ ] It helps to reduce the bias of a model.

*Points: 1 / 1*

## Question 8 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Correct. This will make the dropout have a higher probability of eliminating a node in the neural network, increasing the regularization effect.

Decreasing the parameter keep\_prob from (say) 0.6 to 0.4 will likely cause the following:

- [x] Increasing the regularization effect.
- [ ] Causing the neural network to have a higher variance.
- [ ] Reducing the regularization effect.

*Points: 1 / 1*

## Question 9 (GradedCheckboxQuestion)

Which of these techniques are useful for reducing variance (reducing overfitting)? (Check all that apply.)

- [x] Dropout ✅correct
  > Feedback: Nice work
- [ ] Exploding gradient
- [ ] Xavier initialization
- [ ] Vanishing gradient
- [ ] Gradient Checking
- [x] L2 regularization ✅correct
  > Feedback: Nice work
- [x] Data augmentation ✅correct
  > Feedback: Nice work

*Points: 1 / 1*

## Question 10 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Correct. Since the difference between the ranges of the features is very different, this will likely cause the process of gradient descent to oscillate, making the optimization process longer.

Suppose that a model uses, as one feature, the total number of kilometers walked by a person during a year, and another feature is the height of the person in meters. What is the most likely effect of normalization of the input data?

- [ ] It won't have any positive or negative effects.
- [x] It will make the training faster.
- [ ] It will make the data easier to visualize.
- [ ] It will increase the variance of the model.

*Points: 1 / 1*

