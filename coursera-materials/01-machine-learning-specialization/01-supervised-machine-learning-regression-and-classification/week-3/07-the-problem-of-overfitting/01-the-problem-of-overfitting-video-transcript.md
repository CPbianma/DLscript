---
type: video-transcript
specialization: Machine Learning Specialization
course: "Supervised Machine Learning: Regression and Classification"
week: 3
section: The problem of overfitting
item_title: The problem of overfitting
duration: 12 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/erGPe/the-problem-of-overfitting
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# The problem of overfitting — Transcript

**[0:01]** Now you've seen a couple
**[0:03]** of different learning algorithms,
**[0:05]** linear regression and logistic regression.
**[0:08]** They work well for many tasks.
**[0:10]** But sometimes in an application,
**[0:12]** the algorithm can run into a problem called overfitting,
**[0:16]** which can cause it to perform poorly.
**[0:18]** What I like to do in this video is
**[0:21]** to show you what is overfitting,
**[0:23]** as well as a closely-related,
**[0:25]** almost opposite problem called underfitting.
**[0:28]** In the next videos after this,
**[0:30]** I'll share with you some techniques
**[0:32]** for accuracy overfitting.
**[0:34]** In particular, there's a method called regularization.
**[0:37]** Very useful technique.
**[0:38]** I use it all the time.
**[0:40]** Then regularization will help you minimize
**[0:42]** this overfitting problem and
**[0:44]** get your learning algorithms to work much better.
**[0:47]** Let's take a look at what is overfitting?
**[0:51]** To help us understand what is overfitting.
**[0:54]** Let's take a look at a few examples.
**[0:58]** Let's go back to our original example
**[1:01]** of predicting housing prices with linear regression.
**[1:04]** Where you want to predict the price as
**[1:06]** a function of the size of a house.
**[1:09]** To help us understand what is overfitting,
**[1:12]** let's take a look at a linear regression example.
**[1:17]** I'm going to go back to our original running example
**[1:21]** of predicting housing prices with linear regression.
**[1:24]** Suppose your data-set looks like this,
**[1:28]** with the input feature x being the size of the house,
**[1:31]** and the value, y that you're
**[1:33]** trying to predict the price of the house.
**[1:35]** One thing you could do is fit
**[1:38]** a linear function to this data.
**[1:40]** If you do that, you get
**[1:43]** a straight line fit to
**[1:44]** the data that maybe looks like this.
**[1:47]** But this isn't a very good model.
**[1:49]** Looking at the data,
**[1:51]** it seems pretty clear that as
**[1:53]** the size of the house increases,
**[1:55]** the housing process flattened out.
**[1:58]** This algorithm does not fit the training data very well.
**[2:03]** The technical term for this is
**[2:06]** the model is underfitting the training data.
**[2:10]** Another term is the algorithm has high bias.
**[2:15]** You may have read in the news about
**[2:18]** some learning algorithms really,
**[2:20]** unfortunately, demonstrating bias against
**[2:23]** certain ethnicities or certain genders.
**[2:25]** In machine learning, the term bias has multiple meanings.
**[2:31]** Checking learning algorithms for bias based on
**[2:35]** characteristics such as gender or
**[2:37]** ethnicity is absolutely critical.
**[2:40]** But the term bias has
**[2:42]** a second technical meaning as well,
**[2:45]** which is the one I'm using here,
**[2:47]** which is if the algorithm has underfit the data,
**[2:50]** meaning that it's just not even able to
**[2:52]** fit the training set that well.
**[2:54]** There's a clear pattern in
**[2:56]** the training data that
**[2:57]** the algorithm is just unable to capture.
**[3:00]** Another way to think of this form of bias
**[3:04]** is as if the learning algorithm
**[3:06]** has a very strong preconception,
**[3:08]** or we say a very strong bias,
**[3:10]** that the housing prices are going to be
**[3:12]** a completely linear function of
**[3:15]** the size despite data to the contrary.
**[3:19]** This preconception that the data is linear
**[3:23]** causes it to fit
**[3:24]** a straight line that fits the data poorly,
**[3:27]** leading it to underfitted data.
**[3:30]** Now, let's look at a second variation of a model,
**[3:35]** which is if you insert for
**[3:38]** a quadratic function at the data with two features,
**[3:42]** x and x^2,
**[3:43]** then when you fit the parameters W1 and W2,
**[3:47]** you can get a curve that fits the data somewhat better.
**[3:52]** Maybe it looks like this.
**[3:54]** Also, if you were to get a new house,
**[3:57]** that's not in this set of five training examples.
**[4:00]** This model would probably
**[4:03]** do quite well on that new house.
**[4:06]** If you're real estate agents,
**[4:09]** the idea that you want
**[4:10]** your learning algorithm to do well,
**[4:12]** even on examples that are not on
**[4:14]** the training set, that's called generalization.
**[4:18]** Technically we say that you want
**[4:20]** your learning algorithm to generalize well,
**[4:22]** which means to make good predictions even on
**[4:25]** brand new examples that it has never seen before.
**[4:28]** These quadratic models seem to fit
**[4:30]** the training set not perfectly, but pretty well.
**[4:34]** I think it would generalize well to new examples.
**[4:38]** Now let's look at the other extreme.
**[4:41]** What if you were to fit
**[4:42]** a fourth-order polynomial to the data?
**[4:45]** You have x, x^2,
**[4:48]** x^3, and x^4 all as features.
**[4:51]** With this fourth for the polynomial,
**[4:53]** you can actually fit the curve that passes
**[4:55]** through all five of the training examples exactly.
**[4:59]** You might get a curve that looks like this.
**[5:02]** This, on one hand,
**[5:04]** seems to do an extremely good job fitting
**[5:07]** the training data because it
**[5:09]** passes through all of the training data perfectly.
**[5:12]** In fact, you'd be able to choose
**[5:14]** parameters that will result in the cost function
**[5:17]** being exactly equal to zero because
**[5:19]** the errors are zero on all five training examples.
**[5:23]** But this is a very wiggly curve,
**[5:26]** its going up and down all over the place.
**[5:29]** If you have this whole size right here,
**[5:33]** the model would predict that this house is cheaper
**[5:35]** than houses that are smaller than it.
**[5:39]** We don't think that this is
**[5:42]** a particularly good model for predicting housing prices.
**[5:45]** The technical term is that we'll say
**[5:48]** this model has overfit the data,
**[5:51]** or this model has an overfitting problem.
**[5:54]** Because even though it fits the training set very well,
**[5:57]** it has fit the data almost too well, hence is overfit.
**[6:01]** It does not look like this model will
**[6:03]** generalize to new examples that's never seen before.
**[6:07]** Another term for this is
**[6:10]** that the algorithm has high variance.
**[6:13]** In machine learning,
**[6:15]** many people will use the terms over-fit
**[6:18]** and high-variance almost interchangeably.
**[6:20]** We'll use the terms underfit and high bias
**[6:23]** almost interchangeably.
**[6:25]** The intuition behind overfitting
**[6:28]** or high-variance is that the algorithm is
**[6:29]** trying very hard to fit every single training example.
**[6:34]** It turns out that if
**[6:36]** your training set were just even a little bit different,
**[6:39]** say one holes was
**[6:40]** priced just a little bit more little bit less,
**[6:43]** then the function that the algorithm
**[6:45]** fits could end up being totally different.
**[6:48]** If two different machine learning engineers were to
**[6:52]** fit this fourth-order polynomial model,
**[6:55]** to just slightly different datasets,
**[6:57]** they couldn't end up with totally different predictions
**[7:00]** or highly variable predictions.
**[7:02]** That's why we say the algorithm has high variance.
**[7:07]** Contrasting this rightmost model with
**[7:10]** the one in the middle for the same house,
**[7:13]** it seems, the middle model gives them
**[7:15]** much more reasonable prediction for price.
**[7:18]** There isn't really a name for this case in the middle,
**[7:21]** but I'm just going to call this just right,
**[7:23]** because it is neither underfit nor overfit.
**[7:27]** You can say that the goal machine learning is to find
**[7:30]** a model that hopefully is
**[7:32]** neither underfitting nor overfitting.
**[7:35]** In other words, hopefully,
**[7:37]** a model that has neither high bias nor high variance.
**[7:42]** When I think about underfitting and overfitting,
**[7:45]** high bias and high variance.
**[7:47]** I'm sometimes reminded of the children's story of
**[7:51]** Goldilocks and the Three Bears in this children's tale,
**[7:55]** a girl called Goldilocks
**[7:57]** visits the home of a bear family.
**[8:00]** There's a bowl of porridge that's
**[8:02]** too cold to taste and so that's no good.
**[8:05]** There's also a bowl of porridge that's too hot to eat.
**[8:10]** That's no good either.
**[8:11]** But there's a bowl of porridge that is
**[8:13]** neither too cold nor too hot.
**[8:15]** The temperature is in the middle,
**[8:17]** which is just right to eat.
**[8:19]** To recap, if you have
**[8:22]** too many features like
**[8:24]** the fourth-order polynomial on the right,
**[8:26]** then the model may fit the training set well,
**[8:28]** but almost too well or overfit and have high variance.
**[8:32]** On the flip side if you have too few features,
**[8:34]** then in this example, like the one on the left,
**[8:37]** it underfits and has high bias.
**[8:40]** In this example, using
**[8:42]** quadratic features x and x squared,
**[8:44]** that seems to be just right.
**[8:46]** So far we've looked at underfitting and
**[8:49]** overfitting for linear regression model.
**[8:52]** Similarly, overfitting applies a classification as well.
**[8:56]** Here's a classification example
**[8:58]** with two features, x_1 and x_2,
**[9:00]** where x_1 is maybe
**[9:02]** the tumor size and x_2 is the age of patient.
**[9:05]** We're trying to classify if
**[9:07]** a tumor is malignant or benign,
**[9:10]** as denoted by these crosses and circles,
**[9:13]** one thing you could do is fit
**[9:15]** a logistic regression model.
**[9:17]** Just a simple model like this, where as usual,
**[9:21]** g is the sigmoid function and this term here inside is z.
**[9:29]** If you do that,
**[9:31]** you end up with a straight line as the decision boundary.
**[9:36]** This is the line where z is equal to
**[9:38]** zero that separates the positive and negative examples.
**[9:41]** This straight line doesn't look terrible.
**[9:44]** It looks okay,
**[9:45]** but it doesn't look like a very
**[9:46]** good fit to the data either.
**[9:48]** This is an example of underfitting or of high bias.
**[9:53]** Let's look at another example.
**[9:56]** If you were to add to your features
**[9:58]** these quadratic terms,
**[10:00]** then z becomes this new term in
**[10:03]** the middle and the decision boundary,
**[10:05]** that is where z equals zero can look more like this,
**[10:09]** more like an ellipse or part of an ellipse.
**[10:12]** This is a pretty good fit to the data,
**[10:15]** even though it does not perfectly
**[10:17]** classify every single training
**[10:19]** example in the training set.
**[10:20]** Notice how some of these crosses
**[10:23]** get classified among the circles.
**[10:25]** But this model looks pretty good.
**[10:27]** I'm going to call it just right.
**[10:29]** It looks like this generalized
**[10:31]** pretty well to new patients.
**[10:33]** Finally, at the other extreme,
**[10:36]** if you were to fit
**[10:38]** a very high-order polynomial
**[10:40]** with many features like these,
**[10:42]** then the model may try really hard and contoured or twist
**[10:47]** itself to find a decision boundary
**[10:50]** that fits your training data perfectly.
**[10:53]** Having all these higher-order polynomial features
**[10:56]** allows the algorithm
**[10:58]** to choose this really over the complex decision boundary.
**[11:03]** If the features are tumor size in age,
**[11:06]** and you're trying to classify
**[11:07]** tumors as malignant or benign,
**[11:10]** then this doesn't really look like
**[11:12]** a very good model for making predictions.
**[11:15]** Once again, this is an instance of
**[11:17]** overfitting and high variance because its model,
**[11:21]** despite doing very well on the training set,
**[11:23]** doesn't look like it'll generalize well to new examples.
**[11:27]** Now you've seen how an algorithm can underfit or have
**[11:31]** high bias or overfit and have high variance.
**[11:34]** You may want to know how you can give get
**[11:36]** a model that is just right.
**[11:38]** In the next video,
**[11:40]** we'll look at some ways you can
**[11:41]** address the issue of overfitting.
**[11:44]** We'll also touch on some ideas
**[11:46]** relevant for using underfitting.
**[11:48]** Let's go on to the next video.
