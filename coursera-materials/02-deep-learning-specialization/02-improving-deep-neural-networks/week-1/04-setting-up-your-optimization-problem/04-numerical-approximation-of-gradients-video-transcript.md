---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 1
section: Setting Up your Optimization Problem
item_title: Numerical Approximation of Gradients
duration: 7 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/XzSSa/numerical-approximation-of-gradients
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Numerical Approximation of Gradients — Transcript

**[0:00]** When you implement back propagation you'll find that there's a test called
**[0:04]** creating checking that can really help you make sure
**[0:07]** that your implementation of back prop is correct.
**[0:10]** Because sometimes you write all these equations and you're just not 100% sure if
**[0:14]** you've got all the details right and internal back propagation.
**[0:17]** So in order to build up to gradient and checking,
**[0:21]** let's first talk about how to numerically approximate computations of gradients and
**[0:25]** in the next video, we'll talk about how you can implement
**[0:28]** gradient checking to make sure the implementation of backdrop is correct.
**[0:32]** So let's take the function f and replot it here and remember this is
**[0:37]** f of theta equals theta cubed, and let's again start off to some value of theta.
**[0:43]** Let's say theta equals 1.
**[0:44]** Now instead of just nudging theta to the right to get theta plus epsilon,
**[0:50]** we're going to nudge it to the right and
**[0:52]** nudge it to the left to get theta minus epsilon, as was theta plus epsilon.
**[0:58]** So this is 1, this is 1.01, this is 0.99 where, again,
**[1:02]** epsilon is the same as before, it is 0.01.
**[1:06]** It turns out that rather than taking this little triangle and
**[1:10]** computing the height over the width, you can get a much better estimate of
**[1:15]** the gradient if you take this point, f of theta minus epsilon and this point,
**[1:20]** and you instead compute the height over width of this bigger triangle.
**[1:26]** So for technical reasons which I won't go into, the height over width of this bigger
**[1:31]** green triangle gives you a much better approximation to the derivative at theta.
**[1:37]** And you saw it yourself, taking just this lower triangle in the upper right
**[1:41]** is as if you have two triangles, right?
**[1:43]** This one on the upper right and this one on the lower left.
**[1:47]** And you're kind of taking both of them into account
**[1:49]** by using this bigger green triangle.
**[1:54]** So rather than a one sided difference, you're taking a two sided difference.
**[1:57]** So let's work out the math.
**[1:58]** This point here is F of theta plus epsilon.
**[2:03]** This point here is F of theta minus epsilon.
**[2:07]** So the height of this big green triangle is f of theta plus epsilon
**[2:12]** minus f of theta minus epsilon.
**[2:15]** And then the width, this is 1 epsilon, this is 2 epsilon.
**[2:21]** So the width of this green triangle is 2 epsilon.
**[2:24]** So the height of the width is going to be first the height, so
**[2:28]** that's F of theta plus epsilon minus F of theta minus epsilon divided by the width.
**[2:35]** So that was 2 epsilon which we write that down here.
**[2:38]** And this should hopefully be close to g of theta.
**[2:43]** So plug in the values, remember f of theta is theta cubed.
**[2:46]** So this is theta plus epsilon is 1.01.
**[2:49]** So I take a cube of that minus 0.99 theta cube of that divided by 2 times 0.01.
**[2:58]** Feel free to pause the video and practice in the calculator.
**[3:03]** You should get that this is 3.0001.
**[3:06]** Whereas from the previous slide, we saw that g of theta,
**[3:10]** this was 3 theta squared so when theta was 1, so
**[3:14]** these two values are actually very close to each other.
**[3:18]** The approximation error is now 0.0001.
**[3:22]** Whereas on the previous slide, we've taken the one sided
**[3:27]** of difference just theta + theta + epsilon we had gotten 3.0301 and
**[3:34]** so the approximation error was 0.03 rather than 0.0001.
**[3:40]** So this two sided difference way of
**[3:44]** approximating the derivative you find that this is extremely close to 3.
**[3:48]** And so this gives you a much greater confidence that g of theta is
**[3:53]** probably a correct implementation of the derivative of F.
**[3:58]** When you use this method for grading, checking and back propagation,
**[4:01]** this turns out to run twice as slow as you were to use a one-sided defense.
**[4:06]** It turns out that in practice I think it's worth it to use this other method because
**[4:10]** it's just much more accurate.
**[4:11]** The little bit of optional theory for
**[4:13]** those of you that are a little bit more familiar of Calculus, it turns out that,
**[4:18]** and it's okay if you don't get what I'm about to say here.
**[4:22]** But it turns out that the formal definition of a derivative is for
**[4:26]** very small values of epsilon is f of theta plus epsilon minus f of theta
**[4:31]** minus epsilon over 2 epsilon.
**[4:33]** And the formal definition of derivative is in the limits of exactly
**[4:38]** that formula on the right as epsilon those as 0.
**[4:42]** And the definition of unlimited is something that you learned if you
**[4:46]** took a Calculus class but I won't go into that here.
**[4:48]** And it turns out that for a non zero value of epsilon,
**[4:52]** you can show that the error of this approximation is on the order
**[4:56]** of epsilon squared, and remember epsilon is a very small number.
**[5:00]** So if epsilon is 0.01 which it is here then epsilon squared is 0.0001.
**[5:08]** The big O notation means the error is actually some constant times this, but
**[5:12]** this is actually exactly our approximation error.
**[5:15]** So the big O constant happens to be 1.
**[5:17]** Whereas in contrast if we were to use this formula, the other one,
**[5:22]** then the error is on the order of epsilon.
**[5:25]** And again, when epsilon is a number less than 1, then epsilon is actually
**[5:29]** much bigger than epsilon squared which is why this formula here is actually
**[5:34]** much less accurate approximation than this formula on the left.
**[5:38]** Which is why when doing gradient checking, we rather use this two-sided difference
**[5:43]** when you compute f of theta plus epsilon minus f of theta minus epsilon and then
**[5:48]** divide by 2 epsilon rather than just one sided difference which is less accurate.
**[5:53]** If you didn't understand my last two comments, all of these things are on here.
**[5:57]** Don't worry about it.
**[5:58]** That's really more for those of you that are a bit more familiar with Calculus, and
**[6:02]** with numerical approximations.
**[6:04]** But the takeaway is that this two-sided difference formula is much more accurate.
**[6:08]** And so that's what we're going to use when we do gradient checking in the next video.
**[6:13]** So you've seen how by taking a two sided difference,
**[6:16]** you can numerically verify whether or not a function g, g of theta that someone
**[6:20]** else gives you is a correct implementation of the derivative of a function f.
**[6:25]** Let's now see how we can use this to verify whether or
**[6:28]** not your back propagation implementation is correct or
**[6:31]** if there might be a bug in there that you need to go and tease out
