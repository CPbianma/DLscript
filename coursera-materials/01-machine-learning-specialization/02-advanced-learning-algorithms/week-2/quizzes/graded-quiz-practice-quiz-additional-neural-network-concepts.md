---
type: graded-quiz
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 2
section: "Practice quiz: Additional Neural Network Concepts"
item_title: "Practice quiz: Additional Neural Network Concepts"
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/assignment-submission/ljlgM/practice-quiz-additional-neural-network-concepts
language: en
extracted_at: 2026-10-08T22:52:07+08:00
grade: 100%
status: success
---
# Practice quiz: Additional Neural Network Concepts

**Grade: 100%**

## Question 1 (GradedMultipleChoiceQuestion)

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/b08fec87-b710-4ece-9022-9dcf48ab1305image3.png?expiry=1791556419737&hmac=McHkuFbzXIb-OaJWfs0ufZOcut3e9BNqiUJ6VIDm-cI)

The Adam optimizer is the recommended optimizer for finding the optimal parameters of the model. How do you use the Adam optimizer in TensorFlow?

- [ ] The call to model.compile() will automatically pick the best optimizer, whether it is gradient descent, Adam or something else. So there’s no need to pick an optimizer manually.
- [ ] The Adam optimizer works only with Softmax outputs. So if a neural network has a Softmax output layer, TensorFlow will automatically pick the Adam optimizer.
- [ ] The call to model.compile() uses the Adam optimizer by default
- [x] When calling model.compile, set optimizer=tf.keras.optimizers.Adam(learning\_rate=1e-3).

*Points: 1 / 1*

## Question 2 (GradedMultipleChoiceQuestion)

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/b08fec87-b710-4ece-9022-9dcf48ab1305image4.png?expiry=1791556419752&hmac=TPo1pl-PDNuu-_NuFa159YqlinQnKx14NUQR-P_eDGM)

The lecture covered a different layer type where each single neuron of the layer does not look at all the values of the input vector that is fed into that layer. What is this name of the layer type discussed in lecture?

- [ ] A fully connected layer
- [x] convolutional layer
- [ ] Image layer
- [ ] 1D layer or 2D layer (depending on the input dimension)

*Points: 1 / 1*

