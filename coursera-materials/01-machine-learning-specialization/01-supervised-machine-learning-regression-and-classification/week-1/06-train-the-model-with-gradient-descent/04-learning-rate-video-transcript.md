---
type: video-transcript
specialization: Machine Learning Specialization
course: Supervised Machine Learning: Regression and Classification
week: 1
section: Train the model with gradient descent
item_title: Learning rate
duration: 9 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/OoP3Y/learning-rate
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Learning rate — Transcript

**[0:01]** The choice of the learning rate, alpha will have a huge impact
**[0:05]** on the efficiency of your implementation of gradient descent.
**[0:09]** And if alpha,
**[0:10]** the learning rate is chosen poorly rate of descent may not even work at all.
**[0:15]** In this video, let's take a deeper look at the learning rate.
**[0:19]** This will also help you choose better learning rates for
**[0:23]** your implementations of gradient descent.
**[0:26]** So here again, is the gradient descent rule.
**[0:29]** W is updated to be W minus the learning rate, alpha times the derivative term.
**[0:35]** To learn more about what the learning rate alpha is doing.
**[0:38]** Let's see what could happen if the learning rate alpha is either too small or
**[0:44]** if it is too large.
**[0:46]** For the case where the learning rate is too small.
**[0:49]** Here's a graph where the horizontal axis is W and the vertical axis is the cost J.
**[0:56]** And here's the graph of the function J of W.
**[1:01]** Let's start grading descent at this point here, if the learning rate is too small.
**[1:07]** Then what happens is that you multiply your derivative term by some really,
**[1:13]** really small number.
**[1:14]** So you're going to be multiplying by number alpha.
**[1:18]** That's really small, like 0.0000001.
**[1:23]** And so you end up taking a very small baby step like that.
**[1:28]** Then from this point you're going to take another tiny tiny little baby step.
**[1:33]** But because the learning rate is so small, the second step is also just minuscule.
**[1:40]** The outcome of this process is that you do end up decreasing the cost J but
**[1:45]** incredibly slowly.
**[1:47]** So, here's another step and another step,
**[1:50]** another tiny step until you finally approach the minimum.
**[1:54]** But as you may notice you're going to need a lot of steps to get to the minimum.
**[1:59]** So to summarize if the learning rate is too small,
**[2:03]** then gradient descents will work, but it will be slow.
**[2:07]** It will take a very long time because it's going to take these tiny tiny baby steps.
**[2:12]** And it's going to need a lot of steps before it
**[2:15]** gets anywhere close to the minimum.
**[2:17]** Now, let's look at a different case.
**[2:20]** What happens if the learning rate is too large?
**[2:24]** Here's another graph of the cost function.
**[2:26]** And let's say we start grating descent with W at this value here.
**[2:32]** So it's actually already pretty close to the minimum.
**[2:37]** So the decorative points to the right.
**[2:40]** But if the learning rate is too large then you
**[2:45]** update W very giant step to be all the way over here.
**[2:51]** And that's this point here on the function J.
**[2:56]** So you move from this point on the left, all the way to this point on the right.
**[3:01]** And now the cost has actually gotten worse.
**[3:04]** It has increased because it started out at this value here and
**[3:09]** after one step, it actually increased to this value here.
**[3:13]** Now the derivative at this new point says to decrease W but
**[3:18]** when the learning rate is too big.
**[3:22]** Then you may take a huge step going from here all the way out here.
**[3:27]** So now you've gotten to this point here and again,
**[3:30]** if the learning rate is too big.
**[3:32]** Then you take another huge step with an acceleration and
**[3:36]** way overshoot the minimum again.
**[3:38]** So now you're at this point on the right and one more time you do another update.
**[3:44]** And end up all the way here and so you're now at this point here.
**[3:51]** So as you may notice you're actually getting further and
**[3:54]** further away from the minimum.
**[3:56]** So if the learning rate is too large,
**[3:59]** then creating the sense may overshoot and may never reach the minimum.
**[4:05]** And another way to say that is that great intersect
**[4:10]** may fail to converge and may even diverge.
**[4:14]** So, here's another question, you may be wondering one of
**[4:19]** your parameter W is already at this point here.
**[4:23]** So that your cost J is already at a local minimum.
**[4:29]** What do you think?
**[4:30]** One step of gradient descent will do if you've already reached a minimum?
**[4:35]** So this is a tricky one.
**[4:38]** When I was first learning this stuff,
**[4:40]** it actually took me a long time to figure it out.
**[4:43]** But let's work through this together.
**[4:45]** Let's suppose you have some cost function J.
**[4:49]** And the one you see here isn't a square error cost function and
**[4:55]** this cost function has two local minima corresponding to
**[4:59]** the two valleys that you see here.
**[5:02]** Now let's suppose that after some number of steps of gradient descent,
**[5:08]** your parameter W is over here, say equal to five.
**[5:13]** And so this is the current value of W.
**[5:16]** This means that you're at this point on the cost function J.
**[5:20]** And that happens to be a local minimum,
**[5:23]** turns out if you draw attention to the function at this point.
**[5:28]** The slope of this line is zero and thus the derivative term.
**[5:32]** Here is equal to zero for the current value of W.
**[5:37]** And so you're grading descent update becomes W is updated
**[5:42]** to W minus the learning rate times zero.
**[5:45]** We're here that's because the derivative term is equal to zero.
**[5:50]** And this is the same as saying let's set W to be equal to W.
**[5:56]** So this means that if you're already at a local minimum,
**[6:01]** gradient descent leaves W unchanged.
**[6:04]** Because it just updates the new value of W to be the exact same old value of W.
**[6:10]** So concretely, let's say if the current value of W is five.
**[6:15]** And alpha is 0.1 after one iteration,
**[6:20]** you update W as W minus alpha times zero and
**[6:25]** it is still equal to five.
**[6:28]** So if your parameters have already brought you to a local minimum,
**[6:33]** then further gradient descent steps to absolutely nothing.
**[6:37]** It doesn't change the parameters which is what you want because it keeps
**[6:41]** the solution at that local minimum.
**[6:43]** This also explains why gradient descent can reach a local minimum,
**[6:48]** even with a fixed learning rate alpha.
**[6:51]** Here's what I mean, to illustrate this, let's look at another example.
**[6:57]** Here's the cost function J of W that we want to minimize.
**[7:02]** Let's initialize gradient descent up here at this point.
**[7:07]** If we take one update step, maybe it will take us to that point.
**[7:13]** And because this derivative is pretty large, grading,
**[7:18]** descent takes a relatively big step right.
**[7:21]** Now, we're at this second point where we take another step.
**[7:26]** And you may notice that the slope is not as steep as it was at the first point.
**[7:31]** So the derivative isn't as large.
**[7:33]** And so the next update step will not be as large as that first step.
**[7:39]** Now, read this third point here and
**[7:42]** the derivative is smaller than it was at the previous step.
**[7:47]** And will take an even smaller step as we approach the minimum.
**[7:52]** The decorative gets closer and closer to zero.
**[7:56]** So as we run gradient descent, eventually we're taking very small
**[8:01]** steps until you finally reach a local minimum.
**[8:04]** So just to recap, as we get nearer a local minimum gradient
**[8:09]** descent will automatically take smaller steps.
**[8:13]** And that's because as we approach the local minimum,
**[8:16]** the derivative automatically gets smaller.
**[8:19]** And that means the update steps also automatically gets smaller.
**[8:24]** Even if the learning rate alpha is kept at some fixed value.
**[8:28]** So that's the gradient descent algorithm,
**[8:31]** you can use it to try to minimize any cost function J.
**[8:35]** Not just the mean squared error cost function that we're using for
**[8:40]** the new regression.
**[8:41]** In the next video, we're going to take the function J and
**[8:45]** set that back to be exactly the linear regression models cost function.
**[8:50]** The mean squared error cost function that we come up with earlier.
**[8:54]** And putting together great in dissent with this cost function that will give you
**[8:58]** your first learning algorithm, the linear regression algorithm.
