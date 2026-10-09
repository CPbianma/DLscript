---
type: graded-quiz
specialization: Deep Learning Specialization
course: Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization
week: 2
section: Quiz
item_title: Optimization Algorithms  
source_url: https://www.coursera.org/learn/deep-neural-network/assignment-submission/fPIQZ/optimization-algorithms
language: en
extracted_at: 2026-10-08T22:52:07+08:00
grade: 100%
status: success
---
# Optimization Algorithms  

**Grade: 100%**

## Question 1 (GradedMultipleChoiceQuestion)

Which notation would you use to denote the 4th layer’s activations when the input is the 7th example from the 3rd mini-batch?

- [x] a[4]{3}(7)a^{[4]\lbrace 3 \rbrace (7)}a[4]{3}(7)a, start superscript, open bracket, 4, close bracket, \lbrace, 3, \rbrace, left parenthesis, 7, right parenthesis, end superscript
- [ ] a[3]{7}(4)a^{[3]\lbrace 7 \rbrace (4)}a[3]{7}(4)a, start superscript, open bracket, 3, close bracket, \lbrace, 7, \rbrace, left parenthesis, 4, right parenthesis, end superscript
- [ ] a[7]{3}(4)a^{[7]\lbrace 3 \rbrace (4)}a[7]{3}(4)a, start superscript, open bracket, 7, close bracket, \lbrace, 3, \rbrace, left parenthesis, 4, right parenthesis, end superscript

*Points: 1 / 1*

## Question 2 (GradedMultipleChoiceQuestion)

Which of these statements about mini-batch gradient descent do you agree with?

- [ ] You should implement mini-batch gradient descent without an explicit for-loop over different mini-batches so that the algorithm processes all mini-batches at the same time (vectorization).
- [ ] Training one epoch (one pass through the training set) using mini-batch gradient descent is faster than training one epoch using batch gradient descent.
- [x] When the mini-batch size is the same as the training size, mini-batch gradient descent is equivalent to batch gradient descent.

*Points: 1 / 1*

## Question 3 (GradedMultipleChoiceQuestion)

Which of the following is true about batch gradient descent?

- [ ] It has as many mini-batches as examples in the training set.
- [ ] It is the same as stochastic gradient descent, but we don't use random elements.
- [x] It is the same as the mini-batch gradient descent when the mini-batch size is the same as the size of the training set.

*Points: 1 / 1*

## Question 4 (GradedMultipleChoiceQuestion)

While using mini-batch gradient descent with a batch size larger than 1 but less than m, the plot of the cost function JJJJ looks like this:

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/eaf9a2dd-2169-43b3-8700-d6d449e2c2d1_8711cce42bb643bf8ff16ca154507b9c_d71f0daa-99d2-4b3d-905c-71d4983728afimage2.png?expiry=1791557095930&hmac=YOPtrL1ovwIGl47RgHKFXck4aeeVTsQaJoWDryO3nis)

You notice that the value of JJJJ is not always decreasing. Which of the following is the most likely reason for that?

- [ ] A bad implementation of the backpropagation process, we should use gradient check to debug our implementation.
- [x] In mini-batch gradient descent we calculate J(y^{t},y{t})J(\hat{y}^{\lbrace t \rbrace}, y^{\lbrace t \rbrace})J(y^​{t},y{t})J, left parenthesis, y, with, hat, on top, start superscript, \lbrace, t, \rbrace, end superscript, comma, y, start superscript, \lbrace, t, \rbrace, end superscript, right parenthesis thus with each batch we compute over a new set of data.
- [ ] The algorithm is on a local minimum thus the noisy behavior.
- [ ] You are not implementing the moving averages correctly. Using moving averages will smooth the graph.

*Points: 1 / 1*

## Question 5 (GradedMultipleChoiceQuestion)

Suppose the temperature in Casablanca over the first two days of January are the same:

Jan 1st: θ1=10oC\theta\_1 = 10^o Cθ1​=10oCtheta, start subscript, 1, end subscript, equals, 10, start superscript, o, end superscript, C

Jan 2nd: θ2=10oC\theta\_2 = 10^o Cθ2​=10oCtheta, start subscript, 2, end subscript, equals, 10, start superscript, o, end superscript, C

(We used Fahrenheit in the lecture, so we will use Celsius here in honor of the metric world.)

Say you use an exponentially weighted average with β=0.5\beta = 0.5β=0.5beta, equals, 0, point, 5 to track the temperature: v0=0v\_0 = 0v0​=0v, start subscript, 0, end subscript, equals, 0, vt=βvt−1+(1−β)θtv\_t = \beta v\_{t-1} +(1-\beta)\theta\_tvt​=βvt−1​+(1−β)θt​v, start subscript, t, end subscript, equals, beta, v, start subscript, t, minus, 1, end subscript, plus, left parenthesis, 1, minus, beta, right parenthesis, theta, start subscript, t, end subscript. If v2v\_2v2​v, start subscript, 2, end subscript is the value computed after day 2 without bias correction, and v2correctedv\_2^{corrected}v2corrected​v, start subscript, 2, end subscript, start superscript, c, o, r, r, e, c, t, e, d, end superscript is the value you compute with bias correction. What are these values? (You might be able to do this without a calculator, but you don't actually need one. Remember what bias correction is doing.)

- [x] v2=7.5v\_2 = 7.5v2​=7.5v, start subscript, 2, end subscript, equals, 7, point, 5, v2corrected=10v\_2^{corrected} = 10v2corrected​=10v, start subscript, 2, end subscript, start superscript, c, o, r, r, e, c, t, e, d, end superscript, equals, 10
- [ ] v2=10v\_2 = 10v2​=10v, start subscript, 2, end subscript, equals, 10, v2corrected=10v\_2^{corrected} = 10v2corrected​=10v, start subscript, 2, end subscript, start superscript, c, o, r, r, e, c, t, e, d, end superscript, equals, 10
- [ ] v2=10v\_2 = 10v2​=10v, start subscript, 2, end subscript, equals, 10, v2corrected=7.5v\_2^{corrected} = 7.5v2corrected​=7.5v, start subscript, 2, end subscript, start superscript, c, o, r, r, e, c, t, e, d, end superscript, equals, 7, point, 5
- [ ] v2=7.5v\_2 = 7.5v2​=7.5v, start subscript, 2, end subscript, equals, 7, point, 5, v2corrected=7.5v\_2^{corrected} = 7.5v2corrected​=7.5v, start subscript, 2, end subscript, start superscript, c, o, r, r, e, c, t, e, d, end superscript, equals, 7, point, 5

*Points: 1 / 1*

## Question 6 (GradedMultipleChoiceQuestion)

Which of the following is true about learning rate decay?

- [ ] The intuition behind it is that for later epochs our parameters are closer to a minimum thus it is more convenient to take larger steps to accelerate the convergence.
- [x] The intuition behind it is that for later epochs our parameters are closer to a minimum thus it is more convenient to take smaller steps to prevent large oscillations.
- [ ] We use it to increase the size of the steps taken in each mini-batch iteration.
- [ ] It helps to reduce the variance of a model.

*Points: 1 / 1*

## Question 7 (GradedMultipleChoiceQuestion)

You use an exponentially weighted average on the London temperature dataset. You use the following to track the temperature: vt=βvt−1+(1−β)θtv\_{t} = \beta v\_{t-1} + (1-\beta)\theta\_tvt​=βvt−1​+(1−β)θt​v, start subscript, t, end subscript, equals, beta, v, start subscript, t, minus, 1, end subscript, plus, left parenthesis, 1, minus, beta, right parenthesis, theta, start subscript, t, end subscript. The yellow and red lines were computed using values β1\beta\_1β1​beta, start subscript, 1, end subscript and β2\beta\_2β2​beta, start subscript, 2, end subscript respectively. Which of the following are true?

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/08d12380-1a08-4389-bb64-a8a1fa1f3e78_389c5ff42c914bf4989e8d77059fb02e_d71f0daa-99d2-4b3d-905c-71d4983728afimage5.png?expiry=1791557095948&hmac=daTxLoLxdz9gbx6MPo72ygb5Xn0yJvV-O2CIWKDMzhg)

- [x] β1>β2\beta\_1 > \beta\_2β1​>β2​beta, start subscript, 1, end subscript, is greater than, beta, start subscript, 2, end subscript.
- [ ] β1<β2\beta\_1 < \beta\_2β1​<β2​beta, start subscript, 1, end subscript, is less than, beta, start subscript, 2, end subscript.
- [ ] β1=β2\beta\_1 = \beta\_2β1​=β2​beta, start subscript, 1, end subscript, equals, beta, start subscript, 2, end subscript.
- [ ] β1=0\beta\_1 =0β1​=0beta, start subscript, 1, end subscript, equals, 0, β2>0\beta\_2 >0β2​>0beta, start subscript, 2, end subscript, is greater than, 0.

*Points: 1 / 1*

## Question 8 (GradedMultipleChoiceQuestion)

Consider this figure:

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/8f3d21ad-7772-430a-9a9a-cf6589e6b260_e30c28d08cd2443ab34f3821cfcb1d15_d71f0daa-99d2-4b3d-905c-71d4983728afimage6.png?expiry=1791557095963&hmac=i1-1UAh3j-Ks8IEv5m3mUeT_lOQak6j1Nj0i1ibmeIU)

These plots were generated with gradient descent; with gradient descent with momentum (β\betaβbeta = 0.5); and gradient descent with momentum (β\betaβbeta = 0.9). Which curve corresponds to which algorithm?

- [ ] (1) is gradient descent with momentum (small β\betaβbeta), (2) is gradient descent with momentum (small β\betaβbeta), (3) is gradient descent
- [x] (1) is gradient descent. (2) is gradient descent with momentum (small β\betaβbeta). (3) is gradient descent with momentum (large β\betaβbeta)
- [ ] (1) is gradient descent with momentum (small β\betaβbeta). (2) is gradient descent. (3) is gradient descent with momentum (large β\betaβbeta)
- [ ] (1) is gradient descent. (2) is gradient descent with momentum (large β\betaβbeta) . (3) is gradient descent with momentum (small β\betaβbeta)

*Points: 1 / 1*

## Question 9 (GradedCheckboxQuestion)

Suppose batch gradient descent in a deep network is taking excessively long to find a value of the parameters that achieves a small value for the cost function J(W[1],b[1],...,W[L],b[L])\mathcal{J}(W^{[1]},b^{[1]},..., W^{[L]},b^{[L]})J(W[1],b[1],...,W[L],b[L])J, left parenthesis, W, start superscript, open bracket, 1, close bracket, end superscript, comma, b, start superscript, open bracket, 1, close bracket, end superscript, comma, point, point, point, comma, W, start superscript, open bracket, L, close bracket, end superscript, comma, b, start superscript, open bracket, L, close bracket, end superscript, right parenthesis. Which of the following techniques could help find parameter values that attain a small value forJ\mathcal{J}JJ? (Check all that apply)

- [x] Try using Adam ✅correct
  > Feedback: Nice work
- [x] Try mini-batch gradient descent ✅correct
  > Feedback: Nice work
- [x] Try better random initialization for the weights ✅correct
  > Feedback: Nice work
- [x] Try tuning the learning rate α\alphaαalpha ✅correct
  > Feedback: Nice work
- [ ] Try initializing all the weights to zero

*Points: 1 / 1*

## Question 10 (GradedMultipleChoiceQuestion)

In very high dimensional spaces it is most likely that the gradient descent process gives us a local minimum than a saddle point of the cost function. True/False?

- [ ] True
- [x] False

*Points: 1 / 1*

