---
type: graded-quiz
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 3
section: Practice quiz: Machine learning development process
item_title: Practice quiz: Machine learning development process
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/assignment-submission/eXHPZ/practice-quiz-machine-learning-development-process
language: en
extracted_at: 2026-10-08T22:52:07+08:00
grade: 100%
status: success
---
# Practice quiz: Machine learning development process

**Grade: 100%**

## Question 1 (GradedMultipleChoiceQuestion)

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/25ef86da-6935-47cf-a4af-8945fa6a0ed2image5.png?expiry=1791556500293&hmac=VXjk35wko0AZpPbc1wDq93rNOi4mM4f8P3gS_-RL4Aw)

Which of these is a way to do error analysis?

- [ ] Calculating the test error JtestJ\_{test}Jtest​J, start subscript, t, e, s, t, end subscript
- [x] Manually examine a sample of the training examples that the model misclassified in order to identify common traits and trends.
- [ ] Calculating the training error JtrainJ\_{train}Jtrain​J, start subscript, t, r, a, i, n, end subscript
- [ ] Collecting additional training data in order to help the algorithm do better.

*Points: 1 / 1*

## Question 2 (GradedMultipleChoiceQuestion)

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/25ef86da-6935-47cf-a4af-8945fa6a0ed2image3.png?expiry=1791556500309&hmac=GVNBlVCMVNdRojCKTR5wgPs_vhNDvaHSz0N7UM9eFRk)

We sometimes take an existing training example and modify it (for example, by rotating an image slightly) to create a new example with the same label. What is this process called?

- [ ] Machine learning diagnostic
- [x] Data augmentation
- [ ] Error analysis
- [ ] Bias/variance analysis

*Points: 1 / 1*

## Question 3 (GradedCheckboxQuestion)

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/25ef86da-6935-47cf-a4af-8945fa6a0ed2image4.png?expiry=1791556500325&hmac=guE-3FDLO60J7J2Ee1DUcZ6w69TOIgkvcOGQiaF4-Lk)

What are two possible ways to perform transfer learning? Hint: two of the four choices are correct.

- [ ] Given a dataset, pre-train and then further fine tune a neural network on the same dataset.
- [ ] Download a pre-trained model and use it for prediction without modifying or re-training it.
- [x] You can choose to train all parameters of the model, including the output layers, as well as the earlier layers. ✅correct
  > Feedback: Nice work Correct. It may help to train all the layers of the model on your own training set. This may take more time compared to if you just trained the parameters of the output layers.
- [x] You can choose to train just the output layers' parameters and leave the other parameters of the model fixed. ✅correct
  > Feedback: Nice work Correct. The earlier layers of the model may be reusable as is, because they are identifying low level features that are relevant to your task.

*Points: 1 / 1*

