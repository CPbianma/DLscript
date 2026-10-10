---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 3
section: Bias and variance
item_title: Deciding what to try next revisited
duration: 9 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/WbRtr/deciding-what-to-try-next-revisited
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Deciding what to try next revisited — Transcript

**[0:01]** You've seen how by looking at J train and Jcv,
**[0:06]** that is the training error and cross-validation error,
**[0:09]** or maybe even plotting a learning curve.
**[0:11]** You can try to get a sense of whether
**[0:13]** your learning algorithm has high bias or high variance.
**[0:17]** This is the procedure I routinely
**[0:19]** do when I'm training a learning algorithm more often
**[0:22]** look at the training error and
**[0:23]** cross-validation error to try
**[0:24]** to decide if my algorithm has high bias or high variance.
**[0:27]** It turns out this will help you make
**[0:29]** better decisions about what to
**[0:31]** try next in order to
**[0:32]** improve the performance of your learning algorithm.
**[0:35]** Let's look at an example.
**[0:37]** This is actually the example that you have seen earlier.
**[0:41]** If you've implemented regularized linear regression
**[0:44]** on predicting housing prices,
**[0:46]** but your algorithm makes
**[0:48]** unacceptably large errors in its predictions,
**[0:51]** what do you try next?
**[0:53]** These were the six ideas that we
**[0:54]** had when we had looked over this slide earlier.
**[0:57]** Getting more training examples,
**[0:58]** try small set of features,
**[0:59]** additional features, and so on.
**[1:01]** It turns out that each of these six items either
**[1:06]** helps fix a high variance or a high bias problem.
**[1:11]** In particular, if your learning algorithm has high bias,
**[1:15]** three of these techniques will be useful.
**[1:18]** If your learning algorithm has high variance than a
**[1:20]** different three of these techniques will be useful.
**[1:24]** Let's see if we can figure out which is which.
**[1:26]** First one is get more training examples.
**[1:31]** We saw in the last video that
**[1:33]** if your algorithm has high bias,
**[1:35]** then if the only thing we do is get more training data,
**[1:40]** that by itself probably won't help that much.
**[1:43]** But in contrast, if your algorithm has high variance,
**[1:46]** say it was overfitting to a very small training set,
**[1:50]** then getting more training examples will help a lot.
**[1:55]** This first option or getting
**[1:57]** more training examples helps to
**[1:59]** fix a high variance problem.
**[2:02]** How about the other five?
**[2:04]** Do you think you can figure out
**[2:05]** which of the remaining five
**[2:07]** fix high bias or high variance problems?
**[2:10]** I'm going to go through the rest of them in
**[2:11]** this video in a minute but if you want it,
**[2:13]** you're free to pause the video and see if you can
**[2:16]** think through these five other things by yourself.
**[2:18]** Feel free to pause the video.
**[2:21]** Just kidding, that was me pausing
**[2:24]** and not your video pausing.
**[2:25]** But seriously, if you want it,
**[2:26]** go ahead and pause the video and
**[2:27]** think through that you want or
**[2:29]** not and we'll go over these review in a minute.
**[2:32]** How about trying a smaller set of features?
**[2:36]** Sometimes if your learning algorithm
**[2:38]** has too many features,
**[2:40]** then it gives your algorithm
**[2:42]** too much flexibility to fit very complicated models.
**[2:46]** This is a little bit like if you had x, x squared,
**[2:50]** x cubed, x^4, x^5, and so on.
**[2:54]** If only you were to eliminate a few of these,
**[2:57]** then your model won't be so
**[2:59]** complex and won't have such high variance.
**[3:03]** If you suspect that
**[3:06]** your algorithm has a lot of features that are
**[3:08]** not actually relevant or
**[3:10]** helpful to predicting housing price,
**[3:12]** or if you suspect that you had
**[3:14]** even somewhat redundant features,
**[3:16]** then eliminating or reducing the number of features will
**[3:20]** help reduce the flexibility
**[3:23]** of your algorithm to overfit the data.
**[3:26]** This is a tactic that will help you to fix high variance.
**[3:30]** Conversing, getting additional features,
**[3:32]** that's just adding additional features is
**[3:34]** the opposite of going to a smaller set of features.
**[3:38]** This will help you to fix a high bias problem.
**[3:42]** As a concrete example,
**[3:43]** if you're trying to predict the price of
**[3:45]** the house just based on the size,
**[3:47]** but it turns out that
**[3:49]** the price of house also really depends on
**[3:51]** the number of bedrooms and on
**[3:53]** the number of floors and on the age of the house,
**[3:56]** then the algorithm will never do that
**[3:59]** well unless you add in those additional features.
**[4:01]** That's a high bias problem because you just can't do
**[4:05]** that well on the training set when only the size,
**[4:09]** is only when you tell the algorithm
**[4:11]** how many bedrooms are there, how many floors are there?
**[4:14]** What's the age of the house that it finally has
**[4:16]** enough information to even do better on the training set.
**[4:20]** Adding additional features is a way
**[4:23]** to fix a high bias problem.
**[4:25]** Adding polynomial features is a little bit
**[4:28]** like adding additional features.
**[4:31]** If you're linear functions,
**[4:33]** three-line can fit the training set that well,
**[4:35]** then adding additional polynomial features
**[4:38]** can help you do better on the training set,
**[4:40]** and helping you do better on
**[4:42]** the training set is a way to fix a high bias problem.
**[4:46]** Then decreasing Lambda means to
**[4:49]** use a lower value for the regularization parameter.
**[4:53]** That means we're going to pay
**[4:55]** less attention to this term and pay
**[4:57]** more attention to this term to
**[4:59]** try to do better on the training set.
**[5:01]** Again, that helps you to fix a high bias problem.
**[5:05]** Finally, increasing Lambda,
**[5:07]** well that's the opposite of this,
**[5:09]** but that says you're overfitting the data.
**[5:12]** Increasing Lambda will make sense
**[5:14]** if is overfitting the training set,
**[5:16]** just putting too much attention to fit the training set,
**[5:20]** but at the expense of generalizing to new examples,
**[5:24]** and so increasing Lambda would
**[5:26]** force the algorithm to fit a smoother function,
**[5:29]** may be less wiggly function and use
**[5:32]** this to fix a high variance problem.
**[5:35]** I realized that this was a lot of stuff on this slide.
**[5:39]** But the takeaways I hope you have are,
**[5:42]** if you find that your algorithm has high variance,
**[5:45]** then the two main ways to fix that are;
**[5:48]** neither get more training data or simplify your model.
**[5:53]** By simplifying model I mean,
**[5:56]** either get a smaller set of features
**[5:58]** or increase the regularization parameter Lambda.
**[6:02]** Your algorithm has less flexibility to fit
**[6:05]** very complex, very wiggly curves.
**[6:08]** Conversely, if your algorithm has high bias,
**[6:12]** then that means is not
**[6:13]** doing well even on the training set.
**[6:15]** If that's the case, the main fixes
**[6:18]** are to make your model more
**[6:20]** powerful or to give them more flexibility to
**[6:23]** fit more complex or more wiggly functions.
**[6:26]** Some ways to do that are to give it
**[6:29]** additional features or add these polynomial features,
**[6:32]** or to decrease the regularization parameter Lambda.
**[6:36]** Anyway, in case you're wondering if you
**[6:39]** should fix high bias by reducing the training set size,
**[6:42]** that doesn't actually help.
**[6:44]** If you reduce the training set size,
**[6:46]** you will fit the training set better,
**[6:48]** but that tends to worsen
**[6:49]** your cross-validation error and
**[6:51]** the performance of your learning algorithm,
**[6:52]** so don't randomly throw away
**[6:54]** training examples just to try to fix a high bias problem.
**[6:57]** One of my PhD students from Stanford,
**[7:00]** many years after he'd already graduated from Stanford,
**[7:02]** once said to me that while he was studying at Stanford,
**[7:07]** he learned about bias and variance and
**[7:09]** felt like he got it, he understood it.
**[7:11]** But that subsequently, after
**[7:13]** many years of work experience
**[7:15]** in a few different companies,
**[7:16]** he realized that bias and variance is one of
**[7:19]** those concepts that takes a short time to learn,
**[7:22]** but takes a lifetime to master.
**[7:24]** Those were his exact words.
**[7:26]** Bias and variance is one of those very powerful ideas.
**[7:31]** When I'm training learning algorithms,
**[7:33]** I almost always try to figure
**[7:35]** out if it is high bias or high variance.
**[7:37]** But the way you go about addressing
**[7:39]** that systematically is something
**[7:42]** that you will keep on getting
**[7:44]** better at through repeated practice.
**[7:48]** But you'll find that
**[7:50]** understanding these ideas will help you be much more
**[7:53]** effective at how you decide what to
**[7:55]** try next when developing a learning algorithm.
**[7:59]** Now, I know that we did go through
**[8:01]** a lot in this video and if you feel like,
**[8:04]** boy, this is a lot of stuff here,
**[8:05]** it's okay, don't worry about it.
**[8:07]** Later this week in
**[8:08]** the practice labs and practice quizzes will have
**[8:11]** also additional opportunities to go over
**[8:14]** these ideas so that you can get additional practice.
**[8:17]** We're thinking about bias and
**[8:19]** variance of different learning algorithms.
**[8:21]** If it seems like a lot right now is okay,
**[8:24]** you get to practice these ideas later this week and
**[8:26]** hopefully deepen your understanding
**[8:28]** of them at that time.
**[8:30]** Before moving on,
**[8:32]** bias and variance also are very useful
**[8:35]** when thinking about how to train a neural network.
**[8:38]** In the next video,
**[8:40]** let's take a look at these concepts
**[8:41]** applied to neural network training.
**[8:44]** Let's go on to the next video.
