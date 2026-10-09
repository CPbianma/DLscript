---
type: video-transcript
specialization: Machine Learning Specialization
course: Supervised Machine Learning: Regression and Classification
week: 2
section: Multiple linear regression
item_title: Gradient descent for multiple linear regression
duration: 8 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/ltMMp/gradient-descent-for-multiple-linear-regression
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Gradient descent for multiple linear regression — Transcript

**[0:01]** You've learned about gradient descents about
**[0:05]** multiple linear regression and also vectorization.
**[0:08]** Let's put it all together to
**[0:09]** implement gradient descent for
**[0:11]** multiple linear regression with
**[0:13]** vectorization. This would be cool.
**[0:15]** Let's quickly review what
**[0:16]** multiple linear regression look like.
**[0:18]** Using our previous notation,
**[0:20]** let's see how you can write it more
**[0:22]** succinctly using vector notation.
**[0:24]** We have parameters w_1 to w_n as well as b.
**[0:29]** But instead of thinking of
**[0:30]** w_1 to w_n as separate numbers,
**[0:34]** that is separate parameters,
**[0:35]** let's start to collect all of the w's into
**[0:38]** a vector w so that now w is
**[0:41]** a vector of length n.
**[0:44]** We're just going to think of the parameters of
**[0:46]** this model as a vector w,
**[0:49]** as well as b,
**[0:50]** where b is still a number same as before.
**[0:53]** Whereas before we had to find
**[0:56]** multiple linear regression like this,
**[0:58]** now using vector notation,
**[1:01]** we can write the model as f_w,
**[1:03]** b of x equals the vector
**[1:06]** w dot product with the vector x plus b.
**[1:10]** Remember that this dot here means.product.
**[1:14]** Our cost function can be defined as J
**[1:17]** of w_1 through w_n, b.
**[1:21]** But instead of just thinking of J as a function of these
**[1:24]** and different parameters w_j as well as b,
**[1:28]** we're going to write J as a function of
**[1:32]** parameter vector w and the number b.
**[1:36]** This w_1 through w_n is replaced by this vector W and
**[1:43]** J now takes this input of
**[1:45]** vector w and a number b and returns a number.
**[1:49]** Here's what gradient descent looks like.
**[1:52]** We're going to repeatedly update each parameter w_j to
**[1:56]** be w_j minus Alpha times the derivative of the cost J,
**[2:00]** where J has parameters w_1 through w_n and b.
**[2:06]** Once again, we just write this as J
**[2:09]** of vector w and number b.
**[2:13]** Let's see what this looks like when you implement
**[2:15]** gradient descent and in particular,
**[2:17]** let's take a look at the derivative term.
**[2:20]** We'll see that gradient descent becomes just a little bit
**[2:24]** different with multiple features
**[2:26]** compared to just one feature.
**[2:28]** Here's what we had when we had
**[2:30]** gradient descent with one feature.
**[2:33]** We had an update rule for w and
**[2:36]** a separate update rule for b. Hopefully,
**[2:39]** these look familiar to you.
**[2:41]** This term here is the derivative of the cost function J
**[2:46]** with respect to the parameter w. Similarly,
**[2:50]** we have an update rule for parameter b,
**[2:53]** with univariate regression, we had only one feature.
**[2:57]** We call that feature xi without any subscript.
**[3:02]** Now, here's a new notation for where we have n features,
**[3:06]** where n is two or more.
**[3:08]** We get this update rule for gradient descent.
**[3:12]** Update w_1 to be w_1 minus
**[3:15]** Alpha times this expression here
**[3:18]** and this formula is actually
**[3:21]** the derivative of the cost J with respect to w_1.
**[3:26]** The formula for the derivative of
**[3:29]** J with respect to w_1 on
**[3:31]** the right looks very similar to
**[3:32]** the case of one feature on the left.
**[3:35]** The error term still takes
**[3:37]** a prediction f of x minus the target y.
**[3:41]** One difference is that w and x are now vectors
**[3:46]** and just as w on the left
**[3:48]** has now become w_1 here on the right,
**[3:52]** xi here on the left is now instead xi _1 here on
**[3:57]** the right and this is just for J equals 1.
**[4:03]** For multiple linear regression,
**[4:07]** we have J ranging from 1 through n and
**[4:10]** so we'll update the parameters w_1,
**[4:14]** w_2, all the way up to w_n,
**[4:19]** and then as before, we'll update b.
**[4:23]** If you implement this,
**[4:25]** you get gradient descent for multiple regression.
**[4:29]** That's it for gradient descent for multiple regression.
**[4:33]** Before moving on from this video,
**[4:36]** I want to make a quick aside or a quick side note on
**[4:41]** an alternative way for finding
**[4:43]** w and b for linear regression.
**[4:46]** This method is called the normal equation.
**[4:50]** Whereas it turns out gradient descent is a great method
**[4:54]** for minimizing the cost function J to find w and b,
**[4:58]** there is one other algorithm that works only
**[5:01]** for linear regression and pretty much none of
**[5:04]** the other algorithms you see in this specialization
**[5:06]** for solving for w and b
**[5:09]** and this other method does not need
**[5:11]** an iterative gradient descent algorithm.
**[5:15]** Called the normal equation method,
**[5:17]** it turns out to be possible to use
**[5:19]** an advanced linear algebra library to just solve for
**[5:22]** w and b all in one goal without iterations.
**[5:26]** Some disadvantages of the normal equation method are;
**[5:30]** first unlike gradient descent,
**[5:32]** this is not generalized to other learning algorithms,
**[5:35]** such as the logistic regression algorithm
**[5:37]** that you'll learn about next week
**[5:39]** or the neural networks or
**[5:40]** other algorithms you see later in this specialization.
**[5:44]** The normal equation method is also quite
**[5:46]** slow if the number of features and this large.
**[5:50]** Almost no machine learning
**[5:52]** practitioners should implement the normal equation method
**[5:55]** themselves but if you're using
**[5:58]** a mature machine learning
**[6:00]** library and call linear regression,
**[6:03]** there is a chance that on the backend,
**[6:04]** it'll be using this to solve for w and b.
**[6:08]** If you're ever in the job interview
**[6:10]** and hear the term normal equation,
**[6:12]** that's what this refers to.
**[6:14]** Don't worry about the details of how
**[6:16]** the normal equation works.
**[6:18]** Just be aware that some machine learning libraries
**[6:21]** may use this complicated method
**[6:24]** in the back-end to solve for w and b.
**[6:26]** But for most learning algorithms,
**[6:28]** including how you implement linear regression yourself,
**[6:32]** gradient descents offer a better way to get the job done.
**[6:35]** In the optional lab that follows this video,
**[6:38]** you'll see how to define a multiple regression model
**[6:42]** encode and also how to calculate the prediction f of x.
**[6:47]** You'll also see how to calculate the cost and
**[6:51]** implement gradient descent for
**[6:53]** a multiple linear regression model.
**[6:55]** This will be using Python's NumPy library.
**[6:58]** If any of the code looks very new,
**[7:01]** that's okay but you should feel free
**[7:03]** also to take a look at the previous optional lab that
**[7:07]** introduces NumPy and vectorization for a refresher
**[7:11]** of NumPy functions and how to implement those in code.
**[7:15]** That's it. You now know multiple linear regression.
**[7:19]** This is probably the single most widely used
**[7:22]** learning algorithm in the world today. But there's more.
**[7:25]** With just a few tricks such
**[7:27]** as picking and scaling features
**[7:29]** appropriately and also choosing
**[7:30]** the learning rate alpha appropriately,
**[7:32]** you'd really make this work much better.
**[7:35]** Just a few more videos to go for this week.
**[7:38]** Let's go on to the next video
**[7:39]** to see those little tricks that will
**[7:41]** help you make multiple linear
**[7:43]** regression work much better.
