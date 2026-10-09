---
type: video-transcript
specialization: Machine Learning Specialization
course: "Supervised Machine Learning: Regression and Classification"
week: 3
section: Gradient descent for logistic regression
item_title: Gradient Descent Implementation
duration: 7 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/Ha1RP/gradient-descent-implementation
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Gradient Descent Implementation — Transcript

**[0:01]** To fit the parameters of a logistic regression model,
**[0:05]** we're going to try to find
**[0:06]** the values of the parameters w and b
**[0:08]** that minimize the cost function J of w and b,
**[0:12]** and we'll again apply gradient descent to do this.
**[0:15]** Let's take a look at how.
**[0:18]** In this video we'll focus on how to find
**[0:21]** a good choice of the parameters w and b.
**[0:24]** After you've done so,
**[0:26]** if you give the model a new input, x,
**[0:29]** say a new patients at
**[0:31]** the hospital with a certain tumor size and age,
**[0:34]** then these are diagnosis.
**[0:35]** The model can then make a prediction,
**[0:38]** or it can try to estimate
**[0:41]** the probability that the label y is one.
**[0:45]** The average you can use to minimize
**[0:48]** the cost function is gradient descent.
**[0:50]** Here again is the cost function.
**[0:54]** If you want to minimize
**[0:56]** the cost j as a function of w and b,
**[0:59]** well, here's the usual gradient descent algorithm,
**[1:03]** where you repeatedly update
**[1:05]** each parameter as the 0 value minus Alpha,
**[1:09]** the learning rate times this derivative term.
**[1:14]** Let's take a look at the derivative
**[1:17]** of j with respect to w_j.
**[1:19]** This term up on top here, where as usual,
**[1:23]** j goes from one through n,
**[1:25]** where n is the number of features.
**[1:28]** If someone were to apply the rules of calculus,
**[1:31]** you can show that the derivative with respect to w_j of
**[1:35]** the cost function capital J is
**[1:38]** equal to this expression over here,
**[1:41]** is 1 over m times the sum
**[1:44]** from 1 through m of this error term.
**[1:48]** That is f minus the label y times x_j.
**[1:56]** Here are just x I j is
**[1:58]** the j feature of training example i.
**[2:02]** Now let's also look at the derivative of
**[2:05]** j with respect to the parameter b.
**[2:08]** It turns out to be this expression over here.
**[2:12]** It's quite similar to the expression above,
**[2:15]** except that it is not multiplied by
**[2:17]** this x superscript i subscript j at the end.
**[2:22]** Just as a reminder,
**[2:24]** similar to what you saw for linear regression,
**[2:26]** the way to carry out these updates is
**[2:28]** to use simultaneous updates,
**[2:30]** meaning that you first
**[2:32]** compute the right-hand side for all of
**[2:34]** these updates and then simultaneously
**[2:37]** overwrite all the values on the left at the same time.
**[2:42]** Let me take these derivative expressions
**[2:45]** here and plug them into these terms here.
**[2:50]** This gives you gradient descent for logistic regression.
**[2:56]** Now, one funny thing you might be
**[2:59]** wondering is, that's weird.
**[3:01]** These two equations look
**[3:03]** exactly like the average we had come up
**[3:05]** with previously for linear regression
**[3:08]** so you might be wondering,
**[3:09]** is linear regression actually
**[3:11]** secretly the same as logistic regression?
**[3:14]** Well, even though these equations look the same,
**[3:18]** the reason that this is not linear regression is because
**[3:22]** the definition for the function f of x has changed.
**[3:26]** In linear regression,
**[3:28]** f of x is,
**[3:29]** this is wx plus b.
**[3:31]** But in logistic regression,
**[3:33]** f of x is defined to be
**[3:35]** the sigmoid function applied to wx plus b.
**[3:39]** Although the algorithm written looked the
**[3:42]** same for both linear regression and logistic regression,
**[3:46]** actually they're two very different algorithms
**[3:49]** because the definition for f of x is not the same.
**[3:52]** When we talked about gradient descent
**[3:55]** for linear regression previously,
**[3:57]** you saw how you can monitor
**[3:59]** a gradient descent to make sure it converges.
**[4:02]** You can just apply the same method for
**[4:05]** logistic regression to make sure it also converges.
**[4:09]** I've written out these updates as if you're updating
**[4:13]** the parameters w_j one parameter at a time.
**[4:19]** Similar to the discussion
**[4:23]** on vectorized implementations of linear regression,
**[4:26]** you can also use vectorization to make
**[4:29]** gradient descent run faster for logistic regression.
**[4:33]** I won't dive into the details of
**[4:35]** the vectorized implementation in this video.
**[4:37]** But you can also learn more about it and
**[4:40]** see the code in the optional labs.
**[4:42]** Now you know how to implement
**[4:45]** gradient descent for logistic regression.
**[4:48]** You might also remember feature
**[4:50]** scaling when we were using linear regression.
**[4:54]** Where you saw how feature scaling,
**[4:56]** that is scaling all the features to
**[4:58]** take on similar ranges of values,
**[4:59]** say between negative 1 and plus 1,
**[5:02]** how they can help gradient descent to converge faster.
**[5:06]** Feature scaling applied the same way
**[5:08]** to scale the different features to take on
**[5:10]** similar ranges of values can also speed
**[5:12]** up gradient descent for logistic regression.
**[5:15]** In the upcoming optional lab,
**[5:18]** you also see how the gradient
**[5:21]** for the logistic regression can be calculated in code.
**[5:25]** This will be useful to look at because you
**[5:28]** also implement this in
**[5:29]** the practice lab at the end of this week.
**[5:32]** After you run gradient descent in this lab,
**[5:35]** there'll be a nice set of
**[5:36]** animated plots that show gradient descent in action.
**[5:40]** You see the sigmoid function,
**[5:41]** the contour plot of the cost,
**[5:44]** the 3D surface plot of the cost,
**[5:46]** and the learning curve or
**[5:47]** evolve as gradient descent runs.
**[5:50]** There will be another optional lab after that,
**[5:53]** which is short and sweet,
**[5:54]** but also very useful
**[5:55]** because they're showing you how to use
**[5:57]** the popular scikit-learn library to
**[6:00]** train the logistic regression model for classification.
**[6:04]** Many machine learning practitioners in
**[6:07]** many companies today use
**[6:08]** scikit-learn regularly as part of their job.
**[6:11]** I hope you check out the scikit-learn
**[6:13]** function as well and
**[6:15]** take a look at how that is used. That's it.
**[6:18]** You should now know how to implement logistic regression.
**[6:22]** This is a very powerful and very
**[6:24]** widely used learning algorithm
**[6:26]** and you now know how to get it
**[6:27]** to work yourself. Congratulations.
