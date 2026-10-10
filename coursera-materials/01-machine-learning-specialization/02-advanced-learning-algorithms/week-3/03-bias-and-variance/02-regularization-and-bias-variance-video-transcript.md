---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 3
section: Bias and variance
item_title: Regularization and bias/variance
duration: 10 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/JQZRO/regularization-and-bias-variance
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# Regularization and bias/variance — Transcript

**[0:01]** You saw in the last video how
**[0:04]** different choices of the degree of
**[0:06]** polynomial D affects the bias in
**[0:08]** variance of your learning algorithm
**[0:10]** and therefore its overall performance.
**[0:12]** In this video, let's take a look at how regularization,
**[0:16]** specifically the choice of
**[0:18]** the regularization parameter Lambda
**[0:20]** affects the bias and variance and
**[0:22]** therefore the overall performance of the algorithm.
**[0:24]** This, it turns out,
**[0:26]** will be helpful for when you want
**[0:27]** to choose a good value of
**[0:29]** Lambda of the regularization parameter
**[0:31]** for your algorithm. Let's take a look.
**[0:33]** In this example, I'm going to
**[0:35]** use a fourth-order polynomial,
**[0:38]** but we're going to fit this model using regularization.
**[0:43]** Where here the value of
**[0:45]** Lambda is the regularization parameter that controls how
**[0:49]** much you trade-off keeping the parameters w
**[0:52]** small versus fitting the training data well.
**[0:56]** Let's start with the example of setting
**[0:59]** Lambda to be a very large value.
**[1:02]** Say Lambda is equal to 10,000.
**[1:06]** If you were to do so,
**[1:08]** you would end up fitting
**[1:10]** a model that looks roughly like this.
**[1:14]** Because if Lambda were very large,
**[1:15]** then the algorithm is highly motivated to keep
**[1:19]** these parameters w very
**[1:21]** small and so you end up with w_1,
**[1:24]** w_2, really all of
**[1:26]** these parameters will be very close to zero.
**[1:30]** The model ends up being f of x is
**[1:33]** just approximately b a constant value,
**[1:36]** which is why you end up with a model like this.
**[1:40]** This model clearly has high bias and it underfits
**[1:46]** the training data because it doesn't even do well on
**[1:49]** the training set and J_train is large.
**[1:52]** Let's take a look at the other extreme.
**[1:56]** Let's say you set Lambda to be a very small value.
**[2:01]** With a small value of Lambda,
**[2:04]** in fact, let's go to extreme of
**[2:06]** setting Lambda equals zero.
**[2:08]** With that choice of Lambda,
**[2:11]** there is no regularization,
**[2:12]** so we're just fitting a fourth-order polynomial
**[2:15]** with no regularization and you end up
**[2:17]** with that curve that you saw
**[2:20]** previously that overfits the data.
**[2:24]** What we saw previously
**[2:26]** was when you have a model like this,
**[2:28]** J_train is small,
**[2:29]** but J_cv is much larger than J_train or J_cv is large.
**[2:35]** This indicates we have high variance
**[2:38]** and it overfits this data.
**[2:40]** It would be if you have
**[2:43]** some intermediate value of Lambda,
**[2:45]** not really largely 10,000,
**[2:47]** but not so small as zero that
**[2:49]** hopefully you get a model that looks like this,
**[2:52]** that is just right and fits the data well
**[2:55]** with small J_train and small J_cv.
**[2:59]** If you are trying to decide what is
**[3:03]** a good value of Lambda to
**[3:05]** use for the regularization parameter,
**[3:07]** cross-validation gives you a way to do so as well.
**[3:11]** Let's take a look at how we could do so.
**[3:13]** Just as a reminder,
**[3:15]** the problem we're addressing
**[3:17]** is if you're fitting a fourth-order polynomial,
**[3:19]** so that's the model and you're using regularization,
**[3:22]** how can you choose a good value of Lambda?
**[3:25]** This would be procedures similar to what you had seen for
**[3:29]** choosing the degree of
**[3:30]** polynomial D using cross-validation.
**[3:34]** Specifically, let's say we try to
**[3:37]** fit a model using Lambda equals 0.
**[3:40]** We would minimize the cost function
**[3:44]** using Lambda equals 0 and end up with some parameters w1,
**[3:49]** b1 and you can then compute the cross-validation error,
**[3:54]** J_cv of w1, b1.
**[3:57]** Now let's try a different value of Lambda.
**[3:59]** Let's say you try Lambda equals 0.01.
**[4:02]** Then again, minimizing the cost function
**[4:05]** gives you a second set of parameters, w2,
**[4:07]** b2 and you can also see how well
**[4:11]** that does on the cross-validation set, and so on.
**[4:15]** Let's keep trying other values of
**[4:17]** Lambda and in this example,
**[4:19]** I'm going to try doubling it to Lambda equals
**[4:21]** 0.02 and so that will give you J_cv of w3,
**[4:26]** b3, and so on.
**[4:28]** Then let's double again and double again.
**[4:30]** After doubling a number of times,
**[4:32]** you end up with Lambda approximately equal to 10,
**[4:36]** and that will give you parameters w12,
**[4:39]** b12, and J_cv w12 of b12.
**[4:43]** By trying out a large range
**[4:46]** of possible values for Lambda,
**[4:47]** fitting parameters using
**[4:49]** those different regularization parameters,
**[4:51]** and then evaluating the performance
**[4:53]** on the cross-validation set,
**[4:55]** you can then try to pick what is
**[4:57]** the best value for the regularization parameter.
**[5:00]** Quickly. If in this example,
**[5:02]** you find that J_cv of W5,
**[5:06]** B5 has the lowest value
**[5:09]** of all of these different cross-validation errors,
**[5:11]** you might then decide to pick this value for Lambda,
**[5:16]** and so use W5,
**[5:18]** B5 as to chosen parameters.
**[5:21]** Finally, if you want to report
**[5:23]** out an estimate of the generalization error,
**[5:27]** you would then report out the test set error,
**[5:29]** J tests of W5, B5.
**[5:33]** To further hone intuition
**[5:35]** about what this algorithm is doing,
**[5:36]** let's take a look at
**[5:38]** how training error and cross validation error
**[5:40]** vary as a function of the parameter Lambda.
**[5:44]** In this figure, I've changed the x-axis again.
**[5:47]** Notice that the x-axis here is
**[5:51]** annotated with the value of
**[5:53]** the regularization parameter Lambda,
**[5:56]** and if we look at the extreme
**[5:59]** of Lambda equals zero here on the left,
**[6:03]** that corresponds to not using any regularization,
**[6:06]** and so that's where we wound
**[6:08]** up with this very wiggly curve.
**[6:10]** If Lambda was small or it was even zero,
**[6:13]** and in that case,
**[6:15]** we have a high variance model,
**[6:18]** and so J train is going to be
**[6:21]** small and J_cv is going to be
**[6:24]** large because it does great on
**[6:26]** the training data but does much
**[6:27]** worse on the cross validation data.
**[6:30]** This extreme on the right
**[6:32]** were very large values of Lambda.
**[6:34]** Say Lambda equals 10,000 ends
**[6:36]** up with fitting a model that looks like that.
**[6:39]** This has high bias,
**[6:42]** it underfits the data,
**[6:43]** and it turns out J train will be high and
**[6:46]** J_cv will be high as well.
**[6:50]** In fact, if you were to look at how
**[6:53]** J train varies as a function of Lambda,
**[6:56]** you find that J train will go up like
**[6:59]** this because in the optimization cost function,
**[7:03]** the larger Lambda is,
**[7:05]** the more the algorithm is trying to keep W squared small.
**[7:08]** That is, the more weight is
**[7:10]** given to this regularization term,
**[7:12]** and thus the less attention is paid
**[7:14]** to actually do well on the training set.
**[7:17]** This term on the left is J train,
**[7:19]** so the most trying to keep the parameters small,
**[7:22]** the less good a job it
**[7:23]** does on minimizing the training error.
**[7:26]** That's why as Lambda increases,
**[7:28]** the training error J train will tend to increase like so.
**[7:33]** Now, how about the cross-validation error?
**[7:35]** Turns out the cross-validation error will look like this.
**[7:40]** Because we've seen that if
**[7:42]** Lambda is too small or too large,
**[7:44]** then it doesn't do well on the cross-validation set.
**[7:47]** It either overfits here on
**[7:49]** the left or underfits here on the right.
**[7:53]** There'll be some intermediate value of Lambda that
**[7:57]** causes the algorithm to perform best.
**[8:00]** What cross-validation is doing is,
**[8:03]** it's trying out a lot of different values of Lambda.
**[8:07]** This is what we saw on the last slide;
**[8:08]** trial Lambda equals zero,
**[8:09]** Lambda equals 0.01, logic is 0,02.
**[8:12]** Try a lot of different values of Lambda and
**[8:15]** evaluate the cross-validation error
**[8:17]** in a lot of these different points,
**[8:19]** and then hopefully pick a value
**[8:22]** that has low cross validation error,
**[8:26]** and this will hopefully
**[8:28]** correspond to a good model for your application.
**[8:31]** If you compare this diagram to
**[8:33]** the one that we had in the previous video,
**[8:36]** where the horizontal axis was the degree of polynomial,
**[8:40]** these two diagrams look a little
**[8:42]** bit not mathematically and not in any formal way,
**[8:45]** but they look a little bit
**[8:47]** like mirror images of each other,
**[8:49]** and that's because when
**[8:51]** you're fitting a degree of polynomial,
**[8:54]** the left part of this curve corresponded
**[8:56]** to underfitting and high bias,
**[8:59]** the right part corresponded to
**[9:01]** overfitting and high variance.
**[9:03]** Whereas in this one,
**[9:05]** high-variance was on the left and
**[9:07]** high bias was on the right.
**[9:09]** But that's why these two images are a little bit
**[9:11]** like mirror images of each other.
**[9:13]** But in both cases, cross-validation,
**[9:16]** evaluating different values can help you
**[9:18]** choose a good value of t or a good value of Lambda.
**[9:22]** That's how the choice of
**[9:24]** regularization parameter Lambda affects
**[9:26]** the bias and variance and
**[9:28]** overall performance of your algorithm,
**[9:30]** and you've also seen how you can use cross-validation to
**[9:34]** make a good choice for
**[9:35]** the regularization parameter Lambda.
**[9:37]** Now, so far,
**[9:39]** we've talked about how having a high training set error,
**[9:43]** high J train is indicative of
**[9:45]** high bias and how
**[9:47]** having a high cross-validation error of J_cv,
**[9:49]** specifically if it's much higher than J train,
**[9:53]** how that's indicative of variance problem.
**[9:57]** But what does these words "high" or
**[9:59]** "much higher" actually mean?
**[10:01]** Let's take a look at that in
**[10:02]** the next video where we'll look at how you can look at
**[10:05]** the numbers J train and
**[10:06]** J_cv and judge if it's high or low,
**[10:09]** and it turns out that
**[10:10]** one further refinement of these ideas, that is,
**[10:13]** establishing a baseline level
**[10:15]** of performance we're learning
**[10:15]** algorithm will make it much
**[10:17]** easier for you to look at these numbers,
**[10:19]** J train, J_cv,
**[10:20]** and judge if they are high or low.
**[10:23]** Let's take a look at what all
**[10:24]** this means in the next video.
