---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 3
section: Advice for applying machine learning
item_title: Deciding what to try next
duration: 4 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/ffdx5/deciding-what-to-try-next
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# Deciding what to try next — Transcript

**[0:01]** Hi, and welcome back.
**[0:03]** By now you've seen a lot of
**[0:05]** different learning algorithms,
**[0:06]** including linear regression,
**[0:08]** logistic regression, even deep learning,
**[0:10]** or neural networks,
**[0:11]** and next week, you'll see decision trees as well.
**[0:14]** You now have a lot of
**[0:16]** powerful tools of machine learning,
**[0:18]** but how do you use these tools effectively?
**[0:21]** I've seen teams sometimes,
**[0:23]** say six months to build a machine learning system,
**[0:26]** that I think a more skilled team could have
**[0:28]** taken or done in just a couple of weeks.
**[0:31]** The efficiency of how quickly you can
**[0:33]** get a machine learning system to work well,
**[0:35]** will depend to a large part
**[0:37]** on how well you can repeatedly make
**[0:39]** good decisions about what to do next
**[0:41]** in the course of a machine learning project.
**[0:43]** In this week, I hope to
**[0:45]** share with you a number of tips on
**[0:47]** how to make decisions about what to
**[0:49]** do next in machine learning project,
**[0:50]** that I hope will end up saving you a lot of time.
**[0:53]** Let's take a look at
**[0:55]** some advice on how to build machine learning systems.
**[0:58]** Let's start with an example,
**[1:01]** say you've implemented regularized linear regression
**[1:04]** to predict housing prices,
**[1:05]** so you have the usual cost function
**[1:09]** for your learning algorithm,
**[1:10]** squared error plus this regularization term.
**[1:12]** But if you train the model,
**[1:15]** and find that it makes
**[1:16]** unacceptably large errors in it's predictions,
**[1:19]** what do you try next?
**[1:20]** When you're building a machine learning algorithm,
**[1:22]** there are usually a lot
**[1:24]** of different things you could try.
**[1:25]** For example, you could decide to get
**[1:27]** more training examples since it
**[1:29]** seems having more data should help,
**[1:31]** or maybe you think maybe you have too many features,
**[1:35]** so you could try a smaller set of features.
**[1:37]** Or maybe you want to get additional features,
**[1:40]** such as finally additional properties
**[1:42]** of the houses to toss into your data,
**[1:44]** and maybe that'll help you to do better.
**[1:46]** Or you might take the existing features x_1,
**[1:49]** x_2, and so on,
**[1:50]** and try adding polynomial features x_1 squared,
**[1:53]** x_2 squared, x_1, x_2, and so on.
**[1:55]** Or you might wonder if the value
**[1:57]** of Lambda is chosen well,
**[1:59]** and you might say, maybe
**[2:01]** it's too big, I want to decrease it.
**[2:02]** Or you may say, maybe it's too small,
**[2:04]** I want to try increasing.
**[2:06]** On any given machine learning application,
**[2:10]** it will often turn out that some of
**[2:11]** these things could be fruitful,
**[2:13]** and some of these things not fruitful.
**[2:16]** The key to being effective at how you build
**[2:19]** a machine learning algorithm will be if you can find
**[2:22]** a way to make
**[2:23]** good choices about where to invest your time.
**[2:26]** For example, I have seen teams spend
**[2:28]** literally many many months collecting more training examples,
**[2:32]** thinking that more training data is going to help,
**[2:35]** but it turns out sometimes it helps a lot,
**[2:37]** and sometimes it doesn't.
**[2:39]** In this week, you'll learn about how to
**[2:42]** carry out a set of diagnostic.
**[2:45]** By diagnostic, I mean a test that you can
**[2:48]** run to gain insight into what
**[2:50]** is or isn't working with learning
**[2:52]** algorithm to gain guidance
**[2:54]** into improving its performance.
**[2:55]** Some of these diagnostics will tell you things like,
**[2:58]** is it worth weeks, or even months
**[3:00]** collecting more training data, because if it is,
**[3:02]** then you can then go ahead and make
**[3:04]** the investment to get more data,
**[3:06]** which will hopefully lead to improved performance,
**[3:08]** or if it isn't then running that
**[3:11]** diagnostic could have saved you months of time.
**[3:15]** One thing you see this week as well,
**[3:17]** is that diagnostics can take time to implement,
**[3:21]** but running them can be a very good use of your time.
**[3:25]** This week we'll spend a lot of time talking
**[3:28]** about different diagnostics you can use,
**[3:30]** to give you guidance on how to
**[3:31]** improve your learning algorithm's performance.
**[3:33]** But first, let's take a look at how to
**[3:36]** evaluate the performance of your learning algorithm.
**[3:38]** Let's go do that in the next video.
