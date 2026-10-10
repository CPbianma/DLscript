---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 2
section: Multiclass Classification
item_title: Improved implementation of softmax
duration: 9 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/Tyil1/improved-implementation-of-softmax
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Improved implementation of softmax — Transcript

**[0:01]** The implementation that you saw in the last video of
**[0:06]** a neural network with a softmax layer will work okay.
**[0:10]** But there's an even better way to implement it.
**[0:13]** Let's take a look at what can go wrong with
**[0:15]** that implementation and also how to make it better.
**[0:18]** Let me show you two different ways of
**[0:21]** computing the same quantity in a computer.
**[0:24]** Option 1, we can set x equals to 2/10,000.
**[0:28]** Option 2, we can set x equals 1
**[0:32]** plus 1/10,000 minus 1 minus 1/10,000,
**[0:39]** which you first compute this,
**[0:41]** and then compute this, and you take the difference.
**[0:44]** If you simplify this expression,
**[0:46]** this turns out to be equal to 2/10,000.
**[0:50]** Let me illustrate this in this notebook.
**[0:53]** First, let's set x equals 2/10,000 and print
**[0:57]** the result to a lot of
**[0:59]** decimal points of accuracy. That looks pretty good.
**[1:02]** Second, let me set x equals,
**[1:05]** I'm going to insist on computing 1/1 plus
**[1:08]** 10,000 and then subtract from that 1 minus 1/10,000.
**[1:12]** Let's print that out. It just looks a little bit
**[1:16]** off this as if there's some round-off error.
**[1:20]** Because the computer has
**[1:22]** only a finite amount of memory to store each number,
**[1:26]** called a floating-point number in this case,
**[1:28]** depending on how you decide to
**[1:30]** compute the value 2/10,000,
**[1:33]** the result can have more or
**[1:35]** less numerical round-off error.
**[1:38]** It turns out that while the way we have been
**[1:42]** computing the cost function for softmax is correct,
**[1:47]** there's a different way of formulating it that
**[1:49]** reduces these numerical round-off errors,
**[1:52]** leading to more accurate computations within TensorFlow.
**[1:56]** Let me first explain
**[1:58]** this a little bit more detail using logistic regression.
**[2:01]** Then we will show how these ideas apply
**[2:04]** to improving our implementation of softmax.
**[2:07]** First, let me illustrate
**[2:09]** these ideas using logistic regression.
**[2:12]** Then we'll move on to show how to improve
**[2:15]** your implementation of softmax as well.
**[2:17]** Recall that for logistic regression,
**[2:20]** if you want to compute
**[2:22]** the loss function for a given example,
**[2:26]** you would first compute this output activation a,
**[2:28]** which is g of z or 1/1 plus e to the negative z.
**[2:32]** Then you will compute the loss
**[2:34]** using this expression over here.
**[2:38]** In fact, this is what the codes would look like for
**[2:44]** a logistic output layer with
**[2:47]** this binary cross entropy loss.
**[2:50]** For logistic regression, this works okay,
**[2:52]** and usually the numerical
**[2:54]** round-off errors aren't that bad.
**[2:56]** But it turns out that if you allow
**[2:59]** TensorFlow to not have to
**[3:02]** compute a as an intermediate term.
**[3:05]** But instead, if you tell TensorFlow that
**[3:07]** the loss this expression down here.
**[3:10]** All I've done is I've taken a and expanded
**[3:14]** it into this expression down here.
**[3:18]** Then TensorFlow can rearrange
**[3:20]** terms in this expression and
**[3:23]** come up with a more numerically accurate way
**[3:26]** to compute this loss function.
**[3:28]** Whereas the original procedure was like
**[3:31]** insisting on computing as an intermediate value,
**[3:35]** 1 plus 1/10,000 and another intermediate value,
**[3:40]** 1 minus 1/10,000,
**[3:42]** then manipulating these two to get 2/10,000.
**[3:47]** This partial implementation was insisting on explicitly
**[3:50]** computing a as an intermediate quantity.
**[3:54]** But instead, by specifying
**[3:57]** this expression at the bottom
**[3:58]** directly as the loss function,
**[4:00]** it gives TensorFlow more flexibility in terms of
**[4:04]** how to compute this and whether or not
**[4:06]** it wants to compute a explicitly.
**[4:09]** The code you can use to do this
**[4:12]** is shown here and what this does is it
**[4:16]** sets the output layer to just use
**[4:19]** a linear activation function and it
**[4:21]** puts both the activation function,
**[4:25]** 1/1 plus to the negative z,
**[4:27]** as well as this cross entropy loss into
**[4:30]** the specification of the loss function over here.
**[4:35]** That's what this from
**[4:36]** logits equals true argument causes TensorFlow to do.
**[4:41]** In case you're wondering what the logits are,
**[4:44]** it's basically this number z. TensorFlow
**[4:47]** will compute z as an intermediate value,
**[4:51]** but it can rearrange terms to make
**[4:52]** this become computed more accurately.
**[4:55]** One downside of this code is
**[4:58]** it becomes a little bit less legible.
**[5:00]** But this causes TensorFlow
**[5:02]** to have a little bit less numerical roundoff error.
**[5:05]** Now in the case of logistic regression,
**[5:07]** either of these implementations actually works okay,
**[5:11]** but the numerical roundoff errors can get
**[5:13]** worse when it comes to softmax.
**[5:16]** Now let's take this idea and apply to softmax regression.
**[5:20]** Recall what you saw in the last video
**[5:22]** was you compute the activations as follows.
**[5:26]** The activations is g of z_1,
**[5:29]** through z_10 where a_1, for example,
**[5:32]** is e to the z_1 divided by
**[5:34]** the sum of the e to the z_j's,
**[5:38]** and then the loss was this depending on what is
**[5:40]** the actual value of y is negative log of aj
**[5:44]** for one of the aj's and so this was
**[5:47]** the code that we had to do
**[5:49]** this computation in two separate steps.
**[5:52]** But once again, if you instead specify
**[5:55]** that the loss is if y is equal to
**[5:59]** 1 is negative log of this formula, and so on.
**[6:06]** If y is equal to 10 is this formula,
**[6:10]** then this gives TensorFlow the ability to
**[6:15]** rearrange terms and compute
**[6:17]** this integral numerically accurate way.
**[6:20]** Just to give you some intuition for
**[6:22]** why TensorFlow might want to do this,
**[6:25]** it turns out if one of the z's really
**[6:28]** small than e to negative small number becomes very,
**[6:31]** very small or if one of the z's is a very large number,
**[6:35]** then e to the z can become
**[6:36]** a very large number and by rearranging terms,
**[6:39]** TensorFlow can avoid some of
**[6:41]** these very small or very large numbers
**[6:43]** and therefore come up with
**[6:45]** more actress computation for the loss function.
**[6:48]** The code for doing this is
**[6:50]** shown here in the output layer,
**[6:52]** we're now just using a linear activation function so
**[6:56]** the output layer just computes z_1 through z_10
**[7:00]** and this whole computation of
**[7:04]** the loss is then captured in the loss function over here,
**[7:09]** where again we have the from_logists
**[7:11]** equals true parameter.
**[7:13]** Once again, these two pieces of
**[7:16]** code do pretty much the same thing,
**[7:19]** except that the version that is
**[7:20]** recommended is more numerically accurate,
**[7:24]** although unfortunately, it is a
**[7:25]** little bit harder to read as well.
**[7:27]** If you're reading someone else's code
**[7:29]** and you see this and you're wondering
**[7:31]** what's going on is actually
**[7:32]** equivalent to the original implementation,
**[7:35]** at least in concept,
**[7:36]** except that is more numerically accurate.
**[7:38]** The numerical roundoff errors for_logist
**[7:40]** regression aren't that bad,
**[7:44]** but it is recommended that you use
**[7:46]** this implementation down to
**[7:48]** the bottom instead, and conceptually,
**[7:52]** this code does the same thing as
**[7:54]** the first version that you had previously,
**[7:56]** except that it is a little bit more numerically accurate.
**[8:01]** Although the downside is maybe
**[8:03]** just a little bit harder to interpret as well.
**[8:05]** Now there's just one more detail,
**[8:08]** which is that we've now changed the neural network to use
**[8:11]** a linear activation function
**[8:13]** rather than a softmax activation function.
**[8:16]** The neural network's final layer no
**[8:20]** longer outputs these probabilities A_1 through A_10.
**[8:24]** It is instead of putting z_1 through z_10.
**[8:28]** I didn't talk about it in
**[8:30]** the case of logistic regression,
**[8:32]** but if you were combining
**[8:34]** the output's logistic function with the loss function,
**[8:38]** then for logistic regressions,
**[8:40]** you also have to change the code
**[8:41]** this way to take the output value
**[8:44]** and map it through
**[8:45]** the logistic function in order
**[8:46]** to actually get the probability.
**[8:49]** You now know how to do multi-class classification with
**[8:53]** a softmax output layer and
**[8:55]** also how to do it in a numerically stable way.
**[8:59]** Before wrapping up multi-class classification,
**[9:02]** I want to share with you one other type of
**[9:04]** classification problem called a
**[9:06]** multi-label classification problem.
**[9:09]** Let's talk about that in the next video.
