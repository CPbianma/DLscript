---
type: video-transcript
specialization: Deep Learning Specialization
course: Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization
week: 2
section: Optimization Algorithms
item_title: RMSprop
duration: 8 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/BhJlm/rmsprop
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# RMSprop — Transcript

**[0:00]** You've seen how using momentum can speed up gradient descent.
**[0:03]** There's another algorithm called RMSprop,
**[0:06]** which stands for root mean square prop, that can also speed up gradient descent.
**[0:10]** Let's see how it works.
**[0:11]** Recall our example from before, that if you implement gradient descent,
**[0:16]** you can end up with huge oscillations in the vertical direction,
**[0:20]** even while it's trying to make progress in the horizontal direction.
**[0:24]** In order to provide intuition for this example, let's say that
**[0:28]** the vertical axis is the parameter b and horizontal axis is the parameter w.
**[0:34]** It could be w1 and w2 where some of the center parameters was named as b and
**[0:39]** w for the sake of intuition.
**[0:42]** And so, you want to slow down the learning in the b direction, or
**[0:46]** in the vertical direction.
**[0:48]** And speed up learning, or at least not slow it down in the horizontal direction.
**[0:54]** So this is what the RMSprop algorithm does to accomplish this.
**[0:59]** On iteration t, it will compute as usual the derivative dW,
**[1:07]** db on the current mini-batch.
**[1:15]** So I was going to keep this exponentially weighted average.
**[1:19]** Instead of VdW, I'm going to use the new notation SdW.
**[1:22]** So SdW is equal to beta times their previous
**[1:27]** value + 1- beta times dW squared.
**[1:34]** Sometimes write this dW star star 2, to deliniate expensation we will just write this as dw squared.
**[1:41]** So for clarity, this squaring operation is an element-wise squaring operation.
**[1:48]** So what this is doing is really keeping an exponentially weighted
**[1:52]** average of the squares of the derivatives.
**[1:56]** And similarly, we also have Sdb equals beta Sdb + 1- beta, db squared.
**[2:04]** And again, the squaring is an element-wise operation.
**[2:08]** Next, RMSprop then updates the parameters as follows.
**[2:13]** W gets updated as W minus the learning rate, and
**[2:17]** whereas previously we had alpha times dW, now it's
**[2:22]** dW divided by square root of SdW.
**[2:27]** And b gets updated as b minus the learning rate times,
**[2:33]** instead of just the gradient, this is also divided by, now divided by Sdb.
**[2:39]** So let's gain some intuition about how this works.
**[2:42]** Recall that in the horizontal direction or
**[2:45]** in this example, in the W direction we want learning to go pretty fast.
**[2:50]** Whereas in the vertical direction or in this example in the b direction,
**[2:54]** we want to slow down all the oscillations into the vertical direction.
**[2:59]** So with this terms SdW an Sdb,
**[3:01]** what we're hoping is that SdW will be relatively small,
**[3:06]** so that here we're dividing by relatively small number.
**[3:11]** Whereas Sdb will be relatively large, so that here we're dividing yt relatively
**[3:16]** large number in order to slow down the updates on a vertical dimension.
**[3:21]** And indeed if you look at the derivatives, these derivatives are much
**[3:25]** larger in the vertical direction than in the horizontal direction.
**[3:30]** So the slope is very large in the b direction, right?
**[3:33]** So with derivatives like this, this is a very large db and a relatively small dw.
**[3:40]** Because the function is sloped much more steeply in the vertical direction than as
**[3:45]** in the b direction, than in the w direction, than in horizontal direction.
**[3:50]** And so, db squared will be relatively large.
**[3:53]** So Sdb will relatively large, whereas compared to that dW will be smaller,
**[3:58]** or dW squared will be smaller, and so SdW will be smaller.
**[4:02]** So the net effect of this is that your up days in the vertical direction
**[4:06]** are divided by a much larger number, and so that helps damp out the oscillations.
**[4:11]** Whereas the updates in the horizontal direction are divided by a smaller number.
**[4:15]** So the net impact of using RMSprop is that your updates will end
**[4:19]** up looking more like this.
**[4:22]** That your updates in the, Vertical
**[4:27]** direction and then horizontal direction you can keep going.
**[4:32]** And one effect of this is also that you can therefore use a larger learning rate
**[4:36]** alpha, and get faster learning without diverging in the vertical direction.
**[4:41]** Now just for the sake of clarity, I've been calling the vertical and
**[4:44]** horizontal directions b and w, just to illustrate this.
**[4:48]** In practice, you're in a very high dimensional space of parameters,
**[4:53]** so maybe the vertical dimensions where you're trying to damp
**[4:57]** the oscillation is a sum set of parameters, w1, w2, w17.
**[5:01]** And the horizontal dimensions might be w3, w4 and so on, right?.
**[5:07]** And so, the separation there's a WMP is just an illustration.
**[5:11]** In practice, dW is a very high-dimensional parameter vector.
**[5:15]** Db is also very high-dimensional parameter vector, but
**[5:18]** your intuition is that in dimensions where you're getting these oscillations,
**[5:22]** you end up computing a larger sum.
**[5:26]** A weighted average for these squares and derivatives, and so
**[5:29]** you end up dumping ] out the directions in which there are these oscillations.
**[5:33]** So that's RMSprop, and it stands for root mean squared prop, because here
**[5:39]** you're squaring the derivatives, and then you take the square root here at the end.
**[5:44]** So finally, just a couple last details on this algorithm before we move on.
**[5:49]** In the next video, we're actually going to combine RMSprop together with momentum.
**[5:55]** So rather than using the hyperparameter beta, which we had used for momentum,
**[6:00]** I'm going to call this hyperparameter beta 2 just to not clash.
**[6:05]** The same hyperparameter for both momentum and for RMSprop.
**[6:09]** And also to make sure that your algorithm doesn't divide by 0.
**[6:13]** What if square root of SdW, right, is very close to 0.
**[6:17]** Then things could blow up.
**[6:19]** Just to ensure numerical stability, when you implement this in practice you
**[6:24]** add a very, very small epsilon to the denominator.
**[6:28]** It doesn't really matter what epsilon is used.
**[6:30]** 10 to the -8 would be a reasonable default, but this just ensures slightly
**[6:34]** greater numerical stability that for numerical round off or whatever reason,
**[6:39]** that you don't end up dividing by a very, very small number.
**[6:43]** So that's RMSprop, and similar to momentum, has the effects of
**[6:47]** damping out the oscillations in gradient descent, in mini-batch gradient descent.
**[6:52]** And allowing you to maybe use a larger learning rate alpha.
**[6:56]** And certainly speeding up the learning speed of your algorithm.
**[7:01]** So now you know to implement RMSprop, and this will be another way for
**[7:05]** you to speed up your learning algorithm.
**[7:07]** One fun fact about RMSprop,
**[7:09]** it was actually first proposed not in an academic research paper, but
**[7:13]** in a Coursera course that Jeff Hinton had taught on Coursera many years ago.
**[7:17]** I guess Coursera wasn't intended to be a platform for dissemination of
**[7:22]** novel academic research, but it worked out pretty well in that case.
**[7:26]** And was really from the Coursera course that RMSprop started to become widely
**[7:30]** known and it really took off.
**[7:31]** We talked about momentum.
**[7:32]** We talked about RMSprop.
**[7:34]** It turns out that if you put them together you can get an even better
**[7:37]** optimization algorithm.
**[7:39]** Let's talk about that in the next video.
