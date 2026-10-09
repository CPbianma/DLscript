---
type: graded-quiz
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 3
section: Quiz
item_title: Hyperparameter tuning, Batch Normalization, Programming Frameworks  
source_url: https://www.coursera.org/learn/deep-neural-network/assignment-submission/1mKhR/hyperparameter-tuning-batch-normalization-programming-frameworks
language: en
extracted_at: 2026-10-08T22:52:07+08:00
grade: 100%
status: success
---
# Hyperparameter tuning, Batch Normalization, Programming Frameworks  

**Grade: 100%**

## Question 1 (GradedMultipleChoiceQuestion)

Which of the following are true about hyperparameter search?

- [ ] When using random values for the hyperparameters they must be always uniformly distributed.
- [ ] Choosing values in a grid for the hyperparameters is better when the number of hyperparameters to tune is high since it provides a more ordered way to search.
- [ ] When sampling from a grid, the number of values for each hyperparameter is larger than when using random values.
- [x] Choosing random values for the hyperparameters is convenient since we might not know in advance which hyperparameters are more important for the problem at hand.

*Points: 1 / 1*

## Question 2 (GradedCheckboxQuestion)

If it is only possible to tune two parameters from the following due to limited computational resources. Which two would you choose?

- [ ] α\alphaαalpha
- [x] β1\beta\_1β1​beta, start subscript, 1, end subscript, β2\beta\_2β2​beta, start subscript, 2, end subscript in Adam.
  > Feedback: This should not be selected Incorrect. This hyperparameter has little impact and it is usually better to use the default values 0.9 0.9 0, point, 9 , 0.999 0.999 0, point, 999 .
- [ ] ϵ\epsilonϵ\epsilon in Adam.
- [ ] The β\betaβbeta parameter of the momentum in gradient descent.

*Points: 0.3 / 1*

## Question 3 (GradedMultipleChoiceQuestion)

Even if enough computational power is available for hyperparameter tuning, it is always better to babysit one model ("Panda" strategy), since this will result in a more custom model. True/False?

- [x] False
- [ ] True

*Points: 1 / 1*

## Question 4 (GradedMultipleChoiceQuestion)

Knowing that the hyperparameter α\alphaαalpha should be in the range of 0.000010.000010.000010, point, 00001 and 1.01.01.01, point, 0, which of the following is the recommended way to sample a value for α\alphaαalpha?

- [ ] r = np.random.rand()alpha = 10\*\*r
- [ ] r = np.random.rand()alpha = 0.00001 + r\*0.99999
- [x] r = -4\*np.random.rand()alpha = 10\*\*r
- [ ] r = -5\*np.random.rand()alpha = 10\*\*r

*Points: 0 / 1*

## Question 5 (GradedMultipleChoiceQuestion)

Finding good hyperparameter values is very time-consuming. So typically you should do it once at the start of the project, and try to find very good hyperparameters so that you don’t ever have to tune them again. True or false?

- [ ] True
- [x] False

*Points: 1 / 1*

## Question 6 (GradedMultipleChoiceQuestion)

In batch normalization as presented in the videos, if you apply it on the llllth layer of your neural network, what are you normalizing?

- [ ] a[l]a^{[l]}a[l]a, start superscript, open bracket, l, close bracket, end superscript
- [x] z[l]z^{[l]}z[l]z, start superscript, open bracket, l, close bracket, end superscript
- [ ] W[l]W^{[l]}W[l]W, start superscript, open bracket, l, close bracket, end superscript
- [ ] b[l]b^{[l]}b[l]b, start superscript, open bracket, l, close bracket, end superscript

*Points: 1 / 1*

## Question 7 (GradedMultipleChoiceQuestion)

Which of the following are true about batch normalization?

- [x] There is a global value of γ\gammaγgamma and β\betaβbeta that is used for all the hidden layers where batch normalization is used.
- [ ] The parameter ϵ\epsilonϵ\epsilon in the batch normalization formula is used to accelerate the convergence of the model.
- [ ] The parameters β\betaβbeta and γ\gammaγgamma of batch normalization can't be trained using Adam or RMS prop.
- [ ] One intuition behind why batch normalization works is that it helps reduce the internal covariance.

*Points: 0 / 1*

## Question 8 (GradedMultipleChoiceQuestion)

Which of the following is true about batch normalization?

- [x] The optimal values to use for γ\gammaγgamma and β\betaβbeta are γ=σ2+ϵ\gamma = \sqrt{\sigma^2 + \epsilon}γ=σ2+ϵ​gamma, equals, square root of, sigma, squared, plus, \epsilon, end square root and β=μ\beta = \muβ=μbeta, equals, mu.
- [ ] znorm(i)=z(i)−μσ2z^{(i)}\_{norm} =\frac{z^{(i)}-\mu}{\sqrt{\sigma^2}}znorm(i)​=σ2​z(i)−μ​z, start subscript, n, o, r, m, end subscript, start superscript, left parenthesis, i, right parenthesis, end superscript, equals, start fraction, z, start superscript, left parenthesis, i, right parenthesis, end superscript, minus, mu, divided by, square root of, sigma, squared, end square root, end fraction.
- [ ] The parameters γ[l]\gamma^{[l]}γ[l]gamma, start superscript, open bracket, l, close bracket, end superscript and β[l]\beta^{[l]}β[l]beta, start superscript, open bracket, l, close bracket, end superscript set the variance and mean of z~[l]\widetilde{z}^{[l]}z[l]z, with, \widetilde, on top, start superscript, open bracket, l, close bracket, end superscript.
- [ ] The parameters γ[l]\gamma^{[l]}γ[l]gamma, start superscript, open bracket, l, close bracket, end superscript and β[l]\beta^{[l]}β[l]beta, start superscript, open bracket, l, close bracket, end superscript can be learned only using plain gradient descent.

*Points: 0 / 1*

## Question 9 (GradedMultipleChoiceQuestion)

A neural network is trained with Batch Norm. At test time, to evaluate the neural network we turn off the Batch Norm to avoid random predictions from the network. True/False?

- [x] False
- [ ] True

*Points: 1 / 1*

## Question 10 (GradedMultipleChoiceQuestion)

Which of the following are some recommended criteria to choose a deep learning framework?

- [x] It must be implemented in C to be faster.
- [ ] Running speed.
- [ ] It must run exclusively on cloud services, to ensure its robustness.
- [ ] It must use Python as the primary language.

*Points: 0 / 1*

