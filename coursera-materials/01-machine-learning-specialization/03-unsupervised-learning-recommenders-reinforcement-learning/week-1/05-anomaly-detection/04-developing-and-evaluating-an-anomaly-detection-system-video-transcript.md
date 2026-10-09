---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 1
section: Anomaly detection
item_title: Developing and evaluating an anomaly detection system
duration: 12 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/WyzeY/developing-and-evaluating-an-anomaly-detection-system
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Developing and evaluating an anomaly detection system — Transcript

**[0:00]** I'd like to share with you some practical tips for
**[0:04]** developing an anomaly detection system.
**[0:07]** One of the key ideas will be that if you
**[0:10]** can have a way to evaluate a system,
**[0:13]** even as it's being developed,
**[0:14]** you'll be able to make decisions and change
**[0:17]** the system and improve it much more quickly.
**[0:19]** Let's take a look at what that means.
**[0:21]** When you are developing a learning algorithm,
**[0:24]** say choosing different features or trying
**[0:26]** different values of the parameters like epsilon,
**[0:29]** making decisions about whether or not to change
**[0:33]** a feature in a certain way or to
**[0:34]** increase or decrease epsilon or other parameters,
**[0:37]** making those decisions is much easier if you have
**[0:40]** a way of evaluating the learning algorithm.
**[0:43]** This is sometimes called real number evaluation,
**[0:47]** meaning that if you can
**[0:49]** quickly change the algorithm in some way,
**[0:51]** such as change a feature or change
**[0:52]** a parameter and have a way of
**[0:55]** computing a number that tells
**[0:57]** you if the algorithm got better or worse,
**[1:00]** then it makes it much easier to decide
**[1:02]** whether or not to stick
**[1:03]** with that change to the algorithm.
**[1:05]** This is how it's often done in anomaly detection.
**[1:09]** Which is, even though we've mainly
**[1:12]** been talking about unlabeled data,
**[1:14]** I'm going to change that assumption a bit
**[1:17]** and assume that we have some labeled data,
**[1:20]** including just a small number
**[1:23]** usually of previously observed anomalies.
**[1:27]** Maybe after making airplane engines for a few years,
**[1:31]** you've just seen a few airplane engines
**[1:33]** that were anomalous,
**[1:35]** and for examples that you know are anomalous,
**[1:39]** I'm going to associate a label y
**[1:42]** equals 1 to indicate this anomalous,
**[1:45]** and for examples that we think are normal,
**[1:49]** I'm going to associate the label y equals 0.
**[1:54]** The training set that
**[1:56]** the anomaly detection algorithm will learn from is
**[1:59]** still this unlabeled training set of x1 through xm,
**[2:04]** and I'm going to think of all of these examples
**[2:09]** as ones that we'll just
**[2:10]** assume are normal and not anomalous,
**[2:14]** so y is equal to 0.
**[2:16]** In practice, you have
**[2:18]** a few anomalous examples
**[2:20]** where to slip into this training set,
**[2:21]** your algorithm will still usually do okay.
**[2:24]** To evaluate your algorithm,
**[2:27]** come up with a way for you
**[2:29]** to have a real number evaluation,
**[2:32]** it turns out to be very useful if you have a small number
**[2:38]** of anomalous examples so
**[2:41]** that you can create a cross validation set,
**[2:43]** which I'm going to denote x_cv^1,
**[2:46]** y_cv^1 through x_cv^mcv, y_cv^mcv.
**[2:50]** This is similar notation as you had
**[2:52]** seen in the second course of this specialization.
**[2:55]** As similarly, have a test set
**[2:58]** of some number of examples where
**[3:03]** both the cross validation and test sets hopefully
**[3:07]** includes a few anomalous examples.
**[3:11]** In other words, the cross validation and test sets will
**[3:14]** have a few examples of y equals 1,
**[3:17]** but also a lot of examples where y is equal to 0.
**[3:21]** Again, in practice,
**[3:23]** anomaly detection algorithm will work okay if
**[3:26]** there are some examples that are actually anomalous,
**[3:30]** but there were accidentally labeled with y equals 0.
**[3:33]** Let's illustrate this with the aircraft engine example.
**[3:38]** Let's say you have been manufacturing
**[3:40]** aircraft engines for years and so you've
**[3:42]** collected data from 10,000 good or normal engines,
**[3:47]** but over the years you had also collected data
**[3:51]** from 20 flawed or anomalous engines.
**[3:55]** Usually the number of anomalous engines,
**[3:58]** that is y equals 1,
**[4:00]** will be much smaller.
**[4:02]** It will not be a typical to
**[4:05]** apply this type of algorithm with anywhere from,
**[4:08]** say, 2-50 known anomalies.
**[4:13]** We're going to take this dataset and
**[4:15]** break it up into a training set,
**[4:17]** a cross validation set,
**[4:19]** and the test set. Here's one example.
**[4:21]** I'm going to put 6,000
**[4:24]** good engines into the training set.
**[4:26]** Again, if there are couple of anomalous engines
**[4:30]** that got slipped into this set is actually okay,
**[4:33]** I wouldn't worry too much about that.
**[4:36]** Then let's put 2,000 good engines and
**[4:40]** 10 of the known anomalies into the cross-validation set,
**[4:44]** and a separate 2,000 good and 10
**[4:47]** anomalous engines into the test set.
**[4:50]** What you can do then is
**[4:53]** train the algorithm on the training set,
**[4:57]** fit the Gaussian distributions to these 6,000 examples
**[5:00]** and then on the cross-validation set,
**[5:04]** you can see how many of
**[5:07]** the anomalous engines it correctly flags.
**[5:11]** For example, you could use the cross validation set
**[5:15]** to tune the parameter epsilon and set it
**[5:19]** higher or lower depending
**[5:22]** on whether the algorithm seems to be reliably
**[5:25]** detecting these 10 anomalies without taking too
**[5:29]** many of these 2,000 good
**[5:31]** engines and flagging them as anomalies.
**[5:34]** After you have tuned the parameter epsilon and
**[5:37]** maybe also added or subtracted or
**[5:40]** tuned to features X_J you can then take the algorithm and
**[5:45]** evaluate it on your test set to see
**[5:48]** how many of these 10 anomalous engines it finds,
**[5:52]** as well as how many mistakes it makes by
**[5:54]** flagging the good engines as anomalous ones.
**[5:57]** Notice that this is still
**[6:00]** primarily an unsupervised learning algorithm
**[6:03]** because the training sets really has no labels or
**[6:07]** they all have labels that we're assuming to
**[6:09]** be y equals 0 and so we
**[6:12]** learned from the training set by fitting
**[6:14]** the Gaussian distributions as
**[6:16]** you saw in the previous video.
**[6:18]** But it turns out if you're building
**[6:20]** a practical anomaly detection system,
**[6:22]** having a small number of anomalies to use to evaluate
**[6:27]** the algorithm that your cross validation and test
**[6:30]** sets is very helpful for tuning the algorithm.
**[6:33]** Because the number of flawed engines is so small there's
**[6:38]** one other alternative that I often see
**[6:40]** people use for anomaly detection,
**[6:43]** which is to not use a test set,
**[6:46]** like to have just a training set
**[6:48]** and a cross-validation set.
**[6:50]** In this example, you will set
**[6:52]** train on 6,000 good engines,
**[6:54]** but take the remainder of the data,
**[6:56]** the 4,000 remaining good
**[6:58]** engines as well as all the anomalies,
**[7:00]** and put them in the cross validation set.
**[7:03]** You would then tune the parameters Epsilon
**[7:05]** and add or subtract features x_j to try to
**[7:08]** get it to do as well as possible
**[7:10]** as evaluated on the cross validation set.
**[7:13]** If you have very few flawed engines,
**[7:17]** so if you had only two flawed engines,
**[7:20]** then this really makes sense to
**[7:22]** put all of that in the cross validation set.
**[7:25]** You just don't have enough data to create
**[7:28]** a totally separate test set
**[7:30]** that is distinct from your cross-validation set.
**[7:32]** The downside of this alternative
**[7:35]** here is that after you've tuned your algorithm,
**[7:37]** you don't have a fair way to tell how well
**[7:42]** this will actually do on
**[7:43]** future examples because you don't have the test set.
**[7:46]** But when your dataset is small,
**[7:48]** especially when the number of anomalies you have,
**[7:50]** your dataset is small,
**[7:52]** this might be the best alternative you have.
**[7:54]** I see this done quite often as well when
**[7:58]** you just don't have enough data
**[7:59]** to create a separate test set.
**[8:01]** If this is the case,
**[8:03]** just be aware that there's
**[8:05]** a higher risk that you will have
**[8:07]** over-fit some of your
**[8:08]** decisions around Epsilon and choice of features
**[8:11]** and so on to the cross-validation set
**[8:13]** and so its performance on
**[8:15]** real data in the future may not
**[8:17]** be as good as you were expecting.
**[8:20]** Now, let's take
**[8:22]** a closer look at how to actually evaluate
**[8:25]** the algorithm on your cross-validation sets or
**[8:27]** on the test set. Here's what you'd do.
**[8:30]** You would first fit the model p of x on the training set.
**[8:35]** This was a 6,000 examples of goods engines.
**[8:38]** Then on any cross validation or test example x,
**[8:43]** you would compute p of x and you will predict y equals 1.
**[8:48]** That is anomalous if p of x is
**[8:51]** less than Epsilon and you predict y is 0,
**[8:54]** if p of x is greater than or equal to Epsilon.
**[8:59]** Based on this, you can now look at how accurately
**[9:03]** this algorithm's predictions on
**[9:06]** the cross validation or test set matches the labels,
**[9:10]** y you have in the cross validation or the test sets.
**[9:15]** In the third week of the second course,
**[9:18]** we had had a couple of optional videos on how to handle
**[9:22]** highly skewed data distributions
**[9:25]** where the number of positive examples,
**[9:28]** y equals 1, can be much smaller than
**[9:31]** the number of negative examples where y equals 0.
**[9:34]** This is the case as well for
**[9:36]** many anomaly detection in the applications where
**[9:39]** the number of anomalies in
**[9:40]** your cross-validation set is much smaller.
**[9:43]** In our previous example,
**[9:45]** we had maybe 10 positive examples and 2,000
**[9:49]** negative examples because we had
**[9:51]** 10 anomalies and 2,000 normal examples.
**[9:55]** If you saw those optional videos,
**[9:57]** you may recall that we saw it can
**[9:59]** be useful to compute things like the true positive,
**[10:02]** false positive, false negative,
**[10:03]** and true negative rates.
**[10:05]** Also compute precision recall or
**[10:07]** F_1 score and that these are alternative metrics and
**[10:10]** classification accuracy that could work
**[10:13]** better when your data distribution is very skewed.
**[10:17]** If you saw that video,
**[10:19]** you might consider applying those types of
**[10:21]** evaluation metrics as well to tell how well
**[10:25]** your learning algorithm is doing at finding
**[10:27]** that small handful of anomalies or
**[10:30]** positive examples amidst this much larger set
**[10:34]** of negative examples of normal plane engines.
**[10:37]** If you didn't watch that video,
**[10:39]** don't worry about it. It's okay.
**[10:41]** The intuition I hope you get
**[10:42]** is to use the cross-validation set to just look at
**[10:46]** how many anomalies is finding and also
**[10:49]** how many normal engines is
**[10:50]** incorrectly flagging as an anomaly.
**[10:53]** Then to just use that to try to
**[10:55]** choose a good choice for the parameter Epsilon.
**[11:00]** You find that the practical process
**[11:03]** of building an anomaly detection system is much
**[11:06]** easier if you actually have
**[11:08]** just a small number of
**[11:10]** labeled examples of known anomalies.
**[11:13]** Now, this does raise the question,
**[11:15]** if you have a few labeled examples,
**[11:17]** since you'll still be using
**[11:19]** an unsupervised learning algorithm,
**[11:21]** why not take those labeled examples
**[11:23]** and use a supervised learning algorithm instead?
**[11:26]** In the next video, let's take a look
**[11:28]** at a comparison between
**[11:30]** anomaly detection and supervised learning
**[11:33]** and when you might prefer one over the other.
**[11:35]** Let's go on to the next video.
