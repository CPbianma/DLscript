---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 3
section: Shallow Neural Network
item_title: Vectorizing Across Multiple Examples
duration: 9 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/ZCcMM/vectorizing-across-multiple-examples
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Vectorizing Across Multiple Examples — Transcript

**[0:00]** In the last video, you saw how to compute the prediction on a neural network,
**[0:04]** given a single training example.
**[0:06]** In this video, you see how to vectorize across multiple training examples.
**[0:11]** And the outcome will be quite similar to what you saw for logistic regression.
**[0:15]** Whereby stacking up different training examples in different columns of
**[0:19]** the matrix, you'd be able to take the equations you had from the previous video.
**[0:23]** And with very little modification, change them to make the neural network compute
**[0:27]** the outputs on all the examples on pretty much all at the same time.
**[0:32]** So let's see the details on how to do that.
**[0:35]** These were the four equations we have from the previous video of how you compute z1,
**[0:40]** a1, z2 and a2.
**[0:41]** And they tell you how, given an input feature back to x,
**[0:46]** you can use them to generate a2 =y hat for a single training example.
**[0:54]** Now if you have m training examples, you need to repeat this process for
**[1:00]** say, the first training example.
**[1:01]** x superscript (1) to compute
**[1:06]** y hat 1 does a prediction on your first training example.
**[1:11]** Then x(2) use that to generate prediction y hat (2).
**[1:16]** And so on down to x(m) to generate a prediction y hat (m).
**[1:23]** And so in all these activation function notation as well,
**[1:28]** I'm going to write this as a[2](1).
**[1:31]** And this is a[2](2),
**[1:36]** and a(2)(m), so
**[1:40]** this notation a[2](i).
**[1:46]** The round bracket i refers to training example i,
**[1:52]** and the square bracket 2 refers to layer 2, okay.
**[1:58]** So that's how the square bracket and the round bracket indices work.
**[2:04]** And so to suggest that if you have an unvectorized implementation and
**[2:07]** want to compute the predictions of all your training examples,
**[2:11]** you need to do for i = 1 to m.
**[2:15]** Then basically implement these four equations, right?
**[2:18]** You need to make a z[1](i)
**[2:24]** = W(1) x(i) + b[1],
**[2:30]** a[1](i) = sigma of z[1](1).
**[2:38]** z[2](i) = w[2]a[1](i)
**[2:43]** + b[2] andZ2i equals w2a1i plus b2 and
**[2:50]** a[2](i) = sigma point of z[2](i).
**[2:56]** So it's basically these four equations on top by adding the superscript round
**[3:03]** bracket i to all the variables that depend on the training example.
**[3:08]** So adding this superscript round bracket i to x is z and a,
**[3:12]** if you want to compute all the outputs on your m training examples examples.
**[3:18]** What we like to do is vectorize this whole computation, so as to get rid of this for.
**[3:23]** And by the way, in case it seems like I'm getting a lot of nitty gritty
**[3:27]** linear algebra, it turns out that being able to implement this
**[3:31]** correctly is important in the deep learning era.
**[3:34]** And we actually chose notation very carefully for this course and
**[3:38]** make this vectorization steps as easy as possible.
**[3:41]** So I hope that going through this nitty gritty will actually help you to
**[3:46]** more quickly get correct implementations of these algorithms working.
**[3:51]** Alright, so let me just copy this whole block of code to the next slide and
**[3:56]** then we'll see how to vectorize this.
**[3:59]** So here's what we have from the previous slide with the for
**[4:02]** loop going over our m training examples.
**[4:04]** So recall that we defined the matrix x to be equal
**[4:09]** to our training examples stacked up in these columns like so.
**[4:16]** So take the training examples and stack them in columns.
**[4:20]** So this becomes a n, or
**[4:23]** maybe nx by m diminish the matrix.
**[4:29]** I'm just going to give away the punch line and tell you what you need to implement in
**[4:32]** order to have a vectorized implementation of this for loop.
**[4:35]** It turns out what you need to do is compute
**[4:41]** Z[1] = W[1] X + b[1],
**[4:46]** A[1]= sig point of z[1].
**[4:50]** Then Z[2] = w[2]
**[4:56]** A[1] + b[2] and
**[5:01]** then A[2] = sig point of Z[2].
**[5:10]** So if you want the analogy is that we went from lower case vector xs
**[5:16]** to just capital case X matrix by stacking up the lower case xs in different columns.
**[5:23]** If you do the same thing for the zs, so for example,
**[5:28]** if you take z[1](i), z[1](2), and so
**[5:33]** on, and these are all column vectors, up to z[1](m), right.
**[5:40]** So that's this first quantity that all m of them, and stack them in columns.
**[5:46]** Then just gives you the matrix z[1].
**[5:50]** And similarly you look at say this quantity and
**[5:55]** take a[1](1), a[1](2) and so on and
**[6:00]** a[1](m), and stacked them up in columns.
**[6:06]** Then this, just as we went from lower case x to capital case X, and
**[6:11]** lower case z to capital case Z.
**[6:13]** This goes from the lower case a, which are vectors to this capital A[1],
**[6:20]** that's over there and similarly, for z[2] and a[2].
**[6:26]** Right they're also obtained by taking these vectors and
**[6:30]** stacking them horizontally.
**[6:32]** And taking these vectors and stacking them horizontally,
**[6:37]** in order to get Z[2], and E[2].
**[6:40]** One of the property of this notation that might help
**[6:44]** you to think about it is that this matrixes say Z and A,
**[6:47]** horizontally we're going to index across training examples.
**[6:51]** So that's why the horizontal index corresponds to different training example,
**[6:55]** when you sweep from left to right you're scanning through the training cells.
**[6:59]** And vertically this vertical index corresponds to different nodes in
**[7:04]** the neural network.
**[7:06]** So for example, this node, this value at the top most,
**[7:11]** top left most corner of the mean corresponds to the activation
**[7:16]** of the first heading unit on the first training example.
**[7:21]** One value down corresponds to the activation in the second hidden unit on
**[7:25]** the first training example,
**[7:27]** then the third heading unit on the first training sample and so on.
**[7:31]** So as you scan down this is your indexing to the hidden units number.
**[7:39]** Whereas if you move horizontally, then you're going from the first hidden unit.
**[7:42]** And the first training example to now the first hidden unit and
**[7:45]** the second training sample, the third training example.
**[7:48]** And so on until this node here corresponds to the activation of the first
**[7:53]** hidden unit on the final train example and the nth training example.
**[8:00]** Okay so the horizontally the matrix A goes over different training examples.
**[8:10]** And vertically the different indices in the matrix
**[8:14]** A corresponds to different hidden units.
**[8:22]** And a similar intuition holds true for the matrix Z as well as for
**[8:26]** X where horizontally corresponds to different training examples.
**[8:31]** And vertically it corresponds to different input features which
**[8:36]** are really different than those of the input layer of the neural network.
**[8:42]** So of these equations, you now know how to implement in your network
**[8:46]** with vectorization, that is vectorization across multiple examples.
**[8:51]** In the next video I want to show you a bit more justification about why
**[8:55]** this is a correct implementation of this type of vectorization.
**[8:59]** It turns out the justification would be similar to what you had seen in logistic regression.
**[9:03]** Let's go on to the next video.
