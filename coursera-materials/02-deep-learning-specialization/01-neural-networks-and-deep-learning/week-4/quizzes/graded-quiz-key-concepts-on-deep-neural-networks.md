---
type: graded-quiz
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 4
section: Quiz
item_title: Key Concepts on Deep Neural Networks                 
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/assignment-submission/hE8Y3/key-concepts-on-deep-neural-networks
language: en
extracted_at: 2026-10-08T22:59:23+08:00
grade: 90%
status: success
---
# Key Concepts on Deep Neural Networks                 

**Grade: 90%**

## Question 1 (GradedMultipleChoiceQuestion)

**❌ Incorrect** — Try again Incorrect. The "cache" is used in our implementation to store values computed during forward propagation to be used in backward propagation.

We use the "cache" in our implementation of forward and backward propagation to pass useful values to the next layer in the forward propagation. True/False?

- [ ] False
- [x] True

*Points: 0 / 1*

## Question 2 (GradedCheckboxQuestion)

Among the following, which ones are "hyperparameters"? (Check all that apply.)

- [x] size of the hidden layers n[l]n^{[l]}n[l]n, start superscript, open bracket, l, close bracket, end superscript ✅correct
  > Feedback: Nice work
- [ ] weight matrices W[l]W^{[l]}W[l]W, start superscript, open bracket, l, close bracket, end superscript
- [x] number of iterations ✅correct
  > Feedback: Nice work
- [x] learning rate α\alphaαalpha ✅correct
  > Feedback: Nice work
- [x] number of layers LLLL in the neural network ✅correct
  > Feedback: Nice work
- [ ] activation values a[l]a^{[l]}a[l]a, start superscript, open bracket, l, close bracket, end superscript
- [ ] bias vectors b[l]b^{[l]}b[l]b, start superscript, open bracket, l, close bracket, end superscript

*Points: 1 / 1*

## Question 3 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work

Which of the following statements is true?

- [ ] The earlier layers of a neural network are typically computing more complex features of the input than the deeper layers.
- [x] The deeper layers of a neural network are typically computing more complex features of the input than the earlier layers.

*Points: 1 / 1*

## Question 4 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Correct. We can use vectorization in backpropagation to calculate 𝑑 𝐴 [ 𝑙 ] dA [l] d, A, start superscript, open bracket, l, close bracket, end superscript for each layer. This computation is done over all the training examples.

We can not use vectorization to calculate da[l]da^{[l]}da[l]d, a, start superscript, open bracket, l, close bracket, end superscript in backpropagation, we must use a for loop over all the examples. True/False?

- [ ] True
- [x] False

*Points: 1 / 1*

## Question 5 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Yes. Remember that the range omits the last number thus the range from 1 to L+1 gives the L necessary values.

Suppose W[i] is the array with the weights of the i-th layer, b[i] is the vector of biases of the i-th layer, and g is the activation function used in all layers. Which of the following calculates the forward propagation for the neural network with L layers.

- [ ] for i in range(1, L): Z[i] = W[i]\*A[i-1] + b[i] A[i] = g(Z[i])
- [ ] for i in range(L): Z[i] = W[i]\*X + b[i] A[i] = g(Z[i])
- [x] for i in range(1, L+1): Z[i] = W[i]\*A[i-1] + b[i] A[i] = g(Z[i])
- [ ] for i in range(L): Z[i+1] = W[i+1]\*A[i+1] + b[i+1] A[i+1] = g(Z[i+1])

*Points: 1 / 1*

## Question 6 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Yes. As seen in lecture, the number of layers is counted as the number of hidden layers + 1. The input and output layers are not counted as hidden layers.

Consider the following neural network.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/e16b8129-f87d-43a4-b4d5-7e854b445ac0_dc2be0ec1c2d4c32a1eadee8e7521201_ae17fa57-4712-4920-a9be-2c218d276e53image6.png?expiry=1791557753247&hmac=axuPXDAOsKOT83_Lo7_WD7oVVqhVjCA9KulD6DOlEgQ)

How many layers does this network have?

- [x] The number of layers LLLL is 4. The number of hidden layers is 3.
- [ ] The number of layers LLLL is 5. The number of hidden layers is 4.
- [ ] The number of layers LLLL is 3. The number of hidden layers is 3.
- [ ] The number of layers LLLL is 4. The number of hidden layers is 4.

*Points: 1 / 1*

## Question 7 (GradedMultipleChoiceQuestion)

**❌ Incorrect** — Try again No, as you've seen in week 3 each activation has a different derivative. Thus, during backpropagation you need to know which activation was used in the forward propagation to be able to compute the correct derivative.

During forward propagation, in the forward function for a layer llll you need to know what is the activation function in a layer (sigmoid, tanh, ReLU, etc.). During backpropagation, the corresponding backward function also needs to know what is the activation function for layer llll, since the gradient depends on it. True/False?

- [ ] True
- [x] False

*Points: 0 / 1*

## Question 8 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Correct. As seen during the lectures there are functions you can compute with a "small" L-layer deep neural network that shallower networks require exponentially more hidden units to compute.

A shallow neural network with a single hidden layer and 6 hidden units can compute any function that a neural network with 2 hidden layers and 6 hidden units can compute. True/False?

- [ ] True
- [x] False

*Points: 1 / 1*

## Question 9 (GradedCheckboxQuestion)

Consider the following 2 hidden layer neural network:

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/f60e7ccd-66f4-4dd1-835d-476348ca1412_c3ab2eb8488048388820861784f2db25_ae17fa57-4712-4920-a9be-2c218d276e53image8.png?expiry=1791557753265&hmac=KzESLACWCfzkHT7jLnJkQmATxw9dZeIdh33HPqGP0Bs)

Which of the following statements are True? (Check all that apply).

- [x] W[2]W^{[2]}W[2]W, start superscript, open bracket, 2, close bracket, end superscript will have shape (3, 4) ✅correct
  > Feedback: Nice work Yes. More generally, the shape of 𝑊 [ 𝑙 ] W [l] W, start superscript, open bracket, l, close bracket, end superscript is ( 𝑛 [ 𝑙 ] , 𝑛 [ 𝑙 − 1 ] ) (n [l] ,n [l−1] ) left parenthesis, n, start superscript, open bracket, l, close bracket, end superscript, comma, n, start superscript, open bracket, l, minus, 1, close bracket, end superscript, right parenthesis .
- [x] b[1]b^{[1]}b[1]b, start superscript, open bracket, 1, close bracket, end superscript will have shape (4, 1) ✅correct
  > Feedback: Nice work Yes. More generally, the shape of 𝑏 [ 𝑙 ] b [l] b, start superscript, open bracket, l, close bracket, end superscript is ( 𝑛 [ 𝑙 ] , 1 ) (n [l] ,1) left parenthesis, n, start superscript, open bracket, l, close bracket, end superscript, comma, 1, right parenthesis .
- [ ] b[1]b^{[1]}b[1]b, start superscript, open bracket, 1, close bracket, end superscript will have shape (3, 1)
- [ ] b[2]b^{[2]}b[2]b, start superscript, open bracket, 2, close bracket, end superscript will have shape (1, 1)
- [x] b[2]b^{[2]}b[2]b, start superscript, open bracket, 2, close bracket, end superscript will have shape (3, 1) ✅correct
  > Feedback: Nice work Yes. More generally, the shape of 𝑏 [ 𝑙 ] b [l] b, start superscript, open bracket, l, close bracket, end superscript is ( 𝑛 [ 𝑙 ] , 1 ) (n [l] ,1) left parenthesis, n, start superscript, open bracket, l, close bracket, end superscript, comma, 1, right parenthesis .
- [x] W[3]W^{[3]}W[3]W, start superscript, open bracket, 3, close bracket, end superscript will have shape (1, 3) ✅correct
  > Feedback: Nice work Yes. More generally, the shape of 𝑊 [ 𝑙 ] W [l] W, start superscript, open bracket, l, close bracket, end superscript is ( 𝑛 [ 𝑙 ] , 𝑛 [ 𝑙 − 1 ] ) (n [l] ,n [l−1] ) left parenthesis, n, start superscript, open bracket, l, close bracket, end superscript, comma, n, start superscript, open bracket, l, minus, 1, close bracket, end superscript, right parenthesis .
- [ ] W[3]W^{[3]}W[3]W, start superscript, open bracket, 3, close bracket, end superscript will have shape (3, 1)
- [ ] b[3]b^{[3]}b[3]b, start superscript, open bracket, 3, close bracket, end superscript will have shape (3, 1)
- [x] W[1]W^{[1]}W[1]W, start superscript, open bracket, 1, close bracket, end superscript will have shape (4, 4) ✅correct
  > Feedback: Nice work Yes. More generally, the shape of 𝑊 [ 𝑙 ] W [l] W, start superscript, open bracket, l, close bracket, end superscript is ( 𝑛 [ 𝑙 ] , 𝑛 [ 𝑙 − 1 ] ) (n [l] ,n [l−1] ) left parenthesis, n, start superscript, open bracket, l, close bracket, end superscript, comma, n, start superscript, open bracket, l, minus, 1, close bracket, end superscript, right parenthesis .
- [ ] W[1]W^{[1]}W[1]W, start superscript, open bracket, 1, close bracket, end superscript will have shape (3, 4)
- [x] b[3]b^{[3]}b[3]b, start superscript, open bracket, 3, close bracket, end superscript will have shape (1, 1) ✅correct
  > Feedback: Nice work Yes. More generally, the shape of 𝑏 [ 𝑙 ] b [l] b, start superscript, open bracket, l, close bracket, end superscript is ( 𝑛 [ 𝑙 ] , 1 ) (n [l] ,1) left parenthesis, n, start superscript, open bracket, l, close bracket, end superscript, comma, 1, right parenthesis .
- [ ] W[2]W^{[2]}W[2]W, start superscript, open bracket, 2, close bracket, end superscript will have shape (3, 1)

*Points: 1 / 1*

## Question 10 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work True. 𝑏 [ 𝑙 ] b [l] b, start superscript, open bracket, l, close bracket, end superscript is a column vector with the same number of rows as units in the respective layer.

Whereas the previous question used a specific network, in the general case what is the dimension of b[l]b^{[l]}b[l]b, start superscript, open bracket, l, close bracket, end superscript, the bias vector associated with layer l?

- [ ] b[l]b^{[l]}b[l]b, start superscript, open bracket, l, close bracket, end superscript has shape (n[l+1],1)(n^{[l+1]}, 1)(n[l+1],1)left parenthesis, n, start superscript, open bracket, l, plus, 1, close bracket, end superscript, comma, 1, right parenthesis
- [ ] b[l]b^{[l]}b[l]b, start superscript, open bracket, l, close bracket, end superscript has shape (1,n[l])(1, n^{[l]})(1,n[l])left parenthesis, 1, comma, n, start superscript, open bracket, l, close bracket, end superscript, right parenthesis
- [ ] b[l]b^{[l]}b[l]b, start superscript, open bracket, l, close bracket, end superscript has shape (1,n[l−1])(1, n^{[l-1]})(1,n[l−1])left parenthesis, 1, comma, n, start superscript, open bracket, l, minus, 1, close bracket, end superscript, right parenthesis
- [x] b[l]b^{[l]}b[l]b, start superscript, open bracket, l, close bracket, end superscript has shape (n[l],1)(n^{[l]}, 1)(n[l],1)left parenthesis, n, start superscript, open bracket, l, close bracket, end superscript, comma, 1, right parenthesis

*Points: 1 / 1*

