---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 3
section: Batch Normalization
item_title: Normalizing Activations in a Network
duration: 9 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/4ptp2/normalizing-activations-in-a-network
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Normalizing Activations in a Network — Transcript

**[0:00]** In the rise of deep learning,
**[0:01]** one of the most important ideas has been an algorithm called batch normalization,
**[0:06]** created by two researchers, Sergey Ioffe and Christian Szegedy.
**[0:10]** Batch normalization makes your hyperparameter search problem much easier,
**[0:14]** makes your neural network much more robust.
**[0:16]** The choice of hyperparameters is a much bigger range of hyperparameters that work
**[0:20]** well, and will also enable you to much more easily train even very deep networks.
**[0:25]** Let's see how batch normalization works.
**[0:27]** When training a model, such as logistic regression, you might remember that
**[0:32]** normalizing the input features can speed up learnings in compute the means,
**[0:37]** subtract off the means from your training sets.
**[0:40]** Compute the variances.
**[0:44]** The sum of xi squared.
**[0:46]** This is an element-wise squaring.
**[0:49]** And then normalize your data set according to the variances.
**[0:53]** And we saw in an earlier video how this can turn the contours of your learning
**[0:57]** problem from something that might be very elongated to something that is more round,
**[1:02]** and easier for an algorithm like gradient descent to optimize.
**[1:07]** So this works, in terms of normalizing the input feature values
**[1:12]** to a neural network, alter the regression.
**[1:15]** Now, how about a deeper model?
**[1:17]** You have not just input features x, but in this layer you have activations a1,
**[1:22]** in this layer, you have activations a2 and so on.
**[1:27]** So if you want to train the parameters, say w3, b3, then
**[1:32]** wouldn't it be nice if you can normalize the mean and
**[1:36]** variance of a2 to make the training of w3, b3 more efficient?
**[1:43]** In the case of logistic regression, we saw how normalizing x1,
**[1:46]** x2, x3 maybe helps you train w and b more efficiently.
**[1:51]** So here, the question is, for any hidden layer, can we normalize,
**[1:57]** The values of a, let's say a2,
**[2:01]** in this example but really any hidden layer,
**[2:04]** so as to train w3 b3 faster, right?
**[2:12]** Since a2 is the input to the next layer,
**[2:15]** that therefore affects your training of w3 and b3.
**[2:20]** So this is what batch norm does, batch normalization, or batch norm for
**[2:24]** short, does.
**[2:25]** Although technically, we'll actually normalize the values of not a2 but z2.
**[2:31]** There are some debates in the deep learning literature about whether you
**[2:36]** should normalize the value before the activation function, so z2, or whether
**[2:40]** you should normalize the value after applying the activation function, a2.
**[2:45]** In practice, normalizing z2 is done much more often.
**[2:48]** So that's the version I'll present and
**[2:51]** what I would recommend you use as a default choice.
**[2:54]** So here is how you will implement batch norm.
**[2:58]** Given some intermediate values, In your neural net,
**[3:09]** Let's say that you have some hidden unit values z1 up to zm,
**[3:15]** and this is really from some hidden layer,
**[3:19]** so it'd be more accurate to write this as z for
**[3:23]** some hidden layer i for i equals 1 through m.
**[3:28]** But to reduce writing, I'm going to omit this [l],
**[3:33]** just to simplify the notation on this line.
**[3:35]** So given these values, what you do is compute the mean as follows.
**[3:41]** Okay, and all this is specific to some layer l, but I'm omitting the [l].
**[3:46]** And then you compute the variance using pretty much the formula you
**[3:51]** would expect and then you would take each the zis and normalize it.
**[3:56]** So you get zi normalized by subtracting off the mean and
**[4:00]** dividing by the standard deviation.
**[4:04]** For numerical stability, we usually add epsilon to the denominator like
**[4:09]** that just in case sigma squared turns out to be zero in some estimate.
**[4:14]** And so now we've taken these values z and
**[4:17]** normalized them to have mean 0 and standard unit variance.
**[4:23]** So every component of z has mean 0 and variance 1.
**[4:25]** But we don't want the hidden units to always have mean 0 and variance 1.
**[4:32]** Maybe it makes sense for hidden units to have a different distribution,
**[4:35]** so what we'll do instead is compute,
**[4:38]** I'm going to call this z tilde = gamma zi norm + beta.
**[4:48]** And here, gamma and beta are learnable parameters of your model.
**[4:58]** So we're using gradient descent, or some other algorithm, like the gradient descent
**[5:03]** of momentum, or rms proper atom, you would update the parameters gamma and beta,
**[5:08]** just as you would update the weights of your neural network.
**[5:11]** Now, notice that the effect of gamma and beta is that it allows
**[5:16]** you to set the mean of z tilde to be whatever you want it to be.
**[5:22]** In fact, if gamma equals square root sigma squared
**[5:28]** plus epsilon, so if gamma were equal to this denominator term.
**[5:33]** And if beta were equal to mu, so this value up here,
**[5:39]** then the effect of gamma z norm plus beta is
**[5:43]** that it would exactly invert this equation.
**[5:49]** So if this is true,
**[5:52]** then actually z tilde i is equal to zi.
**[5:57]** And so by an appropriate setting of the parameters gamma and beta,
**[6:02]** this normalization step, that is,
**[6:05]** these four equations is just computing essentially the identity function.
**[6:11]** But by choosing other values of gamma and beta, this allows you to make the hidden
**[6:16]** unit values have other means and variances as well.
**[6:19]** And so the way you fit this into your neural network is,
**[6:23]** whereas previously you were using these values z1, z2, and so
**[6:27]** on, you would now use z tilde i, Instead of zi for
**[6:37]** the later computations in your neural network.
**[6:39]** And you want to put back in this [l] to explicitly denote which layer it is in,
**[6:45]** you can put it back there.
**[6:46]** So the intuition I hope you'll take away from this is that we saw how
**[6:51]** normalizing the input features x can help learning in a neural network.
**[6:56]** And what batch norm does is it applies that normalization process not just
**[7:00]** to the input layer, but
**[7:01]** to the values even deep in some hidden layer in the neural network.
**[7:04]** So it will apply this type of normalization to normalize the mean and
**[7:08]** variance of some of your hidden units' values, z.
**[7:12]** But one difference between the training input and these hidden unit values is you
**[7:16]** might not want your hidden unit values be forced to have mean 0 and variance 1.
**[7:21]** For example, if you have a sigmoid activation function,
**[7:24]** you don't want your values to always be clustered here.
**[7:27]** You might want them to have a larger variance or have a mean that's different
**[7:32]** than 0, in order to better take advantage of the nonlinearity of
**[7:35]** the sigmoid function rather than have all your values be in just this linear regime.
**[7:41]** So that's why with the parameters gamma and beta,
**[7:45]** you can now make sure that your zi values have the range of values that you want.
**[7:51]** But what it does really is it then shows that your hidden units have
**[7:55]** standardized mean and variance, where the mean and
**[7:59]** variance are controlled by two explicit parameters gamma and
**[8:03]** beta which the learning algorithm can set to whatever it wants.
**[8:07]** So what it really does is it normalizes in mean and variance of these hidden
**[8:13]** unit values, really the zis, to have some fixed mean and variance.
**[8:18]** And that mean and variance could be 0 and 1, or it could be some other value,
**[8:22]** and it's controlled by these parameters gamma and beta.
**[8:26]** So I hope that gives you a sense of the mechanics of how to implement batch norm,
**[8:30]** at least for a single layer in the neural network.
**[8:32]** In the next video, I'm going to show you how to fit batch norm into a neural
**[8:36]** network, even a deep neural network, and how to make it work for
**[8:39]** the many different layers of a neural network.
**[8:41]** And after that, we'll get some more intuition about why batch norm could
**[8:45]** help you train your neural network.
**[8:47]** So in case why it works still seems a little bit mysterious, stay with me, and
**[8:51]** I think in two videos from now we'll really make that clearer.
