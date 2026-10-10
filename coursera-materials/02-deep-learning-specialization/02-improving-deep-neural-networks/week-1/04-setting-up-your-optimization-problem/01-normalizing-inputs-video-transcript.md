---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 1
section: Setting Up your Optimization Problem
item_title: Normalizing Inputs
duration: 5 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/lXv6U/normalizing-inputs
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Normalizing Inputs — Transcript

**[0:00]** When training a neural network,
**[0:01]** one of the techniques to speed up
**[0:03]** your training is if you normalize your inputs.
**[0:05]** Let's see what that means.
**[0:07]** Let's see the training sets with two input features.
**[0:10]** The input features x are two-dimensional
**[0:13]** and here's a scatter plot of your training set.
**[0:16]** Normalizing your inputs corresponds to two steps,
**[0:20]** the first is to subtract out or to zero out the mean,
**[0:26]** so your sets mu equals 1 over m,
**[0:29]** sum over I of x_i.
**[0:33]** This is a vector and then x gets
**[0:36]** set as x minus mu for every training example.
**[0:39]** This means that you just move
**[0:41]** the training set until it has zero mean.
**[0:44]** Then the second step is to normalize the variances.
**[0:49]** Notice here that the feature x_1 has
**[0:52]** a much larger variance than the feature x_2 here.
**[0:55]** What we do is set sigma equals 1 over
**[0:59]** m sum of x_i star, star 2.
**[1:04]** I guess this is element-y squaring.
**[1:06]** Now sigma squared is a vector
**[1:09]** with the variances of each of the features.
**[1:12]** Notice we've already subtracted out the mean,
**[1:14]** so x_i squared, element-y square is just the variances.
**[1:19]** You take each example and divide it by this vector sigma.
**[1:23]** In some pictures, you end up with this where now
**[1:28]** the variance of x_1 and x_2 are both equal to one.
**[1:34]** One tip. If you use this to scale your training data,
**[1:39]** then use the same mu and
**[1:42]** sigma to normalize your test set.
**[1:45]** In particular, you don't want to
**[1:48]** normalize the training set and a test set differently.
**[1:51]** Whatever this value is and whatever this value is,
**[1:53]** use them in these two formulas
**[1:56]** so that you scale your test set in
**[1:59]** exactly the same way rather than estimating mu and
**[2:01]** sigma squared separately on
**[2:02]** your training set and test set,
**[2:04]** because you want your data
**[2:06]** both training and test examples to go through
**[2:08]** the same transformation defined by
**[2:11]** the same Mu and Sigma squared
**[2:12]** calculated on your training data.
**[2:15]** Why do we do this?
**[2:16]** Why do we want to normalize the input features?
**[2:19]** Recall that the cost function is
**[2:21]** defined as written on the top right.
**[2:23]** It turns out that if you use unnormalized input features,
**[2:28]** it's more likely that
**[2:29]** your cost function will look like this,
**[2:31]** like a very squished out bar,
**[2:33]** very elongated cost function
**[2:36]** where the minimum you're
**[2:37]** trying to find is maybe over there.
**[2:39]** But if your features are on very different scales,
**[2:43]** say the feature x_1 ranges
**[2:45]** from 1-1,000 and the feature x_2 ranges from 0-1,
**[2:50]** then it turns out that
**[2:52]** the ratio or the range of values for
**[2:55]** the parameters w_1 and
**[2:57]** w_2 will end up taking on very different values.
**[3:00]** Maybe these axes should be w_1 and w_2,
**[3:03]** but the intuition of plot w and b,
**[3:06]** cost function can be very elongated bow like that.
**[3:09]** If you plot the contours of this function,
**[3:12]** you can have a very elongated function like that.
**[3:15]** Whereas if you normalize the features,
**[3:17]** then your cost function
**[3:20]** will on average look more symmetric.
**[3:23]** If you are running gradient descent
**[3:24]** on a cost function like the one on the left,
**[3:26]** then you might have to use a very
**[3:28]** small learning rate because if you're here,
**[3:30]** the gradient decent might need
**[3:32]** a lot of steps to oscillate back and
**[3:34]** forth before it finally finds its way to the minimum.
**[3:38]** Whereas if you have more spherical contours,
**[3:42]** then wherever you start,
**[3:44]** gradient descent can pretty
**[3:46]** much go straight to the minimum.
**[3:47]** You can take much larger steps
**[3:49]** where gradient descent need,
**[3:50]** rather than needing to
**[3:51]** oscillate around like the picture on the left.
**[3:54]** Of course, in practice,
**[3:55]** w is a high dimensional vector.
**[3:58]** Trying to plot this in 2D doesn't
**[4:00]** convey all the intuitions correctly.
**[4:02]** But the rough intuition that you cost function
**[4:05]** will be in a more round and
**[4:06]** easier to optimize when you're
**[4:08]** features are on similar scales.
**[4:10]** Not from 1-1000, 0-1,
**[4:13]** but mostly from minus 1-1
**[4:16]** or about similar variance as each other.
**[4:19]** That just makes your cost function
**[4:21]** j easier and faster to optimize.
**[4:23]** In practice, if one feature,
**[4:25]** say x_1 ranges from 0-1 and x_2 ranges from minus 1-1,
**[4:31]** and x_3 ranges from 1-2,
**[4:33]** these are fairly similar ranges,
**[4:35]** so this will work just fine,
**[4:37]** is when they are on dramatically different ranges like
**[4:39]** ones from 1-1000 and another from 0-1.
**[4:42]** That really hurts your optimization algorithm.
**[4:44]** That by just setting all of them to zero mean
**[4:47]** and say variance one like we did on the last slide,
**[4:50]** that just guarantees that all your features are in
**[4:52]** a similar scale and will
**[4:53]** usually help you learning algorithm run faster.
**[4:56]** If your input features came from very different scales,
**[5:00]** maybe some features are from 0-1,
**[5:01]** sum from 1-1000, then it's
**[5:03]** important to normalize your features.
**[5:06]** If your features came in on similar scales,
**[5:08]** then this step is less important although performing
**[5:11]** this type of normalization
**[5:12]** pretty much never does any harm.
**[5:14]** Often you'll do it anyway,
**[5:16]** if I'm not sure whether or not it will help
**[5:18]** with speeding up training for your algorithm.
**[5:21]** That's it for normalizing your input features.
**[5:24]** Next, let's keep talking about ways to
**[5:26]** speed up the training of your neural network.
