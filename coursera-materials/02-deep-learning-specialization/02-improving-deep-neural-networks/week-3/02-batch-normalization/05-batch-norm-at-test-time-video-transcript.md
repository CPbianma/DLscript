---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 3
section: Batch Normalization
item_title: Batch Norm at Test Time
duration: 6 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/FsoNw/batch-norm-at-test-time
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Batch Norm at Test Time — Transcript

**[0:00]** Batch norm processes your data one mini batch at a time,
**[0:03]** but the test time you might need to process the examples one at a time.
**[0:07]** Let's see how you can adapt your network to do that.
**[0:10]** Recall that during training,
**[0:12]** here are the equations you'd use to implement batch norm.
**[0:15]** Within a single mini batch,
**[0:17]** you'd sum over that mini batch of the ZI values to compute the mean.
**[0:22]** So here, you're just summing over the examples in one mini batch.
**[0:25]** I'm using M to denote the number of examples
**[0:28]** in the mini batch not in the whole training set.
**[0:31]** Then, you compute the variance and then you compute Z norm by
**[0:35]** scaling by the mean and standard deviation with Epsilon added for numerical stability.
**[0:41]** And then Z̃ is taking Z norm and rescaling by gamma and beta.
**[0:47]** So, notice that mu and sigma squared which you
**[0:51]** need for this scaling calculation are computed on the entire mini batch.
**[0:57]** But the test time you might not have a mini batch of
**[1:00]** 6428 or 2056 examples to process at the same time.
**[1:05]** So, you need some different way of coming up with mu and sigma squared.
**[1:07]** And if you have just one example,
**[1:10]** taking the mean and variance of that one example, doesn't make sense.
**[1:15]** So what's actually done?
**[1:16]** In order to apply your neural network and test time is to
**[1:21]** come up with some separate estimate of mu and sigma squared.
**[1:25]** And in typical implementations of batch norm,
**[1:27]** what you do is estimate this using
**[1:32]** a exponentially weighted average where the average is
**[1:37]** across the mini batches.
**[1:42]** So, to be very concrete here's what I mean.
**[1:45]** Let's pick some layer L and let's say you're going through mini batches X1,
**[1:51]** X2 together with the corresponding values of Y and so on.
**[1:57]** So, when training on X1 for that layer L,
**[2:02]** you get some mu L. And in fact,
**[2:06]** I'm going to write this as mu for the first mini batch and that layer.
**[2:12]** And then when you train on the second mini batch for that layer
**[2:15]** and that mini batch,you end up with some second value of mu.
**[2:19]** And then for the fourth mini batch in this hidden layer,
**[2:23]** you end up with some third value for mu.
**[2:29]** So just as we saw how to use
**[2:31]** a exponentially weighted average to compute the mean of Theta one, Theta two,
**[2:37]** Theta three when you were trying to compute
**[2:40]** a exponentially weighted average of the current temperature,
**[2:44]** you would do that to keep track of what's
**[2:47]** the latest average value of this mean vector you've seen.
**[2:50]** So that exponentially weighted average becomes
**[2:54]** your estimate for what the mean of the Zs is for that hidden layer and similarly,
**[3:00]** you use an exponentially weighted average to keep track of
**[3:03]** these values of sigma squared that you see on the first mini batch in that layer,
**[3:09]** sigma square that you see on second mini batch and so on.
**[3:13]** So you keep a running average of the mu and the sigma squared that you're
**[3:18]** seeing for each layer as you train the neural network across different mini batches.
**[3:24]** Then finally at test time,
**[3:26]** what you do is in place of this equation,
**[3:30]** you would just compute Z norm using whatever value your Z have,
**[3:35]** and using your exponentially weighted average of
**[3:39]** the mu and sigma square whatever was the latest value you have to do the scaling here.
**[3:45]** And then you would compute Z̃
**[3:48]** on your one test example using that Z norm that we just computed on
**[3:53]** the left and using the beta and
**[3:57]** gamma parameters that you have learned during your neural network training process.
**[4:02]** So the takeaway from this is that during training time mu and
**[4:07]** sigma squared are computed on an entire mini batch of say 64 engine,
**[4:11]** 28 or some number of examples.
**[4:14]** But that test time, you might need to process a single example at a time.
**[4:18]** So, the way to do that is to estimate mu and sigma squared
**[4:21]** from your training set and there are many ways to do that.
**[4:25]** You could in theory run your whole training
**[4:27]** set through your final network to get mu and sigma squared.
**[4:30]** But in practice, what people usually do is implement and
**[4:33]** exponentially weighted average where you just keep
**[4:36]** track of the mu and sigma squared values you're seeing
**[4:38]** during training and use and exponentially the weighted average,
**[4:42]** also sometimes called the running average,
**[4:44]** to just get a rough estimate of mu and sigma
**[4:46]** squared and then you use those values of mu and sigma squared
**[4:49]** that test time to do the scale and you need the head and unit values Z.
**[4:55]** In practice, this process is pretty robust
**[4:58]** to the exact way you used to estimate mu and sigma squared.
**[5:03]** So, I wouldn't worry too much about exactly how you do
**[5:06]** this and if you're using a deep learning framework,
**[5:09]** they'll usually have some default way to estimate
**[5:13]** the mu and sigma squared that should work reasonably well as well.
**[5:17]** But in practice, any reasonable way to estimate the mean and
**[5:21]** variance of your head and unit values Z should work fine at test.
**[5:28]** So, that's it for batch norm and using it.
**[5:31]** I think you'll be able to train much deeper networks
**[5:33]** and get your learning algorithm to run much more quickly.
**[5:37]** Before we wrap up for this week,
**[5:38]** I want to share with you some thoughts on deep learning frameworks as well.
**[5:43]** Let's start to talk about that in the next video.
