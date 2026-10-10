---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 2
section: Logistic Regression as a Neural Network
item_title: Logistic Regression
duration: 6 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/LoKih/logistic-regression
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Logistic Regression — Transcript

**[0:00]** In this video, we'll go over logistic regression.
**[0:03]** This is a learning algorithm that you use when the output labels Y
**[0:07]** in a supervised learning problem are all either zero or one,
**[0:10]** so for binary classification problems.
**[0:13]** Given an input feature vector X maybe corresponding to
**[0:18]** an image that you want to recognize as either a cat picture or not a cat picture,
**[0:23]** you want an algorithm that can output a prediction,
**[0:26]** which we'll call Y hat,
**[0:28]** which is your estimate of Y.
**[0:31]** More formally, you want Y hat to be the probability of the chance that,
**[0:35]** Y is equal to one given the input features X.
**[0:40]** So in other words, if X is a picture,
**[0:43]** as we saw in the last video,
**[0:45]** you want Y hat to tell you,
**[0:47]** what is the chance that this is a cat picture?
**[0:49]** So X, as we said in the previous video,
**[0:53]** is an X dimensional vector,
**[0:56]** given that the parameters of logistic regression will
**[1:02]** be W which is also an X dimensional vector,
**[1:07]** together with b which is just a real number.
**[1:11]** So given an input X and the parameters W and b,
**[1:16]** how do we generate the output Y hat?
**[1:20]** Well, one thing you could try, that doesn't work,
**[1:22]** would be to have Y hat be w transpose X plus B,
**[1:27]** kind of a linear function of the input X.
**[1:33]** And in fact, this is what you use if you were doing linear regression.
**[1:37]** But this isn't a very good algorithm for binary classification
**[1:41]** because you want Y hat to be the chance that Y is equal to one.
**[1:45]** So Y hat should really be between zero and one,
**[1:50]** and it's difficult to enforce that because W transpose X
**[1:54]** plus B can be much bigger than one or it can even be negative,
**[1:58]** which doesn't make sense for probability.
**[2:00]** That you want it to be between zero and one.
**[2:03]** So in logistic regression, our output is instead going to be Y hat
**[2:07]** equals the sigmoid function applied to this quantity.
**[2:12]** This is what the sigmoid function looks like.
**[2:14]** If on the horizontal axis I plot Z, then the function sigmoid of Z looks like this.
**[2:24]** So it goes smoothly from zero up to one.
**[2:28]** Let me label my axes here,
**[2:30]** this is zero and it crosses the vertical axis as 0.5.
**[2:34]** So this is what sigmoid of Z looks like. And we're going to use Z to denote this quantity,
**[2:41]** W transpose X plus B.
**[2:43]** Here's the formula for the sigmoid function.
**[2:46]** Sigmoid of Z, where Z is a real number,
**[2:49]** is one over one plus E to the negative Z.
**[2:52]** So notice a couple of things.
**[2:54]** If Z is very large, then E to the negative Z will be close to zero.
**[3:01]** So then sigmoid of Z will be
**[3:03]** approximately one over one plus something very close to zero,
**[3:07]** because E to the negative of very large number will be close to zero.
**[3:11]** So this is close to 1.
**[3:13]** And indeed, if you look in the plot on the left,
**[3:16]** if Z is very large the sigmoid of Z is very close to one.
**[3:20]** Conversely, if Z is very small,
**[3:24]** or it is a very large negative number,
**[3:29]** then sigmoid of Z becomes one over one plus E to the negative Z,
**[3:39]** and this becomes, it's a huge number.
**[3:42]** So this becomes, think of it as one over one plus a number that is very,
**[3:47]** very big, and so,
**[3:54]** that's close to zero.
**[3:56]** And indeed, you see that as Z becomes a very large negative number,
**[4:00]** sigmoid of Z goes very close to zero.
**[4:03]** So when you implement logistic regression,
**[4:06]** your job is to try to learn parameters W and B so that
**[4:10]** Y hat becomes a good estimate of the chance of Y being equal to one.
**[4:15]** Before moving on, just another note on the notation.
**[4:18]** When we programmed neural networks,
**[4:20]** we'll usually keep the parameter W and parameter B separate,
**[4:26]** where here, B corresponds to an inter-spectrum.
**[4:30]** In some other courses,
**[4:31]** you might have seen a notation that handles this differently.
**[4:35]** In some conventions you define an extra feature called X0 and that equals a one.
**[4:42]** So that now X is in R of NX plus one.
**[4:47]** And then you define Y hat to be equal to sigma of theta transpose X.
**[4:53]** In this alternative notational convention,
**[4:56]** you have vector parameters theta,
**[5:00]** theta zero, theta one, theta two,
**[5:03]** down to theta NX And so,
**[5:09]** theta zero, place a row a B,
**[5:11]** that's just a real number,
**[5:13]** and theta one down to theta NX play the role of W. It turns out,
**[5:18]** when you implement your neural network,
**[5:20]** it will be easier to just keep B and W as separate parameters.
**[5:26]** And so, in this class,
**[5:27]** we will not use any of this notational convention that I just wrote in red.
**[5:32]** If you've not seen this notation before in other courses, don't worry about it.
**[5:36]** It's just that for those of you that have seen this notation I wanted
**[5:39]** to mention explicitly that we're not using that notation in this course.
**[5:43]** But if you've not seen this before,
**[5:45]** it's not important and you don't need to worry about it.
**[5:48]** So you have now seen what the logistic regression model looks like.
**[5:52]** Next to change the parameters W and B you need to define a cost function.
**[5:57]** Let's do that in the next video.
