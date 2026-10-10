---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 3
section: Shallow Neural Network
item_title: Derivatives of Activation Functions
duration: 8 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/qcG1j/derivatives-of-activation-functions
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Derivatives of Activation Functions — Transcript

**[0:00]** When you implement back propagation for your neural network,
**[0:03]** you need to either compute the slope or the derivative of the activation functions.
**[0:07]** So, let's take a look at our choices of
**[0:09]** activation functions and how you can compute the slope of these functions.
**[0:14]** Here's the familiar Sigmoid activation function.
**[0:18]** So, for any given value of z,
**[0:20]** maybe this value of z.
**[0:22]** This function will have some slope or some derivative corresponding to,
**[0:27]** if you draw a little line there,
**[0:28]** the height over width of this lower triangle here.
**[0:32]** So, if g of z is the sigmoid function,
**[0:36]** then the slope of the function is d,
**[0:39]** dz g of z,
**[0:41]** and so we know from calculus that it is the slope of g of x at z.
**[0:48]** If you are familiar with calculus and know how to take derivatives,
**[0:53]** if you take the derivative of the Sigmoid function,
**[0:56]** it is possible to show that it is equal to this formula.
**[0:59]** Again, I'm not going to do the calculus steps,
**[1:02]** but if you are familiar with calculus,
**[1:04]** feel free to post a video and try to prove this yourself.
**[1:08]** So, this is equal to just g of z,
**[1:12]** times 1 minus g of z.
**[1:16]** So, let's just sanity check that this expression make sense.
**[1:21]** First, if z is very large,
**[1:24]** so say z is equal to 10,
**[1:25]** then g of z will be close to 1,
**[1:30]** and so the formula we have on the left tells us that d dz g of z does be close to g of z,
**[1:38]** which is equal to 1 times 1 minus 1,
**[1:43]** which is therefore very close to 0.
**[1:46]** This isn't the correct because when z is very large,
**[1:49]** the slope is close to 0.
**[1:51]** Conversely, if z is equal to minus 10,
**[1:53]** so it says well there,
**[1:55]** then g of z is close to 0.
**[1:59]** So, the formula on the left tells us d dz g of z would be close to g of z,
**[2:04]** which is 0 times 1 minus 0.
**[2:07]** So it is also very close to 0, which is correct.
**[2:10]** Finally, if z is equal to 0,
**[2:13]** then g of z is equal to one-half,
**[2:17]** that's the sigmoid function right here,
**[2:19]** and so the derivative is equal to one-half times 1 minus one-half,
**[2:26]** which is equal to one-quarter,
**[2:28]** and that actually turns out to be the correct value of
**[2:32]** the derivative or the slope of this function when z is equal to 0.
**[2:36]** Finally, just to introduce one more piece of notation,
**[2:39]** sometimes instead of writing this thing,
**[2:42]** the shorthand for the derivative is g prime of z.
**[2:46]** So, g prime of z in calculus,
**[2:48]** the little dash on top is called prime,
**[2:52]** but so g prime of z is a shorthand for the calculus for
**[2:55]** the derivative of the function of g with respect to the input variable z.
**[3:01]** Then in a neural network,
**[3:05]** we have a equals g of z,
**[3:10]** equals this, then this formula also simplifies to a times 1 minus a.
**[3:17]** So, sometimes in implementation,
**[3:19]** you might see something like g prime of z equals a times 1 minus a,
**[3:25]** and that just refers to the observation that g prime,
**[3:30]** which just means the derivative,
**[3:31]** is equal to this over here.
**[3:33]** The advantage of this formula is that if you've already computed the value for a,
**[3:38]** then by using this expression,
**[3:40]** you can very quickly compute the value for the slope for g prime as well.
**[3:44]** All right. So, that was the sigmoid activation function.
**[3:47]** Let's now look at the Tanh activation function.
**[3:51]** Similar to what we had previously,
**[3:53]** the definition of d dz g of z is
**[3:57]** the slope of g of z at a particular point of z,
**[4:04]** and if you look at the formula for the hyperbolic tangent function,
**[4:10]** and if you know calculus,
**[4:12]** you can take derivatives and show that this simplifies to
**[4:15]** this formula and using
**[4:21]** the shorthand we have previously when we call this g prime of z again.
**[4:27]** So, if you want you can sanity check that this formula makes sense.
**[4:30]** So, for example, if z is equal to 10,
**[4:33]** Tanh of z will be very close to 1.
**[4:37]** This goes from plus 1 to minus 1.
**[4:42]** Then g prime of z,
**[4:45]** according to this formula,
**[4:46]** would be about 1 minus 1 squared,
**[4:48]** so there's very close to 0.
**[4:50]** So, that was if z is very large,
**[4:52]** the slope is close to 0.
**[4:53]** Conversely, if z is very small,
**[4:56]** say z is equal to minus 10,
**[4:58]** then Tanh of z will be close to minus 1,
**[5:02]** and so g prime of z will be close to 1 minus negative 1 squared.
**[5:08]** So, it's close to 1 minus 1,
**[5:10]** which is also close to 0.
**[5:12]** Then finally, if z is equal to 0,
**[5:14]** then Tanh of z is equal to 0,
**[5:18]** and then the slope is actually equal to 1,
**[5:21]** which is actually the slope when z is equal to 0.
**[5:25]** So, just to summarize,
**[5:27]** if a is equal to g of z,
**[5:29]** so if a is equal to this Tanh of z, then the derivative,
**[5:34]** g prime of z, is equal to 1 minus a squared.
**[5:38]** So, once again, if you've already computed the value of a,
**[5:41]** you can use this formula to very quickly compute the derivative as well.
**[5:46]** Finally, here's how you compute the derivatives for
**[5:48]** the ReLU and Leaky ReLU activation functions.
**[5:51]** For the value g of z is equal to max of 0,z,
**[5:57]** so the derivative is equal to,
**[6:00]** turns out to be 0 ,
**[6:02]** if z is less than 0 and 1 if z is greater than 0.
**[6:09]** It's actually undefined, technically undefined if z is equal to exactly 0.
**[6:16]** But if you're implementing this in software,
**[6:19]** it might not be a 100 percent mathematically correct,
**[6:21]** but it'll work just fine if z is exactly a 0,
**[6:26]** if you set the derivative to be equal to 1.
**[6:28]** It always had to be 0, it doesn't matter.
**[6:32]** If you're an expert in optimization, technically,
**[6:34]** g prime then becomes what's called a sub-gradient of the activation function g of z,
**[6:39]** which is why gradient descent still works.
**[6:41]** But you can think of it as that,
**[6:43]** the chance of z being exactly 0.000000.
**[6:47]** It's so small that it almost doesn't matter where you
**[6:51]** set the derivative to be equal to when z is equal to 0.
**[6:54]** So, in practice, this is what people implement for the derivative of z.
**[6:59]** Finally, if you are training a neural network with a Leaky ReLU activation function,
**[7:04]** then g of z is going to be max of say 0.01 z, z, and so,
**[7:14]** g prime of z is equal to 0.01 if z
**[7:20]** is less than 0 and 1 if z is greater than 0.
**[7:26]** Once again, the gradient is technically not defined when z is exactly equal to 0,
**[7:31]** but if you implement a piece of code that sets
**[7:34]** the derivative or that sets g prime to either 0.01 or or to 1,
**[7:38]** either way, it doesn't really matter.
**[7:40]** When z is exactly 0, your code will work just.
**[7:42]** So, under these formulas,
**[7:44]** you should either compute the slopes or the derivatives of your activation functions.
**[7:49]** Now that we have this building block,
**[7:51]** you're ready to see how to implement gradient descent for your neural network.
**[7:55]** Let's go on to the next video to see that.
