---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 4
section: Deep Neural Network
item_title: Forward Propagation in a Deep Network
duration: 7 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/MijzH/forward-propagation-in-a-deep-network
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Forward Propagation in a Deep Network — Transcript

**[0:00]** In the last video, we described what is
**[0:02]** a deep L-layer neural network and also talked
**[0:04]** about the notation we use to describe such networks.
**[0:07]** In this video, you see how you can perform forward propagation,
**[0:11]** in a deep network.
**[0:12]** As usual, let's first go over
**[0:15]** what forward propagation will look like for a single training example x,
**[0:19]** and then later on we'll talk about the vectorized version,
**[0:22]** where you want to carry out forward propagation
**[0:24]** on the entire training set at the same time.
**[0:26]** But given a single training example x,
**[0:30]** here's how you compute the activations of the first layer.
**[0:34]** So for this first layer,
**[0:35]** you compute z1 equals
**[0:39]** w1 times x plus b1.
**[0:45]** So w1 and b1 are the parameters that affect the activations in layer one.
**[0:52]** This is layer one of the neural network,
**[0:55]** and then you compute the activations for that layer to be equal to g of z1.
**[1:03]** The activation function g depends on what layer you're at and
**[1:07]** maybe what index set as the activation function from layer one.
**[1:10]** So if you do that, you've now computed the activations for layer one.
**[1:13]** How about layer two? Say that layer.
**[1:17]** Well, you would then compute z2 equals
**[1:22]** w2 a1 plus b2.
**[1:30]** Then, so the activation of layer two is the y matrix times the outputs of layer one.
**[1:36]** So, it's that value,
**[1:38]** plus the bias vector for layer two.
**[1:42]** Then a2 equals the activation function applied to z2.
**[1:51]** Okay? So that's it for layer two,
**[1:54]** and so on and so forth.
**[1:56]** Until you get to the upper layer, that's layer four.
**[1:59]** Where you would have that z4 is equal
**[2:04]** to the parameters for that layer times the activations from the previous layer,
**[2:11]** plus that bias vector.
**[2:14]** Then similarly, a4 equals g of z4.
**[2:23]** So, that's how you compute your estimated output, y hat.
**[2:28]** So, just one thing to notice,
**[2:30]** x here is also equal to a0,
**[2:34]** because the input feature vector x is also the activations of layer zero.
**[2:39]** So we scratch out x.
**[2:41]** When I cross out x and put a0 here,
**[2:44]** then all of these equations basically look the same.
**[2:49]** The general rule is that zl is equal to
**[2:54]** wl times a of l minus 1 plus bl.
**[3:01]** It's one there. And then,
**[3:04]** the activations for that layer is
**[3:07]** the activation function applied to the values of z.
**[3:15]** So, that's the general forward propagation equation.
**[3:18]** So, we've done all this for a single training example.
**[3:23]** How about for doing it in a vectorized way for the whole training set at the same time?
**[3:30]** The equations look quite similar as before.
**[3:33]** For the first layer, you would have capital Z1 equals
**[3:38]** w1 times capital X plus b1.
**[3:45]** Then, A1 equals g of Z1.
**[3:52]** Bear in mind that X is equal to A0.
**[3:56]** These are just the training examples stacked in different columns.
**[4:00]** You could take this, let me scratch out X,
**[4:03]** they can put A0 there.
**[4:06]** Then for the next layer, looks similar,
**[4:08]** Z2 equals w2
**[4:12]** A1 plus b2 and A2 equals g of Z2.
**[4:21]** We're just taking these vectors z or a and so on,
**[4:26]** and stacking them up.
**[4:28]** This is z vector for the first training example,
**[4:30]** z vector for the second training example,
**[4:35]** and so on, down to the nth training example,
**[4:38]** stacking these and columns and calling this capital Z.
**[4:43]** Similarly, for capital A,
**[4:46]** just as capital X.
**[4:48]** All the training examples are column vectors stack left to right.
**[4:51]** In this process, you end up with y hat which is equal to g of Z4,
**[4:59]** this is also equal to A4.
**[5:02]** That's the predictions on all of your training examples stacked horizontally.
**[5:07]** So just to summarize on notation,
**[5:09]** I'm going to modify this up here.
**[5:11]** A notation allows us to replace lowercase z and a with the uppercase counterparts,
**[5:19]** is that already looks like a capital Z.
**[5:21]** That gives you the vectorized version of
**[5:23]** forward propagation that you carry out on the entire training set at a time,
**[5:27]** where A0 is X.
**[5:31]** Now, if you look at this implementation of vectorization,
**[5:34]** it looks like that there is going to be a For loop here.
**[5:38]** So therefore l equals 1-4.
**[5:43]** For L equals 1 through capital L. Then you have to compute the activations for layer one,
**[5:48]** then layer two, then for layer three,
**[5:50]** and then the layer four.
**[5:51]** So, seems that there is a For loop here.
**[5:54]** I know that when implementing neural networks,
**[5:57]** we usually want to get rid of explicit For loops.
**[5:59]** But this is one place where I don't think
**[6:02]** there's any way to implement this without an explicit For loop.
**[6:05]** So when implementing forward propagation,
**[6:07]** it is perfectly okay to have a For loop to compute the activations for layer one,
**[6:11]** then layer two, then layer three, then layer four.
**[6:14]** No one knows, and I don't think there is any way to do
**[6:18]** this without a For loop that goes from one to capital L,
**[6:22]** from one through the total number of layers in the neural network.
**[6:25]** So, in this place, it's perfectly okay to have an explicit For loop.
**[6:29]** So, that's it for the notation for deep neural networks,
**[6:33]** as well as how to do forward propagation in these networks.
**[6:37]** If the pieces we've seen so far looks a little bit familiar to you,
**[6:40]** that's because what we're seeing is taking a piece very similar to what you've seen in
**[6:45]** the neural network with a single hidden layer and just repeating that more times.
**[6:51]** Now, it turns out that we implement a deep neural network,
**[6:54]** one of the ways to increase your odds of having a bug-free implementation
**[6:58]** is to think very systematic and
**[7:00]** carefully about the matrix dimensions you're working with.
**[7:03]** So, when I'm trying to debug my own code,
**[7:05]** I'll often pull a piece of paper,
**[7:07]** and just think carefully through,
**[7:08]** so the dimensions of the matrix I'm working with.
**[7:12]** Let's see how you could do that in the next video.
