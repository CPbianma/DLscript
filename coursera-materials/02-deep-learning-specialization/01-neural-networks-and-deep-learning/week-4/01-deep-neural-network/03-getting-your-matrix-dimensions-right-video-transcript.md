---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 4
section: Deep Neural Network
item_title: Getting your Matrix Dimensions Right
duration: 11 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/Rz47X/getting-your-matrix-dimensions-right
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Getting your Matrix Dimensions Right — Transcript

**[0:00]** When implementing a deep neural network,
**[0:01]** one of the debugging tools I often
**[0:04]** use to check the correctness of my code
**[0:06]** is to pull a piece of paper and just
**[0:08]** work through the dimensions in matrix I'm working with.
**[0:11]** Let me show you how to do that since I hope this
**[0:14]** will make it easier for you
**[0:15]** to implement your deep networks as well.
**[0:17]** So capital L is equal to 5.
**[0:20]** I counted them quickly.
**[0:21]** Not counting the input layer,
**[0:22]** there are five layers here,
**[0:25]** four hidden layers and one output layer.
**[0:27]** If you implement forward propagation,
**[0:29]** the first step will be Z1 equals
**[0:34]** W1 times the input features x plus b1.
**[0:41]** Let's ignore the bias terms B
**[0:45]** for now and focus on the parameters W. Now,
**[0:48]** this first hidden layer has three hidden units.
**[0:52]** So this is Layer 0,
**[0:56]** Layer 1, Layer 2, Layer 3,
**[0:58]** Layer 4, and Layer 5.
**[0:59]** Using the notation we had from the previous video,
**[1:02]** we have that n1, which is
**[1:04]** the number of hidden units in layer 1,
**[1:06]** is equal to 3.
**[1:08]** Here we would have that n2 is equal to 5,
**[1:13]** n3 is equal to 4,
**[1:16]** n4 is equal to 2,
**[1:19]** and n5 is equal to 1.
**[1:23]** So far we've only seen
**[1:24]** neural networks with a single output unit,
**[1:27]** but in later courses we'll talk about
**[1:29]** neural networks with multiple output units as well.
**[1:32]** Finally, for the input layer,
**[1:35]** we also have n0 equals nX is equal to 2.
**[1:40]** Now, let's think about the dimensions of Z, W, and X.
**[1:45]** Z is the vector of activations
**[1:48]** for this first hidden layer.
**[1:51]** So Z is going to be 3 by 1,
**[1:56]** is going to be a three-dimensional vector.
**[1:59]** I'm going to write it as, n1 by one-dimensional matrix,
**[2:06]** 3 by 1 in this case.
**[2:08]** Now, how about the input features x?
**[2:10]** X we have two input features.
**[2:12]** So x is, in this example,
**[2:14]** 2 by 1, but more generally it'll be n0 by 1.
**[2:18]** What we need is for the matrix W1 to be something
**[2:22]** that when we multiply an n0 by 1 vector to it,
**[2:26]** we get an n1 by 1 vector.
**[2:29]** So you have a three-dimensional vector
**[2:34]** equals something times a two-dimensional vector.
**[2:38]** By the rules of matrix multiplication,
**[2:41]** this has got to be a 3 by 2 matrix.
**[2:47]** Because a 3 by 2 matrix times a 2 by
**[2:50]** 1 matrix or times a 2 by 1 vector,
**[2:53]** that gives you a 3 by 1 vector.
**[2:56]** More generally, this is going to be
**[2:58]** an n1 by n0 dimensional matrix.
**[3:02]** So what we figured out here is that the dimensions of W1
**[3:06]** has to be n1 by n0,
**[3:12]** and more generally, the dimensions of
**[3:15]** WL must be nL by nL minus 1.
**[3:20]** For example, the dimensions of W2,
**[3:23]** for this, it will have to be 5 by 3,
**[3:29]** or it will be n2 by n1,
**[3:35]** because we're going to compute Z2
**[3:39]** as W2 times a1.
**[3:46]** Again, let's ignore the bias for now.
**[3:50]** This is going to be 3 by 1.
**[3:54]** We need this to be 5 by 1.
**[3:57]** So this had better be 5 by 3.
**[4:02]** Similarly, W3 is really the dimension of the next layer,
**[4:10]** the dimension of the previous layer.
**[4:13]** So this is going to be 4 by 5.
**[4:16]** W4 is going to
**[4:22]** be 2 by 4,
**[4:27]** and W5 is going to be 1 by 2.
**[4:33]** The general formula to check is that when you're
**[4:37]** implementing the matrix for a layer L,
**[4:40]** that the dimension of that matrix be nL by nL minus 1.
**[4:48]** Now, let's think about the dimension of this vector B.
**[4:53]** This is going to be a 3 by 1 vector,
**[4:58]** so you have to add that to another 3 by
**[5:01]** 1 vector in order to get a 3 by 1 vector as the output.
**[5:08]** This was going to be 5 by 1,
**[5:11]** so there's going to be another 5 by 1 vector
**[5:14]** in order for the sum
**[5:16]** of these two things that I have in the boxes to
**[5:18]** be itself a 5 by 1 vector.
**[5:22]** The more general rule is that in the example on the left,
**[5:26]** b^[1] is n^[1] by 1,
**[5:31]** like this 3 by 1.
**[5:33]** In the second example,
**[5:35]** it is this is n^[2] by 1 and so
**[5:42]** the more general case is that b^[l]
**[5:44]** should be n^[l] by 1 dimensional.
**[5:50]** Hopefully, these two equations help you to
**[5:53]** double-check that the dimensions of your matrices,
**[5:56]** w, as well as of
**[5:58]** your vectors b are the correct dimensions.
**[6:01]** Of course, if you're implementing back-propagation,
**[6:05]** then the dimensions of
**[6:06]** dw should be the same as dimension of
**[6:10]** w. So dw should be the same dimension as w,
**[6:15]** and db should be the same dimension as b.
**[6:21]** Now, the other key set of quantities
**[6:24]** whose dimensions to check are these z,
**[6:28]** x, as well as a of l,
**[6:31]** which we didn't talk too much about here.
**[6:33]** But because z of l is equal to g of a of l,
**[6:39]** apply element-wise then z and
**[6:42]** a should have the same dimension
**[6:44]** in these types of networks.
**[6:46]** Now, let's see what happens when you have
**[6:48]** a vectorized implementation that
**[6:50]** looks at multiple examples at a time.
**[6:52]** Even for a vectorized implementation, of course,
**[6:55]** the dimensions of w,
**[6:57]** b, dw, and db will stay the same.
**[7:00]** But the dimensions of za,
**[7:03]** as well as x, will change a bit
**[7:06]** in your vectorized implementation.
**[7:09]** Previously we had z^[1] equals
**[7:14]** w^[1] times x plus b^]1],
**[7:21]** where this was n^[1] by 1.
**[7:26]** This was n^[1] by n^[0],
**[7:29]** x was n^[0] by 1,
**[7:36]** and b was n^[1] by 1.
**[7:40]** Now, in a vectorized implementation,
**[7:43]** you would have z^[1] equals w^[1] times x plus b^[1].
**[7:53]** Where now z^[1] is obtained by
**[7:55]** taking the z^[1] for the individual examples.
**[7:59]** So there's z^[1][1], z^[1][2] up to z^[1][m] and
**[8:05]** stacking them as follows and this gives you z^[1].
**[8:10]** The dimension of z^[1] is that
**[8:12]** instead of being n^[1] by 1,
**[8:15]** it ends up being n^[1] by m,
**[8:17]** if m is decisive training set.
**[8:19]** The dimensions of w^[1] stays the same
**[8:23]** so is the n^[1] by n^[0] and
**[8:26]** x instead of being n^[0] by
**[8:29]** 1 is now all your training examples stamped horizontally,
**[8:33]** so it's now n^[0] by m. You notice that when you take a,
**[8:38]** n^[1] by n^[0] matrics and
**[8:40]** multiply that by an n^[0] by m matrics
**[8:43]** that together they actually give you an
**[8:46]** n^[1] by m dimensional matrics as expected.
**[8:49]** Now the final detail is that b^[1] is still n^[1] by 1.
**[8:56]** But when you take this and add it to b,
**[8:58]** then through python broadcasting this will get duplicated
**[9:02]** into an n^[1] by m matrics and then added element-wise.
**[9:08]** On the previous slide,
**[9:09]** we talked about the dimensions of w,
**[9:12]** b, dw, and db.
**[9:14]** Here what we see is that whereas z^[l],
**[9:18]** as well as a^[l],
**[9:22]** are of dimension n^[l] by 1,
**[9:27]** we have now instead that capital Z^[l],
**[9:31]** as well as capital A^[l],
**[9:36]** are n^[l] by m.
**[9:38]** A special case of this is when l is equal to 0,
**[9:42]** in which case A^[0],
**[9:45]** which is equal to just your training
**[9:47]** set input features x is going
**[9:49]** to be equal to n^[0] by m as expected.
**[9:54]** Of course, when you're
**[9:56]** implementing this in back-propagation,
**[10:02]** we'll see later you end up computing dz as well as da.
**[10:09]** This way, of course, has the same dimension as z and a.
**[10:15]** Hope the low exercise went through helps
**[10:18]** clarify the dimensions of
**[10:19]** the various matrices you'll be working with.
**[10:21]** When you implement back-propagation
**[10:23]** for a deep neural network,
**[10:25]** so long as you work through your code and make sure that
**[10:27]** all the matrices or dimensions are consistent,
**[10:30]** that will usually help you go some ways
**[10:32]** towards eliminating some class of possible bugs.
**[10:35]** I hope that exercise for figuring out
**[10:38]** the dimensions of the various matrices
**[10:40]** you'd be working with is helpful.
**[10:41]** When you implement a deep neural
**[10:43]** network if you keep straight
**[10:45]** the dimensions of these various matrices
**[10:46]** and vectors you're working with,
**[10:48]** hopefully, that will help you eliminate
**[10:49]** some class of possible bugs.
**[10:51]** It certainly helps me get my code right.
**[10:54]** Next, we've now seen some of the mechanics of
**[10:58]** how to do the forward propagation in a neural network.
**[11:01]** But why are deep neural networks so effective and
**[11:04]** why do they do better than shallow representations?
**[11:07]** Let's spend a few minutes in the next video to discuss.
