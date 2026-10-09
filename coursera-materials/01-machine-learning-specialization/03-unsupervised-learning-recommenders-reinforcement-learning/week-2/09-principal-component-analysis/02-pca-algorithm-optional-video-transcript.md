---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 2
section: Principal Component Analysis
item_title: PCA algorithm (optional)
duration: 18 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/mqAH4/pca-algorithm-optional
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# PCA algorithm (optional) — Transcript

**[0:01]** How does PCA work?
**[0:04]** If you have a dataset with two features, x_1 and x_2.
**[0:09]** Initially, your data is plotted or
**[0:11]** represented using axes x_1 and x_2.
**[0:15]** But you want to replace
**[0:17]** these two features with just one feature.
**[0:20]** How can you choose a new axis,
**[0:23]** let's call it the z-axis,
**[0:24]** that is somehow a good feature for capturing,
**[0:28]** of representing the data?
**[0:30]** Let's take a look at how PCA does this.
**[0:33]** Here's the data sets with five training examples.
**[0:38]** Remember, this is an unsupervised learning algorithm
**[0:42]** so we just have x_1 and x_2,
**[0:45]** there is no label y.
**[0:48]** An example here like this may have coordinates x_1
**[0:52]** equals 10 and x_2 equals 8.
**[1:02]** If we don't want to use the x_1, x_2 axes,
**[1:06]** how can we pick some different axis with which to
**[1:11]** capture what's in the data or with
**[1:13]** which to represent the data?
**[1:16]** One note on preprocessing,
**[1:18]** before applying the next few steps of PCA the features
**[1:22]** should be first normalized to have
**[1:24]** zero mean and I've already done that here.
**[1:30]** If the features x_1 and
**[1:33]** x_2 take on very different scales,
**[1:36]** for example, if you remember our housing example,
**[1:39]** if x_1 was the size of a house in square feet,
**[1:43]** and x_2 was the number of bedrooms then
**[1:46]** x_1 could be 1,000 or a couple of thousand,
**[1:50]** whereas x_2 is a small number.
**[1:53]** If the features take on very different scales,
**[1:57]** then you will first perform feature
**[2:00]** scaling before applying the next few steps of PCA.
**[2:03]** Assuming the features have been
**[2:06]** normalized to have zero mean,
**[2:08]** so subtract the mean from
**[2:09]** each feature and then maybe apply
**[2:12]** feature scaling as well
**[2:14]** so the ranges are not too far apart.
**[2:17]** What does PCA do next?
**[2:19]** To examine what PCA does,
**[2:21]** let me remove the x_1 and x_2 axes so
**[2:24]** that we're just left with the five training examples.
**[2:28]** This dot here represents the origin.
**[2:31]** The position of zero on this plot still.
**[2:35]** What we have to do now with PCA is,
**[2:38]** pick one axis instead
**[2:40]** of the two axes that we had previously
**[2:43]** with which to capture
**[2:45]** what's important about these five examples.
**[2:48]** If we were to choose this axis to be our new z-axis,
**[2:54]** it's actually the same as the x_1 axis
**[2:56]** just for this example.
**[2:58]** Then what we're saying is that for this example,
**[3:01]** we're going to just capture this value,
**[3:04]** this coordinate on the z-axis.
**[3:06]** For the second example,
**[3:08]** we're going to capture this value,
**[3:10]** and then this will capture this value,
**[3:14]** and so on for all five examples.
**[3:18]** Another way of saying this is that
**[3:20]** we're going to take each of these examples
**[3:22]** and project it down to a point on the z-axis.
**[3:27]** The word project refers to that
**[3:30]** you're taking this example and bringing it to
**[3:33]** the z-axis using this line segment
**[3:36]** that's at a 90-degree angle to the z-axis.
**[3:39]** This little box here is used to denote that
**[3:42]** this line segment is at 90 degrees to the z-axis.
**[3:46]** The term project just means you're
**[3:48]** taking a point and finding
**[3:51]** this corresponding point on the z-axis
**[3:53]** using this line segment that's at 90 degrees.
**[3:57]** Picking this direction as a z-axis is not a bad choice,
**[4:02]** but there's some even better choices.
**[4:04]** This choice isn't too bad because
**[4:07]** when you project your examples onto the z-axis,
**[4:10]** you still capture quite a lot of the spread of the data.
**[4:14]** These five points here,
**[4:16]** they're pretty spread apart
**[4:18]** so you're still capturing a lot of
**[4:19]** the variation or a lot of
**[4:21]** the variance in the original dataset.
**[4:24]** By that I mean these five points are quite spread
**[4:28]** apart and so the variance
**[4:32]** or variation among these five points,
**[4:35]** the projections of the data onto
**[4:36]** the z-axis is decently large.
**[4:39]** What that means is we're still capturing quite a lot
**[4:43]** of the information in the original five examples.
**[4:47]** Let's look at some other possible choices for the axis z.
**[4:52]** Here's another choice. This is
**[4:54]** actually not a great choice.
**[4:55]** But if I were to choose this as my z axis,
**[4:59]** then if I take
**[5:01]** those same five examples
**[5:03]** and project them down to the z-axis,
**[5:06]** I end up with these five points.
**[5:08]** You notice that compare it to the previous choice,
**[5:12]** these five points are quite squished together.
**[5:15]** The amount they are differing from each other,
**[5:17]** or their variance or the variation is much less.
**[5:20]** What this means is with this choice of z,
**[5:23]** you're capturing much less of the information in
**[5:27]** the original dataset because you've
**[5:30]** partially squish all five examples together.
**[5:33]** Let's look at one last choice,
**[5:36]** which is if I choose this to be the z-axis.
**[5:41]** This is actually a better choice
**[5:42]** than the previous two that we saw,
**[5:45]** because if we take
**[5:47]** the data's projections onto the z-axis,
**[5:51]** we find that these dots over here,
**[5:53]** they're actually quite far apart.
**[5:55]** We're capturing a lot of the variation,
**[5:58]** a lot of the information in the original dataset,
**[6:01]** even though we're now using
**[6:04]** just one coordinate or one number to represent or to
**[6:08]** capture each of the training examples instead
**[6:11]** of two numbers or two coordinates, X_1 and X_2.
**[6:14]** In the PCA algorithm,
**[6:16]** this axis is called the principal component.
**[6:21]** In the z-axis that when you project the data onto it,
**[6:25]** you end up with the largest possible amounts of variance.
**[6:30]** If you were to reduce the data
**[6:32]** to one axis or to one feature,
**[6:35]** this principal component is actually a good choice,
**[6:39]** and this is what PCA will do.
**[6:41]** If you want to reduce the data
**[6:43]** to one-dimensional feature,
**[6:47]** then it will choose this principal component.
**[6:50]** Let me show you a visualization of how
**[6:53]** different choices of the axis affects the projection.
**[6:58]** Here we have 10 training examples,
**[7:01]** and as we slide this slider here,
**[7:04]** and you can play with this
**[7:06]** in one of the optional labs yourself.
**[7:08]** As you slide the slider here,
**[7:10]** the angle of the z-axis changes.
**[7:14]** What you're seeing on the left is
**[7:17]** each of the examples projected via
**[7:20]** that short line segment at 90 degrees to the z-axis.
**[7:25]** Here on the right is that projection of the data,
**[7:29]** meaning the value of these 10 examples, z-coordinate.
**[7:35]** You notice that when I set the axis to about here,
**[7:39]** the points are quite squished together.
**[7:42]** So this posses less of
**[7:43]** the automation of the original data.
**[7:45]** Whereas if I set the z-axis say to this,
**[7:49]** then these points vary much more.
**[7:53]** This is capturing much more of
**[7:55]** the information in the original dataset.
**[7:58]** That's why the principal component corresponds
**[8:01]** to setting the z-axis to about here.
**[8:05]** This is the choice that PCA would make if you asked it to
**[8:08]** reduce the data to one dimension.
**[8:12]** Machine learning library, like scikit-learn,
**[8:15]** which you'll hear more about in the next video,
**[8:17]** can help you automatically find the principal component.
**[8:21]** But let's take a little bit deeper into how that works.
**[8:25]** Here are my x_1 and x_2 axis.
**[8:28]** Here's one training example with coordinates 2
**[8:33]** on the x_1 axis and three on the x_2 axis.
**[8:38]** Let's say that PCA has found
**[8:41]** this direction for the z-axis.
**[8:45]** What I'm drawing here,
**[8:47]** this little arrow is a length 1
**[8:50]** vector pointing in the direction of
**[8:53]** this z-axis that PCA will choose or that we have chosen.
**[8:59]** It turns out this length 1 vector is the vector 0.710,
**[9:04]** 0.71 rounded off a bit.
**[9:08]** It's actually 0.707 and then a bunch of other digits.
**[9:12]** Given this example with coordinates 2,3 on the x_1,
**[9:18]** x_2 axis, how do we project
**[9:21]** this example onto the z-axis?
**[9:24]** It turns out the formula for doing
**[9:27]** so is to take a dot product
**[9:30]** between the vector 2,3 and this vector 0.71, 0.71.
**[9:37]** If you do that,
**[9:39]** 2,3 dot product with 0.71,
**[9:41]** 0.71 turns out to be 2 times 0.71 plus 3 times 0.71,
**[9:49]** which is equal to 3.55.
**[9:53]** What that means is the distance from the origin
**[9:56]** of this point over here is 3.55,
**[10:02]** which means that if we were to represent
**[10:05]** or to use one number to try to capture this example,
**[10:08]** that one number is 3.55.
**[10:11]** So far, we have talked about how to use PCA to reduce
**[10:15]** data down to one dimension or down to one number.
**[10:21]** We did so by finding the principal component,
**[10:24]** also called sometimes the first principal component.
**[10:28]** In this example, we had found this as the first axis.
**[10:34]** It turns out that if you were to pick a second axis,
**[10:38]** the second axis will always be at
**[10:40]** 90 degrees to the first axis.
**[10:44]** If you were to choose even a third axis,
**[10:46]** then the third axis will be at
**[10:48]** 90 degrees to the first and the second axis.
**[10:52]** By the way, in mathematics,
**[10:55]** 90 degrees is sometimes called perpendicular.
**[10:58]** The term perpendicular just means at 90 degrees.
**[11:01]** Mathematicians will sometimes say the second axis,
**[11:05]** z_2, is at
**[11:07]** 90 degrees or is perpendicular to the first axis, z_1.
**[11:10]** If you choose additional axes,
**[11:12]** they're also at 90 degrees or perpendicular to
**[11:15]** z_1 and z_2 and to any other axes that PCA will choose.
**[11:20]** If you had 50 features and
**[11:24]** wanted to find three principal components,
**[11:29]** then if that's the first axis,
**[11:31]** the second axis will be at 90 degrees to it.
**[11:35]** Then the third axis will also be
**[11:38]** at 90 degrees to the first and the second axis.
**[11:41]** Now, one question I'm often asked is,
**[11:45]** how is PCA different from linear regression?
**[11:49]** It turns out PCA is not linear regression,
**[11:52]** is a totally different algorithm.
**[11:54]** Let me explain why.
**[11:55]** With linear regression,
**[11:58]** which is a supervised learning algorithm,
**[12:00]** you have data x and y.
**[12:03]** Here's a data set where the horizontal axis is
**[12:07]** the feature x and the vertical axis here is the label y.
**[12:12]** With linear regression you're trying to fit
**[12:15]** a straight line so that
**[12:18]** the predicted value is as
**[12:20]** close as possible to the ground truth label y.
**[12:24]** In other words, you're trying to minimize the length of
**[12:27]** these little line segments which
**[12:29]** are in the vertical direction.
**[12:30]** They just aligned with the y axis.
**[12:33]** In contrast, in PCA,
**[12:35]** there is no ground truth label y.
**[12:37]** You just have unlabeled data,
**[12:39]** X1 and X2,
**[12:41]** and furthermore, you're not trying to fit
**[12:43]** a line to use X1 to predict X2.
**[12:46]** Instead, the average treats X1 and X2 equally.
**[12:50]** We're trying to find this axis Z,
**[12:53]** that it turns out we end up
**[12:55]** making these little line segments
**[12:57]** small when you project the data onto Z.
**[13:03]** In linear regression, there is one number Y,
**[13:08]** which is given very special treatment.
**[13:11]** We're always trying to measure distance
**[13:14]** between the fitted line and Y,
**[13:17]** which is why these distances are
**[13:19]** measured just in the direction of the y-axis.
**[13:22]** Whereas in PCA, you can have a lot of features,
**[13:26]** X1, X2, maybe all the
**[13:28]** way up to X50 if you have 50 features.
**[13:31]** All 50 features are treated equally.
**[13:34]** We're just trying to find an axis
**[13:37]** Z so that when the data is projected onto the axis Z
**[13:40]** using these line segments that you still
**[13:44]** retain as much of the variance
**[13:46]** of the original data as possible.
**[13:49]** I know that when I plot these things in two-dimensions,
**[13:53]** we've just two features, which is,
**[13:55]** I can draw on a flat computer monitor.
**[13:58]** These arrows look like
**[13:59]** maybe they're a little bit similar.
**[14:02]** But when you have more than two features,
**[14:05]** which is most of the case,
**[14:06]** the difference between linear regression and
**[14:08]** PCA and what the algorithms do is very large.
**[14:11]** These algorithms are used for
**[14:12]** totally different purposes and
**[14:14]** give you very different answers.
**[14:16]** When linear regression is used to predict
**[14:18]** a target output Y and PCA is trying to take
**[14:22]** a lot of features and treat them all equally and reduce
**[14:26]** the number of axis needed to represent the data well.
**[14:30]** It turns out that maximizing
**[14:32]** the spread of these projections will
**[14:35]** correspond to minimizing the distances
**[14:39]** of these line segments,
**[14:40]** the distances to the points have to
**[14:42]** move to be projected down to Z.
**[14:44]** To illustrate the difference between
**[14:46]** linear regression and PCA in another way,
**[14:49]** if you have a data set that looks like this,
**[14:51]** linear regression, all it can do is
**[14:54]** fit a line that looks like that.
**[14:56]** Whereas if your data set looks like this,
**[14:59]** PCA will choose this to be the principal component.
**[15:02]** So you should use
**[15:04]** linear regression if you're trying
**[15:05]** to predict the value of y,
**[15:07]** and you should use PCA if you're trying to
**[15:09]** reduce the number of features in your data set,
**[15:13]** say to visualize it.
**[15:14]** Finally, before we wrap up this video,
**[15:17]** there's one more thing you could do with PCA, which is,
**[15:21]** recall this example which was at coordinates 2,3.
**[15:26]** We found that if you projected to the z-axis,
**[15:30]** you end up with 3.55.
**[15:33]** One thing you could do is if you
**[15:36]** have an example where Z equals 3.55,
**[15:39]** given just this one number Z, 3.55,
**[15:43]** can we try to figure out what was the original example?
**[15:47]** It turns out that there's a step
**[15:50]** in PCA called reconstruction,
**[15:52]** which is to try to go from this one number Z equals 3.55
**[15:57]** back to the original two numbers, X1 and X2.
**[16:03]** It turns out you don't have enough information to
**[16:05]** get back X1 and X2 exactly,
**[16:08]** but you can try to approximate it.
**[16:10]** In particular, the formula is,
**[16:13]** you would take this number 3.55,
**[16:17]** which is Z, and multiply
**[16:19]** it by the length one vector that we had just now,
**[16:21]** which is 0.71, 0.71.
**[16:24]** This ends up to be 2.52,
**[16:28]** 2.52, which is this point over here.
**[16:32]** We can approximate the original training example,
**[16:37]** which was a coordinates 2,
**[16:38]** 3 with this new point here,
**[16:40]** which is at 2.52, 2.52.
**[16:44]** The difference between the original point and
**[16:46]** the projected point is this little line segment here.
**[16:50]** In this case is not a bad approximation 2.52,
**[16:54]** 2.52 is not that far from 2, 3.
**[16:58]** With just one number,
**[17:00]** we could get a reasonable approximation to
**[17:03]** the coordinates of the original training example.
**[17:06]** This is called the reconstruction step of PCA.
**[17:11]** To summarize, the PCA algorithm looks at
**[17:14]** your original data and chooses one or more new axis,
**[17:19]** Z or maybe Z1 and Z2,
**[17:22]** to represent your data and by taking
**[17:25]** your original data set and projecting
**[17:27]** it onto your new axis or axis.
**[17:30]** This gives you a smaller set of numbers so you
**[17:33]** can plot if wished to visualize your data.
**[17:36]** You're seeing the math.
**[17:38]** Let's now take a look at how you
**[17:40]** can implement this in code.
**[17:42]** In the next video, we'll look at how you can use PCA
**[17:45]** yourself using the scikit-learn library.
**[17:48]** Let's go on to the next video.
