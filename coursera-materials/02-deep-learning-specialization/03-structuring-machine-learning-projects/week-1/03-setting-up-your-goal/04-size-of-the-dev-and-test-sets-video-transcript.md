---
type: video-transcript
specialization: Deep Learning Specialization
course: Structuring Machine Learning Projects
week: 1
section: Setting Up your Goal
item_title: Size of the Dev and Test Sets
duration: 6 min
source_url: https://www.coursera.org/learn/machine-learning-projects/lecture/HOby4/size-of-the-dev-and-test-sets
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Size of the Dev and Test Sets — Transcript

**[0:00]** >> In the last video,
**[0:01]** you saw how your dev and test sets should come from the same distribution,
**[0:05]** but how long should they be?
**[0:07]** The guidelines to help set up
**[0:08]** your dev and test sets are changing in the Deep Learning era.
**[0:11]** Let's take a look at some best practices.
**[0:14]** You might have heard of the rule of thumb
**[0:17]** in machine learning of taking all the data you have
**[0:20]** and using a 70/30 split into a train and test set,
**[0:26]** or if you had to set up train dev and test sets maybe,
**[0:30]** you would use a 60% training and say 20% dev and 20% tests.
**[0:42]** In earlier eras of machine learning,
**[0:47]** this was pretty reasonable,
**[0:50]** especially back when data set sizes were just smaller.
**[0:54]** So if you had a hundred examples in total,
**[0:57]** these 70/30 or 60/20/20 rule of thumb would be pretty reasonable.
**[1:03]** Or if you had thousand examples,
**[1:05]** maybe if you had ten thousand examples,
**[1:09]** these things are not unreasonable.
**[1:13]** But in the modern machine learning era,
**[1:16]** we are now used to working with much larger data set sizes.
**[1:20]** So let's say you have a million training examples,
**[1:26]** it might be quite reasonable to set up
**[1:29]** your data so that you have 98% in the training set,
**[1:33]** and 1% dev, and 1% test.
**[1:40]** I'm going to use DNT to abbreviate dev and test sets.
**[1:44]** Because if you have a million examples,
**[1:46]** then 1% of that,
**[1:48]** is 10,000 examples, and that might be plenty enough for a dev set or for a test set.
**[1:54]** So, in the modern Deep Learning era where sometimes we have much larger data sets,
**[2:00]** It's quite reasonable to use a much smaller than 20
**[2:04]** or 30% of your data for a dev set or a test set.
**[2:07]** And because Deep Learning algorithms have such a huge hunger for data, I'm seeing that,
**[2:12]** the problems we have large data sets that have
**[2:16]** much larger fraction of it goes into the training set.
**[2:20]** So, how about the test set?
**[2:24]** Remember the purpose of your test set is that,
**[2:28]** after you finish developing a system,
**[2:30]** the test set helps evaluate how good your final system is.
**[2:34]** So, the guideline is, to set your test set to big enough to give
**[2:37]** high confidence in the overall performance of your system.
**[2:41]** So, unless you need to have
**[2:43]** a very accurate measure of how well your final system is performing,
**[2:48]** maybe you don't need millions and millions of examples in your test set,
**[2:54]** and maybe for your application if you think that having 10,000 examples gives you
**[2:57]** enough confidence to find the performance on maybe
**[3:00]** 100,000 or whatever it is, that might be enough.
**[3:03]** And this could be much less than,
**[3:05]** say 30% of your overall data set,
**[3:07]** depending on how much data you have.
**[3:08]** For some applications,
**[3:13]** maybe you don't need a high confidence in the overall performance of your final system.
**[3:18]** Maybe all you need is a train and dev set,
**[3:23]** And I think, not having a test set might be okay.
**[3:29]** In fact, what sometimes happened was,
**[3:31]** people were talking about using
**[3:33]** train test splits but what they were actually doing was iterating on the test set.
**[3:40]** So rather than a test set,
**[3:42]** what they had was a train dev split and no test set.
**[3:46]** If you're actually tuning to this set,
**[3:48]** to this dev set and this test set,
**[3:50]** It's better to call it a dev set.
**[3:53]** Although I think in the history of machine learning,
**[3:56]** not everyone has been completely clean and completely rigorous
**[3:59]** about calling the dev set when it really should be treated as dev set.
**[4:03]** But, if all you care about is having some data that you train on,
**[4:07]** and having some data to tune to,
**[4:09]** and you're just going to shape the final system
**[4:11]** and not worry too much about how well it was actually doing,
**[4:15]** I think it will be healthy and just call the train dev set
**[4:17]** and acknowledge that you have no test set.
**[4:20]** This is a bit unusual.
**[4:22]** I'm definitely not recommending not having a test set when building a system.
**[4:26]** I do find it reassuring to have a separate test set
**[4:30]** you can use to get an unbiased estimate of how it was doing before you ship it,
**[4:33]** but maybe if you have a very large dev
**[4:37]** set so that you think you won't overfit the dev set too badly.
**[4:41]** Maybe it's not totally unreasonable to just have a train dev set,
**[4:45]** although it's not what I usually recommend.
**[4:48]** So to summarize, in the era of big data,
**[4:51]** I think the old rule of thumb of a 70/30 split,
**[4:54]** that no longer applies.
**[4:56]** And the trend has been to use more data for training and less for dev and tests,
**[5:01]** especially when you have a very large data sets.
**[5:03]** And the rule of thumb is really to try to set the dev set to big enough for its purpose,
**[5:06]** which helps you evaluate different ideas and pick this up from AOP better.
**[5:11]** And the purpose of test set is to help you evaluate your final cost buys.
**[5:15]** You just have to set your test set big enough for that purpose,
**[5:18]** and that could be much less than 30% of the data.
**[5:21]** So, I hope that gives some guidance or some suggestions on how to
**[5:24]** set up your dev and test sets in the Deep Learning era.
**[5:28]** Next, it turns out that sometimes,
**[5:30]** part way through a machine learning problem,
**[5:32]** you might want to change your evaluation metric,
**[5:34]** or change your dev and test sets.
**[5:36]** Let's talk about it when you might want to do that.
