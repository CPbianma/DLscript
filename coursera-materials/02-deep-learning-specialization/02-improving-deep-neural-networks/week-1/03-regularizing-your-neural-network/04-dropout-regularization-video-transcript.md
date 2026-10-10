---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 1
section: Regularizing your Neural Network
item_title: Dropout Regularization
duration: 9 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/eM33A/dropout-regularization
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Dropout Regularization — Transcript

**[0:00]** In addition to L2 regularization,
**[0:02]** another very powerful regularization techniques is called "dropout."
**[0:06]** Let's see how that works.
**[0:08]** Let's say you train a neural network like the one on the left and there's over-fitting.
**[0:12]** Here's what you do with dropout.
**[0:14]** Let me make a copy of the neural network.
**[0:16]** With dropout, what we're going to do is go through each of the layers of
**[0:21]** the network and set some probability of eliminating a node in neural network.
**[0:26]** Let's say that for each of these layers,
**[0:29]** we're going to- for each node,
**[0:30]** toss a coin and have a 0.5 chance of
**[0:34]** keeping each node and 0.5 chance of removing each node.
**[0:38]** So, after the coin tosses,
**[0:39]** maybe we'll decide to eliminate those nodes,
**[0:42]** then what you do is actually remove all the outgoing things from that no as well.
**[0:49]** So you end up with a much smaller,
**[0:51]** really much diminished network.
**[0:53]** And then you do back propagation training.
**[0:56]** There's one example on this much diminished network.
**[0:59]** And then on different examples,
**[1:01]** you would toss a set of coins again and keep
**[1:03]** a different set of nodes and then dropout or eliminate different than nodes.
**[1:07]** And so for each training example,
**[1:09]** you would train it using one of these neural based networks.
**[1:14]** So, maybe it seems like a slightly crazy technique.
**[1:16]** They just go around coding those are random,
**[1:20]** but this actually works.
**[1:22]** But you can imagine that because you're training a much smaller network on each example
**[1:28]** or maybe just give a sense for why you end up able to regularize the network,
**[1:34]** because these much smaller networks are being trained.
**[1:38]** Let's look at how you implement dropout.
**[1:41]** There are a few ways of implementing dropout.
**[1:43]** I'm going to show you the most common one,
**[1:44]** which is technique called inverted dropout.
**[1:47]** For the sake of completeness,
**[1:49]** let's say we want to illustrate this with layer l=3.
**[1:58]** So, in the code I'm going to write- there will be a bunch of 3s here.
**[2:03]** I'm just illustrating how to represent dropout in a single layer.
**[2:08]** So, what we are going to do is set a vector d
**[2:12]** and d^3 is going to be the dropout vector for the layer 3.
**[2:16]** That's what the 3 is to be np.random.rand(a).
**[2:21]** And this is going to be the same shape as a3.
**[2:27]** And when I see if this is less than some number,
**[2:31]** which I'm going to call keep.prob.
**[2:34]** And so, keep.prob is a number.
**[2:37]** It was 0.5 on the previous time,
**[2:39]** and maybe now I'll use 0.8 in this example,
**[2:42]** and there will be the probability that a given hidden unit will be kept.
**[2:47]** So keep.prob = 0.8,
**[2:49]** then this means that there's a 0.2 chance of eliminating any hidden unit.
**[2:54]** So, what it does is it generates a random matrix.
**[2:58]** And this works as well if you have factorized.
**[3:00]** So d3 will be a matrix.
**[3:03]** Therefore, each example have a each hidden unit there's a
**[3:06]** 0.8 chance that the corresponding d3 will be one,
**[3:10]** and a 20% chance there will be zero.
**[3:12]** So, this random numbers being less than 0.8 it has a 0.8 chance of being one or be true,
**[3:20]** and 20% or 0.2 chance of being false, of being zero.
**[3:24]** And then what you are going to do is take your activations from the third layer,
**[3:27]** let me just call it a3 in this low example.
**[3:30]** So, a3 has the activations you computate.
**[3:33]** And you can set a3 to be equal to the old a3,
**[3:37]** times- There is element wise multiplication.
**[3:41]** Or you can also write this as a3* = d3.
**[3:44]** But what this does is for every element of d3 that's equal to zero.
**[3:50]** And there was a 20% chance of each of the elements being zero,
**[3:53]** just multiply operation ends up zeroing out,
**[3:57]** the corresponding element of d3.
**[4:00]** If you do this in python,
**[4:02]** technically d3 will be a boolean array where value is true and false,
**[4:05]** rather than one and zero.
**[4:06]** But the multiply operation works and will
**[4:10]** interpret the true and false values as one and zero.
**[4:13]** If you try this yourself in python, you'll see.
**[4:16]** Then finally, we're going to take a3 and scale it up by dividing by
**[4:22]** 0.8 or really dividing by our keep.prob parameter.
**[4:30]** So, let me explain what this final step is doing.
**[4:32]** Let's say for the sake of argument that you have 50 units
**[4:36]** or 50 neurons in the third hidden layer.
**[4:39]** So maybe a3 is 50 by one dimensional or
**[4:43]** if you- factorization maybe it's 50 by m dimensional.
**[4:46]** So, if you have a 80% chance of keeping them and 20% chance of eliminating them.
**[4:51]** This means that on average,
**[4:53]** you end up with 10 units shut off or 10 units zeroed out.
**[4:59]** And so now, if you look at the value of z^4,
**[5:02]** z^4 is going to be equal to w^4 * a^3 + b^4.
**[5:08]** And so, on expectation,
**[5:10]** this will be reduced by 20%.
**[5:14]** By which I mean that 20% of the elements of a3 will be zeroed out.
**[5:18]** So, in order to not reduce the expected value of z^4,
**[5:22]** what you do is you need to take this,
**[5:24]** and divide it by 0.8 because
**[5:28]** this will correct or just a bump that back up by roughly 20% that you need.
**[5:33]** So it's not changed the expected value of a3.
**[5:37]** And, so this line here is what's called the inverted dropout technique.
**[5:43]** And its effect is that,
**[5:44]** no matter what you set to keep.prob to,
**[5:47]** whether it's 0.8 or 0.9 or even one,
**[5:50]** if it's set to one then there's no dropout,
**[5:52]** because it's keeping everything or 0.5 or whatever,
**[5:54]** this inverted dropout technique by dividing by the keep.prob,
**[5:57]** it ensures that the expected value of a3 remains the same.
**[6:02]** And it turns out that at test time,
**[6:05]** when you trying to evaluate a neural network,
**[6:06]** which we'll talk about on the next slide,
**[6:08]** this inverted dropout technique,
**[6:10]** There's this slide, just green box around the next test
**[6:13]** This makes test time easier because you have less of a scaling problem.
**[6:17]** By far the most common implementation
**[6:20]** of dropouts today as far as I know is inverted dropouts.
**[6:22]** I recommend you just implement this.
**[6:24]** But there were some early iterations of dropout that
**[6:27]** missed this divide by keep.prob line,
**[6:30]** and so at test time the average becomes more and more complicated.
**[6:33]** But again, people tend not to use those other versions.
**[6:37]** So, what you do is you use the d vector,
**[6:40]** and you'll notice that for different training examples,
**[6:43]** you zero out different hidden units.
**[6:46]** And in fact, if you make multiple passes through the same training set,
**[6:49]** then on different pauses through the training set,
**[6:52]** you should randomly zero out different hidden units.
**[6:55]** So, it's not that for one example,
**[6:57]** you should keep zeroing out the same hidden units is that,
**[7:01]** on iteration one of grade and descent,
**[7:03]** you might zero out some hidden units.
**[7:05]** And on the second iteration of great descent
**[7:07]** where you go through the training set the second time,
**[7:09]** maybe you'll zero out a different pattern of hidden units.
**[7:13]** And the vector d or d3, for the third layer,
**[7:16]** is used to decide what to zero out,
**[7:18]** both in for prob as well as in that prob.
**[7:21]** We are just showing for prob here.
**[7:22]** Now, having trained the algorithm at test time, here's what you would do.
**[7:26]** At test time, you're given some x or which you want to make a prediction.
**[7:30]** And using our standard notation,
**[7:32]** I'm going to use a^0,
**[7:33]** the activations of the zeroes layer to denote just test example x.
**[7:38]** So what we're going to do is not to use
**[7:40]** dropout at test time in particular which is in a sense.
**[7:44]** Z^1= w^1.a^0 + b^1.
**[7:48]** a^1 = g^1(z^1 Z).
**[7:56]** Z^2 = w^2.a^1 + b^2.
**[8:03]** a^2 =...
**[8:04]** And so on. Until you get to the last layer and that you make a prediction y^.
**[8:10]** But notice that the test time you're not using
**[8:12]** dropout explicitly and you're not tossing coins at random,
**[8:15]** you're not flipping coins to decide which hidden units to eliminate.
**[8:20]** And that's because when you are making predictions at the test time,
**[8:22]** you don't really want your output to be random.
**[8:25]** If you are implementing dropout at test time,
**[8:27]** that just add noise to your predictions.
**[8:29]** In theory, one thing you could do is run a prediction process
**[8:34]** many times with different hidden units randomly dropped out and have it across them.
**[8:38]** But that's computationally inefficient and will give you roughly the same result;
**[8:43]** very, very similar results to this different procedure as well.
**[8:46]** And just to mention,
**[8:47]** the inverted dropout thing,
**[8:49]** you remember the step on the previous line when we divided by the cheap.prob.
**[8:53]** The effect of that was to ensure that even when you don't see
**[8:56]** men dropout at test time to the scaling,
**[8:59]** the expected value of these activations don't change.
**[9:02]** So, you don't need to add in an extra funny scaling parameter at test time.
**[9:06]** That's different than when you have that training time.
**[9:08]** So that's dropouts.
**[9:10]** And when you implement this in week's premier exercise,
**[9:13]** you gain more firsthand experience with it as well.
**[9:16]** But why does it really work?
**[9:18]** What I want to do the next video is give you
**[9:20]** some better intuition about what dropout really is doing.
**[9:23]** Let's go on to the next video.
