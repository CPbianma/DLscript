---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 3
section: Shallow Neural Network
item_title: Why do you need Non-Linear Activation Functions?
duration: 6 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/OASKH/why-do-you-need-non-linear-activation-functions
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Why do you need Non-Linear Activation Functions? — Transcript

**[0:00]** Why does a neural network need a non-linear activation function?
**[0:04]** Turns out that your neural network to compute interesting functions,
**[0:07]** you do need to pick a non-linear activation function, let's see one.
**[0:11]** So, here's the four prop equations for the neural network.
**[0:15]** Why don't we just get rid of this?
**[0:17]** Get rid of the function g?
**[0:19]** And set a1 equals z1.
**[0:21]** Or alternatively, you can say that g of z is equal to z, all right?
**[0:27]** Sometimes this is called the linear activation function.
**[0:32]** Maybe a better name for it would be the identity activation function
**[0:35]** because it just outputs whatever was input.
**[0:38]** For the purpose of this, what if a(2) was just equal z(2)?
**[0:42]** It turns out if you do this, then this model is just computing y or
**[0:48]** y-hat as a linear function of your input features,
**[0:53]** x, to take the first two equations.
**[0:55]** If you have that a(1)
**[1:01]** = Z(1) = W(1)x + b, and
**[1:08]** then a(2) = z (2) =
**[1:14]** W(2)a(1) + b.
**[1:19]** Then if you take this definition of a1 and
**[1:24]** plug it in there, you find that a2 =
**[1:30]** w2(w1x + b1), move that up a bit.
**[1:36]** Right? So this is a1 + b2, and so
**[1:42]** this simplifies to:
**[1:45]** (W2w1)x +
**[1:49]** (w2b1 + b2).
**[1:58]** So this is just,
**[2:01]** let's call this w prime b prime.
**[2:06]** So this is just equal to w' x + b'.
**[2:11]** If you were to use linear activation functions or
**[2:14]** we can also call them identity activation functions,
**[2:17]** then the neural network is just outputting a linear function of the input.
**[2:23]** And we'll talk about deep networks later, neural networks with many, many layers,
**[2:28]** many hidden layers. And it turns out that
**[2:31]** if you use a linear activation function or alternatively,
**[2:34]** if you don't have an activation function, then no matter how many layers your neural
**[2:38]** network has, all it's doing is just computing a linear activation function.
**[2:43]** So you might as well not have any hidden layers.
**[2:47]** Some of the cases that are briefly mentioned, it turns out that if you have
**[2:51]** a linear activation function here and a sigmoid function here, then this model is
**[2:57]** no more expressive than standard logistic regression without any hidden layer.
**[3:02]** So I won't bother to prove that, but you could try to do so if you want.
**[3:06]** But the take home is that a linear hidden layer is more or less useless
**[3:11]** because the composition of two linear functions is itself a linear function.
**[3:17]** So unless you throw a non-linear item in there, then you're not computing more
**[3:21]** interesting functions even as you go deeper in the network.
**[3:25]** There is just one place where you might use a linear activation function.
**[3:29]** g(x) = z.
**[3:32]** And that's if you are doing machine learning on the regression problem.
**[3:37]** So if y is a real number.
**[3:39]** So for example, if you're trying to predict housing prices.
**[3:43]** So y is not 0, 1, but is a real number, anywhere from - I don't know -
**[3:50]** $0 is the price of house up to however expensive, right, houses get, I guess.
**[3:55]** Maybe houses can be potentially millions of dollars, so
**[4:00]** however much houses cost in your data set.
**[4:04]** But if y takes on these real values,
**[4:10]** then it might be okay to have a linear activation function here so
**[4:14]** that your output y hat is also
**[4:19]** a real number going anywhere from minus infinity to plus infinity.
**[4:24]** But then the hidden units should not use the activation functions.
**[4:29]** They could use ReLU or tanh or Leaky ReLU or maybe something else.
**[4:34]** So the one place you might use a linear activation function
**[4:38]** is usually in the output layer.
**[4:40]** But other than that, using a linear activation function in the hidden layer
**[4:47]** except for some very special circumstances relating to compression that we're
**[4:52]** going to talk about using the linear activation function is extremely rare.
**[4:56]** And, of course, if we're actually predicting housing prices,
**[4:58]** as you saw in the week one video, because housing prices are all non-negative,
**[5:02]** Perhaps even then you can use a value activation function so
**[5:06]** that your output y-hats are all greater than or equal to 0.
**[5:10]** So I hope that gives you a sense of why having a non-linear activation
**[5:15]** function is a critical part of neural networks.
**[5:19]** Next we're going to start to talk about gradient descent and
**[5:23]** to do that to set up for our discussion for gradient descent,
**[5:26]** in the next video I want to show you how to estimate-how to compute-the slope or
**[5:30]** the derivatives of individual activation functions.
**[5:34]** So let's go on to the next video.
