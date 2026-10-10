---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 2
section: Back Propagation (Optional)
item_title: Larger neural network example (Optional)
duration: 10 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/qqczh/larger-neural-network-example-optional
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Larger neural network example (Optional) — Transcript

**[0:00]** In this final video on intuition for backprop, let's take a look
**[0:05]** at how the computation draft works on a larger neural network example.
**[0:11]** Here's the network we will use with a single hidden layer,
**[0:16]** with a single hidden unit that outputs a1,
**[0:19]** that feeds into the output layer that outputs the final prediction a2.
**[0:25]** To make the math more tractable, I'm going to continue to
**[0:30]** use just a single training example with inputs x = 1, y = 5.
**[0:34]** And these will be the parameters of the network.
**[0:38]** And throughout we're going to use the ReLU activation functions of g(z) = max(0, z).
**[0:45]** So for prop in your network looks like this.
**[0:47]** As usual, a1 equals g(w1 times x + b1).
**[0:53]** And so it turns out w1x + b will be positive.
**[0:59]** So we're in the max(0, z) = z, parts of this activation function.
**[1:06]** So that's just equal to this, which is 2 times 1,
**[1:10]** that's w1 is 2 times x1 + 0, that's b1, which is equal to 2.
**[1:16]** And then similarly, a2 equals this,
**[1:20]** g(w2a1 + b2) which is w2 times a1 + b.
**[1:24]** Again, because we're in the positive part of the ReLU
**[1:29]** activation function, which is 3 x 2 + 1 = 7.
**[1:33]** Finally, we'll use the squared error cost function.
**[1:36]** So j(w, b) is 1/2(a2- y) squared = 1/2(7-5) squared,
**[1:43]** which is 1/2 of 2 squared, which is just equal to 2.
**[1:49]** So, let's take this calculation that we just did and
**[1:52]** write it down in the form of a computation graph.
**[1:56]** To carry out the computation step by step,
**[1:59]** first thing we need to do is take w1 and multiply that by x.
**[2:03]** So we have w1 that feeds into computation node that computes w1 times x.
**[2:10]** And I'm going to call this a temporary variable t1.
**[2:15]** Next, we compute z1, which is this term here, which is t1 + b1.
**[2:22]** So we also have this input b1 over here.
**[2:26]** And finally a1 equals g(z1).
**[2:29]** We apply the activation function, and so we end up with again this value here, 2.
**[2:35]** And then next we have to compute t2, which is w2 times a1.
**[2:42]** And so, with w2, that gives us this value which is 6.
**[2:47]** Then z2, which is this quantity,
**[2:51]** we had to b2 it and that gives us 7.
**[2:54]** And finally apply the activation function, g.
**[2:57]** We still end up with 7.
**[2:59]** And lastly, j is 1/2(a2- y) squared.
**[3:04]** And that gives us 2.
**[3:06]** Which was this cost function here.
**[3:08]** So this is how you take the step by step computations for
**[3:12]** larger neural network and write it in the computation graph.
**[3:16]** You've already seen in the last video, the mechanics of how to carry out backprop.
**[3:21]** I'm not going to go through the step by step calculations here.
**[3:25]** But if you were to carry out backprop, the first thing you do is ask,
**[3:30]** what is the derivative of the cost function j respect to a2?
**[3:35]** And it turns out if you calculate that, it turns out to be 2.
**[3:39]** So we'll fill that in here.
**[3:41]** And the next step will be asked,
**[3:43]** what's the derivative of the cost j respect to z2.
**[3:47]** And using this derivative that we computed previously,
**[3:51]** you can figure out that this turns out to be 2.
**[3:54]** Because if z goes up by epsilon, you can show that for
**[3:58]** the current setting of all the parameters a2 will go up by epsilon.
**[4:04]** And therefore, j will go up by 2 times epsilon.
**[4:07]** So this derivative is equal to 2, and so on.
**[4:11]** Step by step.
**[4:12]** We can then find out that the derivative of j respective b2 is also equal to 2.
**[4:18]** The derivative respect to t2 is equal to 2, and so on, and so forth.
**[4:24]** Until eventually you've computed the derivative of j
**[4:28]** with respect to all the parameters w1, b1, w2, and b2.
**[4:33]** And so that's backprop.
**[4:35]** And again,
**[4:36]** I didn't go through the mechanical steps of every single step of backprop.
**[4:39]** But it's basically the process that you saw in the previous video.
**[4:44]** Let me just double check one of these examples.
**[4:48]** So we saw here that the derivative of j respect w1 is equal to 6.
**[4:54]** So what this is predicting is that, if w1 goes up by epsilon,
**[5:01]** j should go up by roughly 6 times epsilon.
**[5:05]** Let's step through the map and see if that really is true.
**[5:09]** These are the calculations that we did, again.
**[5:12]** And so if w which was 2 were to be 2.001 goes
**[5:17]** up by epsilon, then a1 becomes, let's see,
**[5:22]** instead of 2, this is 2.001 as well.
**[5:26]** So a1 instead of 2 is now 2.001.
**[5:30]** So 3 x 2.001 + 1, this gives us 7.003.
**[5:37]** And if a2 is 7.003,
**[5:40]** then just becomes 7.003- 5 squared.
**[5:46]** And so this becomes 2.003 squared over 2,
**[5:52]** which turns out to be equal to 2.006005.
**[5:58]** So ignoring some of the extra digits, you see from this
**[6:03]** little calculation that, if w1 goes up by 0.001,
**[6:09]** j of w has gone up from 2 to 2.006 roughly.
**[6:13]** So 6 times as much.
**[6:15]** And so the derivative of j with respect to w1 is indeed equal to 6.
**[6:22]** And so the backprop procedure gives you a very efficient way to
**[6:26]** compute all of these derivatives.
**[6:28]** Which you can then feed into the gradient descent algorithm or the Adam optimization
**[6:33]** algorithm, to then train the parameters of your neural network.
**[6:37]** And again, the reason we use background for this is,
**[6:41]** is a very efficient way to compute all the derivatives of j respect to w1,
**[6:48]** j respect to b1, j respect to w2, and j respect to b2.
**[6:52]** I did just illustrate how we could bump up w1 by a little bit and
**[6:58]** see how much j changes.
**[7:00]** But that was a left to right calculation.
**[7:03]** And then we had to do this procedure for each parameter, one parameter at a time.
**[7:08]** If we had to increase w by 0.001 to see how that changes j.
**[7:12]** Increase b1 by a little bit to see how that changes j, and
**[7:16]** increase every parameter, one at a time by a little bit to see how that changes j.
**[7:21]** Then this becomes a very inefficient calculation.
**[7:24]** And if you had N nodes in your computation graph and P parameters,
**[7:29]** this procedure would end up taking N times P steps, which is very inefficient.
**[7:34]** Whereas we got all four of these derivatives N + P,
**[7:38]** rather than N times P steps.
**[7:41]** And this makes a huge difference in practical neural networks,
**[7:45]** where the number of nodes and the number of parameters can be really large.
**[7:49]** So, that's the end of the video for this week.
**[7:52]** Thanks for sticking with me through the end of these optional videos.
**[7:57]** And I hope that you now have an intuition for when you use a program frameworks,
**[8:01]** like tensorflow, to train a neural network.
**[8:04]** What's actually happening under the hood and
**[8:07]** how is using the computation graph to efficiently compute derivatives for you.
**[8:12]** Many years ago, before the rise of frameworks like tensorflow and
**[8:17]** pytorch, researchers used to have to manually use calculus to compute
**[8:22]** the derivatives of the neural networks that they wanted to train.
**[8:27]** And so in modern program frameworks you can specify forwardprop and
**[8:31]** have it take care of backprop for you.
**[8:34]** Many years ago, researchers used to write down the neural network by hand,
**[8:38]** manually use calculus to compute the derivatives.
**[8:41]** And then neural implement a bunch of equations that they
**[8:44]** had laboriously derived on paper, to implement backprop.
**[8:48]** Thanks to the computation graph and these techniques for
**[8:52]** automatically carrying out derivative calculations.
**[8:56]** Is sometimes called autodiff, for automatic differentiation.
**[9:00]** This process of researchers manually using calculus to take
**[9:04]** derivatives is no longer really done.
**[9:07]** At least, I've not had to do this for many years now myself, because of autodiff.
**[9:12]** So, many years ago, to use neural networks, the bar for
**[9:16]** the amount of calculus you have to know actually used to be higher.
**[9:20]** But because of automatic differentiation algorithms,
**[9:23]** usually based on the computation graph, you can now implement a neural network and
**[9:28]** get derivatives computed for you easier than before.
**[9:31]** So maybe with the maturing of neural networks, the amount of calculus
**[9:35]** you need to know in order to get these algorithms work, has actually gone down.
**[9:39]** And that's been encouraging for a lot of people.
**[9:42]** And so, that's it for the videos for this week.
**[9:47]** I hope you enjoy the labs and I look forward to seeing you next week.
