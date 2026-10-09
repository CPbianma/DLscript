---
type: graded-quiz
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 4
section: Quiz
item_title: Special Applications: Face Recognition & Neural Style Transfer   
source_url: https://www.coursera.org/learn/convolutional-neural-networks/assignment-submission/61BHW/special-applications-face-recognition-neural-style-transfer
language: en
extracted_at: 2026-10-08T22:59:23+08:00
grade: 90%
status: success
---
# Special Applications: Face Recognition & Neural Style Transfer   

**Grade: 90%**

## Question 1 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Correct.

Face verification requires comparing a new picture against one person’s face, whereas face recognition requires comparing a new picture against K persons’ faces.

- [ ] False
- [x] True

*Points: 1 / 1*

## Question 2 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Correct. One-shot learning refers to the amount of data we have to solve a task.

Why is the face verification problem considered a one-shot learning problem? Choose the best answer.

- [x] Because we might have only one example of the person we want to verify.
- [ ] Because of the sensitive nature of the problem, we won't have a chance to correct it if the network makes a mistake.
- [ ] Because we are trying to compare to one specific person only.
- [ ] Because we have only have to forward pass the image one time through our neural network for verification.

*Points: 1 / 1*

## Question 3 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Correct, to train a network using the triplet loss you need several pictures of the same person.

In order to train the parameters of a face recognition system, it would be reasonable to use a training set comprising 100,000 pictures of 100,000 different persons.

- [ ] True
- [x] False

*Points: 1 / 1*

## Question 4 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Correct. In this case ∥ 𝑓 ( 𝐴 ) − 𝑓 ( 𝑃 ) ∥ 2 − ∥ 𝑓 ( 𝐴 ) − 𝑓 ( 𝑁 ) ∥ 2 ∥f(A)−f(P)∥ 2 −∥f(A)−f(N)∥ 2 \|, f, left parenthesis, A, right parenthesis, minus, f, left parenthesis, P, right parenthesis, \|, squared, minus, \|, f, left parenthesis, A, right parenthesis, minus, f, left parenthesis, N, right parenthesis, \|, squared is positive thus the triplet loss gives a positive value larger than 𝛼 α alpha .

Triplet loss:

max⁡(∥f(A)−f(P)∥2−∥f(A)−f(N)∥2+α,0) \max \left( \left\| f(A) - f(P) \right\|^2 - \left\| f(A) - f(N) \right\|^2 + \alpha, 0 \right)max(∥f(A)−f(P)∥2−∥f(A)−f(N)∥2+α,0)\max, left parenthesis, \|, f, left parenthesis, A, right parenthesis, minus, f, left parenthesis, P, right parenthesis, \|, squared, minus, \|, f, left parenthesis, A, right parenthesis, minus, f, left parenthesis, N, right parenthesis, \|, squared, plus, alpha, comma, 0, right parenthesis

is larger in which of the following cases?

- [ ] When A=PA = PA=PA, equals, P and A=NA = NA=NA, equals, N.
- [ ] When the encoding of A is closer to the encoding of P than to the encoding of N.
- [x] When the encoding of A is closer to the encoding of N than to the encoding of P.

*Points: 1 / 1*

## Question 5 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Correct. Part of the idea behind the Siamese network is to compare the encoding of the images, thus they must be consistent.

Consider the following Siamese network architecture:

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/83847558-3b64-4af7-aaf3-56c13b3c6718_d956ed8ab4d140028fe72be0d0fb9a48_2c40a135-85bd-4f97-ac0e-54e4ca3ae477image1.png?expiry=1791557884316&hmac=ElI9lmW5ayQin6zyZTwCiTj3g4mO41HCaiyx6ABHB00)

The upper and lower networks share parameters to have a consistent encoding for both images. True/False?

- [ ] False
- [x] True

*Points: 1 / 1*

## Question 6 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Correct. Neurons that understand more complex shapes are more likely to be in deeper layers of a neural network.

Our intuition about the layers of a neural network tells us that units that respond more to complex features are more likely to be in deeper layers. True/False?

- [x] True
- [ ] False

*Points: 1 / 1*

## Question 7 (GradedMultipleChoiceQuestion)

**❌ Incorrect** — Try again Neural style transfer compares the high-level features of two images and modifies the pixels of one of them in order to look artistic.

In neural style transfer, we train the pixels of an image, and not the parameters of a network.

- [ ] True
- [x] False

*Points: 0 / 1*

## Question 8 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Yes, the style matrix 𝐺 [ 𝑙 ] G [l] G, start superscript, open bracket, l, close bracket, end superscript can be seen as a matrix of cross-correlations between the different feature detectors.

In the deeper layers of a ConvNet, each channel corresponds to a different feature detector. The style matrix G[l]G^{[l]}G[l]G, start superscript, open bracket, l, close bracket, end superscript measures the degree to which the activations of different feature detectors in layer llll vary (or correlate) together with each other.

- [x] True
- [ ] False

*Points: 1 / 1*

## Question 9 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Correct, we use the gradient of the cost function over the value of the pixels of the generated image.

In neural style transfer, which of the following better express the gradients used?

- [ ] ∂J∂S\frac{\partial J}{\partial S}∂S∂J​start fraction, \partial, J, divided by, \partial, S, end fraction
- [ ] Neural style transfer doesn't use gradient descent since there are no trainable parameters.
- [ ] ∂J∂W[l]\frac{\partial J}{\partial W^{[l]}}∂W[l]∂J​start fraction, \partial, J, divided by, \partial, W, start superscript, open bracket, l, close bracket, end superscript, end fraction
- [x] ∂J∂G\frac{\partial J}{\partial G}∂G∂J​start fraction, \partial, J, divided by, \partial, G, end fraction

*Points: 1 / 1*

## Question 10 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Correct, you have used the formula ⌊ 𝑛 [ 𝑙 − 1 ] − 𝑓 + 2 × 𝑝 𝑠 ⌋ + 1 = 𝑛 [ 𝑙 ] ⌊ s n [l−1] −f+2×p ​ ⌋+1=n [l] open floor, start fraction, n, start superscript, open bracket, l, minus, 1, close bracket, end superscript, minus, f, plus, 2, times, p, divided by, s, end fraction, close floor, plus, 1, equals, n, start superscript, open bracket, l, close bracket, end superscript over the three first dimensions of the input data.

You are working with 3D data. You are building a network layer whose input volume has size 32x32x32x16 (this volume has 16 channels), and applies convolutions with 32 filters of dimension 3x3x3x16 (no padding, stride 1). What is the resulting output volume?

- [ ] Undefined: This convolution step is impossible and cannot be performed because the dimensions specified don’t match up.
- [ ] 30x30x30x16
- [x] 30x30x30x32

*Points: 1 / 1*

