---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 3
section: Shallow Neural Network
item_title: Random Initialization
duration: 8 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/XtFPI/random-initialization
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Random Initialization — Transcript

**[0:00]** When you change your neural network,
**[0:01]** it's important to initialize the weights randomly.
**[0:03]** For logistic regression, it was okay to initialize the weights to zero.
**[0:08]** But for a neural network of initialize the weights to parameters to all zero and
**[0:12]** then applied gradient descent, it won't work.
**[0:14]** Let's see why.
**[0:15]** So you have here two input features, so
**[0:20]** n0=2, and two hidden units, so n1=2.
**[0:25]** And so the matrix associated with the hidden layer,
**[0:31]** w 1, is going to be two-by-two.
**[0:35]** Let's say that you initialize it to all 0s, so 0 0 0 0, two-by-two matrix.
**[0:41]** And let's say B1 is also equal to 0 0.
**[0:45]** It turns out initializing the bias terms b to 0 is actually okay,
**[0:50]** but initializing w to all 0s is a problem.
**[0:54]** So the problem with this formalization is that for
**[0:59]** any example you give it, you'll have that a1,1 and
**[1:05]** a1,2, will be equal, right?
**[1:09]** So this activation and this activation will be the same,
**[1:12]** because both of these hidden units are computing exactly the same function.
**[1:17]** And then, when you compute backpropagation,
**[1:21]** it turns out that dz11 and
**[1:24]** dz12 will also be the same colored by symmetry, right?
**[1:30]** Both of these hidden units will initialize the same way.
**[1:33]** Technically, for what I'm saying,
**[1:36]** I'm assuming that the outgoing weights or also identical.
**[1:39]** So that's w2 is equal to 0 0.
**[1:45]** But if you initialize the neural network this way,
**[1:48]** then this hidden unit and this hidden unit are completely identical.
**[1:53]** Sometimes you say they're completely symmetric,
**[1:57]** which just means that they're completing exactly the same function.
**[2:01]** And by kind of a proof by induction,
**[2:03]** it turns out that after every single iteration of training your two hidden
**[2:08]** units are still computing exactly the same function.
**[2:11]** Since plots will show that dw will be a matrix that looks like this.
**[2:17]** Where every row takes on the same value.
**[2:20]** So we perform a weight update.
**[2:23]** So when you perform a weight update, w1 gets updated as w1- alpha times dw.
**[2:30]** You find that w1, after every iteration,
**[2:33]** will have the first row equal to the second row.
**[2:37]** So it's possible to construct a proof by induction that if you
**[2:41]** initialize all the ways, all the values of w to 0,
**[2:44]** then because both hidden units start off computing the same function.
**[2:49]** And both hidden the units have the same influence on the output unit,
**[2:53]** then after one iteration, that same statement is still true,
**[2:57]** the two hidden units are still symmetric.
**[3:00]** And therefore, by induction, after two iterations, three iterations and so on,
**[3:04]** no matter how long you train your neural network,
**[3:07]** both hidden units are still computing exactly the same function.
**[3:10]** And so in this case, there's really no point to having more than one hidden unit.
**[3:15]** Because they are all computing the same thing.
**[3:17]** And of course, for larger neural networks, let's say of three features and
**[3:22]** maybe a very large number of hidden units,
**[3:24]** a similar argument works to show that with a neural network like this.
**[3:29]** Let me draw all the edges, if you initialize the weights to zero,
**[3:34]** then all of your hidden units are symmetric.
**[3:37]** And no matter how long you're upgrading the center,
**[3:40]** all continue to compute exactly the same function.
**[3:44]** So that's not helpful, because you want the different
**[3:48]** hidden units to compute different functions.
**[3:52]** The solution to this is to initialize your parameters randomly.
**[3:57]** So here's what you do.
**[3:58]** You can set w1 = np.random.randn.
**[4:04]** This generates a gaussian random variable (2,2).
**[4:07]** And then usually, you multiply this by very small number, such as 0.01.
**[4:12]** So you initialize it to very small random values.
**[4:14]** And then b, it turns out that b does not have the symmetry problem,
**[4:20]** what's called the symmetry breaking problem.
**[4:24]** So it's okay to initialize b to just zeros.
**[4:29]** Because so long as w is initialized randomly,
**[4:32]** you start off with the different hidden units computing different things.
**[4:36]** And so you no longer have this symmetry breaking problem.
**[4:40]** And then similarly, for w2, you're going to initialize that randomly.
**[4:43]** And b2, you can initialize that to 0.
**[4:48]** So you might be wondering, where did this constant come from and why is it 0.01?
**[4:55]** Why not put the number 100 or 1000?
**[4:58]** Turns out that we usually prefer to initialize
**[5:02]** the weights to very small random values.
**[5:05]** Because if you are using a tanh or sigmoid activation function, or
**[5:10]** the other sigmoid, even just at the output layer.
**[5:14]** If the weights are too large,
**[5:17]** then when you compute the activation values,
**[5:23]** remember that z[1]=w1 x + b.
**[5:28]** And then a1 is the activation function applied to z1.
**[5:34]** So if w is very big, z will be very, or at least some
**[5:39]** values of z will be either very large or very small.
**[5:44]** And so in that case, you're more likely to end up at these fat parts of the tanh
**[5:49]** function or the sigmoid function, where the slope or the gradient is very small.
**[5:55]** Meaning that gradient descent will be very slow.
**[5:58]** So learning was very slow.
**[5:59]** So just a recap, if w is too large, you're more likely to end up
**[6:04]** even at the very start of training, with very large values of z.
**[6:08]** Which causes your tanh or your sigmoid activation function to be saturated,
**[6:13]** thus slowing down learning.
**[6:15]** If you don't have any sigmoid or
**[6:17]** tanh activation functions throughout your neural network, this is less of an issue.
**[6:22]** But if you're doing binary classification, and your output unit is a sigmoid
**[6:26]** function, then you just don't want the initial parameters to be too large.
**[6:30]** So that's why multiplying by 0.01 would be something reasonable to try, or
**[6:35]** any other small number.
**[6:36]** And same for w2, right?
**[6:38]** This can be random.random.
**[6:44]** I guess this would be 1 by 2 in this example, times 0.01.
**[6:49]** Missing an s there.
**[6:51]** So finally, it turns out that sometimes they can be better constants than 0.01.
**[7:00]** When you're training a neural network with just one hidden layer,
**[7:04]** it is a relatively shallow neural network, without too many hidden layers.
**[7:09]** Set it to 0.01 will probably work okay.
**[7:12]** But when you're training a very very deep neural network,
**[7:15]** then you might want to pick a different constant than 0.01.
**[7:19]** And in next week's material, we'll talk a little bit about how and
**[7:23]** when you might want to choose a different constant than 0.01.
**[7:27]** But either way, it will usually end up being a relatively small number.
**[7:32]** So that's it for this week's videos.
**[7:34]** You now know how to set up a neural network of a hidden layer,
**[7:38]** initialize the parameters, make predictions using.
**[7:42]** As well as compute derivatives and implement gradient descent,
**[7:45]** using backprop.
**[7:46]** So that, you should be able to do the quizzes,
**[7:48]** as well as this week's programming exercises.
**[7:51]** Best of luck with that.
**[7:52]** I hope you have fun with the problem exercise, and
**[7:54]** look forward to seeing you in the week four materials.
