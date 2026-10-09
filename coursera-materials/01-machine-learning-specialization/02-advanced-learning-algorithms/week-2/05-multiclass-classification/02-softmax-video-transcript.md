---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 2
section: Multiclass Classification
item_title: Softmax
duration: 12 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/mzLuU/softmax
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Softmax — Transcript

**[0:01]** The softmax regression algorithm is
**[0:04]** a generalization of logistic regression,
**[0:07]** which is a binary classification algorithm
**[0:10]** to the multiclass classification contexts.
**[0:13]** Let's take a look at how works.
**[0:15]** Recall that logistic regression applies when
**[0:19]** y can take on two possible output values,
**[0:23]** either zero or one,
**[0:25]** and the way it computes this output is,
**[0:29]** you would first calculate z equals
**[0:31]** w.product of x plus b,
**[0:34]** and then you would compute what I'm going to call here
**[0:37]** a equals g of z which is a sigmoid function applied to z.
**[0:42]** We interpreted this as logistic regressions estimates of
**[0:47]** the probability of y being equal to
**[0:49]** 1 given those input features x.
**[0:52]** Now, quick quiz question;
**[0:56]** if the probability of y equals 1 is 0.71,
**[1:01]** then what is the probability that y is equal to zero?
**[1:07]** Well, the chance of y being the one,
**[1:10]** and the chances of y being the zero,
**[1:12]** they've got to add up to one, right?
**[1:14]** So there's a 71 percent chance of it being one,
**[1:17]** there has to be a 29 percent or
**[1:20]** 0.29 chance of it being equal to zero.
**[1:24]** To embellish logistic regression a little bit in
**[1:28]** order to set us up for
**[1:29]** the generalization to softmax regression,
**[1:31]** I'm going to think of logistic regression as actually
**[1:34]** computing two numbers: First a_1
**[1:38]** which is this quantity that we had previously
**[1:41]** of the chance of y being equal to 1 given x,
**[1:45]** and second, I'm going to think of
**[1:47]** logistic regression as also computing a_2,
**[1:50]** which is 1 minus this which is
**[1:55]** just the chance of y being
**[1:58]** equal to zero given the input features x,
**[2:01]** and so a_1 and a_2,
**[2:02]** of course, have to add up to 1.
**[2:05]** Let's now generalize this to softmax regression,
**[2:10]** and I'm going to do this with a concrete example of
**[2:14]** when y can take on four possible outputs,
**[2:17]** so y can take on the values 1,
**[2:19]** 2, 3 or 4.
**[2:22]** Here's what softmax regression will do,
**[2:25]** it will compute z_1 as w_1.product with x plus b_1,
**[2:32]** and then z_2 equals w_2.product of x plus b_2,
**[2:36]** and so on for z_3 and z_4.
**[2:39]** Here, w_1,
**[2:41]** w_2, w_3,
**[2:42]** w_4 as well as b_1, b_2, b_3,
**[2:45]** b_4, these are the parameters of softmax regression.
**[2:50]** Next, here's the formula for softmax regression,
**[2:55]** we'll compute a_1 equals e^z_1 divided by e^ z_1,
**[3:02]** plus e^ z_2,
**[3:03]** plus e^z_3 plus,
**[3:05]** e^ z_4, and a_1 will be interpreted as
**[3:09]** the algorithms estimate of the chance of
**[3:12]** y being equal to 1 given the input features x.
**[3:16]** Then the formula for softmax regression,
**[3:20]** we'll compute a_2 equals
**[3:23]** e^ z_2 divided by the same denominator,
**[3:26]** e^z_1 plus e^z_2,
**[3:28]** plus e^z_3, plus e^z4,
**[3:30]** and we'll interpret a_2 as the algorithms estimate of
**[3:34]** the chance that y is equal to
**[3:35]** 2 given the input features x.
**[3:38]** Similarly for a_3,
**[3:40]** where here the numerator is
**[3:42]** now e^z_3 divided by the same denominator,
**[3:45]** that's the estimated chance of y being a_3,
**[3:47]** and similarly a_4 takes on this expression.
**[3:52]** Whereas on the left,
**[3:54]** we wrote down the specification
**[3:56]** for the logistic regression model,
**[3:58]** these equations on the right are
**[4:02]** our specification for the softmax regression model.
**[4:05]** It has parameters w_1 through w_4,
**[4:09]** and b_1 through b_4,
**[4:11]** and if you can learn
**[4:13]** appropriate choices to all these parameters,
**[4:15]** then this gives you a way of
**[4:17]** predicting what's the chance of y being 1,
**[4:20]** 2, 3 or 4,
**[4:21]** given a set of input features x.
**[4:24]** Quick quiz, let's see,
**[4:26]** run softmax regression on a new input x,
**[4:29]** and you find that a_1 is 0.30,
**[4:32]** a_2 is 0.20, a_3 is 0.15.
**[4:39]** What do you think a_4 will be?
**[4:42]** Why don't you take a look at this quiz and see
**[4:44]** if you can figure out the right answer?
**[4:48]** You might have realized that because
**[4:51]** the chance of y take on the values of 1,
**[4:54]** 2, 3 or 4, they have to add up to one,
**[4:57]** a_4 the chance of y being with a four has to be 0.35,
**[5:03]** which is 1 minus 0.3 minus 0.2 minus 0.15.
**[5:07]** Here I wrote down the formulas for
**[5:10]** softmax regression in the case of four possible outputs,
**[5:14]** and let's now write down the formula for
**[5:17]** the general case for softmax regression.
**[5:20]** In the general case,
**[5:22]** y can take on n possible values,
**[5:24]** so y can be 1, 2, 3,
**[5:26]** and so on up to n. In that case,
**[5:30]** softmax regression will compute to z_ j
**[5:34]** equals w_ j.product with x plus b_j,
**[5:38]** where now the parameters of softmax regression are w_1,
**[5:42]** w_2 through to w_n,
**[5:45]** as well as b_1, b_2 through b_n.
**[5:49]** Then finally, we'll compute a j equals
**[5:53]** e to the z j divided by sum from k equals 1
**[5:58]** to n of e to the z sub k. While here I'm using
**[6:03]** another variable k to index the summation because
**[6:07]** here j refers to a specific fixed number like j equals 1.
**[6:12]** A, j is interpreted as
**[6:14]** the model's estimate that y is
**[6:17]** equal to j given the input features x.
**[6:20]** Notice that by construction that this formula,
**[6:24]** if you add up a1,
**[6:25]** a2 all the way through a n,
**[6:27]** these numbers always will end up adding up to 1.
**[6:30]** We specified how you would
**[6:32]** compute the softmax regression model.
**[6:36]** I won't prove it in this video,
**[6:37]** but it turns out that if you apply
**[6:39]** softmax regression with n equals 2,
**[6:42]** so there are only two possible output classes
**[6:46]** then softmax regression ends up
**[6:48]** computing basically the same
**[6:50]** thing as logistic regression.
**[6:52]** The parameters end up being a little bit different,
**[6:54]** but it ends up reducing to logistic regression model.
**[6:58]** But that's why the softmax regression model
**[7:00]** is the generalization of logistic regression.
**[7:03]** Having defined how softmax regression
**[7:06]** computes it's outputs,
**[7:08]** let's now take a look at how to
**[7:09]** specify the cost function for softmax regression.
**[7:13]** Recall for logistic regression, this is what we had.
**[7:17]** We said z is equal to this.
**[7:20]** Then I wrote earlier that a1 is g of z,
**[7:24]** was interpreted as a probability of y is 1.
**[7:27]** We also wrote a2 is the probability that y is equal to 0.
**[7:34]** Previously, we had written
**[7:37]** the loss of logistic regression as
**[7:39]** negative y log a1 minus 1 minus y log 1 minus a1.
**[7:46]** But 1 minus a1 is also equal to a2,
**[7:52]** because a2 is one minus a1
**[7:55]** according to this expression over here.
**[7:58]** I can rewrite or simplify the loss
**[8:01]** for logistic regression little bit to be
**[8:04]** negative y log a1 minus 1 minus y log of a2.
**[8:10]** In other words, the loss if y is equal to 1
**[8:14]** is negative log a1.
**[8:18]** If y is equal to 0, then the loss is negative log a2,
**[8:24]** and then same as before the cost function for
**[8:27]** all the parameters in the model is the average loss,
**[8:30]** average over the entire training set.
**[8:33]** That was a cost function for this regression.
**[8:36]** Let's write down the cost function that
**[8:40]** is conventionally use the softmax regression.
**[8:44]** Recall that these are the equations
**[8:46]** we use for softmax regression.
**[8:49]** The loss we're going to use for
**[8:51]** softmax regression is just this.
**[8:54]** The loss for if the algorithm puts a1 through an.
**[9:01]** The ground truth label is why is if y equals 1,
**[9:07]** the loss is negative log a1.
**[9:09]** Says negative log of the probability that
**[9:12]** it thought y was equal to 1,
**[9:15]** or if y is equal to 2,
**[9:17]** then I'm going to define as negative log a2.
**[9:22]** Y is equal to 2.
**[9:24]** The loss of the algorithm on this example
**[9:27]** is negative log of
**[9:29]** the probability it's thought y was equal to 2.
**[9:32]** On all the way down to if y is equal to n,
**[9:35]** then the loss is negative log of
**[9:38]** a n. To illustrate what this is doing,
**[9:43]** if y is equal to j,
**[9:46]** then the loss is negative log of a j.
**[9:52]** That's what this function looks like.
**[9:54]** Negative log of a j is a curve that looks like this.
**[9:59]** If a j was very close to 1,
**[10:03]** then you beyond this part of
**[10:05]** the curve and the loss will be very small.
**[10:07]** But if it thought, say,
**[10:09]** a j had only a 50% chance
**[10:12]** then the loss gets a little bit bigger.
**[10:14]** The smaller a j is,
**[10:17]** the bigger the loss.
**[10:19]** This incentivizes the algorithm to
**[10:21]** make a j as large as possible,
**[10:25]** as close to 1 as possible.
**[10:26]** Because whatever the actual value y was,
**[10:29]** you want the algorithm to say
**[10:30]** hopefully that the chance of
**[10:32]** y being that value was pretty large.
**[10:35]** Notice that in this loss function,
**[10:37]** y in each training example can take on only one value.
**[10:42]** You end up computing this negative log of
**[10:46]** a j only for one value of a j,
**[10:50]** which is whatever was the actual value of
**[10:52]** y equals j in that particular training example.
**[10:55]** For example, if y was equal to 2,
**[10:57]** you end up computing negative log of a2,
**[11:00]** but not any of the other negative log
**[11:02]** of a1 or the other terms here.
**[11:04]** That's the form of the model as well as
**[11:07]** the cost function for softmax regression.
**[11:09]** If you were to train this model,
**[11:12]** you can start to build
**[11:13]** multiclass classification algorithms.
**[11:16]** What we'd like to do next is
**[11:18]** take this softmax regression model,
**[11:21]** and fit it into a new network
**[11:23]** so that you really do something even better,
**[11:25]** which is to train
**[11:27]** a new network for multi-class classification.
**[11:30]** Let's go through that in the next video.
