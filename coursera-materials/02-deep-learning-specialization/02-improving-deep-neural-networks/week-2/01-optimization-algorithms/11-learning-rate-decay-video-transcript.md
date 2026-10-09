---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 2
section: Optimization Algorithms
item_title: Learning Rate Decay
duration: 7 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/hjgIA/learning-rate-decay
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Learning Rate Decay — Transcript

**[0:00]** One of the things that might
**[0:01]** help speed up your learning algorithm
**[0:03]** is to slowly reduce your learning rate over time.
**[0:06]** We call this learning rate decay.
**[0:08]** Let's see how you can implement this.
**[0:10]** Let's start with an example of why you
**[0:12]** might want to implement learning rate decay.
**[0:14]** Suppose you're implementing mini-batch gradient descents
**[0:18]** with a reasonably small mini-batch,
**[0:20]** maybe a mini-batch has just 64, 128 examples.
**[0:23]** Then as you iterate,
**[0:25]** your steps will be a little bit noisy and
**[0:28]** it will tend towards this minimum over here,
**[0:31]** but it won't exactly converge.
**[0:33]** But your algorithm might just end up wandering
**[0:36]** around and never really converge
**[0:39]** because you're using some fixed value for
**[0:41]** Alpha and there's just some noise
**[0:44]** in your different mini-batches.
**[0:46]** But if you were to
**[0:48]** slowly reduce your learning rate Alpha,
**[0:52]** then during the initial phases,
**[0:54]** while your learning rate Alpha is still large,
**[0:56]** you can still have relatively fast learning.
**[0:58]** But then as Alpha gets smaller,
**[1:01]** your steps you take will be slower and smaller, and so,
**[1:06]** you end up oscillating in a tighter region around
**[1:10]** this minimum rather than
**[1:11]** wandering far away even as training goes on and on.
**[1:15]** The intuition behind slowly reducing
**[1:18]** Alpha is that maybe during the initial steps of learning,
**[1:22]** you could afford to take much bigger steps,
**[1:24]** but then as learning approaches convergence,
**[1:28]** then having a slower learning rate
**[1:30]** allows you to take smaller steps.
**[1:32]** Here's how you can implement learning rate decay.
**[1:36]** Recall that one epoch is one pass through the data.
**[1:44]** If you have a training set as follows,
**[1:49]** maybe break it up into different mini-batches.
**[1:54]** Then the first pass through
**[1:57]** the training set is called the first epoch,
**[2:00]** and then the second pass is the second epoch, and so on.
**[2:05]** One thing you could do is set
**[2:07]** your learning rate Alpha to be
**[2:09]** equal to 1 over 1 plus a parameter,
**[2:13]** which I'm going to call the decay rate,
**[2:17]** times the epoch num.
**[2:22]** This is going to be times some
**[2:24]** initial learning rate Alpha 0.
**[2:27]** Note that the decay rate here becomes
**[2:29]** another hyperparameter which you might need to tune.
**[2:32]** Here's a concrete example.
**[2:34]** If you take several epochs,
**[2:36]** so several passes through your data,
**[2:39]** if Alpha 0 is equal to
**[2:41]** 0.2 and the decay rate is equal to 1,
**[2:46]** then during your first epoch,
**[2:48]** Alpha will be 1 over 1 plus 1 times Alpha 0,
**[2:55]** so your learning rate will be 0.1.
**[2:59]** That's just evaluating this formula
**[3:02]** when the decay rate is equal to 1 and epoch num is 1.
**[3:05]** On the second epoch,
**[3:07]** your learning rate decay is 0.67.
**[3:10]** On the third, 0.5.
**[3:12]** On the fourth, 0.4, and so on.
**[3:16]** Feel free to evaluate more of
**[3:17]** these values yourself and get a sense
**[3:18]** that as a function of epoch number,
**[3:22]** your learning rate gradually decreases,
**[3:25]** according to this formula up on top.
**[3:29]** If you wish to use learning rate decay,
**[3:32]** what you can do is try a variety of
**[3:35]** values of both hyperparameter Alpha 0,
**[3:38]** as well as this decay rate hyperparameter,
**[3:41]** and then try to find a value that works well.
**[3:44]** Other than this formula for learning rate decay,
**[3:46]** there are a few other ways that people use.
**[3:48]** For example, this is called exponential decay,
**[3:52]** where Alpha is equal to some number less than 1,
**[3:57]** such as 0.95, times epoch num times Alpha 0.
**[4:04]** This will exponentially quickly decay your learning rate.
**[4:10]** Other formulas that people use are things like
**[4:12]** Alpha equals some constant
**[4:15]** over epoch num square root times Alpha 0,
**[4:22]** or some constant k and another hyperparameter over
**[4:26]** the mini-batch number t square rooted times Alpha 0.
**[4:32]** Sometimes you also see people
**[4:34]** use a learning rate that decreases and discretes that,
**[4:38]** where for some number of steps,
**[4:41]** you have some learning rate,
**[4:43]** and then after a while,
**[4:44]** you decrease it by one-half, after a while,
**[4:46]** by one-half, after a while,
**[4:48]** by one-half, and so,
**[4:49]** this is a discrete staircase.
**[4:54]** So far, we've talked about using
**[4:58]** some formula to govern how Alpha,
**[5:02]** the learning rate changes over time.
**[5:04]** One other thing that people sometimes do is manual decay.
**[5:08]** If you're training just one model at a time,
**[5:11]** and if your model takes
**[5:13]** many hours or even many days to train,
**[5:15]** what some people would do is just watch your model as
**[5:18]** it's training over a large number of days,
**[5:21]** and then now you say, oh,
**[5:23]** it looks like the learning rate slowed down,
**[5:25]** I'm going to decrease Alpha a little bit.
**[5:26]** Of course, this works, this manually controlling Alpha,
**[5:29]** really tuning Alpha by hand, hour-by-hour, day-by-day.
**[5:33]** This works only if you're training
**[5:35]** only a small number of models,
**[5:36]** but sometimes people do that as well.
**[5:38]** Now you have a few more options of how to
**[5:40]** control the learning rate Alpha.
**[5:43]** Now, in case you're thinking, wow,
**[5:45]** this is a lot of hyperparameters,
**[5:46]** how do I select amongst all these different options?
**[5:49]** I would say don't worry about it for now, and next week,
**[5:51]** we'll talk more about how
**[5:52]** to systematically choose hyperparameters.
**[5:56]** For me, I would say that
**[5:58]** learning rate decay is usually lower
**[5:59]** down on the list of things I try.
**[6:01]** Setting Alpha just a fixed value of Alpha and
**[6:04]** getting that to be well-tuned has a huge impact,
**[6:06]** learning rate decay does help.
**[6:08]** Sometimes it can really help speed up training,
**[6:10]** but it is a little bit lower down
**[6:12]** my list in terms of the things I would try.
**[6:15]** But next week, when we talk about hyperparameter tuning,
**[6:17]** you'll see more systematic ways to organize all of
**[6:20]** these hyperparameters and how
**[6:22]** to efficiently search amongst them.
**[6:24]** That's it for learning rate decay.
**[6:27]** Finally, I also want to talk a little bit
**[6:29]** about local optima and saddle points in
**[6:32]** neural networks so you can have
**[6:33]** a little bit better intuition about the types of
**[6:36]** optimization problems your optimization algorithm
**[6:39]** is trying to solve when you're trying
**[6:40]** to train these neural networks.
**[6:41]** Let's go onto the next video to see that.
