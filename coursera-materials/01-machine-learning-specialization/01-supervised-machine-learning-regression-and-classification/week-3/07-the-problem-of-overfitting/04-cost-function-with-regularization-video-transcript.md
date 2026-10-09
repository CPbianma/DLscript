---
type: video-transcript
specialization: Machine Learning Specialization
course: Supervised Machine Learning: Regression and Classification
week: 3
section: The problem of overfitting
item_title: Cost function with regularization
duration: 9 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/UZTPk/cost-function-with-regularization
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Cost function with regularization — Transcript

**[0:01]** In the last video we saw that regularization tries to make
**[0:05]** the parental values W1 through WN small to reduce overfitting.
**[0:10]** In this video, we'll build on that intuition and developed a modified cost
**[0:15]** function for your learning algorithm that can use to actually apply regularization.
**[0:20]** Let's jump in, recall this example from the previous video in which we saw that if
**[0:26]** you fit a quadratic function to this data, it gives a pretty good fit.
**[0:31]** But if you fit a very high order polynomial,
**[0:34]** you end up with a curve that over fits the data.
**[0:37]** But now consider the following, suppose that you had a way to
**[0:43]** make the parameters W3 and W4 really, really small.
**[0:48]** Say close to 0.
**[0:50]** Here's what I mean.
**[0:51]** Let's say instead of minimizing this objective function,
**[0:56]** this is a cost function for linear regression.
**[0:59]** Let's say you were to modify the cost function and
**[1:04]** add to it 1000 times W3 squared plus 1000 times W4 squared.
**[1:10]** And here I'm just choosing 1000 because it's a big number but
**[1:14]** any other really large number would be okay.
**[1:17]** So with this modified cost function,
**[1:20]** you could in fact be penalizing the model if W3 and W4 are large.
**[1:25]** Because if you want to minimize this function, the only way to make this
**[1:30]** new cost function small is if W3 and W4 are both small, right?
**[1:35]** Because otherwise this 1000 times W3 squared and
**[1:39]** 1000 times W4 square terms are going to be really, really big.
**[1:44]** So when you minimize this function,
**[1:47]** you're going to end up with W3 close to 0 and W4 close to 0.
**[1:53]** So we're effectively nearly canceling out the effects of the features execute and
**[2:00]** extra power of 4 and getting rid of these two terms over here.
**[2:05]** And if we do that, then we end up with a fit to the data that's much closer to
**[2:10]** the quadratic function,
**[2:12]** including maybe just tiny contributions from the features x cubed and extra 4.
**[2:17]** And this is good because it's a much better fit to the data compared to if all
**[2:22]** the parameters could be large and you end up with this weekly quadratic function
**[2:27]** more generally, here's the idea behind regularization.
**[2:30]** The idea is that if there are smaller values for the parameters,
**[2:34]** then that's a bit like having a simpler model.
**[2:37]** Maybe one with fewer features, which is therefore less prone to overfitting.
**[2:44]** On the last slide we penalize or
**[2:47]** we say we regularized only W3 and W4.
**[2:52]** But more generally, the way that regularization tends to be implemented is
**[2:56]** if you have a lot of features, say a 100 features, you may not know which
**[3:01]** are the most important features and which ones to penalize.
**[3:05]** So the way regularization is typically implemented is to penalize all of
**[3:09]** the features or more precisely, you penalize all the WJ parameters and
**[3:14]** it's possible to show that this will usually result in fitting a smoother
**[3:19]** simpler, less weekly function that's less prone to overfitting.
**[3:24]** So for this example, if you have data with 100 features for each house, it may be
**[3:28]** hard to pick an advance which features to include and which ones to exclude.
**[3:32]** So let's build a model that uses all 100 features.
**[3:37]** So you have these 100 parameters W1 through W100,
**[3:43]** as well as 100 and first parameter B.
**[3:47]** Because we don't know which of these parameters are going to be
**[3:50]** the important ones.
**[3:51]** Let's penalize all of them a bit and shrink all of them by adding
**[3:56]** this new term lambda times the sum from J equals 1 through n where n is 100.
**[4:03]** The number of features of wj squared.
**[4:08]** This value lambda here is the Greek alphabet lambda and
**[4:13]** it's also called a regularization parameter.
**[4:17]** So similar to picking a learning rate alpha,
**[4:22]** you now also have to choose a number for lambda.
**[4:26]** A couple of things I would like to point out by convention,
**[4:30]** instead of using lambda times the sum of wj squared.
**[4:34]** We also divide lambda by 2m so that both the 1st and
**[4:39]** 2nd terms here are scaled by 1 over 2m.
**[4:44]** It turns out that by scaling both terms the same way
**[4:47]** it becomes a little bit easier to choose a good value for lambda.
**[4:52]** And in particular you find that even if your training set size growth,
**[4:57]** say you find more training examples.
**[4:59]** So m the training set size is now bigger.
**[5:02]** The same value of lambda that you've picked previously is now also
**[5:07]** more likely to continue to work if you have this extra scaling by 2m.
**[5:12]** Also by the way,
**[5:13]** by convention we're not going to penalize the parameter b for being large.
**[5:19]** In practice, it makes very little difference whether you do or not.
**[5:22]** And some machine learning engineers and actually some learning algorithm
**[5:27]** implementations will also include lambda over 2m times the b squared term.
**[5:33]** But this makes very little difference in practice and
**[5:37]** the more common convention which was used in this course is to regularize
**[5:42]** only the parameters w rather than the parameter b.
**[5:45]** So to summarize in this modified cost function, we want to minimize
**[5:50]** the original cost, which is the mean squared error cost plus additionally,
**[5:56]** the second term which is called the regularization term.
**[6:00]** And so this new cost function trades off two goals that you might have.
**[6:05]** Trying to minimize this first term encourages the algorithm to fit
**[6:09]** the training data well by minimizing the squared differences of the predictions and
**[6:14]** the actual values.
**[6:15]** And try to minimize the second term.
**[6:18]** The algorithm also tries to keep the parameters wj small,
**[6:22]** which will tend to reduce overfitting.
**[6:25]** The value of lambda that you choose, specifies the relative importance or
**[6:31]** the relative trade off or how you balance between these two goals.
**[6:36]** Let's take a look at what different values of lambda will cause you're
**[6:40]** learning algorithm to do.
**[6:42]** Let's use the housing price prediction example using linear regression.
**[6:46]** So F of X is the linear regression model.
**[6:50]** If lambda was set to be 0, then you're not using the regularization
**[6:55]** term at all because the regularization term is multiplied by 0.
**[7:00]** And so if lambda was 0, you end up fitting this overly wiggly,
**[7:05]** overly complex curve and it over fits.
**[7:08]** So that was one extreme of if lambda was 0.
**[7:11]** Let's now look at the other extreme.
**[7:14]** If you said lambda to be a really, really,
**[7:16]** really large number, say lambda equals 10 to the power of 10,
**[7:20]** then you're placing a very heavy weight on this regularization term on the right.
**[7:25]** And the only way to minimize this is to be sure that all
**[7:30]** the values of w are pretty much very close to 0.
**[7:34]** So if lambda is very, very large,
**[7:37]** the learning algorithm will choose W1, W2, W3 and
**[7:42]** W4 to be extremely close to 0 and thus F of X is basically equal to b and
**[7:48]** so the learning algorithm fits a horizontal straight line and under fits.
**[7:55]** To recap if lambda is 0 this model will over fit If
**[7:59]** lambda is enormous like 10 to the power of 10.
**[8:03]** This model will under fit.
**[8:05]** And so what you want is some value of lambda that is in between that more
**[8:10]** appropriately balances these first and second terms of trading off,
**[8:16]** minimizing the mean squared error and keeping the parameters small.
**[8:21]** And when the value of lambda is not too small and not too large, but
**[8:26]** just right, then hopefully you end up able to fit a 4th order polynomial,
**[8:31]** keeping all of these features, but with a function that looks like this.
**[8:36]** So that's how regularization works.
**[8:39]** When we talk about model selection, later into specialization will
**[8:43]** also see a variety of ways to choose good values for lambda.
**[8:48]** In the next two videos will flesh out how to apply regularization to linear
**[8:52]** regression and logistic regression, and how to train these models with great in
**[8:56]** dissent with that, you'll be able to avoid overfitting with both of these algorithms.
