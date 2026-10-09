---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 1
section: Regularizing your Neural Network
item_title: Why Regularization Reduces Overfitting?
duration: 7 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/T6OJj/why-regularization-reduces-overfitting
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Why Regularization Reduces Overfitting? — Transcript

**[0:00]** Why does regularization help with overfitting?
**[0:03]** Why does it help with reducing variance problems?
**[0:05]** Let's go through a couple examples to gain some intuition about how it works.
**[0:10]** So, recall that our high bias, high variance,
**[0:16]** and "just write" pictures from our earlier video had looked something like this.
**[0:25]** Now, let's see a fitting large and deep neural network.
**[0:27]** I know I haven't drawn this one too large or too deep,
**[0:30]** but let's see if [INAUDIBLE] some neural network and is currently overfitting.
**[0:34]** So you have some cost function, write J of W,
**[0:39]** b equals sum of the losses,
**[0:44]** like so, right?
**[0:49]** And so what we did for regularization was add this extra term that
**[0:56]** penalizes the weight matrices from being too large.
**[1:02]** And we said that was the Frobenius norm.
**[1:04]** So why is it that shrinking the L2 norm, or
**[1:08]** the Frobenius norm with the parameters might cause less overfitting?
**[1:12]** One piece of intuition is that if you, you know,
**[1:14]** crank your regularization lambda to be really, really big,
**[1:17]** that'll be really incentivized to set
**[1:20]** the weight matrices, W, to be reasonably close to zero.
**[1:24]** So one piece of intuition is maybe it'll set the weight to be so close to zero for
**[1:30]** a lot of hidden units that's basically zeroing
**[1:33]** out a lot of the impact of these hidden units.
**[1:36]** And if that's the case, then,
**[1:37]** you know, this much simplified neural network becomes a much smaller neural network.
**[1:44]** In fact, it is almost like a logistic regression unit,
**[1:48]** you know, but stacked multiple layers deep.
**[1:50]** And so that will take you from
**[1:51]** this overfitting case, much closer to the left, to the other high bias case.
**[1:57]** But, hopefully, there'll be an intermediate value of lambda that
**[2:00]** results in the result closer to this "just right" case in the middle.
**[2:04]** But the intuition is that by cranking up lambda to be
**[2:07]** really big, it'll set W close to zero,
**[2:10]** which, in practice, this isn't actually what happens.
**[2:13]** We can think of it as zeroing out, or at least reducing,
**[2:17]** the impact of a lot of the hidden units, so you end up
**[2:19]** with what might feel like a simpler network,
**[2:21]** that gets closer and closer as if you're just using logistic regression.
**[2:25]** The intuition of completely zeroing out a bunch of hidden units isn't quite right.
**[2:31]** It turns out that what actually happens is it'll still use all the hidden units,
**[2:35]** but each of them would just have a much smaller effect.
**[2:37]** But you do end up with a simpler network, and as
**[2:41]** if you have a smaller network that is, therefore, less prone to overfitting.
**[2:45]** So I'm not sure if this intuition helps, but
**[2:47]** when you implement regularization in the program exercise,
**[2:50]** you actually see some of these variance reduction results yourself.
**[2:55]** Here's another attempt at additional intuition
**[2:57]** for why regularization helps prevent overfitting.
**[3:01]** And for this, I'm going to assume that we're using
**[3:04]** the tan h activation function, which looks like this.
**[3:08]** This is g of z equals tan h of z.
**[3:13]** So if that's the case,
**[3:15]** notice that so long as z is quite small,
**[3:19]** so if z takes on only a smallish range of parameters,
**[3:23]** maybe around here, then you're just using the linear regime of the tan h function,
**[3:28]** is only if z is allowed to wander, you know, to larger values or smaller values like so,
**[3:34]** that the activation function starts to become less linear.
**[3:37]** So the intuition you might take away from this is that if lambda,
**[3:40]** the regularization parameter is large,
**[3:42]** then you have that your parameters will be relatively small,
**[3:46]** because they are penalized being large in the cost function.
**[3:51]** And so if the weights, W, are small, then because z is
**[3:56]** equal to W, right, and then technically, it's plus b.
**[4:02]** But if W tends to be very small,
**[4:04]** then z will also be relatively small.
**[4:07]** And in particular, if z ends up taking relatively small values,
**[4:10]** just in this little range,
**[4:12]** then g of z will be roughly linear.
**[4:16]** So it's as if every layer will be roughly linear,
**[4:22]** as if it is just linear regression.
**[4:24]** And we saw in course one that if every layer
**[4:27]** is linear, then your whole network is just a linear network.
**[4:31]** And so even a very deep network,
**[4:33]** with a deep network with a linear activation function
**[4:35]** is, at the end of the day, only able to compute a linear function.
**[4:39]** So it's not able to, you know, fit those very, very complicated decision,
**[4:43]** very non-linear decision boundaries that allow it to, you know, really
**[4:49]** overfit, right, to data sets, like we saw on
**[4:52]** the overfitting high variance case on the previous slide, ok?
**[4:57]** So just to summarize,
**[4:59]** if the regularization parameters are very large,
**[5:01]** the parameters W very small,
**[5:03]** so z will be relatively small,
**[5:06]** kind of ignoring the effects of b for now,
**[5:08]** but so z is relatively, so z will be relatively small, or
**[5:12]** really, I should say it takes on a small range of values.
**[5:16]** And so the activation function if it's tan h,
**[5:19]** say, will be relatively linear.
**[5:21]** And so your whole neural network will be computing something not too far from
**[5:25]** a big linear function, which is therefore, pretty
**[5:28]** simple function, rather than a very complex highly non-linear function.
**[5:32]** And so, is also much less able to overfit, ok?
**[5:34]** And again, when you implement regularization for yourself in the program exercise,
**[5:38]** you'll be able to see some of these effects yourself.
**[5:41]** Before wrapping up our def discussion on regularization,
**[5:45]** I just want to give you one implementational tip,
**[5:48]** which is that, when implementing regularization,
**[5:52]** we took our definition of the cost function J and we actually modified
**[5:58]** it by adding this extra term that penalizes the weights being too large.
**[6:05]** And so if you implement gradient descent,
**[6:09]** one of the steps to debug gradient descent is to plot the cost function J, as a function
**[6:18]** of the number of elevations of gradient descent, and you want to see that
**[6:22]** the cost function J decreases monotonically after every elevation of gradient descent.
**[6:27]** And if you're implementing regularization,
**[6:30]** then please remember that J now has this new definition.
**[6:35]** If you plot the old definition of J,
**[6:37]** just this first term,
**[6:39]** then you might not see a decrease monotonically.
**[6:42]** So to debug gradient descent, make sure that you're plotting, you know,
**[6:45]** this new definition of J that includes this second term as well.
**[6:49]** Otherwise, you might not see J decrease monotonically on every single elevation.
**[6:54]** So that's it for L2 regularization, which is actually
**[6:57]** a regularization technique that I use the most in training deep learning models.
**[7:01]** In deep learning, there is another sometimes used regularization technique
**[7:05]** called dropout regularization.
**[7:07]** Let's take a look at that in the next video.
