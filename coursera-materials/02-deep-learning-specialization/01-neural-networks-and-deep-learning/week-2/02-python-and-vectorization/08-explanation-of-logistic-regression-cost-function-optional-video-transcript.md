---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 2
section: Python and Vectorization
item_title: Explanation of Logistic Regression Cost Function (Optional)
duration: 7 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/SmIbQ/explanation-of-logistic-regression-cost-function-optional
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Explanation of Logistic Regression Cost Function (Optional) — Transcript

**[0:00]** In an earlier video, I've written down a form for the cost function for
**[0:03]** logistic regression.
**[0:05]** In this optional video, I want to give you a quick justification for
**[0:09]** why we like to use that cost function for logistic regression.
**[0:13]** To quickly recap, in logistic regression,
**[0:16]** we have that the prediction y hat is sigmoid of w transpose x + b,
**[0:22]** where sigmoid is this familiar function.
**[0:27]** And we said that we want to interpret y hat as the p( y = 1 | x).
**[0:37]** So we want our algorithm to output y hat as the chance
**[0:40]** that y = 1 for a given set of input features x.
**[0:45]** So another way to say this is that if y is equal to 1
**[0:50]** then the chance of y given x is equal to y hat.
**[0:56]** And conversely if y is equal to 0 then
**[1:00]** the chance that y was 0 was 1- y hat, right?
**[1:05]** So if y hat was a chance, that y = 1,
**[1:09]** then 1- y hat is the chance that y = 0.
**[1:13]** So, let me take these last two equations and just copy them to the next slide.
**[1:18]** So what I'm going to do is take these two equations which
**[1:22]** basically define p(y|x) for the two cases of y = 0 or y = 1.
**[1:28]** And then take these two equations and summarize them into a single equation.
**[1:33]** And just to point out y has to be either 0 or 1 because in binary cost equations,
**[1:37]** y = 0 or 1 are the only two possible cases, all right.
**[1:41]** When someone take these two equations and summarize them as follows.
**[1:44]** Let me just write out what it looks like, then we'll explain why it looks like that.
**[1:48]** So (1 – y hat) to the power of (1 – y).
**[1:54]** So it turns out this one line summarizes the two equations on top.
**[1:58]** Let me explain why.
**[2:00]** So in the first case, suppose y = 1, right?
**[2:04]** So if y = 1 then this term ends up being y hat,
**[2:09]** because that's y hat to the power of 1.
**[2:13]** This term ends up being 1- y hat to the power of 1- 1, so that's the power of 0.
**[2:21]** But, anything to the power of 0 is equal to 1, so that goes away.
**[2:26]** And so, this equation, just as p(y|x) = y hat, when y = 1.
**[2:33]** So that's exactly what we wanted.
**[2:37]** Now how about the second case, what if y = 0?
**[2:40]** If y = 0, then this equation above is p(y|x) = y hat to the 0,
**[2:47]** but anything to the power of 0 is equal to 1, so
**[2:51]** that's just equal to 1 times 1- y hat to the power of 1- y.
**[2:58]** So 1- y is 1- 0, so this is just 1.
**[3:02]** And so this is equal to 1 times (1- y hat) = 1- y hat.
**[3:10]** And so here we have that the y = 0, p (y|x) = 1- y hat,
**[3:17]** which is exactly what we wanted above.
**[3:21]** So what we've just shown is that this equation
**[3:25]** is a correct definition for p(ylx).
**[3:30]** Now, finally, because the log function is a strictly monotonically increasing function,
**[3:36]** your maximizing log p(y|x) should give you a similar result as
**[3:43]** optimizing p(y|x). And if you compute log of p(y|x), that’s equal to
**[3:48]** log of y hat to the power of y, 1 - y hat to the power of 1 - y.
**[3:54]** And so that simplifies to y log y hat
**[4:00]** + 1- y times log 1- y hat, right?
**[4:07]** And so this is actually negative of the loss
**[4:10]** function that we had to find previously.
**[4:14]** And there's a negative sign there because usually if you're training a learning
**[4:17]** algorithm, you want to make probabilities large
**[4:20]** whereas in logistic regression we're expressing this.
**[4:23]** We want to minimize the loss function.
**[4:25]** So minimizing the loss corresponds to maximizing the log of the probability.
**[4:30]** So this is what the loss function on a single example looks like.
**[4:33]** How about the cost function,
**[4:35]** the overall cost function on the entire training set on m examples?
**[4:40]** Let's figure that out.
**[4:41]** So, the probability of all the labels In the training set.
**[4:45]** Writing this a little bit informally.
**[4:47]** If you assume that the training examples I've drawn independently or drawn IID,
**[4:51]** identically independently distributed,
**[4:54]** then the probability of the example is the product of probabilities.
**[4:57]** The product from i = 1 through m p(y(i) ) given x(i).
**[5:03]** And so if you want to carry out maximum likelihood estimation, right,
**[5:07]** then you want to maximize the, find the parameters that maximizes
**[5:12]** the chance of your observations and training set.
**[5:15]** But maximizing this is the same as maximizing the log, so
**[5:20]** we just put logs on both sides.
**[5:22]** So log of the probability of the labels in the training set is equal to,
**[5:28]** log of a product is the sum of the log.
**[5:30]** So that's sum from i=1 through m of log p(y(i)) given x(i).
**[5:39]** And we have previously figured out on the previous
**[5:43]** slide that this is negative L of y hat i, y i.
**[5:48]** And so in statistics, there's a principle called the principle of maximum likelihood
**[5:55]** estimation, which just means to choose the parameters that maximizes this thing.
**[6:00]** Or in other words, that maximizes this thing.
**[6:04]** Negative sum from i = 1 through m L(y hat ,y) and
**[6:09]** just move the negative sign outside the summation.
**[6:11]** So this justifies the cost we had for
**[6:15]** logistic regression which is J(w,b) of this.
**[6:21]** And because we now want to minimize the cost instead of maximizing likelihood,
**[6:27]** we've got to rid of the minus sign.
**[6:30]** And then finally for convenience, to make sure that our quantities are better scale,
**[6:35]** we just add a 1 over m extra scaling factor there.
**[6:39]** But so to summarize, by minimizing this cost function J(w,b) we're really
**[6:43]** carrying out maximum likelihood estimation with the logistic regression model.
**[6:48]** Under the assumption that our training examples were IID, or
**[6:53]** identically independently distributed.
**[6:55]** So thank you for watching this video, even though this is optional.
**[6:59]** I hope this gives you a sense of why we use the cost function we do for
**[7:03]** logistic regression.
**[7:05]** And with that, I hope you go on to the programming exercises and
**[7:09]** the quiz questions of this week.
**[7:11]** And best of luck with both the quizzes, and the programming exercise.
