---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 2
section: Multiclass Classification
item_title: Multiclass
duration: 3 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/4u2wC/multiclass
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# Multiclass — Transcript

**[0:02]** Multiclass classification refers to classification problems where
**[0:07]** you can have more than just two possible output labels so not just zero or 1.
**[0:13]** Let's take a look at what that means.
**[0:15]** For the handwritten digit classification problems we've looked at so far,
**[0:20]** we were just trying to distinguish between the handwritten digits 0 and 1.
**[0:25]** But if you're trying to read protocols or zip codes in an envelope, well,
**[0:30]** there are actually 10 possible digits you might want to recognize.
**[0:35]** Or alternatively in the first course you saw the example if you're
**[0:41]** trying to classify whether patients may have any of three or
**[0:46]** five different possible diseases.
**[0:49]** That too would be a multiclass classification problem or
**[0:53]** one thing I've worked on a lot is visual defect inspection
**[0:57]** of parts manufacturer in the factory.
**[0:59]** Where you might look at the picture of a pill that a pharmaceutical
**[1:04]** company has manufactured and try to figure out does it have
**[1:09]** a scratch effect or discoloration defects or a chip defect.
**[1:14]** And this would again be multiple classes of multiple different types of
**[1:18]** defects that you could classify this pill is having.
**[1:23]** So a multiclass classification problem is still a classification problem in that y
**[1:29]** you can take on only a small number of discrete categories is not any number,
**[1:34]** but now y can take on more than just two possible values.
**[1:39]** So whereas previously for buying the classification,
**[1:43]** you may have had a data set like this with features x1 and x2.
**[1:48]** In which case logistic regression would fit model to estimate
**[1:53]** what the probability of y being 1, given the features x.
**[1:58]** Because y was either 01 with multiclass classification problems,
**[2:03]** you would instead have a data set that maybe looks like this.
**[2:07]** Where we have four classes where the Os represents one class,
**[2:11]** the xs represent another class.
**[2:14]** The triangles represent the third class and
**[2:16]** the squares represent the fourth class.
**[2:20]** And instead of just estimating the chance of y being equal to 1,
**[2:23]** well, now want to estimate what's the chance that y is equal to 1, or
**[2:28]** what's the chance that y is equal to 2?
**[2:31]** Or what's the chance that y is equal to 3, or the chance of y being equal to 4?
**[2:38]** And it turns out that the algorithm you learned about in the next video can
**[2:43]** learn a decision boundary that maybe looks like this that divides the space
**[2:48]** exploded next to into four categories rather than just two categories.
**[2:54]** So that's the definition of the multiclass classification problem.
**[2:59]** In the next video, we'll look at the softmax regression algorithm which
**[3:04]** is a generalization of the logistic regression algorithm and
**[3:08]** using that you'll be able to carry out multiclass classification problems.
**[3:14]** And after that we'll take softmax regression and
**[3:17]** fit it into a new neural network so that you'll also be able to train a neural
**[3:22]** network to carry out multiclass classification problems.
**[3:25]** Let's go on to the next video.
