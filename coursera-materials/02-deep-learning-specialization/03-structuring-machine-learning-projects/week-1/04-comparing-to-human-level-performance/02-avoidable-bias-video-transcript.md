---
type: video-transcript
specialization: Deep Learning Specialization
course: Structuring Machine Learning Projects
week: 1
section: Comparing to Human-level Performance
item_title: Avoidable Bias
duration: 7 min
source_url: https://www.coursera.org/learn/machine-learning-projects/lecture/LG12R/avoidable-bias
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Avoidable Bias — Transcript

**[0:02]** We talked about how you want your learning algorithm to do well on the training set but
**[0:07]** sometimes you don't actually want to do too
**[0:10]** well and knowing what human level performance is,
**[0:12]** can tell you exactly how well
**[0:15]** but not too well you want your algorithm to do on the training set.
**[0:18]** Let me show you what I mean.
**[0:19]** We have used Cat classification a lot and given a picture,
**[0:24]** let's say humans have near-perfect accuracy so the human level error is one percent.
**[0:32]** In that case, if your learning algorithm achieves
**[0:34]** 8 percent training error and 10 percent dev error,
**[0:38]** then maybe you want it to do better on the training set.
**[0:44]** So the fact that there's a huge gap between how well your algorithm does on
**[0:49]** your training set versus how humans do
**[0:52]** shows that your algorithm isn't even fitting the training set well.
**[0:55]** So in terms of tools to reduce bias or variance,
**[0:59]** in this case I would say focus on reducing bias.
**[1:03]** So you want to do things like train a bigger neural network or run training set longer,
**[1:09]** just try to do better on the training set.
**[1:12]** But now let's look at the same training error and dev
**[1:15]** error and imagine that human level performance was not 1%.
**[1:19]** So this copy is over but you know in
**[1:22]** a different application or maybe on a different data set,
**[1:25]** let's say that human level error is actually 7.5%.
**[1:30]** Maybe the images in your data set are so blurry that even humans
**[1:33]** can't tell whether there's a cat in this picture.
**[1:37]** This example is maybe slightly contrived because humans
**[1:41]** are actually very good at looking at pictures and telling if there's a cat in it or not.
**[1:44]** But for the sake of this example,
**[1:46]** let's say your data sets images are
**[1:48]** so blurry or so low resolution that even humans get 7.5% error.
**[1:54]** In this case, even though
**[1:56]** your training error and dev error are the same as the other example,
**[2:00]** you see that maybe you're actually doing just fine on the training set.
**[2:04]** It's doing only a little bit worse than human level performance.
**[2:07]** And in this second example,
**[2:10]** you would maybe want to focus on reducing this component,
**[2:14]** reducing the variance in your learning algorithm.
**[2:19]** So you might try regularization to try to bring
**[2:21]** your dev error closer to your training error for example.
**[2:25]** So in the earlier course's discussion on bias and variance,
**[2:29]** we were mainly assuming that there were tasks where Bayes error is nearly zero.
**[2:36]** So to explain what just happened here,
**[2:39]** for our Cat classification example,
**[2:42]** think of human level error as
**[2:47]** a proxy or as a estimate for Bayes error or for Bayes optimal error.
**[2:56]** And for computer vision tasks,
**[2:58]** this is a pretty reasonable proxy because humans are actually very good at
**[3:02]** computer vision and so whatever a human can do is maybe not too far from Bayes error.
**[3:08]** By definition, human level error is worse than
**[3:11]** Bayes error because nothing could be better than
**[3:14]** Bayes error but human level error might not be too far from Bayes error.
**[3:19]** So the surprising thing we saw here is that depending on what human level error is
**[3:25]** or really this is really approximately Bayes error or so we assume it to be,
**[3:31]** but depending on what we think is achievable,
**[3:35]** with the same training error and dev error in these two cases,
**[3:40]** we decided to focus on bias reduction tactics or on variance reduction tactics.
**[3:47]** And what happened is in the example on the left,
**[3:51]** 8% training error is really high when you think you could get it down
**[3:55]** to 1% and so bias reduction tactics could help you do that.
**[4:01]** Whereas in the example on the right,
**[4:02]** if you think that Bayes error is 7.5%
**[4:07]** and here we're using human level error as an estimate or as a proxy for Bayes error,
**[4:12]** but you think that Bayes error is
**[4:13]** close to seven point five percent then you know there's not
**[4:15]** that much headroom for reducing your training error further down.
**[4:20]** You don't really want it to be that much better than 7.5% because you could achieve
**[4:24]** that only by maybe starting to over fit the training set,
**[4:29]** and instead, there's much more room for improvement
**[4:32]** in terms of taking this 2% gap and trying to
**[4:36]** reduce that by using
**[4:38]** variance reduction techniques such as regularization or maybe getting more training data.
**[4:43]** So to give these things a couple of names,
**[4:47]** this is not widely used terminology but I
**[4:50]** found this useful terminology and a useful way of thinking about it,
**[4:54]** which is I'm going to call the difference between Bayes error or
**[4:58]** approximation of Bayes error and the training error to be the avoidable bias.
**[5:05]** So what you want is to maybe keep improving your training performance
**[5:11]** until you get down to Bayes error but you don't
**[5:14]** actually want to do better than Bayes error.
**[5:16]** You can't actually do better than Bayes error unless you're overfitting.
**[5:20]** And this, the difference between your training area and the dev error,
**[5:24]** there's a measure still of the variance problem of your algorithm.
**[5:29]** And the term avoidable bias acknowledges that there's some bias or
**[5:35]** some minimum level of error that you just
**[5:38]** cannot get below which is that if Bayes error is 7.5%,
**[5:42]** you don't actually want to get below that level of error.
**[5:46]** So rather than saying that if you're training error is 8%,
**[5:50]** then the 8% is a measure of bias in this example,
**[5:53]** you're saying that the avoidable bias is maybe 0.5% or 0.5% is a measure of
**[6:01]** the avoidable bias whereas 2% is a measure of the variance and
**[6:06]** so there's much more room in reducing this 2% than in reducing this 0.5%.
**[6:11]** Whereas in contrast in the example on the left,
**[6:14]** this 7% is a measure of the avoidable bias,
**[6:20]** whereas 2% is a measure of how much variance you have.
**[6:24]** And so in this example on the left,
**[6:25]** there's much more potential in focusing on reducing that avoidable bias.
**[6:31]** So in this example,
**[6:33]** understanding human level error,
**[6:35]** understanding your estimate of Bayes error really
**[6:38]** causes you in different scenarios to focus on different tactics,
**[6:42]** whether bias avoidance tactics or variance avoidance tactics.
**[6:45]** There's quite a lot more nuance in how you factor in
**[6:48]** human level performance into how you make decisions in choosing what to focus on.
**[6:53]** Thus in the next video, go deeper into
**[6:55]** understanding of what human level performance really means.
