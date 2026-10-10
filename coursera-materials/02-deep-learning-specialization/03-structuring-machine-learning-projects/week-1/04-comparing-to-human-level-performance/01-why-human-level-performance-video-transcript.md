---
type: video-transcript
specialization: Deep Learning Specialization
course: Structuring Machine Learning Projects
week: 1
section: Comparing to Human-level Performance
item_title: Why Human-level Performance?
duration: 6 min
source_url: https://www.coursera.org/learn/machine-learning-projects/lecture/FWkpo/why-human-level-performance
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Why Human-level Performance? — Transcript

**[0:01]** In the last few years, a lot more machine learning teams have been talking about
**[0:05]** comparing the machine learning systems to human level performance.
**[0:09]** Why is this?
**[0:10]** I think there are two main reasons.
**[0:12]** First is that because of advances in deep learning,
**[0:15]** machine learning algorithms are suddenly working much better and so
**[0:18]** it has become much more feasible in a lot of application areas for machine learning
**[0:22]** algorithms to actually become competitive with human-level performance.
**[0:26]** Second, it turns out that the workflow of designing and
**[0:29]** building a machine learning system, the workflow is much more efficient
**[0:33]** when you're trying to do something that humans can also do.
**[0:36]** So in those settings, it becomes natural to talk about comparing, or
**[0:40]** trying to mimic human-level performance.
**[0:43]** Let's see a couple examples of what this means.
**[0:46]** I've seen on a lot of machine learning tasks that as you work on a problem over
**[0:50]** time, so the x-axis, time, this could be many months or even many years
**[0:56]** over which some team or some research community is working on a problem.
**[0:59]** Progress tends to be relatively rapid as you approach human level performance.
**[1:07]** But then after a while, the algorithm surpasses human-level performance and
**[1:12]** then progress and accuracy actually slows down.
**[1:14]** And maybe it keeps getting better but
**[1:17]** after surpassing human level performance it can still get better, but performance,
**[1:21]** the slope of how rapid the accuracy's going up, often that slows down.
**[1:26]** And the hope is it achieves some theoretical optimum level of performance.
**[1:32]** And over time, as you keep training the algorithm,
**[1:35]** maybe bigger and bigger models on more and more data,
**[1:38]** the performance approaches but never surpasses some theoretical limit,
**[1:44]** which is called the Bayes optimal error.
**[1:53]** So Bayes optimal error, think of this as the best possible error.
**[1:59]** And that's just the way for
**[2:02]** any function mapping from x to y to surpass a certain level of accuracy.
**[2:08]** So for example, for speech recognition, if x is audio clips, some audio is just so
**[2:14]** noisy it is impossible to tell what is in the correct transcription.
**[2:20]** So the perfect error may not be 100%.
**[2:23]** Or for cat recognition.
**[2:25]** Maybe some images are so blurry, that it is just impossible for
**[2:29]** anyone or anything to tell whether or not there's a cat in that picture.
**[2:34]** So, the perfect level of accuracy may not be 100%.
**[2:39]** And Bayes optimal error, or Bayesian optimal error, or sometimes Bayes error
**[2:44]** for short, is the very best theoretical function for mapping from x to y.
**[2:52]** That can never be surpassed.
**[2:56]** So it should be no surprise that this purple line, no matter how many years you
**[3:00]** work on a problem you can never surpass Bayes error, Bayes optimal error.
**[3:05]** And it turns out that progress is often quite fast
**[3:08]** until you surpass human level performance.
**[3:12]** And it sometimes slows down after you surpass human level performance.
**[3:16]** And I think there are two reasons for
**[3:18]** that, for why progress often slows down when you surpass human level performance.
**[3:22]** One reason is that human level performance is for
**[3:25]** many tasks not that far from Bayes' optimal error.
**[3:28]** People are very good at looking at images and telling if there's a cat or
**[3:32]** listening to audio and transcribing it.
**[3:34]** So, by the time you surpass human level performance maybe there's not that much
**[3:38]** head room to still improve.
**[3:42]** But the second reason is that so long as your performance is worse than human level
**[3:46]** performance, then there are actually certain tools you could use to improve
**[3:50]** performance that are harder to use once you've surpassed human level performance.
**[3:55]** So here's what I mean.
**[3:59]** For tasks that humans are quite good at, and
**[4:02]** this includes looking at pictures and recognizing things, or listening to audio,
**[4:07]** or reading language, really natural data tasks humans tend to be very good at.
**[4:11]** For tasks that humans are good at, so long as your machine learning algorithm is
**[4:16]** still worse than the human, you can get labeled data from humans.
**[4:20]** That is you can ask people, ask/hire humans, to label examples for you so
**[4:25]** that you can have more data to feed your learning algorithm.
**[4:29]** Something we'll talk about next week is manual error analysis.
**[4:33]** But so long as humans are still performing better than any other algorithm, you can
**[4:37]** ask people to look at examples that your algorithm's getting wrong, and try to gain
**[4:41]** insight in terms of why a person got it right but the algorithm got it wrong.
**[4:44]** And we'll see next week that this helps improve your algorithm's performance.
**[4:48]** And you can also get a better analysis of bias and
**[4:51]** variance which we'll talk about in a little bit.
**[4:53]** But so long as your algorithm is still doing worse then humans
**[4:56]** you have these important tactics for improving your algorithm.
**[5:00]** Whereas once your algorithm is doing better than humans,
**[5:03]** then these three tactics are harder to apply.
**[5:07]** So, this is maybe another reason why comparing to human level performance
**[5:11]** is helpful, especially on tasks that humans do well.
**[5:17]** And why machine learning algorithms tend to be really good
**[5:21]** at trying to replicate tasks that people can do and kind of catch up and
**[5:25]** maybe slightly surpass human level performance.
**[5:29]** In particular, even though you know what is bias and what is variance it turns out
**[5:34]** that knowing how well humans can do on a task can help you understand better how
**[5:38]** much you should try to reduce bias and how much you should try to reduce variance.
**[5:43]** I want to show you an example of this in the next video.
