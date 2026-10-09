---
type: video-transcript
specialization: Deep Learning Specialization
course: Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization
week: 1
section: Setting Up your Optimization Problem
item_title: Gradient Checking
duration: 7 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/htA0l/gradient-checking
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Gradient Checking — Transcript

**[0:00]** Gradient checking is a technique that's helped me save tons of time, and
**[0:04]** helped me find bugs in my implementations of back propagation many times.
**[0:08]** Let's see how you could use it too to debug, or
**[0:10]** to verify that your implementation and back process correct.
**[0:14]** So your new network will have some sort of parameters, W1, B1 and so on up to WL bL.
**[0:20]** So to implement gradient checking, the first thing you should do is take all your
**[0:23]** parameters and reshape them into a giant vector data.
**[0:28]** So what you should do is take W which is a matrix, and reshape it into a vector.
**[0:34]** You gotta take all of these Ws and reshape them into vectors, and then concatenate
**[0:39]** all of these things, so that you have a giant vector theta.
**[0:45]** Giant vector pronounced as theta.
**[0:47]** So we say that the cos function J being a function of the Ws and
**[0:52]** Bs, You would now have the cost function J being just a function of theta.
**[0:58]** Next, with W and B ordered the same way,
**[1:02]** you can also take dW[1], db[1] and so on, and initiate them into big,
**[1:07]** giant vector d theta of the same dimension as theta.
**[1:12]** So same as before, we shape dW[1] into the matrix, db[1] is already a vector.
**[1:17]** We shape dW[L], all of the dW's which are matrices.
**[1:21]** Remember, dW1 has the same dimension as W1.
**[1:24]** db1 has the same dimension as b1.
**[1:27]** So the same sort of reshaping and concatenation operation,
**[1:31]** you can then reshape all of these derivatives into a giant vector d theta.
**[1:36]** Which has the same dimension as theta.
**[1:38]** So the question is, now, is the theta the gradient or
**[1:43]** the slope of the cos function J?
**[1:47]** So here's how you implement gradient checking, and
**[1:49]** often abbreviate gradient checking to grad check.
**[1:52]** So first we remember that J Is now a function of the giant parameter,
**[1:57]** theta, right?
**[1:58]** So expands to j is a function of theta 1, theta 2, theta 3, and so on.
**[2:06]** Whatever's the dimension of this giant parameter vector theta.
**[2:11]** So to implement grad check, what you're going to do is implements a loop so
**[2:18]** that for each I, so for each component of theta,
**[2:23]** let's compute D theta approx i to b.
**[2:26]** And let me take a two sided difference.
**[2:28]** So I'll take J of theta.
**[2:30]** Theta 1, theta 2, up to theta i.
**[2:34]** And we're going to nudge theta i to add epsilon to this.
**[2:38]** So just increase theta i by epsilon, and keep everything else the same.
**[2:42]** And because we're taking a two sided difference,
**[2:46]** we're going to do the same on the other side with theta i, but now minus epsilon.
**[2:51]** And then all of the other elements of theta are left alone.
**[2:54]** And then we'll take this, and we'll divide it by 2 theta.
**[2:59]** And what we saw from the previous video is that
**[3:04]** this should be approximately equal to d theta i.
**[3:10]** Of which is supposed to be the partial derivative of J or of respect to,
**[3:15]** I guess theta i, if d theta i is the derivative of the cost function J.
**[3:21]** So what you going to do is you're going to compute to this for every value of i.
**[3:25]** And at the end, you now end up with two vectors.
**[3:28]** You end up with this d theta approx, and
**[3:31]** this is going to be the same dimension as d theta.
**[3:35]** And both of these are in turn the same dimension as theta.
**[3:39]** And what you want to do is check if these vectors are approximately equal to
**[3:43]** each other.
**[3:44]** So, in detail, well how you do you define whether or
**[3:47]** not two vectors are really reasonably close to each other?
**[3:50]** What I do is the following.
**[3:52]** I would compute the distance between these two vectors,
**[3:57]** d theta approx minus d theta, so just the o2 norm of this.
**[4:02]** Notice there's no square on top, so
**[4:03]** this is the sum of squares of elements of the differences, and
**[4:06]** then you take a square root, as you get the Euclidean distance.
**[4:09]** And then just to normalize by the lengths of these vectors,
**[4:15]** divide by d theta approx plus d theta.
**[4:19]** Just take the Euclidean lengths of these vectors.
**[4:22]** And the row for the denominator is just in case any of these vectors are really small
**[4:28]** or really large, your the denominator turns this formula into a ratio.
**[4:32]** So we implement this in practice,
**[4:35]** I use epsilon equals maybe 10 to the minus 7, so minus 7.
**[4:39]** And with this range of epsilon, if you find that this formula gives you
**[4:44]** a value like 10 to the minus 7 or smaller, then that's great.
**[4:49]** It means that your derivative approximation is very likely correct.
**[4:53]** This is just a very small value.
**[4:55]** If it's maybe on the range of 10 to the -5, I would take a careful look.
**[5:00]** Maybe this is okay.
**[5:02]** But I might double-check the components of this vector, and
**[5:05]** make sure that none of the components are too large.
**[5:07]** And if some of the components of this difference are very large,
**[5:10]** then maybe you have a bug somewhere.
**[5:12]** And if this formula on the left is on the other is -3, then I would wherever you
**[5:17]** have would be much more concerned that maybe there's a bug somewhere.
**[5:21]** But you should really be getting values much smaller then 10 minus 3.
**[5:25]** If any bigger than 10 to minus 3, then I would be quite concerned.
**[5:29]** I would be seriously worried that there might be a bug.
**[5:32]** And I would then, you should then look at the individual
**[5:37]** components of data to see if there's a specific value of i for
**[5:41]** which d theta across i is very different from d theta i.
**[5:45]** And use that to try to track down whether or
**[5:47]** not some of your derivative computations might be incorrect.
**[5:51]** And after some amounts of debugging, it finally, it ends up being this
**[5:54]** kind of very small value, then you probably have a correct implementation.
**[5:59]** So when implementing a neural network,
**[6:01]** what often happens is I'll implement foreprop, implement backprop.
**[6:04]** And then I might find that this grad check has a relatively big value.
**[6:08]** And then I will suspect that there must be a bug, go in debug, debug, debug.
**[6:12]** And after debugging for a while, If I find that it passes grad check with a small
**[6:16]** value, then you can be much more confident that it's then correct.
**[6:20]** So you now know how gradient checking works.
**[6:22]** This has helped me find lots of bugs in my implementations of neural nets,
**[6:24]** and I hope it'll help you too.
**[6:27]** In the next video, I want to share with you some tips or
**[6:29]** some notes on how to actually implement gradient checking.
**[6:33]** Let's go onto the next video.
