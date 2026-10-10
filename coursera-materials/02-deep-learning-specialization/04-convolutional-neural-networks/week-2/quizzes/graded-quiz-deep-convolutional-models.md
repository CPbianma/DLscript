---
type: graded-quiz
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 2
section: Quiz
item_title: Deep Convolutional Models    
source_url: https://www.coursera.org/learn/convolutional-neural-networks/assignment-submission/40woH/deep-convolutional-models
language: en
extracted_at: 2026-10-08T22:59:23+08:00
grade: 90%
status: success
---
# Deep Convolutional Models    

**Grade: 90%**

## Question 1 (GradedCheckboxQuestion)

Which of the following do you typically see in a ConvNet? (Check all that apply.)

- [x] FC layers in the last few layers ✅correct
  > Feedback: Nice work True, fully-connected layers are often used after flattening a volume to output a set of classes in classification.
- [x] Multiple CONV layers followed by a POOL layer ✅correct
  > Feedback: Nice work True, as seen in the case studies.
- [ ] Multiple POOL layers followed by a CONV layer
- [ ] FC layers in the first few layers

*Points: 1 / 1*

## Question 2 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Yes, back in 1998 when the corresponding paper of LeNet - 5 was written padding wasn't used.

LeNet - 5 made extensive use of padding to create valid convolutions, to avoid increasing the number of channels after every convolutional layer. True/False?

- [x] False
- [ ] True

*Points: 1 / 1*

## Question 3 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Yes, in theory, we expect that as we increase the number of layers the training error decreases; but in practice after a certain number of layers the error increases.

Based on the lectures, in the following picture, which curve corresponds to the expected behavior in theory, and which one corresponds to the behavior we get in practice? This when using plain neural networks.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/a665934e-d0b4-4079-9319-f008654d7662_e0c0b924bf844e97b3a7a899912c2a89_bacb0bf3-933b-4d67-b89e-0cb74686df97image1.png?expiry=1791557858050&hmac=qmUv_Bd8YLIOyWjIvnppqWinyLdupMQmeyGDkMGDpM8)

- [ ] The green one depicts the results in theory, and also in practice.
- [ ] The blue one depicts the results in theory, and also in practice.
- [x] The green one depicts the results in theory, and the blue one the reality.
- [ ] The blue one depicts the theory, and the green one the reality.

*Points: 1 / 1*

## Question 4 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Correct

The following equation captures the computation in a ResNet block. What goes into the two blanks above?

a[l+2]=g(W[l+2]g(W[l+1]a[l]+b[l+1])+bl+2+\_\_\_\_\_\_\_ )+\_\_\_\_\_\_\_

- [ ] z[l]z^{[l]}z[l]z, start superscript, open bracket, l, close bracket, end superscript and a[l]a^{[l]}a[l]a, start superscript, open bracket, l, close bracket, end superscript, respectively
- [ ] 0 and a[l]a^{[l]}a[l]a, start superscript, open bracket, l, close bracket, end superscript, respectively
- [x] a[l]a^{[l]}a[l]a, start superscript, open bracket, l, close bracket, end superscript and 0, respectively
- [ ] 0000 and z[l+1]z^{[l+1]}z[l+1]z, start superscript, open bracket, l, plus, 1, close bracket, end superscript, respectively

*Points: 1 / 1*

## Question 5 (GradedMultipleChoiceQuestion)

**❌ Incorrect** — Try again Incorrect. When adding a ResNet block it can easily learn to approximate the identity function, thus in a worst-case scenario, it will not affect the performance of the network at all.

In the best scenario when adding a ResNet block it will learn to approximate the identity function after a lot of training, helping improve the overall performance of the network. True/False?

- [ ] False
- [x] True

*Points: 0 / 1*

## Question 6 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Yes, a 1 × 1 1×1 1, times, 1 layer doesn't act as a single number because it makes a sum over the depth of the volume.

1×11 \times 11×11, times, 1 convolutions are the same as multiplying by a single number. True/False?

- [ ] True
- [x] False

*Points: 1 / 1*

## Question 7 (GradedCheckboxQuestion)

Which of the following are true about the inception Network? (Check all that apply)

- [ ] Making an inception network deeper won't hurt the training set performance.
- [x] One problem with simply stacking up several layers is the computational cost of it. ✅correct
  > Feedback: Nice work Correct. That is why the bottleneck layer is used to reduce the computational cost.
- [x] Inception blocks allow the use of a combination of 1x1, 3x3, 5x5 convolutions and pooling by stacking up all the activations resulting from each type of layer. ✅correct
  > Feedback: Nice work Correct. The use of several different types of layers and stacking up the results to get a single volume is at the heart of the inception network.
- [ ] Inception blocks allow the use of a combination of 1x1, 3x3, 5x5 convolutions, and pooling by applying one layer after the other.

*Points: 1 / 1*

## Question 8 (GradedCheckboxQuestion)

Which of the following are common reasons for using open-source implementations of ConvNets (both the model and/or weights)? Check all that apply.

- [x] It is a convenient way to get working with an implementation of a complex ConvNet architecture. ✅correct
  > Feedback: Nice work True
- [ ] The same techniques for winning computer vision competitions, such as using multiple crops at test time, are widely used in practical deployments (or production system deployments) of ConvNets.
- [ ] A model trained for one computer vision task can usually be used to perform data augmentation for a different computer vision task.
- [x] Parameters trained for one computer vision task are often useful as pre-training for other computer vision tasks. ✅correct
  > Feedback: Nice work True

*Points: 1 / 1*

## Question 9 (GradedCheckboxQuestion)

Which of the following are true about Depth wise-separable convolutions? (Choose all that apply)

- [x] They have a lower computational cost than normal convolutions. ✅correct
  > Feedback: Nice work Yes, as seen in the lectures the use of the depthwise and pointwise convolution reduces the computational cost significantly.
- [ ] The result has always the same number of channels ncn\_cnc​n, start subscript, c, end subscript as the input.
- [ ] They are just a combination of a normal convolution and a bottleneck layer.
- [x] They combine depthwise convolutions with pointwise convolutions. ✅correct
  > Feedback: Nice work Correct, this combination is what we call depth wise separable convolutions.

*Points: 1 / 1*

## Question 10 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Correct, the size of the input and output volume of the depthwise convolution is determined by the number of filters in the expansion.

Suppose that in a MobileNet v2 Bottleneck block the input volume has shape 64×64×1664 \times 64 \times 1664×64×1664, times, 64, times, 16. If we use 32323232 filters for the expansion and 16161616 filters for the projection. What is the size of the input and output volume of the depthwise convolution, assuming a pad='same'?

- [ ] 32×32×3232 \times 32 \times 3232×32×3232, times, 32, times, 32, 32×32×3232 \times 32 \times 3232×32×3232, times, 32, times, 32
- [x] 64×64×3264 \times 64 \times 3264×64×3264, times, 64, times, 32, 64×64×3264 \times 64 \times 3264×64×3264, times, 64, times, 32
- [ ] 64×64×1664 \times 64 \times 1664×64×1664, times, 64, times, 16, 64×64×3264 \times 64 \times 3264×64×3264, times, 64, times, 32
- [ ] 64×64×3264 \times 64 \times 3264×64×3264, times, 64, times, 32, 64×64×1664 \times 64 \times 1664×64×1664, times, 64, times, 16

*Points: 1 / 1*

