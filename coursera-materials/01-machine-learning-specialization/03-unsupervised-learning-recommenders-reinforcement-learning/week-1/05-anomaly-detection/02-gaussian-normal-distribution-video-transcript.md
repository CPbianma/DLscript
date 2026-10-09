---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 1
section: Anomaly detection
item_title: Gaussian (normal) distribution
duration: 11 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/1pURx/gaussian-normal-distribution
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Gaussian (normal) distribution — Transcript

**[0:01]** In order to apply anomaly detection,
**[0:05]** we're going to need to use the Gaussian distribution,
**[0:08]** which is also called the normal distribution.
**[0:12]** When you hear me say either Gaussian
**[0:14]** distribution or normal distribution,
**[0:16]** they mean exactly the same thing.
**[0:19]** If you've heard the bell-shaped distribution,
**[0:22]** that also refers to the same thing.
**[0:24]** But if you haven't heard of
**[0:26]** the bell-shaped distribution, that's fine too.
**[0:28]** But let's take a look at what is
**[0:30]** the Gaussian or the normal distribution.
**[0:33]** Say x is a number,
**[0:35]** and if x is a random number,
**[0:37]** sometimes called the random variable,
**[0:40]** x can take on random values.
**[0:42]** If the probability of x is given by
**[0:45]** a Gaussian or normal distribution
**[0:48]** with mean parameter Mu,
**[0:51]** and with variance Sigma squared.
**[0:55]** What that means is that the probability of
**[0:59]** x looks like a curve that goes like this.
**[1:04]** The center or the middle of
**[1:06]** the curve is given by the mean Mu,
**[1:10]** and the standard deviation or the width of this curve is
**[1:15]** given by that variance parameter Sigma.
**[1:20]** Technically, Sigma is called
**[1:22]** the standard deviation and the square of
**[1:24]** Sigma or Sigma squared is
**[1:26]** called the variance of the distribution.
**[1:29]** This curve here shows what
**[1:32]** is p of x or the probability of x.
**[1:35]** If you've heard of the bell-shaped curve,
**[1:37]** this is that bell-shaped curve because a lot
**[1:40]** of classic bells say
**[1:43]** in towers were shaped like
**[1:46]** this with the bell clapper hanging down here,
**[1:50]** and so the shape of this curve is
**[1:52]** vaguely reminiscent of the shape of
**[1:54]** the large bells that
**[1:56]** you will still find in some old buildings today.
**[2:00]** Better looking than my hand-drawn one.
**[2:03]** There's a picture of the Liberty Bell.
**[2:05]** Indeed, the Liberty Bell's shape on
**[2:07]** top is vaguely bell-shaped curve.
**[2:11]** If you're wondering what does p of x really means?
**[2:15]** Here's one way to interpret it.
**[2:18]** It means that if you were to get, say,
**[2:22]** 100 numbers drawn from this probability distribution,
**[2:25]** and you were to plot
**[2:27]** a histogram of these 100 numbers
**[2:31]** drawn from this distribution,
**[2:32]** you might get a histogram that looks like this.
**[2:34]** It looks vaguely bell-shaped.
**[2:37]** What this curve on the left indicates is not
**[2:42]** if you have just 100 examples
**[2:45]** or 1,000 or a million or a billion.
**[2:47]** But if you had a practically infinite number of examples,
**[2:51]** and you were to draw a histogram of
**[2:53]** this practically infinite number of
**[2:55]** examples with a very fine histogram bin.
**[2:59]** Then you end up with
**[3:01]** essentially this bell-shaped curve here on the left.
**[3:05]** The formula for p of x is given by this expression;
**[3:10]** p of x equals 1 over square root 2 Pi.
**[3:15]** Pi here is that 3.14159 or it's about 22 over 7.
**[3:20]** Ratio of a circle's diameter circumference times
**[3:25]** Sigma times e to the negative x minus Mu,
**[3:31]** the mean parameter squared divided by 2 Sigma squared.
**[3:36]** For any given value of Mu and Sigma,
**[3:40]** if you were to plot this function as a function of x,
**[3:44]** you get this type of bell-shaped curve
**[3:46]** that is centered at Mu,
**[3:48]** and with the width of this bell-shaped curve
**[3:51]** being determined by the parameter Sigma.
**[3:55]** Now let's look at a few examples of how changing Mu
**[3:59]** and Sigma will affect the Gaussian distribution.
**[4:03]** First, let me set Mu equals 0 and Sigma equals 1.
**[4:09]** Here's my plot of the Gaussian distribution with mean 0,
**[4:13]** Mu equals 0,
**[4:15]** and standard deviation Sigma equals 1.
**[4:18]** You notice that this distribution is centered at zero
**[4:22]** and that is the standard deviation Sigma is equal to 1.
**[4:28]** Now, let's reduce the standard deviation Sigma to 0.5.
**[4:34]** If you plot the Gaussian distribution
**[4:38]** with Mu equals 0 and Sigma equals 0.5,
**[4:41]** it now it looks like this.
**[4:43]** Notice that it's still centered at
**[4:44]** zero because Mu is zero.
**[4:46]** But it's become a much thinner curve
**[4:50]** because Sigma is now 0.5.
**[4:54]** You might recall that Sigma
**[4:57]** is the standard deviation is 0.5,
**[5:00]** whereas Sigma squared is also called the variance.
**[5:03]** That's equal to 0.5 squared or 0.25.
**[5:08]** You may have heard that probabilities
**[5:10]** always have to sum up to one,
**[5:12]** so that's why the area under
**[5:14]** the curve is always equal to one,
**[5:16]** which is why when
**[5:18]** the Gaussian distribution becomes skinnier,
**[5:21]** it has to become taller as well.
**[5:23]** Let's look at another value of Mu and Sigma.
**[5:26]** Now, I'm going to increase Sigma to 2,
**[5:30]** so the standard deviation is 2 and the variance is 4.
**[5:34]** This now creates a much wider distribution
**[5:38]** because Sigma here is now much larger,
**[5:43]** and because it's now a wider distribution is become
**[5:46]** shorter as well because the area
**[5:47]** under the curve is still equals 1.
**[5:50]** Finally, let's try changing the mean parameter Mu,
**[5:56]** and I'll leave Sigma equals 0.5.
**[6:00]** In this case, the center of
**[6:03]** the distribution Mu moves over here to the right.
**[6:07]** But the width of
**[6:09]** the distribution is the same as the one on
**[6:11]** top because the standard deviation is
**[6:13]** 0.5 in both of these cases on the right.
**[6:16]** This is how different choices of Mu and
**[6:20]** Sigma affect the Gaussian distribution.
**[6:24]** When you're applying this to anomaly detection,
**[6:27]** here's what you have to do.
**[6:29]** You are given a dataset of m examples,
**[6:32]** and here x is just a number.
**[6:37]** Here, are plots of the training sets with 11 examples.
**[6:41]** What we have to do is try to estimate what
**[6:45]** a good choice is for the mean parameter Mu,
**[6:48]** as well as for the variance parameter Sigma squared.
**[6:53]** Given a dataset like this,
**[6:55]** it would seem that
**[6:57]** a Gaussian distribution maybe looking like
**[7:00]** that with a center
**[7:02]** here and a standard deviation like that.
**[7:06]** This might be a pretty good fit to the data.
**[7:09]** The way you would compute Mu
**[7:12]** and Sigma squared mathematically is
**[7:14]** our estimate for Mu will be
**[7:16]** just the average of all the training examples.
**[7:19]** It's 1 over m times sum from i
**[7:22]** equals 1 through m of
**[7:24]** the values of your training examples.
**[7:26]** The value we will use to estimate Sigma squared
**[7:29]** will be the average of
**[7:31]** the squared difference between two examples,
**[7:34]** and that Mu that you just estimated here on the left.
**[7:39]** It turns out that if you implement these two formulas
**[7:42]** in code with this value for
**[7:44]** Mu and this value for Sigma squared,
**[7:47]** then you pretty much get
**[7:48]** the Gaussian distribution that I hand drew on top.
**[7:51]** This will give you a choice of Mu and
**[7:54]** Sigma for a Gaussian distribution so
**[7:56]** that it looks like
**[7:58]** the 11 training samples might have
**[8:00]** been drawn from this Gaussian distribution.
**[8:03]** If you've taken an advanced statistics class,
**[8:05]** you may have heard that
**[8:07]** these formulas for Mu and Sigma squared are
**[8:10]** technically called the maximum likelihood
**[8:12]** estimates for Mu and Sigma.
**[8:15]** Some statistics classes will tell
**[8:17]** you to use the formula 1
**[8:19]** over n minus 1 instead of 1 over m. In practice,
**[8:24]** using 1 over m or 1 over n
**[8:26]** minus 1 makes very little difference.
**[8:29]** I always use 1 over m,
**[8:31]** but just some other properties of dividing
**[8:34]** by m minus 1 that some statisticians prefer.
**[8:39]** But if you don't understand what they
**[8:41]** just said, don't worry about it.
**[8:42]** All you need to know is that if you set Mu according to
**[8:46]** this formula and Sigma
**[8:48]** squared according to this formula,
**[8:51]** you'd get a pretty good estimate of
**[8:53]** Mu and Sigma and in particular,
**[8:55]** you get a Gaussian distribution that will be
**[8:58]** a possible probability distribution in terms
**[9:02]** of what's the probability distribution
**[9:04]** that the training examples had come from.
**[9:06]** You can probably guess what comes next.
**[9:10]** If you were to get an example over here,
**[9:14]** then p of x is pretty high.
**[9:18]** Whereas if you were to get an example,
**[9:21]** we are here, then p of x is pretty low,
**[9:24]** which is why we would consider this example,
**[9:27]** okay, not really anomalous,
**[9:30]** not a lot like the other ones.
**[9:31]** Whereas an example we are here to be
**[9:34]** pretty unusual compared to the examples we've seen,
**[9:37]** and therefore more anomalous because p of x,
**[9:40]** which is the height of this curve,
**[9:42]** is much lower over here on the left compared
**[9:45]** to this point over here, closer to the middle.
**[9:49]** Now, we've done this only for when x is a number,
**[9:54]** as if you had only a single feature
**[9:56]** for your anomaly detection problem.
**[9:58]** For practical anomaly detection applications,
**[10:01]** you usually have a lot of different features.
**[10:05]** You've now seen how the Gaussian distribution works.
**[10:09]** If x is a single number,
**[10:11]** this corresponds to if,
**[10:13]** say you had just one feature
**[10:15]** for your anomaly detection problem.
**[10:18]** But for practical anomaly detection applications,
**[10:21]** you will have many features,
**[10:23]** two or three or some even larger number n of features.
**[10:28]** Let's take what you saw for a single Gaussian and use
**[10:31]** it to build a more
**[10:32]** sophisticated anomaly detection algorithm.
**[10:34]** They can handle multiple features.
**[10:37]** Let's go do that in the next video.
