---
type: video-transcript
specialization: Deep Learning Specialization
course: Structuring Machine Learning Projects
week: 1
section: Setting Up your Goal
item_title: Satisficing and Optimizing Metric
duration: 6 min
source_url: https://www.coursera.org/learn/machine-learning-projects/lecture/uNWnZ/satisficing-and-optimizing-metric
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Satisficing and Optimizing Metric — Transcript

**[0:00]** It's not always easy to combine all the things you care
**[0:02]** about into a single row number evaluation metric.
**[0:06]** In those cases I've found it sometimes useful to set up
**[0:09]** satisficing as well as optimizing metrics.
**[0:12]** Let me show you what I mean.
**[0:13]** Let's say that you've decided you care about
**[0:16]** the classification accuracy of your cat's classifier,
**[0:20]** this could have been F1 score or some other measure of accuracy,
**[0:25]** but let's say that in addition to accuracy you also care about the running time.
**[0:29]** So how long it takes to classify an image and classifier A takes 80 milliseconds,
**[0:35]** B takes 95 milliseconds,
**[0:36]** and C takes 1,500 milliseconds,
**[0:39]** that's 1.5 seconds to classify an image.
**[0:42]** So, one thing you could do is combine accuracy
**[0:45]** and running time into an overall evaluation metric.
**[0:48]** And so the costs such as maybe the overall cost is accuracy minus 0.5 times running time.
**[0:57]** But maybe it seems a bit artificial to combine
**[1:01]** accuracy and running time using a formula like this,
**[1:05]** like a linear weighted sum of these two things.
**[1:08]** So here's something else you could do instead which is
**[1:11]** that you might want to choose a classifier
**[1:13]** that maximizes accuracy but subject to that the running time,
**[1:26]** that is the time it takes to classify an image,
**[1:28]** that that has to be less than or equal to 100 milliseconds.
**[1:36]** So in this case we would say that accuracy is an
**[1:40]** optimizing metric because you want to maximize accuracy.
**[1:44]** You want to do as well as possible on accuracy but
**[1:48]** that running time is what we call a satisficing metric.
**[1:53]** Meaning that it just has to be good enough,
**[1:55]** it just needs to be less than 100 milliseconds and beyond that you don't really care,
**[2:00]** or at least you don't care that much.
**[2:04]** So this will be a pretty reasonable way to trade off or to put
**[2:07]** together accuracy as well as running time.
**[2:11]** And it may be the case that so long as the running time is less that 100 milliseconds,
**[2:16]** your users won't care that much whether it's
**[2:18]** 100 milliseconds or 50 milliseconds or even faster.
**[2:21]** And by defining optimizing as well as satisficing metrics,
**[2:26]** this gives you a clear way to pick the, quote, "best classifier",
**[2:30]** which in this case would be classifier B because of all the ones with
**[2:34]** a running time better than 100 milliseconds, it has the best accuracy.
**[2:39]** So more generally, if you have N metrics that you care
**[2:45]** about it's sometimes reasonable to pick one of them to be optimizing.
**[2:50]** So you want to do as well as is possible on that one.
**[2:54]** And then N minus 1 to be satisficing,
**[2:57]** meaning that so long as they reach
**[2:59]** some threshold such as running times faster than 100 milliseconds,
**[3:02]** but so long as they reach some threshold,
**[3:04]** you don't care how much better it is in that threshold,
**[3:06]** but they have to reach that threshold.
**[3:09]** Here's another example.
**[3:11]** Let's say you're building a system to detect wake words,
**[3:15]** also called trigger words.
**[3:19]** So this refers to the voice control devices like
**[3:22]** the Amazon Echo where you wake up by saying
**[3:25]** Alexa or some Google devices which you wake up
**[3:29]** by saying okay Google or some Apple devices which you wake up by saying Hey Siri
**[3:35]** or some Baidu devices which you wake up by saying you ni hao Baidu.
**[3:42]** Oh I guess, you want to read the Chinese, that's ni hao Baidu.
**[3:46]** Right, so these are the wake words you use to
**[3:51]** tell one of these voice control devices
**[3:54]** to wake up and listen to something you want to say.
**[3:56]** And these are the Chinese characters for ni hao Baidu.
**[4:02]** So you might care about the accuracy of your trigger word detection system.
**[4:07]** So when someone says one of these trigger words,
**[4:10]** how likely are you to actually wake up your device,
**[4:13]** and you might also care about the number of false positives.
**[4:16]** So when no one actually said this trigger word,
**[4:19]** how often does it randomly wake up?
**[4:23]** So in this case maybe one reasonable way of
**[4:27]** combining these two evaluation metrics might be to maximize accuracy,
**[4:33]** so when someone says one of the trigger words,
**[4:35]** maximize the chance that your device wakes up.
**[4:37]** And subject to that,
**[4:39]** you have at most one false positive every 24 hours
**[4:48]** of operation, right?
**[4:51]** So that your device randomly wakes up only once
**[4:53]** per day on average when no one is actually talking to it.
**[4:57]** So in this case accuracy is the
**[5:00]** optimizing metric and a number of false positives every 24 hours
**[5:05]** is the satisficing metric where you'd be satisfied so long as there
**[5:09]** is at most one false positive every 24 hours.
**[5:14]** To summarize, if there are multiple things you care
**[5:17]** about by say there's one as the optimizing metric
**[5:19]** that you want to do as well as possible on and one or
**[5:22]** more as satisficing metrics were you'll be satisfice.
**[5:25]** So long as it does better than some threshold you can now have
**[5:29]** an almost automatic way of quickly
**[5:32]** looking at multiple core size and picking the, quote, best one.
**[5:35]** Now these evaluation metrics must be
**[5:39]** evaluated or calculated on a training set or a development set or maybe on the test set.
**[5:44]** So one of the things you also need to do is set up training,
**[5:46]** dev or development, as well as test sets.
**[5:50]** In the next video, I want to share with you some guidelines for
**[5:52]** how to set up training, dev, and test sets.
**[5:55]** So let's go on to the next.
