---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 1
section: Neural network model
item_title: Inference: making predictions (forward propagation)
duration: 5 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/vYsrR/inference-making-predictions-forward-propagation
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Inference: making predictions (forward propagation) — Transcript

**[0:01]** Let's take what we've learned and put it together into an algorithm to let your
**[0:05]** neural network make inferences or make predictions.
**[0:09]** This will be an algorithm called forward propagation.
**[0:12]** Let's take a look.
**[0:14]** I'm going to use as a motivating example, handwritten digit recognition.
**[0:19]** And for simplicity we are just going to distinguish between
**[0:23]** the handwritten digits zero and one.
**[0:26]** So it's just a binary classification problem where we're going to input
**[0:30]** an image and classify, is this the digit zero or the digit one?
**[0:34]** And you get to play with this yourself later this week in the practice lab
**[0:38]** as well.
**[0:38]** For the example of the slide, I'm going to use an eight by eight image.
**[0:43]** And so this image of a one is this grid or matrix of eight by eight or
**[0:49]** 64 pixel intensity values where 255 denotes a bright white pixel and
**[0:54]** zero would denote a black pixel.
**[0:57]** And different numbers are different shades of gray
**[1:01]** in between the shades of black and white.
**[1:05]** Given these 64 input features,
**[1:08]** we're going to use the neural network with two hidden layers.
**[1:12]** Where the first hidden layer has 25 neurons or 25 units.
**[1:17]** Second hidden layer has 15 neurons or 15 units.
**[1:21]** And then finally the output layer or outputs unit,
**[1:24]** what's the chance of this being 1 versus 0?.
**[1:27]** So let's step through the sequence of computations that in your
**[1:31]** neural network will need to make to go from the input X,
**[1:36]** this eight by eight or 64 numbers to the predicted probability a3.
**[1:41]** The first computation is to go from X to a1, and
**[1:44]** that's what the first layer of the first hidden layer does.
**[1:49]** It carries out a computation of a super strip square bracket 1
**[1:53]** equals this formula on the right.
**[1:56]** Notice that a one has 25 numbers because this hidden layer has 25 units.
**[2:04]** Which is why the parameters go from w1 through w25 as well as b1 through b25.
**[2:11]** And I've written x here but I could also have written a0 here because by convention
**[2:17]** the activation of layer zero, that is a0 is equal to the input feature value x.
**[2:23]** So let's just compute a1.
**[2:26]** The next step is to compute a2.
**[2:30]** Looking at the second hidden layer,
**[2:33]** it then carries out this computation where a2 is a function of a1 and
**[2:39]** it's computed as the safe point activation function applied
**[2:44]** to w dot product a1 plus the corresponding value of b.
**[2:49]** Notice that layer two has 15 neurons or 15 units,
**[2:53]** which is why the parameters Here run from w1 through w15 and b1 through b15.
**[3:01]** Now we've computed a2.
**[3:03]** The Final step is then to compute a3 and we do so using a very similar computation.
**[3:10]** Only now, this third layer, the output layer has just one unit,
**[3:15]** which is why there's just one output here.
**[3:19]** So a3 is just a scalar.
**[3:21]** And finally you can optionally take a3 subscript one and
**[3:26]** threshold it at 4.5 to come up with a binary classification label.
**[3:31]** Is this the digit 1?
**[3:33]** Yes or no?
**[3:35]** So the sequence of computations first takes x and then computes a1, and then
**[3:39]** computes a2, and then computes a3, which is also the output of the neural networks.
**[3:45]** You can also write that as f(x).
**[3:48]** So remember when we learned about linear regression and logistic regression,
**[3:53]** we use f(x) to denote the output of linear regression or logistic regression.
**[3:59]** So we can also use f(x) to denote the function
**[4:02]** computed by the neural network as a function of x.
**[4:06]** Because this computation goes from left to right, you start from x and compute a1,
**[4:11]** then a2, then a3.
**[4:12]** This album is also called forward propagation because you're
**[4:17]** propagating the activations of the neurons.
**[4:20]** So you're making these computations in the forward direction from left to right.
**[4:26]** And this is in contrast to a different algorithm called backward propagation or
**[4:30]** back propagation, which is used for learning.
**[4:33]** And that's something you learn about next week.
**[4:35]** And by the way, this type of neural network architecture where you have more
**[4:39]** hidden units initially and
**[4:41]** then the number of hidden units decreases as you get closer to the output layer.
**[4:46]** There's also a pretty typical choice when choosing neural network architectures.
**[4:50]** And you see more examples of this in the practice lab as well.
**[4:53]** So that's neural network inference using the forward propagation algorithm.
**[4:59]** And with this, you'd be able to download the parameters of a neural network that
**[5:04]** someone else had trained and posted on the Internet.
**[5:07]** And you'd be able to carry out inference on your new data using their
**[5:12]** neural network.
**[5:13]** Now that you've seen the math and the algorithm,
**[5:16]** let's take a look at how you can actually implement this in tensorflow.
**[5:20]** Specifically, let's take a look at this in the next video.
