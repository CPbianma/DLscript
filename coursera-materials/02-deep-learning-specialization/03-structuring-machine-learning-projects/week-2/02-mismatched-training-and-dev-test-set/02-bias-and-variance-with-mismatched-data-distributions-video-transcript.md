---
type: video-transcript
specialization: Deep Learning Specialization
course: Structuring Machine Learning Projects
week: 2
section: Mismatched Training and Dev/Test Set
item_title: Bias and Variance with Mismatched Data Distributions
duration: 18 min
source_url: https://www.coursera.org/learn/machine-learning-projects/lecture/ht85t/bias-and-variance-with-mismatched-data-distributions
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Bias and Variance with Mismatched Data Distributions — Transcript

**[0:00]** Estimating the bias and variance
**[0:01]** of your learning algorithm really helps you prioritize what to work on next.
**[0:06]** But the way you analyze bias and variance changes when your training set
**[0:11]** comes from a different distribution than your dev and test sets.
**[0:14]** Let's see how.
**[0:16]** Let's keep using our cat classification example and
**[0:19]** let's say humans get near perfect performance on this.
**[0:22]** So, Bayes error, or Bayes optimal error, we know is nearly 0% on this problem.
**[0:28]** So, to carry out error analysis you usually look at the training error and
**[0:33]** also look at the error on the dev set.
**[0:37]** So let's say, in this example that your training error is 1%,
**[0:41]** and your dev error is 10%.
**[0:45]** If your dev data came from the same distribution as your training set,
**[0:49]** you would say that here you have a large variance problem,
**[0:53]** that your algorithm's just not generalizing well from the training set
**[0:56]** which it's doing well on to the dev set, which it's suddenly doing much worse on.
**[1:01]** But in the setting where your training data and your dev data comes from
**[1:05]** a different distribution, you can no longer safely draw this conclusion.
**[1:09]** In particular, maybe it's doing just fine on the dev set,
**[1:13]** it's just that the training set was really easy because it was high res,
**[1:18]** very clear images, and maybe the dev set is just much harder.
**[1:23]** So maybe there isn't a variance problem and this just reflects that
**[1:27]** the dev set contains images that are much more difficult to classify accurately.
**[1:33]** So the problem with this analysis is that when you went from the training error to
**[1:38]** the dev error, two things changed at a time.
**[1:41]** One is that the algorithm saw data in the training set but not in the dev set.
**[1:47]** Two, the distribution of data in the dev set is different.
**[1:51]** And because you changed two things at the same time, it's difficult to know of this
**[1:55]** 9% increase in error, how much of it is because the algorithm didn't
**[2:00]** see the data in the dev set, so that's some of the variance part of the problem.
**[2:04]** And how much of it, is because the dev set data is just different.
**[2:09]** So, in order to tease out these two effects, and
**[2:14]** if you didn't totally follow what these two different effects are, don't worry,
**[2:17]** we will go over it again in a second.
**[2:19]** But in order to tease out these two effects it will be useful to define a new
**[2:23]** piece of data which we'll call the training-dev set.
**[2:26]** So, this is a new subset of data,
**[2:29]** which we carve out that should have the same distribution as training sets, but
**[2:34]** you don't explicitly train your neural network on this.
**[2:37]** So here's what I mean.
**[2:40]** Previously we had set up some training sets and
**[2:45]** some dev sets and some test sets as follows.
**[2:50]** And the dev and test sets have the same distribution, but
**[2:53]** the training sets will have some different distribution.
**[2:56]** What we're going to do is randomly shuffle the training sets and then carve out just
**[3:01]** a piece of the training set to be the training-dev set.
**[3:09]** So just as the dev and test set have the same distribution, the training set and
**[3:14]** the training-dev set, also have the same distribution.
**[3:21]** But, the difference is that now you train your neural network,
**[3:24]** just on the training set proper.
**[3:27]** You won't let the neural network,
**[3:29]** you won't run that obligation on the training-dev portion of this data.
**[3:34]** To carry out error analysis,
**[3:36]** what you should do is now look at the error of your classifier
**[3:39]** on the training set, on the training-dev set, as well as on the dev set.
**[3:44]** So let's say in this example that your training error is 1%.
**[3:53]** And let's say the error on the training-dev set is 9%,
**[4:00]** and the error on the dev set is 10%, same as before.
**[4:08]** What you can conclude from this is that when you went from
**[4:13]** training data to training dev data the error really went up a lot.
**[4:17]** And only the difference between the training data and the training-dev
**[4:22]** data is that your neural network got to sort the first part of this.
**[4:27]** It was trained explicitly on this, but
**[4:30]** it wasn't trained explicitly on the training-dev data.
**[4:34]** So this tells you that you have a variance problem.
**[4:40]** Because the training-dev error was measured on data that comes from the same
**[4:44]** distribution as your training set.
**[4:46]** So you know that even though your neural network does well in a training set,
**[4:50]** it's just not generalizing well to data
**[4:53]** in the training-dev set which comes from the same distribution, but it's just not
**[4:58]** generalizing well to data from the same distribution that it hadn't seen before.
**[5:04]** So in this example we have really a variance problem.
**[5:09]** Let's look at a different example.
**[5:11]** Let's say the training error is 1%, and the training-dev error is 1.5%,
**[5:17]** but when you go to the dev set your error is 10%.
**[5:21]** So now, you have actually a pretty low variance problem,
**[5:24]** because when you went from training data that you've seen to the training-dev data
**[5:29]** that the neural network has not seen, the error increases only a little bit, but
**[5:34]** then it really jumps when you go to the dev set.
**[5:37]** So this is a data mismatch problem, where data mismatched.
**[5:44]** So this is a data mismatch problem,
**[5:51]** because your learning algorithm was not trained explicitly on data from
**[5:55]** training-dev or dev, but these two data sets come from different distributions.
**[6:00]** But whatever algorithm it's learning,
**[6:01]** it works great on training-dev but it doesn't work well on dev.
**[6:06]** So somehow your algorithm has learned to do well on a different distribution
**[6:10]** than what you really care about, so we call that a data mismatch problem.
**[6:17]** Let's just look at a few more examples.
**[6:20]** I'll write this on the next row since I'm running out of space on top.
**[6:24]** So Training error, Training-Dev error, and Dev error.
**[6:33]** Let's say that training error is 10%,
**[6:37]** training-dev error is 11%, and dev error is 12%.
**[6:42]** Remember that human level proxy for Bayes error
**[6:46]** is roughly 0%.
**[6:50]** So if you have this type of performance, then you really have a bias,
**[6:56]** an avoidable bias problem, because you're doing much worse than human level.
**[7:02]** So this is really a high bias setting.
**[7:07]** And one last example.
**[7:08]** If your training error is 10%, your training-dev error is 11% and
**[7:14]** your dev error is 20 %, then it looks like this actually has two issues.
**[7:19]** One, the avoidable bias is quite high,
**[7:24]** because you're not even doing that well on the training set.
**[7:26]** Humans get nearly 0% error, but you're getting 10% error on your training set.
**[7:31]** The variance here seems quite small,
**[7:38]** but this data mismatch is quite large.
**[7:43]** So for for this example I will say, you have a large bias or
**[7:48]** avoidable bias problem as well as a data mismatch problem.
**[7:56]** So let's take what we've done on this slide and
**[7:59]** write out the general principles.
**[8:02]** The key quantities I would look at are human level error,
**[8:09]** your training set error,
**[8:14]** your training-dev set error.
**[8:21]** So that's the same distribution as the training set, but
**[8:23]** you didn't train explicitly on it.
**[8:25]** Your dev set error, and depending on the differences between these errors,
**[8:30]** you can get a sense of how big is the avoidable bias, the variance,
**[8:35]** the data mismatch problems.
**[8:38]** So let's say that human level error is 4%.
**[8:40]** Your training error is 7%.
**[8:43]** And your training-dev error is 10%.
**[8:46]** And your dev error is 12%.
**[8:50]** So this gives you a sense of the avoidable bias.
**[8:55]** because you know, you'd like your algorithm to do at least as well or
**[8:58]** approach human level performance maybe on the training set.
**[9:01]** This is a sense of the variance.
**[9:04]** So how well do you generalize from the training set to the training-dev set?
**[9:10]** This is the sense of how much of a data mismatch problem have you have.
**[9:15]** And technically you could also add one more thing,
**[9:18]** which is the test set performance, and we'll write test error.
**[9:21]** You shouldn't be doing development on your test set because you don't want to overfit
**[9:24]** your test set.
**[9:25]** But if you also look at this, then this gap here tells you the degree
**[9:31]** of overfitting to the dev set.
**[9:36]** So if there's a huge gap between your dev set performance and
**[9:41]** your test set performance, it means you maybe overtuned to the dev set.
**[9:45]** And so maybe you need to find a bigger dev set, right?
**[9:49]** So remember that your dev set and your test set come from the same distribution.
**[9:53]** So the only way for there to be a huge gap here, for it to do much better on the dev
**[9:57]** set than the test set, is if you somehow managed to overfit the dev set.
**[10:01]** And if that's the case, what you might consider doing is going back and
**[10:04]** just getting more dev set data.
**[10:06]** Now, I've written these numbers,
**[10:08]** as you go down the list of numbers, always keep going up.
**[10:13]** Here's one example of numbers that doesn't always go up,
**[10:17]** maybe human level performance is 4%, training error is 7%,
**[10:22]** training-dev error is 10%, but let's say that we go to the dev set.
**[10:26]** You find that you actually, surprisingly, do much better on the dev set.
**[10:30]** Maybe this is 6%, 6% as well.
**[10:36]** So you have seen effects like this, working on for
**[10:41]** example a speech recognition task, where the training data
**[10:45]** turned out to be much harder than your dev set and test set.
**[10:48]** So these two were evaluated on your training set distribution and
**[10:53]** these two were evaluated on your dev/test set distribution.
**[10:57]** So sometimes if your dev/test set distribution is much easier for
**[11:02]** whatever application you're working on then these numbers can actually go down.
**[11:07]** So if you see funny things like this,
**[11:08]** there's an even more general formulation of this analysis that might be helpful.
**[11:13]** Let me quickly explain that on the next slide.
**[11:17]** So, let me motivate this using the speech
**[11:21]** activated rear-view mirror example.
**[11:26]** It turns out that the numbers we've been writing down can be placed into
**[11:31]** a table where on the horizontal axis, I'm going to place different data sets.
**[11:36]** So for example, you might have data from your general speech recognition task.
**[11:43]** So you might have a bunch of data that you just collected from a lot
**[11:48]** of speech recognition problems you worked on from small speakers,
**[11:51]** data you have purchased and so on.
**[11:53]** And then you all have the rear view mirror specific speech data,
**[12:00]** recorded inside the car.
**[12:04]** So on this x axis on the table, I'm going to vary the data set.
**[12:09]** On this other axis, I'm going to label different ways or
**[12:16]** algorithms for examining the data.
**[12:18]** So first, there's human level performance,
**[12:21]** which is how accurate are humans on each of these data sets?
**[12:27]** Then there is the error on the
**[12:31]** examples that your neural network has trained on.
**[12:38]** And then finally there's error on the examples
**[12:43]** that your neural network has not trained on.
**[12:50]** So turns out that what we're calling on a human level on the previous slide,
**[12:55]** there's the number that goes in this box,
**[12:59]** which is how well do humans do on this category of data.
**[13:03]** Say data from all sorts of speech recognition tasks,
**[13:06]** the 500,000 utterances that you could into your training set.
**[13:10]** And the example in the previous slide is this 4%.
**[13:13]** This number here was our, maybe the training error.
**[13:23]** Which in the example in the previous slide was 7%
**[13:29]** Right, if you're learning algorithm has seen this example, performed gradient
**[13:33]** descent on this example, and this example came from your training set distribution,
**[13:37]** or some general speech recognition distribution.
**[13:39]** How well does your algorithm do on the example it has trained on?
**[13:45]** Then here is the training-dev set error.
**[13:53]** It's usually a bit higher, which is for data from this distribution,
**[13:58]** from general speech recognition, if your algorithm did not train explicitly on
**[14:02]** some examples from this distribution, how well does it do?
**[14:05]** And that's what we call the training dev error.
**[14:10]** And then if you move over to the right, this box here
**[14:14]** is the dev set error, or maybe also the test set error.
**[14:20]** Which was 6% in the example just now.
**[14:25]** And dev and test error, it's actually technically two numbers, but
**[14:28]** either one could go into this box here.
**[14:32]** And this is if you have data from your rearview mirror, from actually recorded in
**[14:37]** the car from the rearview mirror application, but your neural network did
**[14:41]** not perform back propagation on this example, what is the error?
**[14:46]** So what we're doing in the analysis in the previous slide was look at
**[14:51]** differences between these two numbers, these two numbers, and these two numbers.
**[14:57]** And this gap here is a measure of avoidable bias.
**[15:03]** This gap here is a measure of variance, and
**[15:08]** this gap here was a measure of data mismatch.
**[15:13]** And it turns out that it could be useful to also throw in
**[15:17]** the remaining two entries in this table.
**[15:21]** And so if this turns out to be also 6%, and
**[15:25]** the way you get this number is you ask some humans to label their rearview mirror speech data
**[15:30]** and just measure how good humans are at this task.
**[15:33]** And maybe this turns out also to be 6%.
**[15:35]** And the way you do that is you take some rearview mirror speech data,
**[15:39]** put it in the training set so the neural network learns on it as well, and
**[15:42]** then you measure the error on that subset of the data.
**[15:46]** But if this is what you get, then, well, it turns out that you're actually already
**[15:50]** performing at the level of humans on this rearview mirror speech data, so
**[15:54]** maybe you're actually doing quite well on that distribution of data.
**[15:58]** When you do this more subsequent analysis, it doesn't always give you one
**[16:03]** clear path forward, but sometimes it just gives you additional insights as well.
**[16:07]** So for example, comparing these two numbers in this case tells us that for
**[16:12]** humans, the rearview mirror speech data is actually harder than for
**[16:16]** general speech recognition, because humans get 6% error, rather than 4% error.
**[16:21]** But then looking at these differences as well may help you
**[16:25]** understand bias and variance and data mismatch problems in different degrees.
**[16:30]** So this more general formulation is something I've used a few times.
**[16:35]** I've not used it, but for a lot of problems you find that examining
**[16:41]** this subset of entries, kind of looking at this difference and this difference and
**[16:46]** this difference, that that's enough to point you in a pretty promising direction.
**[16:51]** But sometimes filling out this whole table can give you additional insights.
**[16:55]** Finally, we've previously talked a lot about ideas for addressing bias.
**[17:02]** Talked a lot about techniques on addressing variance, but
**[17:05]** how do you address data mismatch?
**[17:08]** In particular training on data that comes from different distribution
**[17:12]** that your dev and test set can get you more data and
**[17:15]** really help your learning algorithm's performance.
**[17:17]** But rather than just bias and variance problems,
**[17:20]** you now have this new potential problem of data mismatch.
**[17:24]** What are some good ways that you could use to address data mismatch?
**[17:28]** I'll be honest and say there actually aren't great or
**[17:30]** at least not very systematic ways to address data mismatch.
**[17:34]** But there are some things you could try that could help.
**[17:36]** Let's take a look at them in the next video.
**[17:38]** So what we've seen is that by using training data that can come from
**[17:43]** a different distribution as a dev and test set, this could give you a lot more data
**[17:47]** and therefore help the performance of your learning algorithm.
**[17:50]** But instead of just having bias and variance as two potential problems,
**[17:55]** you now have this third potential problem, data mismatch.
**[17:58]** So what if you perform error analysis and conclude that data mismatch
**[18:02]** is a huge source of error, how can you go about addressing that?
**[18:05]** It turns out that unfortunately there are super systematic ways
**[18:09]** to address data mismatch, but there are a few things you can try that could help.
**[18:14]** Let's take a look at them in the next video.
