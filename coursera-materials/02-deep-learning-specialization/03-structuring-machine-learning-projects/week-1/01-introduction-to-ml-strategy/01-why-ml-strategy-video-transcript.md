---
type: video-transcript
specialization: Deep Learning Specialization
course: Structuring Machine Learning Projects
week: 1
section: Introduction to ML Strategy
item_title: Why ML Strategy
duration: 3 min
source_url: https://www.coursera.org/learn/machine-learning-projects/lecture/yeHYT/why-ml-strategy
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Why ML Strategy — Transcript

**[0:00]** Hi, welcome to this course on how to structure your machine learning project,
**[0:05]** that is on machine learning strategy.
**[0:08]** I hope that through this course you will learn how to much more
**[0:11]** quickly and efficiently get your machine learning systems working.
**[0:15]** So, what is machine learning strategy.
**[0:17]** Let's start with a motivating example.
**[0:20]** Let's say you are working on your cat cost file.
**[0:23]** And after working it for some time,
**[0:26]** you've gotten your system to have 90% accuracy,
**[0:29]** but this isn't good enough for your application.
**[0:31]** You might then have a lot of ideas as to how to improve your system.
**[0:34]** For example, you might think well let's collect more data, more training data.
**[0:39]** Or you might say,
**[0:40]** maybe your training set isn't diverse enough yet,
**[0:42]** you should collect images of cats in more diverse poses,
**[0:46]** or maybe a more diverse set of negative examples.
**[0:49]** Or maybe you want to train the algorithm longer with gradient descent.
**[0:52]** Or maybe you want to try a different optimization algorithm,
**[0:54]** like the Adam optimization algorithm.
**[0:57]** Or maybe trying a bigger network or a smaller network or maybe you want
**[1:01]** to try dropout or maybe L2 regularization.
**[1:05]** Or maybe you want to change
**[1:06]** the network architecture such as changing activation functions,
**[1:09]** changing the number of hidden units and so on and so on.
**[1:12]** When trying to improve a deep learning system,
**[1:15]** you often have a lot of ideas or things you could try.
**[1:19]** And the problem is that if you choose poorly,
**[1:21]** it is entirely possible that you end up spending six months charging in
**[1:25]** some direction only to realize after six months that that didn't do any good.
**[1:29]** For example, I've seen some teams spend literally six months collecting
**[1:33]** more data only to realize after
**[1:36]** six months that it barely improved the performance of their system.
**[1:40]** So, assuming you don't have six months to waste on your problem,
**[1:43]** won't it be nice if you had quick and effective ways to
**[1:46]** figure out which of all of these ideas and maybe even other ideas,
**[1:50]** are worth pursuing and which ones you can safely discard.
**[1:54]** So what I hope to do in this course is teach you a number of strategies, that is,
**[1:59]** ways of analyzing a machine learning problem that will
**[2:02]** point you in the direction of the most promising things to try.
**[2:06]** What I will do in this course also is share with
**[2:08]** you a number of lessons I've learned through
**[2:09]** building and shipping large number of deep learning products.
**[2:13]** And I think these materials are actually quite unique to this course.
**[2:17]** I don't see a lot of these ideas being taught
**[2:20]** in universities' deep learning courses for example.
**[2:23]** It turns out also that machine learning strategy is
**[2:26]** changing in the era of deep learning because the things you could
**[2:29]** do are now different with deep learning algorithms
**[2:32]** than with previous generation of machine learning algorithms.
**[2:36]** I hope that these ideas will help you become much more
**[2:39]** effective at getting your deep learning systems to work.
