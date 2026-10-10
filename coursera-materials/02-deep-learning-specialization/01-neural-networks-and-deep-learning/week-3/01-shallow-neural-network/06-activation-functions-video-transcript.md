---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 3
section: Shallow Neural Network
item_title: Activation Functions
duration: 11 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/4dDC1/activation-functions
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Activation Functions — Transcript

**[0:00]** When you build your neural network, one of the choices you get to make is what
**[0:04]** activation function to use in the hidden layers
**[0:07]** as well as at the output units of your neural network.
**[0:10]** So far, we've just been using the sigmoid activation function, but
**[0:14]** sometimes other choices can work much better.
**[0:17]** Let's take a look at some of the options.
**[0:20]** In the forward propagation steps for the neural network,
**[0:23]** we had these two steps where we use the sigmoid function here.
**[0:27]** So that sigmoid is called an activation function.
**[0:31]** And here's the familiar sigmoid function,
**[0:36]** a = 1/1 + e to -z.
**[0:39]** So in the more general case,
**[0:43]** we can have a different function g(z).
**[0:49]** Which I'm going to write here where g could be a nonlinear function
**[0:53]** that may not be the sigmoid function.
**[0:56]** So for example, the sigmoid function goes between zero and one.
**[1:02]** An activation function that almost always works better than the sigmoid
**[1:06]** function is the tangent function or the hyperbolic tangent function.
**[1:12]** So this is z, this is a, this is a = tan h(z).
**[1:19]** And this goes between +1 and -1.
**[1:24]** The formula for the tan h function is e to
**[1:30]** the z minus e to-z over their sum.
**[1:36]** And it's actually mathematically a shifted version of the sigmoid function.
**[1:42]** So as a sigmoid function just like that but shifted so
**[1:47]** that it now crosses the zero zero point on the scale.
**[1:51]** So it goes between minus one and plus one.
**[1:53]** And it turns out that for hidden units,
**[1:59]** if you let the function g(z) be equal to tan h(z).
**[2:07]** This almost always works better than the sigmoid function because with values
**[2:12]** between plus one and minus one, the mean of the activations that come out
**[2:17]** of your hidden layer are closer to having a zero mean.
**[2:20]** And so just as sometimes when you train a learning algorithm,
**[2:24]** you might center the data and
**[2:26]** have your data have zero mean using a tan h instead of a sigmoid function.
**[2:31]** Kind of has the effect of centering your data so
**[2:34]** that the mean of your data is close to zero rather than maybe 0.5.
**[2:39]** And this actually makes learning for the next layer a little bit easier.
**[2:43]** We'll say more about this in the second course when we talk about optimization
**[2:46]** algorithms as well.
**[2:47]** But one takeaway is that I pretty much never use
**[2:51]** the sigmoid activation function anymore.
**[2:54]** The tan h function is almost always strictly superior.
**[2:58]** The one exception is for the output layer because if y is either zero or
**[3:04]** one, then it makes sense for y hat to be a number that you want
**[3:09]** to output that's between zero and one rather than between -1 and 1.
**[3:15]** So the one exception where I would use the sigmoid activation function is when
**[3:20]** you're using binary classification.
**[3:23]** In which case you might use the sigmoid activation function for the upper layer.
**[3:28]** So g(z2) here is equal to sigmoid of z2.
**[3:34]** And so what you see in this example is where you might have
**[3:39]** a tan h activation function for the hidden layer and sigmoid for the output layer.
**[3:47]** So the activation functions can be different for different layers.
**[3:50]** And sometimes to denote that the activation functions are different for
**[3:55]** different layers,
**[3:56]** we might use these square brackets superscripts as well to indicate that
**[4:00]** gf square bracket one may be different than gf square bracket two, right.
**[4:05]** Again, square bracket one superscript refers to this layer and
**[4:09]** superscript square bracket two refers to the output layer.
**[4:12]** Now, one of the downsides of both the sigmoid function and
**[4:16]** the tan h function is that if z is either very large or very small,
**[4:21]** then the gradient of the derivative of the slope of this function becomes very small.
**[4:26]** So if z is very large or z is very small, the slope of the function either ends
**[4:31]** up being close to zero and so this can slow down gradient descent.
**[4:36]** So one other choice that is very popular in machine learning is
**[4:40]** what's called the rectified linear unit.
**[4:44]** So the value function looks like this and
**[4:51]** the formula is a = max(0,z).
**[4:56]** So the derivative is one so long as z is positive and
**[5:01]** derivative or the slope is zero when z is negative.
**[5:05]** If you're implementing this,
**[5:07]** technically the derivative when z is exactly zero is not well defined.
**[5:11]** But when you implement this in the computer,
**[5:14]** the odds that you get exactly z equals 000000000000 is very small.
**[5:20]** So you don't need to worry about it.
**[5:22]** In practice, you could pretend a derivative when z is equal to zero,
**[5:27]** you can pretend is either one or zero.
**[5:29]** And you can work just fine.
**[5:31]** So the fact is not differentiable.
**[5:33]** The fact that, so here's some rules of thumb for choosing activation functions.
**[5:38]** If your output is zero one value, if you're using binary classification,
**[5:43]** then the sigmoid activation function is very natural choice for the output layer.
**[5:48]** And then for all other units value or
**[5:53]** the rectified linear unit is increasingly
**[5:59]** the default choice of activation function.
**[6:06]** So if you're not sure what to use for your hidden layer, I would just use
**[6:11]** the value activation function, is what you see most people using these days.
**[6:16]** Although sometimes people also use the tan h activation function.
**[6:21]** One disadvantage of the value is that the derivative is equal to zero when z
**[6:26]** is negative.
**[6:27]** In practice this works just fine.
**[6:29]** But there is another version of the value called the Leaky ReLU.
**[6:33]** We'll give you the formula on the next slide but instead of it being zero
**[6:37]** when z is negative, it just takes a slight slope like so.
**[6:41]** So this is called Leaky ReLU.
**[6:44]** This usually works better than the value activation function.
**[6:49]** Although, it's just not used as much in practice.
**[6:53]** Either one should be fine.
**[6:54]** Although, if you had to pick one, I usually just use the value.
**[6:58]** And the advantage of both the value and the Leaky ReLU is that for
**[7:02]** a lot of the space of z, the derivative of the activation function,
**[7:07]** the slope of the activation function is very different from zero.
**[7:11]** And so in practice, using the value activation function,
**[7:15]** your neural network will often learn much faster than when using the tan h or
**[7:19]** the sigmoid activation function.
**[7:21]** And the main reason is that there's less of this effect of the slope of
**[7:26]** the function going to zero, which slows down learning.
**[7:29]** And I know that for half of the range of z, the slope for value is zero.
**[7:34]** But in practice, enough of your hidden units will have z greater than zero.
**[7:39]** So learning can still be quite fast for most training examples.
**[7:42]** So let's just quickly recap the pros and cons of different activation functions.
**[7:47]** Here's the sigmoid activation function.
**[7:49]** I would say never use this except for the output layer if you're doing binomial
**[7:53]** classification or maybe almost never use this.
**[7:56]** And the reason I almost never use this is because the tan h is
**[8:01]** pretty much strictly superior.
**[8:04]** So the tan h activation function is this.
**[8:10]** And then the default,
**[8:12]** the most commonly used activation function is the ReLU, which is this.
**[8:18]** So if you're not sure what else to use, use this one.
**[8:20]** And maybe, feel free also to try
**[8:25]** the Leaky ReLU where might be
**[8:30]** 0.01(z,z), right?
**[8:34]** So a is the max of 0.1 times z and z.
**[8:39]** So that gives you this bend in the function.
**[8:42]** And you might say, why is that constant 0.01?
**[8:48]** Well, you can also make that another parameter of the learning algorithm.
**[8:53]** And some people say that works even better, but how they see people do that.
**[8:56]** So, but if you feel like trying it in your application, please feel free to do so.
**[9:01]** And you can just see how it works and how well it works, and
**[9:05]** stick with it if it gives you a good result.
**[9:07]** So I hope that gives you a sense of some of the choices of activation functions
**[9:11]** you can use in your neural network.
**[9:13]** One of the things we'll see in deep learning is that you often have a lot of
**[9:16]** different choices in how you build your neural network.
**[9:19]** Ranging from a number of hidden units to the choices activation function,
**[9:23]** to how you initialize the ways which we'll see later.
**[9:26]** A lot of choices like that.
**[9:28]** And it turns out that it is sometimes difficult to get good guidelines for
**[9:32]** exactly what will work best for your problem.
**[9:35]** So throughout these courses, I'll keep on giving you a sense of what I
**[9:38]** see in the industry in terms of what's more or less popular.
**[9:41]** But for your application with your applications, idiosyncrasies is actually
**[9:45]** very difficult to know in advance exactly what will work best.
**[9:49]** So common piece of advice would be, if you're not sure which one of these
**[9:52]** activation functions work best, try them all.
**[9:55]** And evaluate on like a holdout validation set or like a development set,
**[10:00]** which we'll talk about later.
**[10:02]** And see which one works better and then go of that.
**[10:05]** And I think that by testing these different choices for
**[10:08]** your application, you'd be better at future proofing your neural
**[10:13]** network architecture against the idiosyncracies problems.
**[10:17]** As well as evolutions of the algorithms rather than,
**[10:21]** if I were to tell you always use a value activation and don't use anything else.
**[10:26]** That just may or may not apply for whatever problem you end up working on.
**[10:30]** Either in the near future or in the distant future.
**[10:33]** All right, so, that was choice of activation functions and
**[10:36]** you see the most popular activation functions.
**[10:39]** There's one other question that sometimes you can ask which is,
**[10:43]** why do you even need to use an activation function at all?
**[10:46]** Why not just do away with that?
**[10:48]** So, let's talk about that in the next video where you see why neural
**[10:52]** networks do need some sort of non linear activation function.
