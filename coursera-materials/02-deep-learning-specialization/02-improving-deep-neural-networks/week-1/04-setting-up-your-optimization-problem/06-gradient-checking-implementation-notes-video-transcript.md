---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 1
section: Setting Up your Optimization Problem
item_title: Gradient Checking Implementation Notes
duration: 5 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/6igIc/gradient-checking-implementation-notes
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Gradient Checking Implementation Notes — Transcript

**[0:00]** In the last video you learned about gradient checking.
**[0:03]** In this video, I want to share with you some practical tips or
**[0:06]** some notes on how to actually go about implementing this for your neural network.
**[0:10]** First, don't use grad check in training, only to debug.
**[0:14]** So what I mean is that, computing d theta approx i, for
**[0:19]** all the values of i, this is a very slow computation.
**[0:22]** So to implement gradient descent, you'd use backprop to compute d theta and
**[0:26]** just use backprop to compute the derivative.
**[0:29]** And it's only when you're debugging that you would compute this
**[0:32]** to make sure it's close to d theta.
**[0:34]** But once you've done that, then you would turn off the grad check, and
**[0:37]** don't run this during every iteration of gradient descent,
**[0:39]** because that's just much too slow.
**[0:41]** Second, if an algorithm fails grad check, look at the components,
**[0:45]** look at the individual components, and try to identify the bug.
**[0:48]** So what I mean by that is if d theta approx is very far from d theta,
**[0:52]** what I would do is look at the different values of i to see which are the values of
**[0:57]** d theta approx that are really very different than the values of d theta.
**[1:02]** So for example, if you find that the values of theta or d theta,
**[1:06]** they're very far off, all correspond to dbl for some layer or for
**[1:11]** some layers, but the components for dw are quite close, right?
**[1:16]** Remember, different components of theta correspond to different components
**[1:20]** of b and w.
**[1:21]** When you find this is the case, then maybe you find that the bug is in how
**[1:25]** you're computing db, the derivative with respect to parameters b.
**[1:30]** And similarly, vice versa, if you find that the values that are very far,
**[1:35]** the values from d theta approx that are very far from d theta,
**[1:39]** you find all those components came from dw or from dw in a certain layer,
**[1:44]** then that might help you hone in on the location of the bug.
**[1:48]** This doesn't always let you identify the bug right away, but
**[1:51]** sometimes it helps you give you some guesses about where to track down the bug.
**[1:56]** Next, when doing grad check,
**[1:59]** remember your regularization term if you're using regularization.
**[2:03]** So if your cost function is J of theta equals 1 over m sum of your
**[2:10]** losses and then plus this regularization term.
**[2:15]** And sum over l of wl squared, then this is the definition of J.
**[2:22]** And you should have that d theta is gradient of J with
**[2:27]** respect to theta, including this regularization term.
**[2:30]** So just remember to include that term.
**[2:32]** Next, grad check doesn't work with dropout, because in every iteration,
**[2:37]** dropout is randomly eliminating different subsets of the hidden units.
**[2:41]** There isn't an easy to compute cost function J that dropout is
**[2:45]** doing gradient descent on.
**[2:48]** It turns out that dropout can be viewed as optimizing some cost function J, but
**[2:52]** it's cost function J defined by summing over all exponentially large
**[2:57]** subsets of nodes they could eliminate in any iteration.
**[3:00]** So the cost function J is very difficult to compute, and
**[3:04]** you're just sampling the cost function
**[3:07]** every time you eliminate different random subsets in those we use dropout.
**[3:11]** So it's difficult to use grad check to double check your
**[3:14]** computation with dropouts.
**[3:16]** So what I usually do is implement grad check without dropout.
**[3:20]** So if you want, you can set keep-prob and dropout to be equal to 1.0.
**[3:25]** And then turn on dropout and hope that my implementation of dropout was correct.
**[3:30]** There are some other things you could do, like fix the pattern of nodes dropped and
**[3:35]** verify that grad check for that pattern of [INAUDIBLE] is correct, but
**[3:39]** in practice I don't usually do that.
**[3:43]** So my recommendation is turn off dropout, use grad check to double check that your
**[3:48]** algorithm is at least correct without dropout, and then turn on dropout.
**[3:52]** Finally, this is a subtlety.
**[3:55]** It is not impossible, rarely happens, but it's not impossible that your
**[3:59]** implementation of gradient descent is correct when w and b are close to 0, so
**[4:04]** at random initialization.
**[4:06]** But that as you run gradient descent and w and b become bigger,
**[4:10]** maybe your implementation of backprop is correct only when w and b is close to 0,
**[4:15]** but it gets more inaccurate when w and b become large.
**[4:18]** So one thing you could do, I don't do this very often,
**[4:21]** but one thing you could do is run grad check at random initialization and
**[4:25]** then train the network for a while so that w and
**[4:27]** b have some time to wander away from 0, from your small random initial values.
**[4:33]** And then run grad check again after you've trained for some number of iterations.
**[4:37]** So that's it for gradient checking.
**[4:39]** And congratulations for coming to the end of this week's materials.
**[4:42]** In this week, you've learned about how to set up your train, dev, and test sets,
**[4:47]** how to analyze bias and variance and what things to do if you have high bias versus
**[4:51]** high variance versus maybe high bias and high variance.
**[4:54]** You also saw how to apply different forms of regularization,
**[4:57]** like L2 regularization and dropout on your neural network.
**[5:02]** So some tricks for speeding up the training of your neural network.
**[5:05]** And then finally, gradient checking.
**[5:07]** So I think you've seen a lot in this week and
**[5:10]** you get to exercise a lot of these ideas in this week's programming exercise.
**[5:14]** So best of luck with that, and
**[5:15]** I look forward to seeing you in the week two materials.
