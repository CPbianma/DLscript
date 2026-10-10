---
type: video-transcript
specialization: Machine Learning Specialization
course: "Supervised Machine Learning: Regression and Classification"
week: 2
section: Gradient descent in practice
item_title: Feature scaling part 2
duration: 8 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/akapu/feature-scaling-part-2
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Feature scaling part 2 — Transcript

**[0:01]** Let's look at how you can implement feature scaling,
**[0:04]** to take features that take on
**[0:06]** very different ranges of values and
**[0:08]** skill them to have comparable ranges
**[0:10]** of values to each other.
**[0:11]** How do you actually scale features?
**[0:14]** Well, if x_1 ranges from 3-2,000,
**[0:18]** one way to get a scale version of x_1 is to take
**[0:22]** each original x1_ value and divide by 2,000,
**[0:26]** the maximum of the range.
**[0:28]** The scale x_1 will range from 0.15 up to one.
**[0:34]** Similarly, since x_2 ranges from 0-5,
**[0:38]** you can calculate a scale version of x_2 by
**[0:41]** taking each original x_2 and dividing by five,
**[0:44]** which is again the maximum.
**[0:46]** So the scale is x_2 will now range from 0-1.
**[0:51]** If you plot the scale to x_1 and x_2 on a graph,
**[0:56]** it might look like this.
**[0:58]** In addition to dividing by the maximum,
**[1:01]** you can also do what's called mean normalization.
**[1:04]** What this looks like is,
**[1:06]** you start with the original features and then you
**[1:09]** re-scale them so that both
**[1:10]** of them are centered around zero.
**[1:13]** Whereas before they only had values greater than zero,
**[1:16]** now they have both negative and positive values
**[1:20]** that may be usually between negative one and plus one.
**[1:24]** To calculate the mean normalization of x_1,
**[1:28]** first find the average,
**[1:30]** also called the mean of x_1 on your training set,
**[1:33]** and let's call this mean Mu_1,
**[1:35]** with this being the Greek alphabets Mu.
**[1:39]** For example, you may find that the average of feature 1,
**[1:43]** Mu_1 is 600 square feet.
**[1:46]** Let's take each x_1,
**[1:48]** subtract the mean Mu_1,
**[1:51]** and then let's divide by the difference 2,000 minus 300,
**[1:56]** where 2,000 is the maximum and 300 the minimum,
**[2:01]** and if you do this,
**[2:02]** you get the normalized x_1 to
**[2:05]** range from negative 0.18-0.82.
**[2:10]** Similarly, to mean normalized x_2,
**[2:13]** you can calculate the average of feature 2.
**[2:16]** For instance, Mu_2 may be 2.3.
**[2:20]** Then you can take each x_2,
**[2:22]** subtract Mu_2 and divide by 5 minus 0.
**[2:27]** Again, the max 5 minus the mean, which is 0.
**[2:32]** The mean normalized x_2 now ranges
**[2:35]** from negative 0.46-0 54.
**[2:41]** If you plot the training data
**[2:43]** using the mean normalized x_1 and x_2,
**[2:45]** it might look like this.
**[2:47]** There's one last common re-scaling
**[2:51]** method call Z-score normalization.
**[2:54]** To implement Z-score normalization,
**[2:56]** you need to calculate something called
**[2:58]** the standard deviation of each feature.
**[3:00]** If you don't know what the standard deviation is,
**[3:02]** don't worry about it, you won't
**[3:04]** need to know it for this course.
**[3:06]** Or if you've heard of
**[3:07]** the normal distribution or the bell-shaped curve,
**[3:10]** sometimes also called the Gaussian distribution,
**[3:12]** this is what the standard deviation
**[3:14]** for the normal distribution looks like.
**[3:17]** But if you haven't heard of this,
**[3:18]** you don't need to worry about that either.
**[3:20]** But if you do know what is the standard deviation,
**[3:23]** then to implement a Z-score normalization,
**[3:26]** you first calculate the mean Mu,
**[3:29]** as well as the standard deviation,
**[3:31]** which is often denoted by
**[3:33]** the lowercase Greek alphabet Sigma of each feature.
**[3:38]** For instance, maybe feature 1 has
**[3:41]** a standard deviation of 450 and mean 600,
**[3:46]** then to Z-score normalize x_1,
**[3:49]** take each x_1,
**[3:51]** subtract Mu_1, and
**[3:53]** then divide by the standard deviation,
**[3:56]** which I'm going to denote as Sigma 1.
**[3:59]** What you may find is that the Z-score normalized
**[4:03]** x_1 now ranges from negative 0.67-3.1.
**[4:09]** Similarly, if you calculate the
**[4:12]** second features standard deviation
**[4:14]** to be 1.4 and mean to be 2.3,
**[4:19]** then you can compute x_2 minus Mu_2 divided by Sigma_2,
**[4:25]** and in this case,
**[4:26]** the Z-score normalized by x_2 might now
**[4:30]** range from negative 1.6-1.9.
**[4:36]** If you plot the training data on
**[4:37]** the normalized x_1 and x_2 on a graph,
**[4:40]** it might look like this.
**[4:42]** As a rule of thumb,
**[4:44]** when performing feature scaling,
**[4:47]** you might want to aim for getting
**[4:48]** the features to range from maybe anywhere
**[4:51]** around negative one to somewhere around
**[4:54]** plus one for each feature x.
**[4:57]** But these values, negative one and
**[5:00]** plus one can be a little bit loose.
**[5:02]** If the features range from negative three to plus
**[5:06]** three or negative 0.3 to plus 0.3,
**[5:10]** all of these are completely okay.
**[5:12]** If you have a feature x_1 that
**[5:14]** winds up being between zero and three,
**[5:17]** that's not a problem.
**[5:18]** You can re-scale it if you want,
**[5:21]** but if you don't re-scale it,
**[5:22]** it should work okay too.
**[5:24]** Or if you have a different feature, x_2,
**[5:27]** whose values are between negative
**[5:29]** 2 and plus 0.5, again,
**[5:32]** that's okay, no harm re-scaling it,
**[5:34]** but it might be okay if you leave it alone as well.
**[5:38]** But if another feature, like x_3 here,
**[5:41]** ranges from negative 100 to plus 100,
**[5:45]** then this takes on a very different range of values,
**[5:48]** say something from around negative one to plus one.
**[5:51]** You're probably better off re-scaling this feature x_3 so
**[5:56]** that it ranges from something
**[5:57]** closer to negative one to plus one.
**[6:01]** Similarly, if you have a feature
**[6:04]** x_4 that takes on really small values,
**[6:07]** say between negative 0.001 and plus 0.001,
**[6:11]** then these values are so small.
**[6:14]** That means you may want to re-scale it as well.
**[6:18]** Finally, what if your feature x_5,
**[6:21]** such as measurements of
**[6:23]** a hospital patients by the temperature
**[6:26]** ranges from 98.6-105 degrees Fahrenheit?
**[6:32]** In this case, these values are around 100,
**[6:35]** which is actually pretty large
**[6:37]** compared to other scale features,
**[6:40]** and this will actually cause
**[6:41]** gradient descent to run more slowly.
**[6:44]** In this case, feature re-scaling will likely help.
**[6:47]** There's almost never any harm to
**[6:50]** carrying out feature re-scaling.
**[6:52]** When in doubt, I encourage you to just carry it out.
**[6:56]** That's it for feature scaling.
**[6:58]** With this little technique,
**[6:59]** you'll often be able to get
**[7:01]** gradient descent to run much faster.
**[7:04]** That's features scaling.
**[7:07]** With or without feature scaling,
**[7:10]** when you run gradient descent,
**[7:11]** how can you know, how can you check
**[7:13]** if gradient descent is really working?
**[7:15]** If it is finding you
**[7:17]** the global minimum or something close to it.
**[7:19]** In the next video,
**[7:21]** let's take a look at how to recognize
**[7:23]** if gradient descent is converging,
**[7:26]** and then in the video after that,
**[7:28]** this will lead to discussion of how to choose
**[7:30]** a good learning rate for gradient descent.
