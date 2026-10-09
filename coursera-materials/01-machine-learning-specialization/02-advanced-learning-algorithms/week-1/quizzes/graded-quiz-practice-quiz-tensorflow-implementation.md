---
type: graded-quiz
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 1
section: "Practice quiz: TensorFlow implementation"
item_title: "Practice quiz: TensorFlow implementation"
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/assignment-submission/75mlV/practice-quiz-tensorflow-implementation
language: en
extracted_at: 2026-10-08T22:52:07+08:00
grade: 100%
status: success
---
# Practice quiz: TensorFlow implementation

**Grade: 100%**

## Question 1 (GradedMultipleChoiceQuestion)

For the the following code:

model = Sequential([

Dense(units=25, activation="sigmoid"),

Dense(units=15, activation="sigmoid"),

Dense(units=10, activation="sigmoid"),

Dense(units=1, activation="sigmoid")])

This code will define a neural network with how many layers?

- [ ] 3
- [ ] 25
- [ ] 5
- [x] 4

*Points: 1 / 1*

## Question 2 (GradedMultipleChoiceQuestion)

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/98c635c3-33fc-4d9c-9af5-6f1f18da35aeimage2.png?expiry=1791556264944&hmac=zaYj_IruROKH_Ympky20zAktRbSkA0NgTgcPEjNSBcs)

How do you define the second layer of a neural network that has 4 neurons and a sigmoid activation?

- [x] Dense(units=4, activation=‘sigmoid’)
- [ ] Dense(units=[4], activation=[‘sigmoid’])
- [ ] Dense(layer=2, units=4, activation = ‘sigmoid’)
- [ ] Dense(units=4)

*Points: 1 / 1*

## Question 3 (GradedMultipleChoiceQuestion)

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/98c635c3-33fc-4d9c-9af5-6f1f18da35aeimage3.png?expiry=1791556264965&hmac=m3XH4Argiw3HMHhecYjba1y_UvIKfeO4fLyQPIE2vlk)

If the input features are temperature (in Celsius) and duration (in minutes), how do you write the code for the first feature vector x shown above?

- [x] x = np.array([[200.0, 17.0]])
- [ ] x = np.array([[200.0],[17.0]])
- [ ] x = np.array([[200.0 + 17.0]])
- [ ] x = np.array([[‘200.0’, ’17.0’]])

*Points: 1 / 1*

