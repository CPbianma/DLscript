---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 2
section: Optimization Algorithms
item_title: Gradient Descent with Momentum
duration: 9 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/y0m1f/gradient-descent-with-momentum
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Gradient Descent with Momentum — Transcript

**[0:00]** There's an algorithm called momentum, or gradient descent with momentum
**[0:04]** that almost always works faster than the standard gradient descent algorithm.
**[0:09]** In one sentence, the basic idea is to compute an exponentially weighted average
**[0:14]** of your gradients, and then use that gradient to update your weights instead.
**[0:18]** In this video, let's unpack that one-sentence description and
**[0:22]** see how you can actually implement this.
**[0:23]** As a example let's say that you're trying to optimize a cost function
**[0:28]** which has contours like this.
**[0:30]** So the red dot denotes the position of the minimum.
**[0:34]** Maybe you start gradient descent here and if you take one iteration of gradient
**[0:39]** descent either or descent maybe end up heading there.
**[0:44]** But now you're on the other side of this ellipse, and
**[0:47]** if you take another step of gradient descent maybe you end up doing that.
**[0:51]** And then another step, another step, and so on.
**[0:55]** And you see that gradient descents will sort of take a lot of steps, right?
**[1:00]** Just slowly oscillate toward the minimum.
**[1:07]** And this up and down oscillations slows down gradient descent and
**[1:11]** prevents you from using a much larger learning rate.
**[1:14]** In particular, if you were to use a much larger learning rate you might end up over
**[1:19]** shooting and end up diverging like so.
**[1:21]** And so the need to prevent the oscillations from getting too big forces
**[1:25]** you to use a learning rate that's not itself too large.
**[1:29]** Another way of viewing this problem is that on the vertical axis
**[1:34]** you want your learning to be a bit slower, because you don't want those oscillations.
**[1:38]** But on the horizontal axis, you want faster learning.
**[1:45]** Right, because you want it to aggressively move from left to right,
**[1:48]** toward that minimum, toward that red dot.
**[1:51]** So here's what you can do if you implement gradient descent with momentum.
**[1:58]** On each iteration, or more specifically,
**[2:03]** during iteration t you would compute the usual derivatives dw, db.
**[2:11]** I'll omit the superscript square bracket l's but
**[2:15]** you compute dw, db on the current mini-batch.
**[2:19]** And if you're using batch gradient descent,
**[2:21]** then the current mini-batch would be just your whole batch.
**[2:24]** And this works as well off a batch gradient descent.
**[2:26]** So if your current mini-batch is your entire training set,
**[2:29]** this works fine as well.
**[2:31]** And then what you do is you
**[2:32]** compute vdW to be Beta vdw
**[2:41]** plus 1 minus Beta dW.
**[2:45]** So this is similar to when we're previously computing
**[2:50]** the theta equals beta v theta plus 1 minus beta theta t.
**[2:57]** Right, so it's computing a moving average of the derivatives for w you're getting.
**[3:02]** And then you similarly compute vdb
**[3:07]** equals that plus 1 minus Beta times db.
**[3:13]** And then you would update your weights using W gets
**[3:18]** updated as W minus the learning rate times, instead of updating it with dW,
**[3:23]** with the derivative, you update it with vdW.
**[3:28]** And similarly, b gets updated as b minus alpha times vdb.
**[3:35]** So what this does is smooth out the steps of gradient descent.
**[3:41]** For example, let's say that in the last few derivatives you computed were this,
**[3:45]** this, this, this, this.
**[3:48]** If you average out these gradients, you find that the oscillations in the vertical
**[3:52]** direction will tend to average out to something closer to zero.
**[3:55]** So, in the vertical direction, where you want to slow things down, this will
**[4:00]** average out positive and negative numbers, so the average will be close to zero.
**[4:05]** Whereas, on the horizontal direction,
**[4:07]** all the derivatives are pointing to the right of the horizontal direction, so
**[4:11]** the average in the horizontal direction will still be pretty big.
**[4:14]** So that's why with this algorithm, with a few iterations
**[4:18]** you find that the gradient descent with momentum ends up eventually just taking
**[4:22]** steps that are much smaller oscillations in the vertical direction,
**[4:28]** but are more directed to just moving quickly in the horizontal direction.
**[4:33]** And so this allows your algorithm to take a more straightforward path,
**[4:37]** or to damp out the oscillations in this path to the minimum.
**[4:42]** One intuition for this momentum which works for some people, but
**[4:47]** not everyone is that if you're trying to minimize your bowl shape function, right?
**[4:53]** This is really the contours of a bowl.
**[4:55]** I guess I'm not very good at drawing.
**[4:57]** They kind of minimize this type of bowl shaped function
**[5:00]** then these derivative terms you can think of as providing
**[5:06]** acceleration to a ball that you're rolling down hill.
**[5:11]** And these momentum terms you can think of as representing the velocity.
**[5:20]** And so imagine that you have a bowl, and you take a ball and
**[5:24]** the derivative imparts acceleration to this little ball as
**[5:28]** the little ball is rolling down this hill, right?
**[5:32]** And so it rolls faster and faster, because of acceleration.
**[5:36]** And data, because this number a little bit less than one, displays a row of
**[5:42]** friction and it prevents your ball from speeding up without limit.
**[5:46]** But so rather than gradient descent,
**[5:50]** just taking every single step independently of all previous steps.
**[5:54]** Now, your little ball can roll downhill and
**[5:56]** gain momentum, but it can accelerate down this bowl and therefore gain momentum.
**[6:01]** I find that this ball rolling down a bowl analogy, it seems to work for
**[6:05]** some people who enjoy physics intuitions.
**[6:07]** But it doesn't work for everyone, so if this analogy of a ball rolling
**[6:12]** down the bowl doesn't work for you, don't worry about it.
**[6:15]** Finally, let's look at some details on how you implement this.
**[6:18]** Here's the algorithm and so you now have two
**[6:22]** hyperparameters of the learning rate alpha, as well as this parameter Beta,
**[6:27]** which controls your exponentially weighted average.
**[6:30]** The most common value for Beta is 0.9.
**[6:33]** We're averaging over the last ten days temperature.
**[6:35]** So it is averaging of the last ten iteration's gradients.
**[6:39]** And in practice, Beta equals 0.9 works very well.
**[6:42]** Feel free to try different values and
**[6:45]** do some hyperparameter search, but 0.9 appears to be a pretty robust value.
**[6:50]** Well, and how about bias correction, right?
**[6:51]** So do you want to take vdW and vdb and divide it by 1 minus beta to the t.
**[6:58]** In practice, people don't usually do this because after just ten iterations,
**[7:02]** your moving average will have warmed up and is no longer a bias estimate.
**[7:06]** So in practice, I don't really see people bothering with bias correction
**[7:11]** when implementing gradient descent or momentum.
**[7:14]** And of course, this process initialize the vdW equals 0.
**[7:18]** Note that this is a matrix of zeroes with the same dimension as dW,
**[7:23]** which has the same dimension as W.
**[7:26]** And Vdb is also initialized to a vector of zeroes.
**[7:30]** So, the same dimension as db, which in turn has same dimension as b.
**[7:35]** Finally, I just want to mention that if you read the literature on gradient
**[7:40]** descent with momentum often you see it with this term omitted,
**[7:45]** with this 1 minus Beta term omitted.
**[7:48]** So you end up with vdW equals Beta vdw plus dW.
**[7:57]** And the net effect of using this version in purple is that vdW ends up being
**[8:02]** scaled by a factor of 1 minus Beta, or really 1 over 1 minus Beta.
**[8:07]** And so when you're performing these gradient descent updates, alpha just needs
**[8:11]** to change by a corresponding value of 1 over 1 minus Beta.
**[8:16]** In practice, both of these will work just fine,
**[8:18]** it just affects what's the best value of the learning rate alpha.
**[8:23]** But I find that this particular formulation is a little less intuitive.
**[8:28]** Because one impact of this is that if you end up tuning the hyperparameter Beta,
**[8:33]** then this affects the scaling of vdW and vdb as well.
**[8:37]** And so you end up needing to retune the learning rate, alpha, as well, maybe.
**[8:42]** So I personally prefer the formulation that I have written here on the left,
**[8:46]** rather than leaving out the 1 minus Beta term.
**[8:49]** But, so I tend to use the formula on the left,
**[8:52]** the printed formula with the 1 minus Beta term.
**[8:55]** But both versions having Beta equal 0.9 is a common choice of hyperparameter.
**[9:00]** It's just at alpha the learning rate would need to be tuned differently for
**[9:03]** these two different versions.
**[9:04]** So that's it for gradient descent with momentum.
**[9:07]** This will almost always work better than the straightforward
**[9:11]** gradient descent algorithm without momentum.
**[9:13]** But there's still other things we could do to speed up your learning algorithm.
**[9:17]** Let's continue talking about these in the next couple videos.
