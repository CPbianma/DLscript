---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 1
section: Anomaly detection
item_title: Anomaly detection vs. supervised learning
duration: 8 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/eLO9Y/anomaly-detection-vs-supervised-learning
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Anomaly detection vs. supervised learning — Transcript

**[0:02]** When you have a few positive examples with y = 1 and
**[0:07]** a large number of negative examples say y = 0?
**[0:10]** When should you use anomaly detection and when should you use supervised learning?
**[0:15]** The decision is actually quite subtle in some applications.
**[0:19]** So let me share with you some thoughts and some suggestions for
**[0:22]** how to pick between these two types of algorithms.
**[0:26]** And anomaly detection algorithm will typically be the more appropriate
**[0:31]** choice when you have a very small number of positive examples,
**[0:36]** 0-20 positive examples is not uncommon.
**[0:40]** And a relatively large number of negative examples
**[0:45]** with which to try to build a model for p of x.
**[0:49]** When you recall that the parameters for
**[0:51]** p of x are learned only from the negative examples and this much smaller.
**[0:56]** So the positive examples is only used in your cross validation set and
**[1:00]** test set for parameter tuning and for evaluation.
**[1:04]** In contrast, if you have a larger number of positive and
**[1:07]** negative examples, then supervised learning might be more applicable.
**[1:13]** Now, even if you have only 20 positive training examples,
**[1:18]** it might be okay to apply a supervised learning algorithm.
**[1:23]** But it turns out that the way anomaly detection looks at the data set
**[1:27]** versus the way supervised learning looks at the data set are quite different.
**[1:32]** Here is the main difference, which is that if you think there are many
**[1:37]** different types of anomalies or many different types of positive examples.
**[1:43]** Then anomaly detection might be more appropriate when there
**[1:47]** are many different ways for an aircraft engine to go wrong.
**[1:51]** And if tomorrow there may be a brand new way for
**[1:54]** an aircraft engine to have something wrong with it.
**[1:59]** Then your 20 say positive examples may not cover all of the ways that
**[2:04]** an aircraft engine could go wrong.
**[2:06]** That makes it hard for any algorithm to learn from the small set of
**[2:10]** positive examples what the anomalies, what the positive examples look like.
**[2:15]** And future anomalies may look nothing like any
**[2:18]** of the anomalous examples we've seen so far.
**[2:21]** If you believe this to be true for your problem,
**[2:24]** then I would gravitate to using an anomaly detection algorithm.
**[2:28]** Because what anomaly detection does is it looks at the normal examples that
**[2:34]** is the y = 0 negative examples and just try to model what they look like.
**[2:39]** And anything that deviates a lot from normal It flags as an anomaly.
**[2:43]** Including if there's a brand new way for
**[2:46]** an aircraft engine to fail that had never been seen before in your data set.
**[2:50]** In contrast, supervised learning has a different way of looking at the problem.
**[2:55]** When you're applying supervised learning ideally you would hope to have
**[2:59]** enough positive examples for
**[3:01]** the average to get a sense of what the positive examples are like.
**[3:04]** And with supervised learning, we tend to assume that the future positive
**[3:10]** examples are likely to be similar to the ones in the training set.
**[3:14]** So let me illustrate this with one example,
**[3:18]** if you are using a system to find, say financial fraud.
**[3:23]** There are many different ways unfortunately that
**[3:26]** some individuals are trying to commit financial fraud.
**[3:30]** And unfortunately there are new types of
**[3:33]** financial fraud attempts every few months or every year.
**[3:36]** And what that means is that because they keep on popping up completely new.
**[3:42]** And unique forms of financial fraud anomaly detection is often used to just
**[3:47]** look for anything that's different, then transactions we've seen in the past.
**[3:52]** In contrast, if you look at the problem of email spam detection, well,
**[3:57]** there are many different types of spam email, but even over many years.
**[4:02]** Spam emails keep on trying to sell similar things or
**[4:06]** get you to go to similar websites and so on.
**[4:10]** Spam email that you will get in the next few days is much more likely
**[4:14]** to be similar to spam emails that you have seen in the past.
**[4:18]** So that's why supervised learning works well for
**[4:22]** spam because it's trying to detect more of the types of spam
**[4:26]** emails that you have probably seen in the past in your training set.
**[4:31]** Whereas if you're trying to detect brand new types of fraud that have never been
**[4:35]** seen before, then anomaly detection maybe more applicable.
**[4:39]** Let's go through a few more examples.
**[4:42]** We have already seen fraud detection being one use case of anomaly detection.
**[4:48]** Although supervised learning is used to find previously observed forms of fraud.
**[4:54]** And we've seen email spam classification typically being address
**[4:58]** using supervised learning.
**[5:00]** You've also seen the example of manufacturing where
**[5:05]** you may want to find new previously unseen defects.
**[5:09]** Such as if there are brand new ways for
**[5:11]** an aircraft engine to fail in the future that you still want to detect.
**[5:15]** Even if you don't have any positive example like that in your training set.
**[5:20]** It turns out that the manufacturing supervised learning is also used to find
**[5:25]** defects.
**[5:25]** The more for finding known and previously seen defects.
**[5:29]** For example, if you are a smartphone maker, you're making cell phones.
**[5:34]** And you know that occasionally your machine for
**[5:37]** making the case of the smartphone will accidentally scratch the cover.
**[5:41]** So scratches are a common defect on smartphones and so you can get
**[5:47]** enough training examples of scratched smartphones responding to label y =1.
**[5:53]** And just train the system to decide if a new smartphone that you just
**[5:57]** manufactured has any scratches in it.
**[6:00]** And the difference is if you just see scratched smartphones over and over and
**[6:04]** you want to check if your phones are scratched,
**[6:07]** then supervised learning works well.
**[6:10]** Whereas if you suspect that they're going to be brand new ways for
**[6:13]** something to go wrong in the future, then anomaly detection will work well.
**[6:17]** Some other examples you've heard me talk about monitoring machines in the data
**[6:22]** center, especially the machine's been hacked.
**[6:25]** It can behave differently in a brand new way unlike any previous way in his
**[6:29]** behavior.
**[6:29]** So that would feel more like an anomaly detection application.
**[6:34]** In fact, one theme is that many security related applications because
**[6:38]** hackers are often finding brand new ways to hack into systems.
**[6:43]** Many security related applications will use anomaly detection.
**[6:47]** Whereas returning to supervised learning, if you want to learn to predict
**[6:51]** the weather well, there's only a handful types of weather that you typically see.
**[6:57]** Is it sunny, rainy, is it going to snow?
**[6:59]** And so because you see the same output labels over and over,
**[7:03]** weather prediction would tend to be a supervised learning task.
**[7:07]** Or if you want to use the symptoms of the patient to see if the patient has
**[7:11]** a specific disease that you've seen before.
**[7:13]** Then that would also tend to be a supervised learning application.
**[7:18]** So I hope that gives you a framework for deciding when you have a small set of
**[7:22]** positive examples as well as maybe a large set of negative examples.
**[7:27]** Whether to use anomaly detection or supervised learning.
**[7:30]** Anomaly detection tries to find brand new positive examples that may be unlike
**[7:35]** anything you've seen before.
**[7:37]** Where supervised learning looks at your positive examples and
**[7:40]** tries to decide if a future example is similar to the positive examples that
**[7:45]** you've already seen.
**[7:46]** Now, it turns out that when building an anomaly detection algorithm, the choice
**[7:52]** of features is very important and when building anomaly detection systems.
**[7:57]** I often spend a bit of time trying to tune the features I use for
**[8:00]** the system in the next video.
**[8:02]** Let me share some practical tips on how to tune the features you feed to anomaly
**[8:07]** detection algorithm.
