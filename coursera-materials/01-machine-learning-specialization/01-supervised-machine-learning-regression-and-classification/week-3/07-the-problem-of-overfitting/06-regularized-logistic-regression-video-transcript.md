---
type: video-transcript
specialization: Machine Learning Specialization
course: "Supervised Machine Learning: Regression and Classification"
week: 3
section: The problem of overfitting
item_title: Regularized logistic regression
duration: 6 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/cAxpF/regularized-logistic-regression
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Regularized logistic regression — Transcript

**[0:00]** In this video, you see how to
**[0:03]** implement regularized logistic regression.
**[0:05]** Just as the gradient update for logistic regression has
**[0:09]** seemed surprisingly similar to
**[0:11]** the gradient update for linear regression,
**[0:13]** you find that the gradient descent update
**[0:15]** for regularized logistic regression will
**[0:17]** also look similar to
**[0:18]** the update for regularized linear regression.
**[0:21]** Let's take a look. Here is the idea.
**[0:23]** We saw earlier that
**[0:25]** logistic regression can be prone to overfitting
**[0:27]** if you fit it with very high order
**[0:29]** polynomial features like this.
**[0:32]** Here, z is a high order polynomial that gets passed into
**[0:37]** the sigmoid function like so to compute f. In particular,
**[0:42]** you can end up with a decision boundary that is
**[0:45]** overly complex and overfits as training set.
**[0:49]** More generally, when you train
**[0:52]** logistic regression with a lot of features,
**[0:54]** whether polynomial features or some other features,
**[0:58]** there could be a higher risk of overfitting.
**[1:01]** This was the cost function for logistic regression.
**[1:05]** If you want to modify it to use regularization,
**[1:09]** all you need to do is add to it the following term.
**[1:13]** Let's add lambda to regularization parameter over
**[1:16]** 2m times the sum from j equals 1 through n,
**[1:21]** where n is the number of features as usual of wj squared.
**[1:26]** When you minimize this cost function
**[1:28]** as a function of w and b,
**[1:30]** it has the effect of penalizing parameters w_1,
**[1:34]** w_2 through w_n,
**[1:36]** and preventing them from being too large.
**[1:39]** If you do this, then even though you're fitting
**[1:42]** a high order polynomial with a lot of parameters,
**[1:45]** you still get a decision boundary that looks like this.
**[1:49]** Something that looks more reasonable
**[1:51]** for separating positive and negative examples
**[1:54]** while also generalizing hopefully
**[1:56]** to new examples not in the training set.
**[1:59]** When using regularization,
**[2:02]** even when you have a lot of features.
**[2:04]** How can you actually implement this?
**[2:07]** How can you actually minimize this cost function j of
**[2:09]** wb that includes the regularization term?
**[2:13]** Well, let's use gradient descent as before.
**[2:17]** Here's a cost function that you want to minimize.
**[2:21]** To implement gradient descent, as before,
**[2:24]** we'll carry out the following simultaneous updates
**[2:27]** over wj and b.
**[2:30]** These are the usual update rules for gradient descent.
**[2:34]** Just like regularized linear regression,
**[2:37]** when you compute where there are these derivative terms,
**[2:41]** the only thing that changes now is that
**[2:44]** the derivative respect to wj gets this additional term,
**[2:49]** lambda over m times wj added here at the end.
**[2:54]** Again, it looks a lot like
**[2:56]** the update for regularized linear regression.
**[2:59]** In fact is the exact same equation,
**[3:02]** except for the fact that the definition of
**[3:04]** f is now no longer the linear function,
**[3:07]** it is the logistic function applied to z.
**[3:11]** Similar to linear regression,
**[3:13]** we will regularize only the parameters w, j,
**[3:16]** but not the parameter b,
**[3:19]** which is why there's no change
**[3:20]** the update you will make for b.
**[3:23]** In the final optional lab of
**[3:26]** this week, you revisit overfitting.
**[3:29]** In the interactive plot in the optional lab,
**[3:33]** you can now choose to regularize your models,
**[3:36]** both regression and classification,
**[3:38]** by enabling regularization during
**[3:41]** gradient descent by selecting a value for lambda.
**[3:44]** Please take a look at the code for
**[3:46]** implementing regularized
**[3:48]** logistic regression in particular,
**[3:50]** because you'll implement this in
**[3:51]** practice lab yourself at the end of this week.
**[3:55]** Now you know how to implement
**[3:58]** regularized logistic regression.
**[4:00]** When I walk around Silicon Valley,
**[4:03]** there are many engineers using machine
**[4:04]** learning to create a ton of value,
**[4:06]** sometimes making a lot of money for the companies.
**[4:09]** I know you've only been studying
**[4:11]** this stuff for a few weeks but
**[4:14]** if you understand and can
**[4:15]** apply linear regression and logistic regression,
**[4:18]** that's actually all you need to create
**[4:20]** some very valuable applications.
**[4:23]** While the specific learning outcomes
**[4:25]** you use are important,
**[4:26]** knowing things like when and how to reduce
**[4:29]** overfitting turns out to be one of
**[4:31]** the very valuable skills in the real world as well.
**[4:34]** I want to say congratulations
**[4:37]** on how far you've come and I want
**[4:39]** to say great job for getting through
**[4:41]** all the way to the end of this video.
**[4:44]** I hope you also work through
**[4:46]** the practice labs and quizzes.
**[4:48]** Having said that, there are still
**[4:50]** many more exciting things to learn.
**[4:53]** In the second course of this specialization,
**[4:55]** you'll learn about neural networks,
**[4:57]** also called deep learning algorithms.
**[5:00]** Neural networks are responsible for
**[5:02]** many of the latest breakthroughs in the eye today,
**[5:04]** from practical speech recognition to computers
**[5:07]** accurately recognizing objects and
**[5:09]** images, to self-driving cars.
**[5:11]** The way neural network gets built
**[5:13]** actually uses a lot of what you've already learned,
**[5:16]** like cost functions,
**[5:18]** and gradient descent, and sigmoid functions.
**[5:20]** Again, congratulations on reaching
**[5:23]** the end of this third and final week of Course 1.
**[5:26]** I hope you have [inaudible] and I will see you
**[5:29]** in next week's material on neural networks.
