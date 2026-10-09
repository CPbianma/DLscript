---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 1
section: Anomaly detection
item_title: Anomaly detection algorithm
duration: 12 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/nZcu2/anomaly-detection-algorithm
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Anomaly detection algorithm — Transcript

**[0:00]** Now that you've seen how the Gaussian or the normal distribution works for
**[0:05]** a single number, we're ready to build our anomaly detection algorithm.
**[0:10]** Let's dive in.
**[0:12]** You have a training set x1 through xm,
**[0:16]** where here each example x has n features.
**[0:20]** So, each example x is a vector with n numbers.
**[0:24]** In the case of the airplane engine example,
**[0:27]** we had two features corresponding to the heat and the vibrations.
**[0:32]** And so, each of these Xi's would be a two dimensional vector and
**[0:37]** n would be equal to 2.
**[0:38]** But for many practical applications n can be much larger and
**[0:42]** you might do this with dozens or even hundreds of features.
**[0:46]** Given this training set, what we would like to do is to carry
**[0:51]** out density estimation and all that means is,
**[0:55]** we will build a model or estimate the probability for p(x).
**[1:00]** What's the probability of any given feature vector?
**[1:05]** And our model for p(x) is going to be as follows,
**[1:11]** x is a feature vector with values x1, x2 and so on down to xn.
**[1:18]** And I'm going to model p(x) as the probability of x1,
**[1:24]** times the probability of x2,
**[1:27]** times the probability of x3 times the probability of xn,
**[1:33]** for the n th features in the feature vectors.
**[1:37]** If you've taken an advanced class in probably in statistics before,
**[1:42]** you may recognize that this equation corresponds to assuming that
**[1:47]** the features x1, x2 and so on up to xm are statistically independent.
**[1:53]** But it turns out this algorithm often works fine even that the features
**[1:57]** are not actually statistically independent.
**[1:59]** But if you don't understand what I just said, don't worry about it.
**[2:03]** Understanding statistical independence is not needed to fully complete this class and
**[2:09]** also, be able to very effectively use anomaly detection algorithm.
**[2:14]** Now, to fill in this equation a little bit more,
**[2:17]** we are saying that the probability of all the features of this vector features x,
**[2:23]** is the product of p(x) 1 and p(x2) and so on up through p(xn).
**[2:28]** And in order to model the probability of x1,
**[2:33]** say the heat feature in this example we're going to have two parameters,
**[2:40]** mu 1 and sigma 1 or sigma squared is 1.
**[2:44]** And what that means is we're going to estimate, the mean of the feature x1 and
**[2:51]** also the variance of feature x1 and that will be new 1 and sigma 1.
**[2:56]** To model p(x2) x2 is a totally different
**[2:59]** feature measuring the vibrations of the airplane engine.
**[3:03]** We're going to have two different parameters,
**[3:07]** which I'm going to write as mu 2, sigma 2 squared.
**[3:11]** And it turns out this will correspond to the mean or the average of
**[3:16]** the vibration feature and the variance of the vibration feature and so on.
**[3:21]** If you have additional features mu 3 sigma 3
**[3:26]** squared up through mu n and sigma n squared.
**[3:31]** In case you're wondering why we multiply probabilities,
**[3:36]** maybe here's 1 example that could build intuition.
**[3:40]** Suppose for an aircraft engine there's a 1/10
**[3:45]** chance that it is really hot, unusually hot and
**[3:50]** maybe there is a 1 in 20 chance that it vibrates really hard.
**[3:56]** Then, what is the chance that it runs really hot and vibrates really hard.
**[4:00]** We're saying that the chance of that is 1/10 times 1/20 which is 1/200.
**[4:08]** So it's really unlikely to get an engine that both run really hot and
**[4:13]** vibrates really hard.
**[4:14]** It's the product of these two probabilities
**[4:17]** A somewhat more compact way to write this equation up here,
**[4:23]** is to say that this is equal to,
**[4:26]** the product from j =1 through n of p(xj).
**[4:31]** Would parameters mu j and sigma squared j.
**[4:38]** And this symbol here is a lot like the summation symbol except that
**[4:43]** whereas the summation symbol corresponds to addition, this
**[4:48]** symbol here corresponds to multiplying these terms over here for j =1 through n.
**[4:55]** So let's put it all together to see how you can build an
**[5:00]** anamoly detection system.
**[5:02]** The first step is to choose features xi that you
**[5:06]** think might be indicative of anomalous examples.
**[5:11]** Having come up with the features you want to use,
**[5:15]** you would then fit the parameters mu 1 through mu n and
**[5:19]** sigma square 1 through sigma squared n, for the n features in your data set.
**[5:25]** As you might guess, the parameter mu j will be just the average
**[5:31]** of xj of the feature j of all the examples in your training set.
**[5:36]** And sigma square j will be the average of the square
**[5:41]** difference between the feature and the value mu j,
**[5:45]** that you just computed.
**[5:48]** And by the way, if you have a vectorized implementation,
**[5:53]** you can also compute mu as the average of the training examples as follows,
**[5:59]** we're here, x and mu are both vectors.
**[6:02]** And so this would be the vectorized way of computing mu 1 through mu and
**[6:07]** all at the same time.
**[6:09]** And by estimating these parameters on your unlabeled training set,
**[6:14]** you've now computed all the parameters of your model.
**[6:17]** Finally, when you are given a new example, x test or
**[6:22]** I'm just going to write a new example as x here,
**[6:25]** what you would do is compute p(x) and see if it's large or small.
**[6:31]** So p(x) as you saw on the last slide is the product from j = 1 through
**[6:36]** n of the probability of the individual features.
**[6:40]** So p(x) j with parameters mu j and single square j.
**[6:46]** And if you substitute in, the formula for this probability, you end
**[6:52]** up with this expression 1 over root 2 pi sigma j of e to this expression over here.
**[6:58]** And so xj are the features, this is a j feature of your new example,
**[7:04]** mu j and sigma j are numbers or parameters you have computed in the previous step.
**[7:11]** And if you compute out this formula, you get some number for p(x).
**[7:19]** And the final step is to see a p(x) is less than epsilon.
**[7:25]** And if it is then you flag that it is an anomaly.
**[7:29]** 1 intuition behind what this algorithm is doing is that it will tend to
**[7:34]** flag an example as anomalous if 1 or more of the features are either very large or
**[7:40]** very small relative to what it has seen in the training set.
**[7:46]** So for each of the features x j, you're fitting a Gaussian distribution like this.
**[7:51]** And so if even 1 of the features of the new example was
**[7:56]** way out here, say, then P f xJ would be very small.
**[8:01]** And if just 1 of the terms in this product is very small, then this overall product,
**[8:07]** when you multiply together will tend to be very small and does p(x) will be small.
**[8:13]** And what anomaly detection is doing in this algorithm is
**[8:18]** a systematic way of quantifying whether or not this new example x
**[8:23]** has any features that are unusually large or unusually small.
**[8:28]** Now, let's take a look at what all this actually means on 1 example,
**[8:34]** Here's the data set with features x 1 and x 2.
**[8:39]** And you notice that the features x 1 take on a much larger range
**[8:44]** of values than the features x 2.
**[8:48]** If you were to compute the mean of the Features x 1, you end up with five,
**[8:53]** which is why you want is equal to 1.
**[8:55]** And it turns out that for this data said, if you compute sigma 1,
**[9:00]** it will be equal to about 2.
**[9:02]** And if you were to compute mu to the average of the features on next
**[9:07]** to the average is three and similarly is variance or
**[9:11]** standard deviation is much smaller, which is why Sigma 2 is equal to 1.
**[9:15]** So that corresponds to this Gaussian distribution for
**[9:20]** x 1 and this Gaussian distribution for x 2.
**[9:25]** If you were to actually multiply p(x) 1 and p(x) 2,
**[9:30]** then you end up with this three D surface plot for p(x) where any point,
**[9:36]** the height of this is the product of p(x) 1 times p(x) 2.
**[9:42]** For the corresponding values of x 1 and x 2.
**[9:46]** And this signifies that values where p(x) is higher or more likely.
**[9:52]** So, values near the middle kind of here are more likely.
**[9:56]** Whereas values far out here, values out here are much less likely.
**[10:02]** I have much lower chance.
**[10:05]** Now, let me pick two test examples, the first 1 here,
**[10:10]** I'm going to write this x test 1 and the second 1 down here as x test 2.
**[10:17]** And let's see which of these 2 examples the algorithm will flag as anomalous.
**[10:22]** I'm going to pick The Parameter ε to be equal to 0.02.
**[10:30]** And if you were to compute p(x) test 1,
**[10:34]** it turns out to be about 0.4 and this is much bigger than epsilon.
**[10:40]** And so the album will say this looks okay, doesn't look like an anomaly.
**[10:44]** Whereas in contrast, if you were to compute p(x) for
**[10:49]** this point down here corresponding to x 1 equals about eight and
**[10:54]** x 2 equals about 0.5.
**[10:58]** Kind of down here, then p(x) test 2 is 0.0021.
**[11:03]** So this is much smaller than epsilon.
**[11:06]** And so the album will flag this as a likely anomaly.
**[11:10]** So, pretty much as you might hope it decides that x test 1 looks pretty normal.
**[11:17]** Whereas excess to which is much further away than anything you see in the training
**[11:22]** set looks like it could be an anomaly.
**[11:25]** So you've seen the process of how to build an anomaly detection system.
**[11:30]** But how do you choose the parameter epsilon?
**[11:33]** And how do you know if your anomaly detection system is working well in
**[11:37]** the next video, let's dive a little bit more deeply into the process of
**[11:42]** developing and evaluating the performance of an anomaly detection system.
**[11:47]** Let's go on to the next video
