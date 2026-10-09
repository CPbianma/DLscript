---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 1
section: Setting up your Machine Learning Application
item_title: Bias / Variance
duration: 9 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/ZhclI/bias-variance
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Bias / Variance — Transcript

**[0:00]** I've noticed that almost all the really good machine learning practitioners tend
**[0:04]** to have a very sophisticated understanding of bias and variance.
**[0:08]** Bias and variance is one of those concepts that's easy to learn but
**[0:11]** difficult to master.
**[0:12]** Even if you think you've seen the basic concepts of bias and
**[0:15]** variance is often more nuanced to it than you'd expect.
**[0:18]** In the deep learning era, another trend is that there's been less discussion of
**[0:23]** what's called the bias variance trade off.
**[0:25]** You might have heard this thing called the bias variance trade off, but
**[0:28]** in the deep learning era, there's less of a trade off.
**[0:31]** So we still talk about bias, we still talk about variance, but
**[0:34]** we just talk less about the bias variance trade off.
**[0:37]** Let's see what this means.
**[0:40]** Let's say you have a data set that looks like this.
**[0:42]** If you fit a straight line to the data,
**[0:44]** maybe you get a logistic regression fit to that.
**[0:47]** This is not a very good fit to the data, and so there's a cause of high bias.
**[0:52]** Or we say that this is underfitting the data.
**[0:56]** On the opposite end, if you fit an incredibly complex classifier,
**[1:01]** maybe a deep neural network.
**[1:03]** Or a new network with a lot of hidden units,
**[1:07]** maybe you can fit the data perfectly.
**[1:10]** But that doesn't look like a great fit either.
**[1:12]** So this is a classifier with high variance,
**[1:15]** and this is overfitting the data.
**[1:17]** And there might be some classifier in between with a medium level of
**[1:21]** complexity that maybe fits a curve like that.
**[1:24]** That looks like a much more reasonable fit to the data.
**[1:27]** So that's the, and call that just right somewhere in each tree.
**[1:31]** So in a 2d example like this, with just two features, x1 and x2,
**[1:36]** you can plot the data and visualize bias and variance.
**[1:39]** In high dimensional problems, you can't plot the data and
**[1:42]** visualize the decision boundary.
**[1:44]** Instead, there are couple different metrics that we'll look at to try to
**[1:48]** understand bias and variance.
**[1:49]** So, continuing our example of cat picture classification,
**[1:53]** where that's a positive example and that's a negative example.
**[1:57]** The two key numbers to look at to understand bias and
**[2:00]** variance will be the trading set error and the dev set, or the development set error.
**[2:06]** So, for the sake of argument, let's say that recognizing
**[2:09]** cats in pictures is something that people can do nearly perfectly, right?
**[2:13]** And so let's say your trading size error is 1% and your dev set error is,
**[2:20]** for the sake of argument, let's say, is 11%.
**[2:25]** So in this example, you're doing very well on the training set, but
**[2:30]** you're doing relatively poorly on the development set.
**[2:34]** So this looks like you might have overfit the training set.
**[2:37]** That somehow you're not generalizing well to this holdout cost validation set to
**[2:42]** development set.
**[2:43]** And so if you have an example like this, we will say this has high variance.
**[2:50]** So by looking at the training set error and the development set error,
**[2:54]** you would be able to render a diagnosis of your algorithm having high variance.
**[2:59]** Now let's say that you measure your training set in your dev set error and
**[3:04]** you get a different result.
**[3:05]** Let's say that your training set error is 15%.
**[3:09]** I'm writing your training set error in the top row and your dev set error is 16%.
**[3:15]** In this case, assuming that humans achieve roughly 0% error,
**[3:21]** that humans can look at these pictures and just tell if it's cat or not.
**[3:27]** Then it looks like the algorithm is not even doing very well on the training set.
**[3:31]** So if it's not even fitting the training data, as seen that well,
**[3:35]** then this is underfitting the data.
**[3:38]** And so this algorithm has high bias.
**[3:41]** But in contrast,
**[3:41]** this is actually generalizing at a reasonable level to the dev set, whereas
**[3:45]** performance of the dev set is only 1% worse as performance on the training set.
**[3:49]** So this algorithm has a problem of high bias because it's not even training,
**[3:53]** it's not even fitting the training set well.
**[3:56]** This is similar to the leftmost plot we had on the previous slide.
**[4:00]** Now here's another example.
**[4:03]** Let's say that you have 15% trading set error.
**[4:06]** So that's pretty high bias.
**[4:08]** But when you evaluate on a dev set, it does even worse., maybe it does 30%.
**[4:13]** In this case, I would diagnose this algorithm as having high bias
**[4:18]** because it's not doing that well on the trading set and high variance.
**[4:24]** So this is really the worst of both worlds.
**[4:28]** And one last example, if you have 0.5 training set error and 1% dev set error.
**[4:34]** Then maybe our users are quite happy that you have a cad costly with only 1% error,
**[4:41]** then this would have low bias and low variance.
**[4:45]** One subtlety that I'll just briefly mention, but
**[4:48]** we'll leave to a later video to discuss in detail.
**[4:50]** Is that this analysis is predicated on the assumption that human
**[4:55]** level performance gets nearly 0% error.
**[4:59]** Or more generally they're the optimal error, sometimes called Bayes error for
**[5:05]** the so the bayesian optimal error is nearly 0%.
**[5:10]** I don't want to go into detail on this in this particular video.
**[5:13]** But it turns out that if the optimal error or the Bayes error were much higher,
**[5:18]** say it were 15%.
**[5:19]** Then if you look at this classifier, 15% is actually perfectly reasonable for
**[5:24]** training set.
**[5:25]** And you wouldn't say it as high bias and also have pretty low variance.
**[5:30]** So the case of how to analyze bias and
**[5:33]** variance when no classifier can do very well.
**[5:36]** For example, if you have really blurry images so
**[5:40]** that even a human or just no system could possibly do very well.
**[5:46]** Then maybe Bayes error is much higher.
**[5:49]** And then there's some details of how this analysis will change.
**[5:52]** But leaving aside this subtlety for now,
**[5:55]** the takeaway is that by looking at your trading set error.
**[5:59]** You can get a sense of how well you're fitting at least the training data.
**[6:04]** And so that tells you if you have a bias problem.
**[6:06]** And then looking at how much higher your error goes when you go from the training
**[6:11]** set to the dev set.
**[6:13]** That should give you a sense of how bad is the variance problem.
**[6:16]** So are you doing a good job generalizing from the training set to the dev set that
**[6:21]** gives you a sense of your variance?
**[6:22]** All this is under the assumption that the Bayes error is quite small and
**[6:26]** that your train and your death sets are drawn from the same distribution.
**[6:30]** If those assumptions are violated, there's more sophisticated analysis you could do,
**[6:34]** which we'll talk about in the later video.
**[6:36]** Now, on the previous slide you saw what high bias, high variance looks like, and
**[6:41]** I guess you have the sense of what a good classifier looks like.
**[6:44]** What does high bias and high variance looks like?
**[6:48]** It's kind of the worst of both worlds.
**[6:50]** So you remember we said that a classifier like this,
**[6:53]** a linear classifier, has high bias because it under fits the data.
**[6:58]** So this would be a classifier that is mostly linear and
**[7:01]** therefore under fits the data.
**[7:03]** We'll join this in purple.
**[7:05]** But if somehow your classifier does some weird things,
**[7:09]** then it's actually overfitting parts of the data as well.
**[7:14]** So the classifier that I drew in purple has both high bias and high variance.
**[7:19]** There's high bias because by being a mostly linear classifier,
**[7:24]** it's just not fitting this quadratic light shape that well.
**[7:28]** But by having too much flexibility in the middle, it somehow gets this example.
**[7:32]** And this example overfits those two examples as well.
**[7:36]** So this classifier kind of has high bias because it was mostly linear, but
**[7:40]** you needed maybe a curve function, a quadratic function.
**[7:43]** And it has high variance because it had too much flexibility to fit those two
**[7:48]** mislabeled outlier examples in the middle as well.
**[7:52]** In case this seems contrived, well, it is.
**[7:54]** This example is a little bit contrived in two dimensions, but
**[7:57]** with very high dimensional inputs.
**[7:59]** You actually do get things with high bias in some regions and
**[8:02]** high variance in some regions.
**[8:04]** And so it is possible to get cross files like this in high dimensional inputs
**[8:09]** that seem less contrived.
**[8:11]** So, to summarize, you've seen how by looking at your algorithm's error
**[8:15]** on the training set and your algorithm's error on the dev set.
**[8:19]** You can try to diagnose whether it has problem of high bias or high variance, or
**[8:23]** maybe both, or maybe neither.
**[8:25]** And depending on whether your algorithm suffers from bias or variance,
**[8:28]** it turns out that there are different things you could try.
**[8:31]** So in the next video, I want to present to you what I call a basic recipe for
**[8:36]** machine learning.
**[8:37]** That lets you more systematically try to improve your algorithm depending on
**[8:41]** whether as high bias or high variance issues.
**[8:44]** So let's go on to the next video.
