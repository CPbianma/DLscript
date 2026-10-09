---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 2
section: Logistic Regression as a Neural Network
item_title: Logistic Regression Cost Function
duration: 8 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/yWaRd/logistic-regression-cost-function
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Logistic Regression Cost Function — Transcript

**[0:00]** In the previous video, you saw the logistic regression model
**[0:04]** to train the parameters W and B, of logistic regression model.
**[0:08]** You need to define a cost function, let's take a look at the cost function.
**[0:12]** You can use to train logistic regression to recap this is what we have defined from
**[0:16]** the previous slide.
**[0:18]** So you output Y hat is sigmoid of W transports experts be where sigmoid of
**[0:23]** Z is as defined here.
**[0:24]** So to learn parameters for your model, you're given a training set of
**[0:29]** training examples and it seems natural that you want to find parameters W and B.
**[0:34]** So that at least on the training set, the outputs you have the predictions you have
**[0:38]** on the training set, which I will write as
**[0:40]** y hat I that that will be close to the ground troops labels y I that you
**[0:45]** got in the training set.
**[0:48]** So to fill in a little bit more detail for the equation on top,
**[0:52]** we had said that y hat as defined at the top for a training example X.
**[0:58]** And of course for each training example, we're using these superscripts with
**[1:02]** round brackets with parentheses to index into different train examples.
**[1:07]** Your prediction on training example I which is y hat I is
**[1:11]** going to be obtained by taking the sigmoid function and
**[1:15]** applying it to W transposed X I the input for the training example plus B.
**[1:21]** And you can also define Z I as follows where Z I is equal to,
**[1:26]** you know, W transport Z I plus B.
**[1:29]** So throughout this course we're going to use this notational convention
**[1:36]** that the super strip parentheses I refers to data be an X or Y or Z.
**[1:42]** Or something else associated with the I've training example associated
**[1:48]** with the life example, okay, that's what the superscript I in parenthesis means.
**[1:54]** Now let's see what loss function or
**[1:57]** an error function we can use to measure how well our album is doing.
**[2:01]** One thing you could do is define the loss when your algorithm outputs y hat and
**[2:06]** the true label is y to be maybe the square error or one half a square error.
**[2:12]** It turns out that you could do this, but
**[2:14]** in logistic regression people don't usually do this.
**[2:17]** Because when you come to learn the parameters, you find that the optimization
**[2:22]** problem, which we'll talk about later becomes non convex.
**[2:25]** So you end up with optimization problem, you're with multiple local optima.
**[2:30]** So great in dissent, may not find a global optimum, if you didn't understand the last
**[2:34]** couple of comments, don't worry about it, Ww'll get to it in a later video.
**[2:38]** But the intuition to take away is that dysfunction L called the loss
**[2:43]** function is a function will need to define to measure how good our
**[2:47]** output y hat is when the true label is y.
**[2:51]** And squared era seems like it might be a reasonable choice except that
**[2:55]** it makes great in descent not work well.
**[2:58]** So in logistic regression were actually define a different loss function
**[3:02]** that plays a similar role as squared error but
**[3:05]** will give us an optimization problem that is convex.
**[3:09]** And so we'll see in a later video becomes much easier to optimize, so
**[3:14]** what we use in logistic regression is actually the following loss function,
**[3:19]** which I'm just going right out here is negative.
**[3:25]** y log y hat plus 1 minus y log 1 minus,
**[3:30]** y hat here's some intuition on why this loss function makes sense.
**[3:38]** Keep in mind that if we're using squared error then you want to square
**[3:43]** error to be as small as possible.
**[3:45]** And with this logistic regression,
**[3:47]** lost function will also want this to be as small as possible.
**[3:51]** To understand why this makes sense, let's look at the two cases,
**[3:55]** in the first case let's say y is equal to 1, then the loss function.
**[4:01]** y hat comma Y is just this first term right in this negative science,
**[4:06]** it's negative log y hat if y is equal to 1.
**[4:09]** Because if y equals 1, then the second term 1 minus Y is equal to 0, so
**[4:14]** this says if y equals 1, you want negative log y hat to be as small as possible.
**[4:20]** So that means you want log y hat to be large to be as big as possible,
**[4:28]** and that means you want y hat to be large.
**[4:33]** But because y hat is you know the sigmoid function, it can never be bigger than one.
**[4:38]** So this is saying that if y is equal to 1, you want,
**[4:41]** y hat to be as big as possible, but it can't ever be bigger than one.
**[4:45]** So saying you want, y hat to be close to one as well,
**[4:49]** the other case is Y equals zero, if Y equals 0.
**[4:52]** Then this first term in the loss function is equal to 0 because y equals 0,
**[4:58]** and in the second term defines the loss function.
**[5:02]** So the loss becomes negative Log 1 minus y hat, and so
**[5:06]** if in your learning procedure you try to make the loss function small.
**[5:11]** What this means is that you want, Log 1 minus y hat
**[5:16]** to be large and because it's a negative sign there.
**[5:22]** And then through a similar piece of reasoning, you can conclude that this
**[5:27]** loss function is trying to make y hat as small as possible, and
**[5:31]** again, because y hat has to be between zero and 1.
**[5:34]** This is saying that if y is equal to zero then your loss function will
**[5:39]** push the parameters to make y hat as close to zero as possible.
**[5:44]** Now there are a lot of functions with roughly this effect that if y is equal to
**[5:48]** one, try to make y hat large and y is equal to zero or
**[5:51]** try to make y hat small.
**[5:53]** We just gave here in green a somewhat informal justification for
**[5:57]** this particular loss function we will provide an optional video later
**[6:02]** to give a more formal justification for y.
**[6:04]** In logistic regression, we like to use the loss function with this particular form.
**[6:08]** Finally, the last function was defined with respect to a single training example.
**[6:14]** It measures how well you're doing on a single training example,
**[6:17]** I'm now going to define something called the cost function,
**[6:21]** which measures how are you doing on the entire training set.
**[6:25]** So the cost function j, which is applied to your parameters W and B,
**[6:31]** is going to be the average, really one of the m of the sun
**[6:37]** of the loss function apply to each of the training examples.
**[6:42]** In turn, we're here, y hat is of course the prediction output by your logistic
**[6:47]** regression algorithm using, you know, a particular set of parameters W and B.
**[6:53]** And so just to expand this out, this is equal to negative one of them,
**[6:58]** some from I equals one through of the definition of the lost function above.
**[7:03]** So this is y I log y hat I plus 1 minus Y,
**[7:09]** I log 1minus y hat I I guess it can put square brackets here.
**[7:18]** So the minus sign is outside everything else, so the terminology I'm going
**[7:23]** to use is that the loss function is applied to just a single training example.
**[7:28]** Like so and the cost function is the cost of your parameters, so in training
**[7:33]** your logistic regression model, we're going to try to find parameters W and B.
**[7:39]** That minimize the overall cost function J, written at the bottom.
**[7:43]** So you've just seen the setup for the logistic regression algorithm,
**[7:47]** the loss function for training example, and the overall cost function for
**[7:51]** the parameters of your algorithm.
**[7:54]** It turns out that logistic regression can be viewed as a very,
**[7:58]** very small neural network.
**[7:59]** In the next video, we'll go over that so
**[8:01]** you can start gaining intuition about what neural networks do.
**[8:05]** So with that let's go on to the next video about how to view logistic regression as
**[8:10]** a very small neural network.
