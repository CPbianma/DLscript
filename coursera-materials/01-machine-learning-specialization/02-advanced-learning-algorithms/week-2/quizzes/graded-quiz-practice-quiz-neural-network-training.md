---
type: graded-quiz
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 2
section: "Practice quiz: Neural Network Training"
item_title: "Practice quiz: Neural Network Training"
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/assignment-submission/nBZd2/practice-quiz-neural-network-training
language: en
extracted_at: 2026-10-08T22:52:07+08:00
grade: 100%
status: success
---
# Practice quiz: Neural Network Training

**Grade: 100%**

## Question 1 (GradedMultipleChoiceQuestion)

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/141c2e0d-b88f-4876-a375-6b18af36255fimage3.png?expiry=1791556320711&hmac=MbkpgqaI3VWD1S7fHaz51_wFVMBATigDhpkJbM-NJqs)

Here is some code that you saw in the lecture:

```

model.compile(loss=BinaryCrossentropy())

```

For which type of task would you use the binary cross entropy loss function?

- [ ] A classification task that has 3 or more classes (categories)
- [ ] BinaryCrossentropy() should not be used for any task.
- [ ] regression tasks (tasks that predict a number)
- [x] binary classification (classification with exactly 2 classes)

*Points: 1 / 1*

## Question 2 (GradedMultipleChoiceQuestion)

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/141c2e0d-b88f-4876-a375-6b18af36255fimage3.png?expiry=1791556320723&hmac=FxNwzEzrqK4yObo2nMFXhCv-NMf_na4hTNA1NcG4xcY)

Here is code that you saw in the lecture:

```

model = Sequential([

Dense(units=25, activation='sigmoid’),

Dense(units=15, activation='sigmoid’),

Dense(units=1, activation='sigmoid’)

])

model.compile(loss=BinaryCrossentropy())

model.fit(X,y,epochs=100)

```

Which line of code updates the network parameters in order to reduce the cost?

- [ ] None of the above -- this code does not update the network parameters.
- [x] model.fit(X,y,epochs=100)
- [ ] model = Sequential([...])
- [ ] model.compile(loss=BinaryCrossentropy())

*Points: 1 / 1*

