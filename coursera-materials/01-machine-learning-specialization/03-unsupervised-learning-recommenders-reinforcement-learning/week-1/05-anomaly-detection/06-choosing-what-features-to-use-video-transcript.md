---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 1
section: Anomaly detection
item_title: Choosing what features to use
duration: 15 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/7MOXj/choosing-what-features-to-use
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Choosing what features to use — Transcript

**[0:02]** When building an anomaly detection algorithm,
**[0:05]** I found that choosing a good choice of features turns out to be really important.
**[0:10]** In supervised learning, if you don't have the features quite right, or
**[0:15]** if you have a few extra features that are not relevant to the problem,
**[0:19]** that often turns out to be okay.
**[0:21]** Because the algorithm has to supervised signal that is enough labels why for
**[0:26]** the algorithm to figure out what features ignore, or how to re scale feature and
**[0:30]** to take the best advantage of the features you do give it.
**[0:34]** But for anomaly detection which runs, or learns just from unlabeled data,
**[0:39]** is harder for the algorithm to figure out what features to ignore.
**[0:43]** So I found that carefully choosing the features, is even more important for
**[0:48]** anomaly detection, than for supervised learning approaches.
**[0:52]** Let's take a look at this video as some practical tips, for how to tune
**[0:56]** the features for anomaly detection, to try to get you the best possible performance.
**[1:01]** One step that can help your anomaly detection algorithm,
**[1:05]** is to try to make sure the features you give it are more or less Gaussian.
**[1:11]** And if your features are not Gaussian,
**[1:14]** sometimes you can change it to make it a little bit more Gaussian.
**[1:19]** Let me show you what I mean.
**[1:20]** If you have a feature X, I will often plot a
**[1:26]** histogram of the feature which you can do using the python command PLT.
**[1:33]** Though you see this in the practice lab as well,
**[1:36]** in order to look at the histogram of the data.
**[1:41]** This distribution here looks pretty Gaussian.
**[1:43]** So this would be a good candidate feature.
**[1:46]** If you think this is a feature that helps distinguish between anomalies and
**[1:51]** normal examples.
**[1:53]** But quite often when you plot a histogram of your features,
**[1:57]** you may find that the feature has a distribution like this.
**[2:01]** This does not at all look like that symmetric bell shaped curve.
**[2:06]** When that is the case, I would consider if you can take this feature X,
**[2:14]** and transform it in order to make a more Gaussian.
**[2:19]** For example, maybe if you were to compute the log of X and
**[2:24]** plot a histogram of log of X, look like this, and
**[2:29]** this looks much more Gaussian.
**[2:32]** And so if this feature was feature X one, then instead of using the original
**[2:37]** feature X one which looks like this on the left, you might instead replace
**[2:43]** that feature with log of X one, to get this distribution over here.
**[2:48]** Because when X one is made more Gaussian.
**[2:51]** When anomaly detection models P of X one using a Gaussian
**[2:56]** distribution like that, is more likely to be a good fit to the data.
**[3:01]** Other than the log function, other things you might do is, given
**[3:07]** a different feature X two, you may replace it with X two, log of X two plus one.
**[3:13]** This would be a different way of transforming X two.
**[3:16]** And more generally, log of X two plus C, would be one example of
**[3:21]** a formula you can use, to change X to try to make it more Gaussian.
**[3:26]** Or for a different feature, you might try taking the square root or
**[3:31]** really the square would have executed this X lead to the power of
**[3:36]** one half,and you may change that exponentially term.
**[3:40]** So for a different feature X four,
**[3:42]** you might use X four to the power of one third, for example.
**[3:47]** So when I'm building an anomaly detection system,
**[3:50]** I'll sometimes take a look at my features, and if I see any highly non Gaussian
**[3:56]** by plotting histogram, I might choose transformations like these or
**[4:01]** others, In order to try to make it more Gaussian.
**[4:04]** It turns out a larger value of C, will end up transforming this distribution less.
**[4:10]** But in practice I just try a bunch of different values of C,
**[4:14]** and then try to take a look to pick one that looks better in terms of making
**[4:19]** the distribution more Gaussian.
**[4:22]** Now, let me illustrate how I actually do this and that you put a notebook.
**[4:27]** So this is what the process of exploring different transformations in
**[4:30]** the features might look like.
**[4:33]** When you have a feature X, you can plot a histogram of it as follows.
**[4:39]** It actually looks like there's a pretty cause histogram.
**[4:43]** Let me increase the number of bins in my history gram to 50.
**[4:47]** So bins equals 50 there.
**[4:51]** That's what histogram bins.
**[4:53]** And by the way, if you want to change the color, you can also do so as follows.
**[5:00]** And if you want to try a different transformation,
**[5:04]** you can try for example to plot X square root of X.
**[5:08]** So X to the power of 0.5 with again 50 histogram bins,
**[5:13]** in which case it might look like this.
**[5:17]** And this actually looks somewhat more Gaussian.
**[5:21]** But not perfectly, and let's try a different parameter.
**[5:25]** So let me try to the power of 4.25.
**[5:30]** Maybe I just a little bit too far.
**[5:33]** It's the old 0.4 that looks pretty Gaussian.
**[5:35]** So one thing you could do is replace X with excellent power of 0.4.
**[5:42]** And so you would set X to be equal to X to the power of 0.4.
**[5:48]** And just use the value of X in your training process instead.
**[5:53]** Or let me show you another transformation.
**[5:56]** Here, I'm going to try taking the log of X.
**[5:59]** So log of X spotted with 50 bins,
**[6:03]** I'm going to use the numpy log function as follows.
**[6:09]** And it turns out you get an error, because it turns out that excellent.
**[6:14]** This example has some values that are equal to zero, and
**[6:18]** we'll log of zero is negative infinity is not defined.
**[6:22]** So common trick is to add just a very tiny number there.
**[6:28]** So exports 0.001, becomes non negative.
**[6:33]** And so you get the histogram that looks like this.
**[6:36]** But if you want the distribution to look more Gaussian, you can also
**[6:40]** play around with this parameter, to try to see if there's a value of that.
**[6:44]** Cause user data to look more symmetric and maybe look more Gaussian as follows.
**[6:51]** And just as I'm doing right now in real time, you can see that,
**[6:57]** you can very quickly change these parameters and plot the histogram.
**[7:02]** In order to try to take a look and try to get something a bit more Gaussian,
**[7:08]** than was the original data next that you saw in this histogram up above.
**[7:15]** If you read the machine learning literature, there are some ways to
**[7:18]** automatically measure how close these distributions are to Gaussian.
**[7:22]** But I found it in practice, it doesn't make a big difference,
**[7:25]** if you just try a few values and pick something that looks right to you,
**[7:29]** that will work well for all practical purposes.
**[7:32]** So, by trying things out in Jupiter notebook,
**[7:35]** you can try to pick a transformation that makes your data more Gaussian.
**[7:41]** And just as a reminder,
**[7:42]** whatever transformation you apply to the training set, please remember to apply
**[7:48]** the same transformation to your cross validation and test set data as well.
**[7:53]** Other than making sure that your data is approximately Gaussian,
**[7:58]** after you've trained your anomaly detection algorithm,
**[8:02]** if it doesn't work that well on your cross validation set,
**[8:07]** you can also carry out an error analysis process for anomaly detection.
**[8:12]** In other words, you can try to look at where the algorithm is not yet doing well
**[8:18]** whereas making errors, and then use that to try to come up with improvements.
**[8:23]** So as a reminder, what we want is for P of X to be large.
**[8:29]** For normal examples X, so greater than equal to epsilon, and
**[8:34]** p f X to be small or less than epsilon, for the anomalous examples X.
**[8:40]** When you've learned the model P of X from your unlabeled data,
**[8:45]** the most common problem that you may run into is that, P of X is comparable
**[8:50]** in value say is, large for both normal and for anomalous examples.
**[8:55]** As a concrete example, if this is your data set,
**[8:59]** you might fit that Gaussian into it.
**[9:02]** And if you have an example in your cross validation set or test set,
**[9:06]** that is over here, that is anomalous, then this has a pretty high probability.
**[9:11]** And in fact, it looks quite similar to the other examples in your training set.
**[9:17]** And so, even though this is an anomaly, P of X is actually pretty large.
**[9:23]** And so the algorithm will fail to flag this particular example as an anomaly.
**[9:28]** In that case, what I would normally do is, try to look at that example and
**[9:35]** try to figure out what is it that made me think is an anomaly,
**[9:40]** even if this feature X one took on values similar to other training examples.
**[9:48]** And if I can identify some new feature say X two,
**[9:52]** that helps distinguish this example from the normal examples.
**[9:58]** Then adding that feature, can help improve the performance of the algorithm.
**[10:03]** Here's a picture showing what I mean.
**[10:05]** If I can come up with a new feature X two, say, I'm trying to detect
**[10:10]** fraudulent behavior, and if X one is the number of transactions they make,
**[10:15]** maybe this user looks like they're making some of the transactions as everyone else.
**[10:22]** But if I discover that this user has some insanely fast typing speed,
**[10:28]** and if I were to add a new feature X two, that is the typing speed of this user.
**[10:35]** And if it turns out that when I plot this data using the old feature X one and
**[10:40]** this new feature X two, causes X two to stand out over here.
**[10:45]** Then it becomes much easier for
**[10:47]** the anomaly detection algorithm to recognize an X two is an anomalous user.
**[10:52]** Because when you have this new feature X two, the learning algorithm may fit
**[10:57]** a Gaussian distribution that assigns high probability to points in this region,
**[11:02]** a bit lower in this region, and a bit lower in this region.
**[11:06]** And so this example, because of the very anomalous value of X two,
**[11:12]** becomes easier to detect as an anomaly.
**[11:15]** So just to summarize the development process will often go through is,
**[11:21]** to train the model and then to see what anomalies in the cross
**[11:25]** validation set the algorithm is failing to detect.
**[11:29]** And then to look at those examples to see if that can inspire
**[11:33]** the creation of new features that would allow the algorithm to spot.
**[11:38]** That example takes on unusually large or unusually small values on the new
**[11:43]** features, so that you can now successfully flag those examples as anomalies.
**[11:49]** Just as one more example, let's say you're building an anomaly detection system to
**[11:54]** monitor computers in the data center.
**[11:56]** To try to figure out if a computer may be behaving strangely and
**[11:59]** deserves a closer look, maybe because of a hardware failure, or
**[12:03]** because it's been hacked into or something.
**[12:06]** So what you'd like to do is, to choose features that might take on unusually
**[12:11]** large or small values in the event of an anomaly.
**[12:14]** You might start off with features like X one is the memory use, X two is the number
**[12:19]** of disk accesses per second, then the CPU load, and the volume of network traffic.
**[12:25]** And if you train the algorithm, you may find that it detects
**[12:30]** some anomalies but fails to detect some other anomalies.
**[12:35]** In that case, it's not unusual to create new features by combining old features.
**[12:41]** So, for example, if you find that there's a computer that is behaving
**[12:47]** very strangely, but neither is CPU load nor network traffic is that unusual.
**[12:53]** But what is unusual is, it has a really high CPU load,
**[12:57]** while having a very low network traffic volume.
**[13:02]** If you're running the data center that streams videos, then computers may have
**[13:07]** high CPU load and high network traffic, or low CPU load and no network traffic.
**[13:12]** But what's unusual about this one machine is a very high CPU load,
**[13:16]** despite a very low traffic volume.
**[13:18]** In that case, you might create a new feature X five,
**[13:21]** which is a ratio of CPU load to network traffic.
**[13:23]** And this new feature with hope, the anomaly detection algorithm
**[13:28]** flagged future examples like the specific machine you may be seeing as anomalous.
**[13:35]** Or you can also consider other features like the square of the CPU load,
**[13:41]** divided by the network traffic volume.
**[13:44]** And you can play around with different choices of these features.
**[13:49]** In order to try to get it so that P of X is still large for the normal examples but
**[13:55]** it becomes small in the anomalies in your cross validation set.
**[14:00]** So that's it.
**[14:01]** Thanks for sticking with me to the end of this week.
**[14:04]** I hope you enjoy hearing about both clustering algorithms and
**[14:08]** anomaly detection algorithms.
**[14:10]** And that you also enjoy playing with these ideas
**[14:13]** in the practice labs.
**[14:15]** Next week, we'll go on to talk about recommender systems.
**[14:19]** When you go to a website and recommends products, or movies, or
**[14:23]** other things to you.
**[14:24]** How does that algorithm actually work?
**[14:28]** This is one of the most commercially important algorithms in machine learning
**[14:32]** that gets talked about surprisingly little but next week we'll take a look at how
**[14:37]** these algorithms work so that you understand the next time you go to the website and
**[14:41]** then recommend something to you.
**[14:43]** Maybe how that came about.
**[14:45]** As was you'll be able to build other algorithms like that for yourself as well.
**[14:50]** So have fun with the labs and they look forward to seeing you next week.
