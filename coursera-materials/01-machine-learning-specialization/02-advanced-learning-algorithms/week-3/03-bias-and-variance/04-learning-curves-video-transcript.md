---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 3
section: Bias and variance
item_title: Learning curves
duration: 12 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/X8i9Z/learning-curves
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Learning curves — Transcript

**[0:00]** Learning curves are a way to help understand how
**[0:04]** your learning algorithm is doing as
**[0:06]** a function of the amount of experience it has,
**[0:09]** whereby experience, I mean,
**[0:10]** for example, the number of training examples it has.
**[0:13]** Let's take a look. Let me plot the learning curves for
**[0:16]** a model that fits
**[0:18]** a second-order polynomial quadratic function like so.
**[0:22]** I'm going to plot both J_cv,
**[0:24]** the cross-validation error,
**[0:26]** as well as J_train the training error.
**[0:29]** On this figure, the horizontal axis is
**[0:32]** going to be m_train.
**[0:36]** That is the training set size or
**[0:38]** the number of examples so the algorithm can learn from.
**[0:41]** On the vertical axis,
**[0:42]** I'm going to plot the error.
**[0:44]** By error, I mean either J_cv or J_train.
**[0:47]** Let's start by plotting the cross-validation error.
**[0:50]** It will look something like this.
**[0:53]** That's what J_cv of (w, b) will look like.
**[0:58]** Is maybe no surprise that as m_train,
**[1:01]** the training set size gets bigger,
**[1:03]** then you learn a better model
**[1:05]** and so the cross-validation error goes down.
**[1:08]** Now, let's plot J_train of (w,
**[1:11]** b) of what the training error looks like as
**[1:14]** the training set size gets bigger.
**[1:16]** It turns out that the training error
**[1:19]** will actually look like this.
**[1:21]** That as the training set size gets bigger,
**[1:24]** the training set error actually increases.
**[1:28]** Let's take a look at why this is the case.
**[1:29]** We'll start with an example of
**[1:32]** when you have just a single training example.
**[1:35]** Well, if you were to fit a quadratic model to this,
**[1:37]** you can fit easiest straight line or
**[1:40]** a curve and your training error will be zero.
**[1:43]** How about if you have two training examples like this?
**[1:46]** Well, you can again fit
**[1:48]** a straight line and achieve zero training error.
**[1:51]** In fact, if you have three training examples,
**[1:53]** the quadratic function can still fit this very
**[1:56]** well and get pretty much zero training error,
**[1:59]** but now, if your training set gets a little bit bigger,
**[2:02]** say you have four training examples,
**[2:04]** then it gets a little bit harder to
**[2:06]** fit all four examples perfectly.
**[2:09]** You may get a curve that looks like this,
**[2:11]** is a pretty well, but you're a
**[2:13]** little bit off in a few places here and there.
**[2:15]** When you have increased,
**[2:17]** the training set size to four
**[2:20]** the training error has actually gone up a little bit.
**[2:23]** How about we have five training examples.
**[2:26]** Well again, you can fit it pretty well,
**[2:27]** but it gets even a little bit harder
**[2:29]** to fit all of them perfectly.
**[2:32]** We haven't even larger training
**[2:33]** sets it just gets harder and
**[2:35]** harder to fit every
**[2:37]** single one of your training examples perfectly.
**[2:39]** To recap, when you have a very small number of
**[2:42]** training examples like one or two or even three,
**[2:45]** is relatively easy to
**[2:48]** get zero or very small training error,
**[2:51]** but when you have a larger training set is
**[2:54]** harder for quadratic function
**[2:56]** to fit all the training examples perfectly.
**[2:59]** Which is why as the training set gets bigger,
**[3:02]** the training error increases because it's
**[3:05]** harder to fit all of the training examples perfectly.
**[3:09]** Notice one other thing about these curves,
**[3:11]** which is the cross-validation error,
**[3:14]** will be typically higher than
**[3:17]** the training error because
**[3:19]** you fit the parameters to the training set.
**[3:21]** You expect to do at least a little
**[3:23]** bit better or when m is small,
**[3:25]** maybe even a lot better on
**[3:28]** the training set than on the trans validation set.
**[3:31]** Let's now take a look at what
**[3:33]** the learning curves will look like for an
**[3:35]** algorithm with high bias versus one with high variance.
**[3:39]** Let's start at the high bias or the underfitting case.
**[3:43]** Recall that an example of
**[3:45]** high bias would be if you're fitting a linear function,
**[3:47]** so curve that looks like this.
**[3:50]** If you were to plot the training error,
**[3:53]** then the training error will go
**[3:55]** up like so as you'd expect.
**[3:58]** In fact, this curve of
**[4:00]** training error may start to flatten out.
**[4:03]** We call it plateau,
**[4:05]** meaning flatten out after a while.
**[4:08]** That's because as you get
**[4:10]** more and more training examples
**[4:12]** when you're fitting the simple linear function,
**[4:15]** your model doesn't actually change that much more.
**[4:18]** It's fitting a straight line and even as you
**[4:20]** get more and more and more examples,
**[4:22]** there's just not that much more to change,
**[4:24]** which is why the average training error
**[4:26]** flattens out after a while.
**[4:29]** Similarly, your cross-validation error will come
**[4:33]** down and also fattened out after a while,
**[4:36]** which is why J_cv again is higher than J_train,
**[4:40]** but J_cv will tend to look like that.
**[4:43]** It's because beyond a certain point,
**[4:46]** even as you get more and more and more examples,
**[4:48]** not much is going to change
**[4:50]** about the straight line you're fitting.
**[4:51]** It's just too simple a model
**[4:54]** to be fitting into this much data.
**[4:56]** Which is why both of these curves, J_cv,
**[4:58]** and J_train tend to flatten after a while.
**[5:02]** If you had a measure
**[5:05]** of that baseline level of performance,
**[5:07]** such as human-level performance,
**[5:09]** then they'll tend to be a value that is
**[5:12]** lower than your J_train and your J_cv.
**[5:15]** Human-level performance may look like this.
**[5:18]** There's a big gap between
**[5:20]** the baseline level of performance and J_train,
**[5:22]** which was our indicator for
**[5:25]** this algorithm having high bias.
**[5:28]** That is, one could hope to be doing much better if
**[5:32]** only we could fit
**[5:33]** a more complex function than just a straight line.
**[5:37]** Now, one interesting thing about
**[5:40]** this plot is you can ask,
**[5:43]** what do you think will happen if you
**[5:45]** could have a much bigger training set?
**[5:49]** What would it look like if we could
**[5:52]** increase even further than the right of this plot,
**[5:55]** you can go further to the right as follows?
**[5:58]** Well, you can imagine if you
**[6:00]** were to extend both of these curves to the right,
**[6:02]** they'll both flatten out and both of them will
**[6:04]** probably just continue to be flat like that.
**[6:08]** No matter how far you extend to the right
**[6:10]** of this plot, these two curves,
**[6:12]** they will never somehow find a way to dip down to
**[6:15]** this human level performance or just keep on
**[6:18]** being flat like this,
**[6:20]** pretty much forever no matter
**[6:22]** how large the training set gets.
**[6:25]** That gives this conclusion,
**[6:27]** maybe a little bit surprising,
**[6:29]** that if a learning algorithm has high bias,
**[6:32]** getting more training data will not
**[6:34]** by itself hope that much.
**[6:36]** I know that we're used to thinking
**[6:38]** that having more data is good,
**[6:41]** but if your algorithm has high bias,
**[6:44]** then if the only thing you
**[6:45]** do is throw more training data at it,
**[6:48]** that by itself will not ever let
**[6:51]** you bring down the error rate that much.
**[6:52]** It's because of this really,
**[6:54]** no matter how many more examples you add to this figure,
**[6:57]** the straight linear fitting just isn't
**[6:59]** going to get that much better.
**[7:01]** That's why before investing a lot of
**[7:04]** effort into collecting more training data,
**[7:06]** it's worth checking if
**[7:08]** your learning algorithm has
**[7:09]** high bias, because if it does,
**[7:11]** then you probably need to do
**[7:12]** some other things other than
**[7:14]** just throw more training data at it.
**[7:16]** Let's now take a look at what
**[7:18]** the learning curve looks like for
**[7:19]** learning algorithm with high variance.
**[7:22]** You might remember that if you were to fit
**[7:25]** the fourth-order polynomial with small lambda, say,
**[7:29]** or even lambda equals zero,
**[7:30]** then you get a curve that looks like this,
**[7:32]** and even though it fits the training data
**[7:35]** very well, it doesn't generalize.
**[7:38]** Let's now look at what
**[7:39]** a learning curve might look like in
**[7:41]** this high variance scenario.
**[7:44]** J train will be going
**[7:46]** up as the training set size increases,
**[7:50]** so you get a curve that looks like this,
**[7:52]** and J cv will be much higher,
**[7:55]** so your cross-validation error is
**[7:58]** much higher than your training error.
**[8:00]** The fact there's a huge gap
**[8:02]** here is what I can tell you that
**[8:05]** this high-variance is doing
**[8:06]** much better on the training set
**[8:07]** than it's doing on your cross-validation set.
**[8:10]** If you were to plot a baseline level of performance,
**[8:14]** such as human level performance,
**[8:15]** you may find that it turns out to be here,
**[8:19]** that J train can sometimes be even lower than
**[8:22]** the human level performance or maybe
**[8:24]** human level performance is a little bit lower than this.
**[8:27]** But when you're over fitting the training set,
**[8:30]** you may be able to fit the training set so
**[8:32]** well to have an unrealistically low error,
**[8:35]** such as zero error in this example over here,
**[8:38]** which is actually better than how well humans will
**[8:42]** actually be able to predict
**[8:43]** housing prices or whatever
**[8:44]** the application you're working on.
**[8:46]** But again, to signal for high variance is whether
**[8:49]** J cv is much higher than J train.
**[8:52]** When you have high variance,
**[8:55]** then increasing the training set size could help a lot,
**[8:59]** and in particular, if we
**[9:01]** could extrapolate these curves to the right,
**[9:03]** increase M train,
**[9:05]** then the training error will continue to go up,
**[9:08]** but then the cross-validation error hopefully
**[9:11]** will come down and approach J train.
**[9:15]** So in this scenario,
**[9:18]** it might be possible just by
**[9:20]** increasing the training set size to
**[9:23]** lower the cross-validation error and
**[9:25]** to get your algorithm to perform better and better,
**[9:28]** and this is unlike the high bias case,
**[9:31]** where if the only thing you do is get more training data,
**[9:34]** that won't actually help you
**[9:35]** learn your algorithm performance much.
**[9:38]** To summarize,
**[9:39]** if a learning algorithm suffers from high variance,
**[9:42]** then getting more training data is indeed likely to help.
**[9:47]** Because extrapolating to the right of this curve,
**[9:49]** you see that you can expect J cv to keep on coming down.
**[9:53]** In this example, just by getting more training data,
**[9:56]** allows the algorithm to go from
**[9:58]** relatively high cross-validation error to
**[10:01]** get much closer to human level performance.
**[10:04]** You can see that if you were to add
**[10:07]** a lot more training examples and
**[10:08]** continue to fill the fourth-order polynomial,
**[10:10]** then you can just get a better fourth order
**[10:14]** polynomial fit to this data
**[10:15]** than this very wiggly curve up on top.
**[10:18]** If you're building a machine learning application,
**[10:22]** you could plot the
**[10:23]** learning curves if you want, that is,
**[10:24]** you can take different subsets of your training sets,
**[10:27]** and even if you have, say,
**[10:28]** 1,000 training examples,
**[10:30]** you could train a model on
**[10:31]** just 100 training examples and look
**[10:33]** at the training error and cross-validation error,
**[10:36]** then train a model on 200 examples,
**[10:39]** holding out 800 examples
**[10:40]** and just not using them for now,
**[10:42]** and plot J train and J cv and so on
**[10:45]** the repeats and plot out
**[10:46]** what the learning curve looks like.
**[10:48]** If we were to visualize it that way,
**[10:50]** then that could be another way for you to see
**[10:54]** if your learning curve looks more like
**[10:55]** a high bias or high variance one.
**[10:57]** One downside of the plotting learning curves
**[11:00]** like this is something I've done,
**[11:01]** but one downside is,
**[11:02]** it is computationally quite expensive to train
**[11:06]** so many different models using
**[11:07]** different size subsets of
**[11:09]** your training set, so in practice,
**[11:11]** it isn't done that often, but nonetheless,
**[11:14]** I find that having
**[11:15]** this mental visual picture
**[11:17]** in my head of what the training set looks like,
**[11:19]** sometimes that helps me to think through what I think
**[11:22]** my learning algorithm is doing and whether it
**[11:24]** has high bias or high variance.
**[11:27]** I know we've gone through a lot about bias and variance,
**[11:31]** let's go back to our earlier example of
**[11:34]** if you've trained a model for housing price prediction,
**[11:37]** how does bias and variance
**[11:39]** help you decide what to do next?
**[11:41]** Let's go back to that earlier example,
**[11:42]** which I hope will now make a lot more sense to you.
**[11:45]** Let's do that in the next video.
