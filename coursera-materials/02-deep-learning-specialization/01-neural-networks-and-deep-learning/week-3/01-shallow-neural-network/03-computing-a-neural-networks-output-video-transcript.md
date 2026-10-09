---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 3
section: Shallow Neural Network
item_title: Computing a Neural Network's Output
duration: 10 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/tyAGh/computing-a-neural-networks-output
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Computing a Neural Network's Output — Transcript

**[0:00]** In the last video, you saw what a single hidden layer neural network looks like.
**[0:04]** In this video, let's go through the details of
**[0:07]** exactly how this neural network computes these outputs.
**[0:10]** What you see is that it is like logistic regression,
**[0:13]** but repeated a lot of times.
**[0:15]** Let's take a look. So, this is how a two-layer neural network looks.
**[0:19]** Let's go more deeply into exactly what this neural network computes.
**[0:23]** Now, we've said before that logistic regression,
**[0:26]** the circle in logistic regression,
**[0:28]** really represents two steps of computation rows.
**[0:31]** You compute z as follows, and a second,
**[0:33]** you compute the activation as a sigmoid function of z.
**[0:37]** So, a neural network just does this a lot more times.
**[0:40]** Let's start by focusing on just one of the nodes in the hidden layer.
**[0:44]** Let's look at the first node in the hidden layer.
**[0:46]** So, I've grayed out the other nodes for now.
**[0:48]** So, similar to logistic regression on the left,
**[0:50]** this nodes in the hidden layer does two steps of computation.
**[0:54]** The first step and think of as the left half of this node,
**[0:57]** it computes z equals w transpose x plus b,
**[1:02]** and the notation we'll use is,
**[1:05]** these are all quantities associated with the first hidden layer.
**[1:08]** So, that's why we have a bunch of square brackets there.
**[1:10]** This is the first node in the hidden layer.
**[1:13]** So, that's why we have the subscript one over there.
**[1:16]** So first, it does that,
**[1:18]** and then the second step,
**[1:19]** is it computes a_[1]_1 equals sigmoid of z_[1]_1, like so.
**[1:24]** So, for both z and a,
**[1:26]** the notational convention is that a, l, i,
**[1:29]** the l here in superscript square brackets,
**[1:32]** refers to the layer number,
**[1:33]** and the i subscript here,
**[1:35]** refers to the nodes in that layer.
**[1:37]** So, the node we'll be looking at is layer one,
**[1:40]** that is a hidden layer node one.
**[1:42]** So, that's why the superscripts and subscripts were both one, one.
**[1:45]** So, that little circle,
**[1:47]** that first node in the neural network,
**[1:49]** represents carrying out these two steps of computation.
**[1:52]** Now, let's look at the second node in the neural network,
**[1:55]** or the second node in the hidden layer of the neural network.
**[1:58]** Similar to the logistic regression unit on the left,
**[2:01]** this little circle represents two steps of computation.
**[2:04]** The first step is it computes z.
**[2:07]** This is still layer one,
**[2:08]** but now as a second node equals w transpose x,
**[2:12]** plus b_[1]_2, and then a_[1] two equals sigmoid of z_[1]_2.
**[2:19]** Again, feel free to pause the video if you want,
**[2:21]** but you can double-check that the superscript and
**[2:23]** subscript notation is consistent with what we have written here above in purple.
**[2:28]** So, we've talked through the first two hidden units in a neural network,
**[2:32]** having units three and four also represents some computations.
**[2:36]** So now, let me take this pair of equations,
**[2:40]** and this pair of equations,
**[2:42]** and let's copy them to the next slide.
**[2:44]** So, here's our neural network,
**[2:45]** and here's the first,
**[2:46]** and here's the second equations that we've worked out
**[2:49]** previously for the first and the second hidden units.
**[2:54]** If you then go through and write out the corresponding equations
**[2:57]** for the third and fourth hidden units, you get the following.
**[3:01]** So, let me show this notation is clear,
**[3:03]** this is the vector w_[1]_1,
**[3:06]** this is a vector transpose times x.
**[3:09]** So, that's what the superscript T there represents.
**[3:12]** It's a vector transpose.
**[3:13]** Now, as you might have guessed,
**[3:15]** if you're actually implementing a neural network,
**[3:17]** doing this with a for loop, seems really inefficient.
**[3:20]** So, what we're going to do,
**[3:21]** is take these four equations and vectorize.
**[3:25]** So, we're going to start by showing how to compute z as a vector,
**[3:29]** it turns out you could do it as follows.
**[3:30]** Let me take these w's and stack them into a matrix,
**[3:34]** then you have w_[1]_1 transpose,
**[3:37]** so that's a row vector,
**[3:39]** or this column vector transpose gives you a row vector, then w_[1]_2,
**[3:42]** transpose, w_[1]_3 transpose, w_[1]_4 transpose.
**[3:48]** So, by stacking those four w vectors together,
**[3:53]** you end up with a matrix.
**[3:54]** So, another way to think of this is that we have four logistic regression units there,
**[3:58]** and each of the logistic regression units,
**[4:01]** has a corresponding parameter vector,
**[4:03]** w. By stacking those four vectors together,
**[4:06]** you end up with this four by three matrix.
**[4:08]** So, if you then take this matrix and multiply it by your input features x1,
**[4:14]** x2, x3, you end up with by how matrix multiplication works.
**[4:18]** You end up with w_[1]_1 transpose x,
**[4:20]** w_2_[1] transpose x, w_3_[1] transpose x, w_4_[1] transpose x.
**[4:28]** Then, let's not figure the b's.
**[4:31]** So, we now add to this a vector b_[1]_1 one, b_[1]_2, b_[1]_3, b_[1]_4.
**[4:39]** So, that's basically this,
**[4:40]** then this is b_[1]_1, b_[1]_2, b_[1]_3, b_[1]_4.
**[4:46]** So, you see that each of the four rows of
**[4:48]** this outcome correspond exactly to each of these four rows,
**[4:53]** each of these four quantities that we had above.
**[4:55]** So, in other words, we've just shown that this thing is therefore equal to
**[4:59]** z_[1]_1, z_[1]_2, z_[1]_3, z_[1]_4, as defined here.
**[5:05]** Maybe not surprisingly, we're going to call this whole thing, the vector z_[1],
**[5:09]** which is taken by stacking up these individuals of z's into a column vector.
**[5:15]** When we're vectorizing, one of the rules of thumb that might help you navigate this,
**[5:20]** is that while we have different nodes in the layer,
**[5:22]** we'll stack them vertically.
**[5:23]** So, that's why we have z_[1]_1 through z_[1]_4,
**[5:27]** those corresponded to four different nodes in the hidden layer,
**[5:30]** and so we stacked these four numbers vertically to form the vector z[1].
**[5:35]** To use one more piece of notation,
**[5:37]** this four by three matrix here which we obtained by stacking the lowercase w_[1]_1,
**[5:44]** w_[1]_2, and so on, we're going to call this matrix W capital [1].
**[5:48]** Similarly, this vector, we're going to call b superscript [1] square bracket.
**[5:52]** So, this is a four by one vector.
**[5:54]** So now, we've computed z using this vector matrix notation,
**[5:59]** the last thing we need to do is also compute these values of a.
**[6:03]** So, prior won't surprise you to see that we're going to define a_[1],
**[6:08]** as just stacking together,
**[6:09]** those activation values, a [1],
**[6:11]** 1 through a [1], 4.
**[6:13]** So, just take these four values and stack them together in a vector called a[1].
**[6:18]** This is going to be a sigmoid of z[1],
**[6:21]** where this now has been implementation of
**[6:23]** the sigmoid function that takes in the four elements of z,
**[6:26]** and applies the sigmoid function element-wise to it.
**[6:30]** So, just a recap,
**[6:31]** we figured out that z_[1] is equal to w_[1] times the vector x plus the vector b_[1],
**[6:38]** and a_[1] is sigmoid times z_[1].
**[6:42]** Let's just copy this to the next slide.
**[6:44]** What we see is that for the first layer of the neural network given an input x,
**[6:48]** we have that z_[1] is equal to w_[1] times x plus b_[1],
**[6:52]** and a_[1] is sigmoid of z_[1].
**[6:55]** The dimensions of this are four by one equals,
**[6:59]** this was a four by three matrix times a three by one vector plus a four by one vector b,
**[7:05]** and this is four by one same dimension as end.
**[7:08]** Remember, that we said x is equal to a_[0].
**[7:12]** Just say y hat is also equal to a two.
**[7:16]** If you want, you can actually take this x and replace it with a_[0],
**[7:21]** since a_[0] is if you want as an alias for the vector of input features, x.
**[7:25]** Now, through a similar derivation,
**[7:27]** you can figure out that the representation for the next layer can
**[7:31]** also be written similarly where what the output layer does is,
**[7:36]** it has associated with it,
**[7:37]** so the parameters w_[2] and b_[2].
**[7:40]** So, w_[2] in this case is going to be a one by four matrix,
**[7:44]** and b_[2] is just a real number as one by on.
**[7:47]** So, z_[2] is going to be a real number we'll write as a one by one matrix.
**[7:52]** Is going to be a one by four thing times a was four by one,
**[7:56]** plus b_[2] as one by one,
**[7:57]** so this gives you just a real number.
**[7:59]** If you think of this last upper unit as just being
**[8:02]** analogous to logistic regression which have parameters w and b,
**[8:07]** w really plays an analogous role to w_[2] transpose,
**[8:12]** or w_[2] is really W transpose and b is equal to b_[2].
**[8:16]** I said we want to cover up the left of this network and ignore all that for now,
**[8:21]** then this last upper unit is a lot like logistic regression,
**[8:26]** except that instead of writing the parameters as w and b,
**[8:29]** we're writing them as w_[2] and b_[2],
**[8:32]** with dimensions one by four and one by one.
**[8:35]** So, just a recap.
**[8:37]** For logistic regression, to implement the output or to implement prediction,
**[8:41]** you compute z equals w transpose x plus b,
**[8:44]** and a or y hat equals a,
**[8:48]** equals sigmoid of z.
**[8:50]** When you have a neural network with one hidden layer,
**[8:54]** what you need to implement,
**[8:55]** is to computer this output is just these four equations.
**[8:59]** You can think of this as a vectorized implementation of computing
**[9:03]** the output of first these for logistic regression units in the hidden layer,
**[9:08]** that's what this does, and
**[9:09]** then this logistic regression in the output layer which is what this does.
**[9:13]** I hope this description made sense,
**[9:15]** but the takeaway is to compute the output of this neural network,
**[9:19]** all you need is those four lines of code.
**[9:21]** So now, you've seen how given a single input feature,
**[9:25]** vector a, you can with four lines of code,
**[9:27]** compute the output of this neural network.
**[9:30]** Similar to what we did for logistic regression,
**[9:32]** we'll also want to vectorize across multiple training examples.
**[9:36]** We'll see that by stacking up training examples in different columns in the matrix,
**[9:41]** with just slight modification to this, you also,
**[9:44]** similar to what you saw in this regression,
**[9:46]** be able to compute the output of this neural network,
**[9:50]** not just a one example at a time,
**[9:52]** prolong your, say your entire training set at a time.
**[9:55]** So, let's see the details of that in the next video.
