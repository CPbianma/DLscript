---
type: graded-quiz
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 1
section: Quiz
item_title: The Basics of ConvNets    
source_url: https://www.coursera.org/learn/convolutional-neural-networks/assignment-submission/jlqZk/the-basics-of-convnets
language: en
extracted_at: 2026-10-08T22:52:07+08:00
grade: 100%
status: success
---
# The Basics of ConvNets    

**Grade: 100%**

## Question 1 (GradedMultipleChoiceQuestion)

What do you think applying this filter to a grayscale image will do?

[−1−12−121211]\begin{bmatrix} -1 & -1 & 2 \\ -1 & 2 & 1 \\ 2 & 1 & 1 \end{bmatrix}⎣⎢⎡​−1−12​−121​211​⎦⎥⎤​\begin{bmatrix} -1 & -1 & 2 \\ -1 & 2 & 1 \\ 2 & 1 & 1 \end{bmatrix}

- [ ] Detect horizontal edges.
- [ ] Detect vertical edges.
- [x] Detect 45-degree edges.
- [ ] Detecting image contrast.

*Points: 1 / 1*

## Question 2 (GradedMultipleChoiceQuestion)

Suppose your input is a 300 by 300 color (RGB) image, and you are not using a convolutional network. If the first hidden layer has 100 neurons, each one fully connected to the input, how many parameters does this hidden layer have (including the bias parameters)?

- [ ] 9,000,100
- [x] 27,000,100
- [ ] 27,000,001
- [ ] 9,000,001

*Points: 100.1 / 1*

## Question 3 (GradedMultipleChoiceQuestion)

Suppose your input is a 256 by 256 grayscale image, and you use a convolutional layer with 128 filters that are each 3×33\times 33×33, times, 3. How many parameters does this hidden layer have (including the bias parameters)?

- [ ] 1152
- [x] 1280
- [ ] 3584
- [ ] 75497600

*Points: 128.1 / 1*

## Question 4 (GradedMultipleChoiceQuestion)

You have an input volume that is 63x63x16, and convolve it with 32 filters that are each 7x7, using a stride of 2 and no padding. What is the output volume?

- [ ] 16x16x16
- [ ] 29x29x16
- [ ] 16x16x32
- [x] 29x29x32

*Points: 1 / 1*

## Question 5 (GradedMultipleChoiceQuestion)

You have an input volume that is 15x15x8, and pad it using “pad=2”. What is the dimension of the resulting volume (after padding)?

- [ ] 19x19x12
- [ ] 17x17x10
- [x] 19x19x8
- [ ] 17x17x8

*Points: 1 / 1*

## Question 6 (GradedMultipleChoiceQuestion)

You have a volume that is 64×64×3264 \times 64 \times 3264×64×3264, times, 64, times, 32, and convolve it with 40 filters of 9×99\times 99×99, times, 9, and stride 1. You want to use a "same" convolution. What is the padding?

- [ ] 8
- [x] 4
- [ ] 0
- [ ] 6

*Points: 1.1 / 1*

## Question 7 (GradedMultipleChoiceQuestion)

You have an input volume that is 66x66x21, and apply max pooling with a stride of 3 and a filter size of 3. What is the output volume?

- [x] 22×22×2122 \times 22 \times 2122×22×2122, times, 22, times, 21
- [ ] 21×21×2121 \times 21 \times 2121×21×2121, times, 21, times, 21
- [ ] 22×22×722 \times 22 \times 722×22×722, times, 22, times, 7
- [ ] 66×66×766 \times 66 \times 766×66×766, times, 66, times, 7

*Points: 66.1 / 1*

## Question 8 (GradedCheckboxQuestion)

Which of the following are hyperparameters of the pooling layers? (Choose all that apply)

- [x] Stride ✅correct
  > Feedback: Nice work Yes, although usually, we set 𝑓 = 𝑠 f=s f, equals, s this is one of the hyperparameters of a pooling layer.
- [x] Whether it is max or average. ✅correct
  > Feedback: Nice work Yes, these are the two types of pooling discussed in the lectures, and choosing which to use is considered a hyperparameter.
- [ ] b[l]b^{[l]}b[l]b, start superscript, open bracket, l, close bracket, end superscript bias.
- [ ] W[l]W^{[l]}W[l]W, start superscript, open bracket, l, close bracket, end superscript weights.

*Points: 1 / 1*

## Question 9 (GradedCheckboxQuestion)

Which of the following are the benefits of using convolutional layers? (Check all that apply)

- [ ] It reduces the computations in backpropagation since we omit the convolutional layers in the process.
- [x] Convolutional layers are good at capturing translation invariance. ✅correct
  > Feedback: Nice work Yes, this is due in part to applying the same filter all over the image.
- [x] It reduces the total number of parameters, thus reducing overfitting through parameter sharing. ✅correct
  > Feedback: Nice work Yes, a convolutional layer uses parameters sharing and has usually a lot fewer parameters than a fully-connected layer.

*Points: 1 / 1*

## Question 10 (GradedMultipleChoiceQuestion)

The sparsity of connections and weight sharing are mechanisms that allow us to use fewer parameters in a convolutional layer making it possible to train a network with smaller training sets. True/False?

- [x] True
- [ ] False

*Points: 1 / 1*

