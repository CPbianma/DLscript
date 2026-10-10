---
type: video-transcript
specialization: Machine Learning Specialization
course: "Supervised Machine Learning: Regression and Classification"
week: 1
section: Train the model with gradient descent
item_title: Gradient descent for linear regression
duration: 7 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/lgSMj/gradient-descent-for-linear-regression
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Gradient descent for linear regression — Transcript

**[0:00]** Previously, you took a look at
**[0:03]** the linear regression model and then the cost function,
**[0:07]** and then the gradient descent algorithm.
**[0:10]** In this video, we're going to pull out together and use
**[0:13]** the squared error cost function for
**[0:15]** the linear regression model with gradient descent.
**[0:19]** This will allow us to train
**[0:20]** the linear regression model to fit
**[0:23]** a straight line to achieve
**[0:24]** the training data. Let's get to it.
**[0:26]** Here's the linear regression model.
**[0:30]** To the right is the squared error cost function.
**[0:34]** Below is the gradient descent algorithm.
**[0:38]** It turns out if you calculate these derivatives,
**[0:42]** these are the terms you would get.
**[0:45]** The derivative with respect to W is this 1 over m,
**[0:51]** sum of i equals 1 through m. Then the error term,
**[0:55]** that is the difference between the predicted and
**[0:58]** the actual values times the input feature xi.
**[1:03]** The derivative with respect to b
**[1:05]** is this formula over here,
**[1:08]** which looks the same as the equation above,
**[1:10]** except that it doesn't have that xi term at the end.
**[1:15]** If you use these formulas to compute
**[1:18]** these two derivatives and
**[1:20]** implements gradient descent this way, it will work.
**[1:24]** Now, you may be wondering,
**[1:26]** where did I get these formulas from?
**[1:28]** They're derived using calculus.
**[1:31]** If you want to see the full derivation,
**[1:33]** I'll quickly run through
**[1:34]** the derivation on the next slide.
**[1:36]** But if you don't remember or aren't
**[1:38]** interested in the calculus, don't worry about it.
**[1:41]** You can skip the materials on
**[1:42]** the next slide entirely and still be able
**[1:45]** to implement gradient descent and finish
**[1:47]** this class and everything will work just fine.
**[1:50]** In this slide, which is one of
**[1:52]** the most mathematical slide of the entire specialization,
**[1:55]** and again is completely optional,
**[1:57]** we'll show you how to calculate the derivative terms.
**[2:01]** Let's start with the first term.
**[2:03]** The derivative of the cost function J with
**[2:06]** respect to w. We'll start by plugging in
**[2:10]** the definition of the cost function J. J of WP is this.
**[2:18]** 1 over 2m times this sum of the squared error terms.
**[2:25]** Now remember also that f of wb
**[2:30]** of X^i is equal to this term over here,
**[2:36]** which is WX^i plus b.
**[2:41]** What we would like to do is compute the derivative,
**[2:45]** also called the partial derivative with respect to
**[2:49]** w of this equation right here on the right.
**[2:54]** If you taken a calculus class before,
**[2:57]** and again is totally fine if you haven't,
**[2:59]** you may know that by the rules of calculus,
**[3:02]** the derivative is equal to this term over here.
**[3:06]** Which is why the two here and two here cancel out,
**[3:12]** leaving us with this equation
**[3:15]** that you saw on the previous slide.
**[3:18]** This is why we had to find the cost function with the
**[3:23]** 1.5 earlier this week
**[3:25]** is because it makes the partial derivative neater.
**[3:29]** It cancels out the two that appears
**[3:31]** from computing the derivative.
**[3:33]** For the other derivative with respect to b,
**[3:38]** this is quite similar.
**[3:39]** I can write it out like this, and once again,
**[3:43]** plugging the definition of f
**[3:45]** of X^i, giving this equation.
**[3:49]** By the rules of calculus,
**[3:52]** this is equal to this
**[3:54]** where there's no X^i anymore at the end.
**[3:58]** The 2's cancel one small and you end up with
**[4:02]** this expression for the derivative with respect to b.
**[4:07]** Now you have these two expressions for the derivatives.
**[4:11]** You can plug them into the gradient descent algorithm.
**[4:15]** Here's the gradient descent algorithm
**[4:18]** for linear regression.
**[4:20]** You repeatedly carry out these updates
**[4:23]** to w and b until convergence.
**[4:26]** Remember that this f of x is a linear regression model,
**[4:30]** so as equal to w times x plus b.
**[4:35]** This expression here is
**[4:37]** the derivative of the cost function with respect to
**[4:40]** w. This expression is
**[4:43]** the derivative of the cost function with respect to b.
**[4:47]** Just as a reminder,
**[4:49]** you want to update w and b simultaneously on each step.
**[4:54]** Now, let's get familiar with how gradient descent works.
**[4:58]** One the shoe we saw with gradient descent is that it can
**[5:01]** lead to a local minimum instead of a global minimum.
**[5:05]** Whether global minimum means the point that has
**[5:08]** the lowest possible value for the cost function
**[5:10]** J of all possible points.
**[5:13]** You may recall this surface plot that looks like
**[5:16]** an outdoor park with a few hills with
**[5:18]** the process and the birds as a relaxing Hobo Hill.
**[5:21]** This function has more than one local minimum.
**[5:24]** Remember, depending on where
**[5:27]** you initialize the parameters w and b,
**[5:29]** you can end up at different local minima.
**[5:32]** You can end up here,
**[5:34]** or you can end up here.
**[5:36]** But it turns out when you're using
**[5:38]** a squared error cost function with linear regression,
**[5:41]** the cost function does not and will
**[5:44]** never have multiple local minima.
**[5:47]** It has a single global minimum
**[5:49]** because of this bowl-shape.
**[5:51]** The technical term for this is that
**[5:54]** this cost function is a convex function.
**[5:58]** Informally, a convex function
**[6:01]** is of bowl-shaped function and
**[6:03]** it cannot have any local minima
**[6:05]** other than the single global minimum.
**[6:09]** When you implement gradient descent on a convex function,
**[6:13]** one nice property is that so
**[6:16]** long as you're learning rate is chosen appropriately,
**[6:19]** it will always converge to the global minimum.
**[6:22]** Congratulations, you now know how to
**[6:24]** implement gradient descent for linear regression.
**[6:27]** We have just one last video for this week.
**[6:30]** That video, we'll see this algorithm in action.
**[6:33]** Let's go to that last video.
