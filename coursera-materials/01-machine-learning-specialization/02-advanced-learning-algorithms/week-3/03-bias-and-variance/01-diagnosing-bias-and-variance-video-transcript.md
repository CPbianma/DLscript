---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 3
section: Bias and variance
item_title: Diagnosing bias and variance
duration: 11 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/L6SHx/diagnosing-bias-and-variance
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Diagnosing bias and variance — Transcript

**[0:01]** The typical workflow of developing
**[0:04]** a machine learning system is that
**[0:06]** you have an idea and you train the model,
**[0:09]** and you almost always find that it
**[0:11]** doesn't work as well as you wish yet.
**[0:13]** When I'm training a machine learning model,
**[0:15]** it pretty much never works that well the first time.
**[0:18]** Key to the process of building
**[0:20]** machine learning system is how to
**[0:22]** decide what to do next in
**[0:24]** order to improve his performance.
**[0:25]** I've found across many different applications
**[0:28]** that looking at the bias and
**[0:30]** variance of a learning algorithm gives you
**[0:32]** very good guidance on what to try next.
**[0:35]** Let's take a look at what this means.
**[0:37]** You might remember this example from
**[0:40]** the first course on linear regression.
**[0:44]** Where given this dataset,
**[0:46]** if you were to fit a straight line to it,
**[0:48]** it doesn't do that well.
**[0:49]** We said that this algorithm has
**[0:51]** high bias or that it underfits this dataset.
**[0:55]** If you were to fit a fourth-order polynomial,
**[0:59]** then it has high-variance or it overfits.
**[1:03]** In the middle if you fit a quadratic polynomial,
**[1:07]** then it looks pretty good.
**[1:08]** Then I said that was just right.
**[1:10]** Because this is a problem with just a single feature x,
**[1:14]** we could plot the function f and look at it like this.
**[1:17]** But if you had more features,
**[1:19]** you can't plot f and
**[1:21]** visualize whether it's doing well as easily.
**[1:24]** Instead of trying to look at plots like this,
**[1:27]** a more systematic way to
**[1:29]** diagnose or to find
**[1:32]** out if your algorithm has high bias or
**[1:34]** high variance will be to look at the performance of
**[1:37]** your algorithm on the training set
**[1:39]** and on the cross validation set.
**[1:42]** In particular, let's look at the example on the left.
**[1:44]** If you were to compute J_train,
**[1:48]** how well does the algorithm do on the training set?
**[1:51]** Not that well. I'd say
**[1:53]** J train here would be high because there are actually
**[1:56]** pretty large errors between
**[1:58]** the examples and the actual predictions of the model.
**[2:02]** How about J_cv?
**[2:05]** J_cv would be if we had a few new examples,
**[2:09]** maybe examples like that,
**[2:11]** that the algorithm had not previously seen.
**[2:15]** Here the algorithm also doesn't do that
**[2:18]** well on examples that it had not previously seen,
**[2:21]** so J_cv will also be high.
**[2:25]** One characteristic of an algorithm with high bias,
**[2:28]** something that is under fitting,
**[2:30]** is that it's not even
**[2:31]** doing that well on the training set.
**[2:34]** When J_train is high,
**[2:35]** that is your strong indicator
**[2:37]** that this algorithm has high bias.
**[2:40]** Let's now look at the example on the right.
**[2:42]** If you were to compute J_train,
**[2:45]** how well is this doing on the training set?
**[2:47]** Well, it's actually doing great on the training set.
**[2:49]** Fits the training data really well.
**[2:51]** J_train here will be low.
**[2:54]** But if you were to evaluate
**[2:56]** this model on other houses not in the training set,
**[3:00]** then you find that J_cv,
**[3:03]** the cross-validation error, will be quite high.
**[3:07]** A characteristic signature or
**[3:10]** a characteristic Q that your algorithm has
**[3:12]** high variance will be of
**[3:14]** J_cv is much higher than J_train.
**[3:18]** In other words, it does much better on data it
**[3:20]** has seen than on data it has not seen.
**[3:23]** This turns out to be
**[3:24]** a strong indicator that your algorithm has high variance.
**[3:28]** Again, the point of what we're doing is
**[3:30]** that I'm computing J_train and
**[3:33]** J_cv and seeing if J _train
**[3:36]** is high or if J_cv is much higher than J_train.
**[3:39]** This gives you a sense,
**[3:41]** even if you can't plot to function f,
**[3:43]** of whether your algorithm has high bias or high variance.
**[3:48]** Finally, the case in the middle.
**[3:51]** If you look at J_train,
**[3:54]** it's pretty low, so this is doing
**[3:56]** quite well on the training set.
**[3:58]** If you were to look at a few new examples,
**[4:02]** like those from, say,
**[4:04]** your cross-validation set, you
**[4:06]** find that J_cv is also a pretty low.
**[4:10]** J_train not being too high
**[4:13]** indicates this doesn't have a high bias problem and
**[4:16]** J_cv not being much worse than
**[4:18]** J_train this indicates that
**[4:20]** it doesn't have a high variance problem either.
**[4:23]** Which is why the quadratic model
**[4:27]** seems to be a pretty good one for this application.
**[4:29]** To summarize, when d equals 1 for a linear polynomial,
**[4:34]** J_train was high and J_cv was high.
**[4:38]** When d equals 4,
**[4:40]** J train was low,
**[4:41]** but J_cv is high.
**[4:43]** When d equals 2,
**[4:44]** both were pretty low.
**[4:46]** Let's now take a different view on bias and variance.
**[4:50]** In particular, on the next slide I'd
**[4:52]** like to show you how J_train and
**[4:54]** J_cv variance as a function
**[4:57]** of the degree of the polynomial you're fitting.
**[5:00]** Let me draw a figure where
**[5:02]** the horizontal axis, this d here,
**[5:04]** will be the degree of polynomial
**[5:06]** that we're fitting to the data.
**[5:09]** Over on the left we'll correspond to a small value of d,
**[5:13]** like d equals 1,
**[5:14]** which corresponds to fitting straight line.
**[5:17]** Over to the right we'll correspond to, say,
**[5:20]** d equals 4 or even higher values of
**[5:23]** d. We're fitting this high order polynomial.
**[5:26]** So if you were to plot J train or W,
**[5:33]** B as a function of the degree of polynomial,
**[5:35]** what you find is that as you fit
**[5:38]** a higher and higher degree polynomial,
**[5:41]** here I'm assuming we're not using regularization,
**[5:44]** but as you fit a higher and higher order polynomial,
**[5:47]** the training error will tend to go down
**[5:50]** because when you have a very simple linear function,
**[5:53]** it doesn't fit the training data that well,
**[5:55]** when you fit a quadratic function or
**[5:57]** third order polynomial or fourth-order polynomial,
**[6:00]** it fits the training data better and better.
**[6:04]** As the degree of polynomial increases,
**[6:07]** J train will typically go down.
**[6:10]** Next, let's look at J_cv,
**[6:14]** which is how well does it do
**[6:17]** on data that it did not get to fit to?
**[6:21]** What we saw was when d equals one,
**[6:24]** when the degree of polynomial was very low,
**[6:26]** J_cv was pretty high because it underfits,
**[6:30]** so it didn't do well on the cross validation set.
**[6:34]** Here on the right as well,
**[6:36]** when the degree of polynomial is very large, say four,
**[6:39]** it doesn't do well on the cross-validation set either,
**[6:43]** and so it's also high.
**[6:45]** But if d was in-between say,
**[6:48]** a second-order polynomial,
**[6:49]** then it actually did much better.
**[6:51]** If you were to vary the degree of polynomial,
**[6:55]** you'd actually get a curve that looks like this,
**[6:57]** which comes down and then goes back up.
**[7:00]** Where if the degree of polynomial is too low,
**[7:04]** it underfits and so doesn't do the cross validation set,
**[7:08]** if it is too high,
**[7:10]** it overfits and also doesn't
**[7:11]** do well on the cross validation set.
**[7:13]** Is only if it's somewhere in the middle,
**[7:16]** that is just right,
**[7:18]** which is why the second-order polynomial
**[7:20]** in our example ends up with
**[7:22]** a lower cross-validation error and
**[7:24]** neither high bias nor high-variance.
**[7:27]** To summarize, how do you diagnose
**[7:30]** bias and variance in your learning algorithm?
**[7:34]** If your learning algorithm has
**[7:35]** high bias or it has undefeated data,
**[7:38]** the key indicator will be if J train is high.
**[7:42]** That corresponds to this leftmost portion of the curve,
**[7:46]** which is where J train as high.
**[7:48]** Usually you have J train and
**[7:50]** J_cv will be close to each other.
**[7:52]** How do you diagnose if you have high variance?
**[7:56]** While the key indicator for high-variance
**[7:58]** will be if J_cv is much
**[8:01]** greater than J train does double
**[8:03]** greater than sign in math refers to a much greater than,
**[8:06]** so this is greater,
**[8:08]** and this means much greater.
**[8:10]** This rightmost portion of the plot is where
**[8:13]** J_cv is much greater than J train.
**[8:17]** Usually J train will be pretty low,
**[8:20]** but the key indicator is whether
**[8:22]** J_cv is much greater than J train.
**[8:25]** That's what happens when we had
**[8:27]** fit a very high order polynomial to this small dataset.
**[8:31]** Even though we've just seen bias in the areas,
**[8:34]** it turns out, in some cases,
**[8:36]** is possible to simultaneously
**[8:39]** have high bias and have high-variance.
**[8:41]** You won't see this happen that
**[8:43]** much for linear regression,
**[8:45]** but it turns out that
**[8:46]** if you're training a neural network,
**[8:48]** there are some applications where
**[8:49]** unfortunately you have high bias and high variance.
**[8:53]** One way to recognize that situation
**[8:55]** will be if J train is high,
**[8:58]** so you're not doing that well on
**[8:59]** the training set, but even worse,
**[9:02]** the cross-validation error is again,
**[9:04]** even much larger than the training set.
**[9:07]** The notion of high bias and high variance,
**[9:09]** it doesn't really happen for
**[9:11]** linear models applied to 1D.
**[9:14]** But to give intuition about what it looks like,
**[9:17]** it would be as if for part of the input,
**[9:21]** you had a very complicated model that overfit,
**[9:25]** so it overfits to part of the inputs.
**[9:28]** But then for some reason,
**[9:29]** for other parts of the input,
**[9:32]** it doesn't even fit the training data well,
**[9:34]** and so it underfits for part of the input.
**[9:37]** In this example, which looks artificial
**[9:39]** because it's a single feature input,
**[9:42]** we fit the training set really well
**[9:44]** and we overfit in part of the input,
**[9:47]** and we don't even fit the training data well,
**[9:49]** and we underfit the part of the input.
**[9:51]** That's how in some applications you can
**[9:54]** unfortunate end up with both high bias and high variance.
**[9:58]** The indicator for that will be if
**[10:00]** the algorithm does poorly on the training set,
**[10:02]** and it even does much worse than on the training set.
**[10:05]** For most learning applications,
**[10:07]** you probably have primarily a high bias
**[10:10]** or high variance problem
**[10:12]** rather than both at the same time.
**[10:13]** But it is possible
**[10:15]** sometimes they're both at the same time.
**[10:17]** I know that there's a lot of process,
**[10:19]** there are a lot of concepts on the slides,
**[10:21]** but the key takeaways are,
**[10:23]** high bias means is not
**[10:25]** even doing well on the training set,
**[10:27]** and high variance means,
**[10:29]** it does much worse on
**[10:32]** the cross validation set than the training set.
**[10:34]** Whenever I'm training a machine learning algorithm,
**[10:37]** I will almost always try to figure
**[10:39]** out to what extent the algorithm has
**[10:41]** a high bias or underfitting
**[10:43]** versus a high-variance when overfitting problem.
**[10:46]** This will give good guidance,
**[10:48]** as we'll see later this week,
**[10:49]** on how you can improve the performance of the algorithm.
**[10:52]** But first, let's take a look at
**[10:55]** how regularization effects the bias and
**[10:57]** variance of a learning algorithm because that will help
**[11:00]** you better understand when you should use regularization.
**[11:03]** Let's take a look at that in the next video.
