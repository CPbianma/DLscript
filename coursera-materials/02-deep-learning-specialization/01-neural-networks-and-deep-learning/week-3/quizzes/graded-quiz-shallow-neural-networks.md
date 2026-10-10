---
type: graded-quiz
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 3
section: Quiz
item_title: Shallow Neural Networks                 
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/assignment-submission/mLgvR/shallow-neural-networks
language: en
extracted_at: 2026-10-08T22:59:23+08:00
grade: 96.66%
status: success
---
# Shallow Neural Networks                 

**Grade: 96.66%**

## Question 1 (GradedCheckboxQuestion)

Which of the following are true? (Check all that apply.)

- [x] a4[2]a^{[2]}\_4a4[2]​a, start subscript, 4, end subscript, start superscript, open bracket, 2, close bracket, end superscript is the activation output of the 2nd2^{nd}2nd2, start superscript, n, d, end superscript layer for the 4th4^{th}4th4, start superscript, t, h, end superscript training example
  > Feedback: This should not be selected
- [x] a[2](12)a^{[2](12)}a[2](12)a, start superscript, open bracket, 2, close bracket, left parenthesis, 12, right parenthesis, end superscript denotes activation vector of the 12th12^{th}12th12, start superscript, t, h, end superscript layer on the 2nd2^{nd}2nd2, start superscript, n, d, end superscript training example.
  > Feedback: This should not be selected
- [x] XXXX is a matrix in which each column is one training example. ✅correct
  > Feedback: Nice work
- [x] a[2]a^{[2]}a[2]a, start superscript, open bracket, 2, close bracket, end superscript denotes the activation vector of the 2nd2^{nd}2nd2, start superscript, n, d, end superscript layer. ✅correct
  > Feedback: Nice work
- [ ] XXXX is a matrix in which each row is one training example.
- [x] a[2](12)a^{[2](12)}a[2](12)a, start superscript, open bracket, 2, close bracket, left parenthesis, 12, right parenthesis, end superscript denotes the activation vector of the 2nd2^{nd}2nd2, start superscript, n, d, end superscript layer for the 12th12^{th}12th12, start superscript, t, h, end superscript training example. ✅correct
  > Feedback: Nice work
- [x] a4[2]a^{[2]}\_4a4[2]​a, start subscript, 4, end subscript, start superscript, open bracket, 2, close bracket, end superscript is the activation output by the 4th4^{th}4th4, start superscript, t, h, end superscript neuron of the 2nd2^{nd}2nd2, start superscript, n, d, end superscript layer ✅correct
  > Feedback: Nice work

*Points: 0.7 / 1*

## Question 2 (GradedMultipleChoiceQuestion)

**❌ Incorrect** — Try again No. Although the tanh almost always works better than the sigmoid function when used in hidden layers, thus is always proffered as activation function, the exception is for the output layer in classification problems.

The sigmoid function is only mentioned as an activation function for historical reasons. The tanh is always preferred without exceptions in all the layers of a Neural Network. True/False?

- [x] True
- [ ] False

*Points: 0 / 1*

## Question 3 (GradedMultipleChoiceQuestion)

**❌ Incorrect** — Try again No. The superscript in brackets indicates the layer number, the superscript in parenthesis represents the number of examples, and the subscript the number of the neuron.

Which of the following represents the activation output of the second neuron of the third layer applied to the fourth example?

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/02a53dbb-b235-48a8-8458-5aaab92472f7_8f19875047184abeb0e8d0a395b70441_520e50c6-06be-40d3-bc3e-297326faf7edimage1.png?expiry=1791557725646&hmac=m-d9Tm03eL7jUw4Yy7Dh8wt5v7OtcJsfQ-nM0OJdsI0)

- [ ] a2[3](4)a^{[3](4)}\_2a2[3](4)​a, start subscript, 2, end subscript, start superscript, open bracket, 3, close bracket, left parenthesis, 4, right parenthesis, end superscript
- [ ] a2[4](3)a^{[4](3)}\_2a2[4](3)​a, start subscript, 2, end subscript, start superscript, open bracket, 4, close bracket, left parenthesis, 3, right parenthesis, end superscript
- [x] a4[3](2)a^{[3](2)}\_4a4[3](2)​a, start subscript, 4, end subscript, start superscript, open bracket, 3, close bracket, left parenthesis, 2, right parenthesis, end superscript
- [ ] a3[4]2a^{[4]{2}}\_3a3[4]2​a, start subscript, 3, end subscript, start superscript, open bracket, 4, close bracket, 2, end superscript

*Points: 0 / 1*

## Question 4 (GradedMultipleChoiceQuestion)

**❌ Incorrect** — Try again No. Sigmoid outputs a value between 0 and 1 which makes it a very good choice for binary classification. You can classify as 0 if the output is less than 0.5 and classify as 1 if the output is more than 0.5. It can be done with tanh as well but it is less convenient as the output is between -1 and 1.

You are building a binary classifier for recognizing cucumbers (y=1) vs. watermelons (y=0). Which one of these activation functions would you recommend using for the output layer?

- [ ] Leaky ReLU
- [ ] sigmoid
- [x] tanh
- [ ] ReLU

*Points: 1.0 / 1*

## Question 5 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Yes, we use (keepdims = True) to make sure that A.shape is (4,1) and not (4, ). It makes our code more robust.

Consider the following code:

A = np.random.randn(4,3)

B = np.sum(A, axis = 1, keepdims = True)

What will be B.shape? (If you’re not sure, feel free to run this in python to find out).

- [ ] (4, )
- [ ] (1, 3)
- [ ] (3, )
- [x] (4, 1)

*Points: 1 / 1*

## Question 6 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work The use of random numbers helps to "break the symmetry" between all the neurons allowing them to compute different functions. When using small random numbers the values 𝑧 [ 𝑘 ] z [k] z, start superscript, open bracket, k, close bracket, end superscript will be close to zero thus the activation values will have a larger gradient speeding up the training process.

Suppose you have built a neural network with one hidden layer and tanh as activation function for the hidden layers. Which of the following is a best option to initialize the weights?

- [x] Initialize the weights to small random numbers.
- [ ] Initialize the weights to large random numbers.
- [ ] Initialize all weights to 0.
- [ ] Initialize all weights to a single number chosen randomly.

*Points: 1 / 1*

## Question 7 (GradedMultipleChoiceQuestion)

**❌ Incorrect** — Try again No, Logistic Regression doesn't have a hidden layer. If you initialize the weights to zeros, the first example x fed in the logistic regression will output zero but the derivatives of the Logistic Regression depend on the input x (because there's no hidden layer) which is not zero. So at the second iteration, the weights’ values follow x's distribution and are different from each other if x is not a constant vector.

Logistic regression’s weights w should be initialized randomly rather than to all zeros, because if you initialize to all zeros, then logistic regression will fail to learn a useful decision boundary because it will fail to “break symmetry”, True/False?

- [x] True
- [ ] False

*Points: 0 / 1*

## Question 8 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work

Which of the following is true about the ReLU activation functions?

- [ ] They cause several problems in practice because they have no derivative at 0. That is why Leaky ReLU was invented.
- [ ] They are increasingly being replaced by the tanh in most cases.
- [x] They are the go to option when you don't know what activation function to choose for hidden layers.
- [ ] They are only used in the case of regression problems, such as predicting house prices.

*Points: 1 / 1*

## Question 9 (GradedCheckboxQuestion)

Consider the following 1 hidden layer neural network:

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/7ef20af7-b54a-4147-90d3-45020833d16e_5350a74f33dc4f2aaa07a789f6c4c4f1_520e50c6-06be-40d3-bc3e-297326faf7edimage3.png?expiry=1791557725665&hmac=QGMalvb-K_Hpgwng3ez3PR3CbeXqJC3fPt2CicIq39I)

Which of the following statements are True? (Check all that apply).

- [ ] b[1]b^{[1]}b[1]b, start superscript, open bracket, 1, close bracket, end superscript will have shape (4, 2)
- [ ] W[1]W^{[1]}W[1]W, start superscript, open bracket, 1, close bracket, end superscript will have shape (2, 4).
- [x] W[2]W^{[2]}W[2]W, start superscript, open bracket, 2, close bracket, end superscript will have shape (1, 2) ✅correct
  > Feedback: Nice work Yes. The number of rows in 𝑊 [ 𝑘 ] W [k] W, start superscript, open bracket, k, close bracket, end superscript is the number of neurons in the k-th layer and the number of columns is the number of inputs of the layer.
- [ ] W[2]W^{[2]}W[2]W, start superscript, open bracket, 2, close bracket, end superscript will have shape (2, 1)
- [x] W[1]W^{[1]}W[1]W, start superscript, open bracket, 1, close bracket, end superscript will have shape (4, 2).
  > Feedback: This should not be selected No. The number of rows in 𝑊 [ 𝑘 ] W [k] W, start superscript, open bracket, k, close bracket, end superscript is the number of neurons in the k-th layer and the number of columns is the number of inputs of the layer.
- [ ] b[1]b^{[1]}b[1]b, start superscript, open bracket, 1, close bracket, end superscript will have shape (2, 1).

*Points: 0.5 / 1*

## Question 10 (GradedMultipleChoiceQuestion)

**❌ Incorrect** — Try again No. The 𝑍 [ 1 ] Z [1] Z, start superscript, open bracket, 1, close bracket, end superscript and 𝐴 [ 1 ] A [1] A, start superscript, open bracket, 1, close bracket, end superscript are calculated over a batch of training examples. The number of columns in 𝑍 [ 1 ] Z [1] Z, start superscript, open bracket, 1, close bracket, end superscript and 𝐴 [ 1 ] A [1] A, start superscript, open bracket, 1, close bracket, end superscript is equal to the number of examples in the batch, m. And the number of rows in 𝑍 [ 1 ] Z [1] Z, start superscript, open bracket, 1, close bracket, end superscript and 𝐴 [ 1 ] A [1] A, start superscript, open bracket, 1, close bracket, end superscript is equal to the number of neurons in the first layer.

Consider the following 1 hidden layer neural network:

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/7ef20af7-b54a-4147-90d3-45020833d16e_5350a74f33dc4f2aaa07a789f6c4c4f1_520e50c6-06be-40d3-bc3e-297326faf7edimage3.png?expiry=1791557725681&hmac=FrXqPQ-wxSjqugpsbsP1EixUiWew2ssoCpBEP__zt6I)

What are the dimensions of Z[1]Z^{[1]}Z[1]Z, start superscript, open bracket, 1, close bracket, end superscript and A[1]A^{[1]}A[1]A, start superscript, open bracket, 1, close bracket, end superscript?

- [ ] Z[1]Z^{[1]}Z[1]Z, start superscript, open bracket, 1, close bracket, end superscript and A[1]A^{[1]}A[1]A, start superscript, open bracket, 1, close bracket, end superscript are (2, m)
- [ ] Z[1]Z^{[1]}Z[1]Z, start superscript, open bracket, 1, close bracket, end superscript and A[1]A^{[1]}A[1]A, start superscript, open bracket, 1, close bracket, end superscript are (2, 1)
- [ ] Z[1]Z^{[1]}Z[1]Z, start superscript, open bracket, 1, close bracket, end superscript and A[1]A^{[1]}A[1]A, start superscript, open bracket, 1, close bracket, end superscript are (4, 1)
- [x] Z[1]Z^{[1]}Z[1]Z, start superscript, open bracket, 1, close bracket, end superscript and A[1]A^{[1]}A[1]A, start superscript, open bracket, 1, close bracket, end superscript are (4, m)

*Points: 0 / 1*

