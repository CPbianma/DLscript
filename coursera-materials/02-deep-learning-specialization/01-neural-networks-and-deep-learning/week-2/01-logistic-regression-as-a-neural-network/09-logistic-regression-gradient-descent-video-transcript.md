---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 2
section: Logistic Regression as a Neural Network
item_title: Logistic Regression Gradient Descent
duration: 7 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/5sdh6/logistic-regression-gradient-descent
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Logistic Regression Gradient Descent — Transcript

**[0:00]** Welcome back. In this video,
**[0:02]** we'll talk about how to compute derivatives for you
**[0:04]** to implement gradient descent for logistic regression.
**[0:08]** The key takeaways will be what you need to implement.
**[0:11]** That is, the key equations you need in order to
**[0:13]** implement gradient descent for logistic regression.
**[0:17]** In this video, I want to do this computation using the computation graph.
**[0:22]** I have to admit, using the computation graph is a little bit of
**[0:25]** an overkill for deriving gradient descent for logistic regression,
**[0:29]** but I want to start explaining things this
**[0:31]** way to get you familiar with these ideas so that,
**[0:33]** hopefully, it will make a bit more sense when we talk about full-fledged neural networks.
**[0:38]** To that, let's dive into gradient descent for logistic regression.
**[0:44]** To recap, we had set up logistic regression as follows,
**[0:49]** your predictions, Y_hat, is defined as follows,
**[0:53]** where z is that.
**[0:56]** If we focus on just one example for now, then the loss,
**[1:01]** or respect to that one example,
**[1:03]** is defined as follows,
**[1:05]** where A is the output of logistic regression,
**[1:07]** and Y is the ground truth label.
**[1:10]** Let's write this out as a computation graph and for this example,
**[1:15]** let's say we have only two features, X1 and X2.
**[1:20]** In order to compute Z,
**[1:22]** we'll need to input W1,
**[1:27]** W2, and B, in addition to the feature values X1, X2.
**[1:31]** These things, in a computational graph,
**[1:33]** get used to compute Z, which is W1,
**[1:36]** X1 + W2 X2 + B,
**[1:41]** rectangular box around that.
**[1:45]** Then, we compute Y_hat,
**[1:48]** or A = Sigma_of_Z,
**[1:52]** that's the next step in the computation graph, and then, finally,
**[1:55]** we compute L, AY,
**[1:58]** and I won't copy the formula again.
**[2:01]** In logistic regression, what we want to do is to modify the parameters,
**[2:06]** W and B, in order to reduce this loss.
**[2:12]** We've described the forward propagation steps of how you actually
**[2:15]** compute the loss on a single training example,
**[2:19]** now let's talk about how you can go backwards to compute the derivatives.
**[2:23]** Here's a cleaned-up version of the diagram.
**[2:26]** Because what we want to do is compute derivatives with respect to this loss,
**[2:30]** the first thing we want to do when going backwards is to
**[2:33]** compute the derivative of this loss with respect to,
**[2:38]** the script over there, with respect to this variable A.
**[2:41]** So, in the code,
**[2:43]** you just use DA to denote this variable.
**[2:49]** It turns out that if you are familiar with calculus,
**[2:52]** you could show that this ends up being -Y_over_A+1-Y_over_1-A.
**[3:02]** And the way you do that is you take the formula for the loss and,
**[3:06]** if you're familiar with calculus,
**[3:07]** you can compute the derivative with respect to the variable,
**[3:10]** lowercase A, and you get this formula.
**[3:12]** But if you're not familiar with calculus, don't worry about it.
**[3:15]** We'll provide the derivative formulas,
**[3:17]** what else you need, throughout this course.
**[3:20]** If you are an expert in calculus,
**[3:21]** I encourage you to look up the formula for the loss from
**[3:24]** their previous slide and try taking derivative with respect to A using calculus,
**[3:29]** but if you don't know enough calculus to do that, don't worry about it.
**[3:32]** Now, having computed this quantity of DA and
**[3:35]** the derivative or your final alpha variable with respect to A,
**[3:38]** you can then go backwards.
**[3:40]** It turns out that you can show DZ which,
**[3:45]** this is the part called variable name,
**[3:47]** this is going to be the derivative of the loss,
**[3:51]** with respect to Z, or for L,
**[3:53]** you could really write the loss including A and Y explicitly as parameters or not, right?
**[3:59]** Either type of notation is equally acceptable.
**[4:04]** We can show that this is equal to A-Y.
**[4:09]** Just a couple of comments only for those of you experts in calculus,
**[4:14]** if you're not expert in calculus, don't worry about it.
**[4:16]** But it turns out that this, DL DZ,
**[4:20]** this can be expressed as DL_DA_times_DA_DZ,
**[4:27]** and it turns out that DA DZ,
**[4:29]** this turns out to be A_times_1-A,
**[4:33]** and DL DA we have previously worked out over here,
**[4:37]** if you take these two quantities, DL DA,
**[4:41]** which is this term, together with DA DZ,
**[4:43]** which is this term, and just take these two things and multiply them.
**[4:47]** You can show that the equation simplifies to A-Y.
**[4:51]** That's how you derive it,
**[4:53]** and that this is really the chain rule that have briefly eluded to the form.
**[4:57]** Feel free to go through that calculation yourself if you are knowledgeable in calculus,
**[5:02]** but if you aren't, all you need to know is that you can compute
**[5:05]** DZ as A-Y and we've already done that calculus for you.
**[5:09]** Then, the final step in that computation is to go back to
**[5:13]** compute how much you need to change W and B.
**[5:17]** In particular, you can show that the derivative with respect to W1 and in quotes,
**[5:24]** call this DW1, that this is equal to X1_times_DZ.
**[5:31]** Then, similarly, DW2, which is how much you want to change W2,
**[5:36]** is X2_times_DZ and B,
**[5:39]** excuse me, DB is equal to DZ.
**[5:42]** If you want to do gradient descent with respect to just this one example,
**[5:47]** what you would do is the following;
**[5:49]** you would use this formula to compute DZ,
**[5:52]** and then use these formulas to compute DW1, DW2,
**[5:56]** and DB, and then you perform these updates.
**[6:01]** W1 gets updated as W1 minus,
**[6:04]** learning rate alpha, times DW1.
**[6:06]** W2 gets updated similarly,
**[6:09]** and B gets set as B minus the learning rate times DB.
**[6:14]** And so, this will be one step of grade with respect to a single example.
**[6:18]** You see in how to compute derivatives and implement
**[6:22]** gradient descent for logistic regression with respect to a single training example.
**[6:27]** But training logistic regression model,
**[6:28]** you have not just one training example given training sets of M training examples.
**[6:34]** In the next video,
**[6:36]** let's see how you can take these ideas and apply them to learning,
**[6:39]** not just from one example,
**[6:40]** but from an entire training set.
