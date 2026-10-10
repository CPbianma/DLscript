---
type: video-transcript
specialization: Deep Learning Specialization
course: Structuring Machine Learning Projects
week: 1
section: Comparing to Human-level Performance
item_title: Improving your Model Performance
duration: 5 min
source_url: https://www.coursera.org/learn/machine-learning-projects/lecture/4IPD6/improving-your-model-performance
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Improving your Model Performance — Transcript

**[0:00]** You've heard about orthogonalization,
**[0:02]** how to set up your dev and test sets,
**[0:05]** human-level performance as a proxy for
**[0:07]** Bayes error and how to estimate your avoidable bias and variance.
**[0:11]** Let's pull it all together into a set of guidelines
**[0:14]** to how to improve the performance of your learning algorithm.
**[0:17]** So, I think getting a supervised learning algorithm to work well means
**[0:20]** fundamentally hoping or assuming they can do two things.
**[0:25]** First, is that you can fit the training set pretty well,
**[0:29]** and you can think of this as roughly saying that you can achieve low avoidable bias.
**[0:38]** And the second thing you're assuming you can do well,
**[0:41]** is that doing well on the training set
**[0:43]** generalizes pretty well to the dev set or the test set,
**[0:46]** and this is sort of saying that variance is not too bad.
**[0:51]** And in the spirit of orthogonalization,
**[0:54]** what you see is that there's a certain set of knobs you can
**[0:56]** use to fix avoidable bias issues,
**[0:59]** such as training a bigger network or training longer,
**[1:03]** and as a separate set of things you could use to address variance problems,
**[1:09]** such as regularization or getting more training data.
**[1:12]** So, to summarize up the process we've seen in the last several videos,
**[1:17]** if you want to improve the performance of your machine learning system,
**[1:21]** I would recommend looking at the difference between your training error and
**[1:26]** your proxy for Bayes error and just gives you a sense of the avoidable bias.
**[1:31]** In other words, just how much better do you
**[1:34]** think you should be trying to do on your training set.
**[1:37]** And then look at the difference between your dev error and
**[1:39]** your training error as an estimate of how much of a variance problem you have.
**[1:44]** In other words, how much harder you should be
**[1:46]** working to make your performance generalized from
**[1:48]** the training set to the dev set that it wasn't trained on explicitly.
**[1:57]** So, to whatever extent you want to try to reduce avoidable bias,
**[2:02]** I would try to apply tactics like train a bigger model.
**[2:07]** So, you can just do better on your training sets or train longer,
**[2:11]** use a better optimization algorithm,
**[2:13]** such as ADS momentum or RMSprop,
**[2:21]** or use a better algorithm like Adam,
**[2:27]** or one other thing you could try is to just find
**[2:32]** a better neural network architecture or better set of hyperparameters,
**[2:37]** and this could include everything from changing
**[2:39]** the activation function to changing the number of layers or hidden units.
**[2:43]** Although if you do that, it would be in the direction of increasing
**[2:46]** the model size to trying out other models or other model architectures,
**[2:52]** such as recurrent neural networks and convolutional neural networks,
**[2:57]** which we'll see in later courses.
**[2:59]** Whether or not a new neural network architecture will
**[3:02]** fit your training set better is sometimes hard to tell in advance,
**[3:05]** but sometimes you can get much better results with a better architecture.
**[3:10]** Next to the extent that you find out variance is a problem,
**[3:14]** some of the many techniques you could try then includes the following: you can try to get
**[3:20]** more data because getting more data to train on could help you
**[3:24]** generalize better to dev set data that your algorithm didn't see,
**[3:29]** you could try regularization.
**[3:31]** So, this includes things like L2 regularization or dropout or data augmentation,
**[3:39]** which we talked about in the previous course, or once again,
**[3:45]** you can also try various neural network architecture/hyperparameters search to see if
**[3:50]** that can help you find
**[3:52]** a neural network architecture that is better suited for your problem.
**[3:56]** I think that this notion of bias or avoidable bias and
**[4:00]** variance is one of those things that's easily learnt but tough to master.
**[4:04]** And if you're able to systematically apply the concepts from this week's video,
**[4:08]** you actually will be much more efficient and much more systematic and
**[4:11]** much more strategic than a lot of
**[4:15]** machine learning teams in terms of how to
**[4:17]** systematically go about improving the performance of your machine learning system.
**[4:22]** So, that this week's homework will allow you
**[4:26]** to practice and exercise more your understanding of these concepts.
**[4:30]** Best of luck with this week's homework,
**[4:32]** and I look forward to also seeing you in next week's videos.
