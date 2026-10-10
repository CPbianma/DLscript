---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 1
section: Neural network model
item_title: Neural network layer
duration: 10 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/z5sks/neural-network-layer
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Neural network layer — Transcript

**[0:01]** The fundamental building block of
**[0:04]** most modern neural networks is a layer of neurons.
**[0:08]** In this video, you'll learn how to construct
**[0:10]** a layer of neurons and once you have that down,
**[0:13]** you'd be able to take those building blocks and put them
**[0:16]** together to form a large neural network.
**[0:18]** Let's take a look at how a layer of neurons works.
**[0:22]** Here's the example we had from
**[0:24]** the demand prediction example where we
**[0:27]** had four input features that were set to
**[0:29]** this layer of three neurons in the hidden layer
**[0:34]** that then sends its output to
**[0:36]** this output layer with just one neuron.
**[0:39]** Let's zoom in to
**[0:41]** the hidden layer to look at its computations.
**[0:46]** This hidden layer inputs four numbers and
**[0:49]** these four numbers are inputs to each of three neurons.
**[0:54]** Each of these three neurons is just implementing
**[0:58]** a little logistic regression unit
**[1:01]** or a little bit logistic regression function.
**[1:04]** Take this first neuron.
**[1:06]** It has two parameters, w and b.
**[1:11]** In fact, to denote that,
**[1:13]** this is the first hidden unit,
**[1:15]** I'm going to subscript this as w_1, b_1.
**[1:19]** What it does is I'll output some activation value a,
**[1:24]** which is g of w_1 in a product with x plus b_1,
**[1:31]** where this is the familiar z value that you
**[1:36]** have learned about in
**[1:37]** logistic regression in the previous course,
**[1:40]** and g of z is the familiar logistic function,
**[1:46]** 1 over 1 plus e to the negative z.
**[1:49]** Maybe this ends up being a number 0.3 and
**[1:54]** that's the activation value a of the first neuron.
**[1:58]** To denote that this is the first neuron,
**[2:00]** I'm also going to add a subscript a_1 over here,
**[2:04]** and so a_1 may be a number like 0.3.
**[2:07]** There's a 0.3 chance of
**[2:09]** this being highly affordable based on the input features.
**[2:13]** Now let's look at the second neuron.
**[2:15]** The second neuron has parameters w_2 and b_2,
**[2:22]** and these w,
**[2:23]** b or w_2,
**[2:24]** b_2 are the parameters of the second logistic unit.
**[2:28]** It computes a_2 equals the logistic function g applied to
**[2:34]** w_2 dot product x plus
**[2:38]** b_2 and this may be some other number, say 0.7.
**[2:43]** Because in this example,
**[2:45]** there's a 0.7 chance that we
**[2:47]** think the potential buyers will be aware of this t-shirt.
**[2:51]** Similarly, the third neuron has
**[2:54]** a third set of parameters w_3, b_3.
**[2:57]** Similarly, it computes
**[2:58]** an activation value a_3 equals g of
**[3:01]** w_3 dot product x plus b_3 and that may be say, 0.2.
**[3:06]** In this example, these three neurons output 0.3,
**[3:10]** 0.7, and 0.2,
**[3:12]** and this vector of three numbers
**[3:16]** becomes the vector of activation values a,
**[3:21]** that is then passed to
**[3:24]** the final output layer of this neural network.
**[3:27]** Now, when you build
**[3:29]** neural networks with multiple layers,
**[3:31]** it'll be useful to give the layers different numbers.
**[3:35]** By convention, this layer is called layer 1 of
**[3:41]** the neural network and this layer is
**[3:43]** called layer 2 of the neural network.
**[3:46]** The input layer is also sometimes
**[3:49]** called layer 0 and today,
**[3:52]** there are neural networks that can have
**[3:54]** dozens or even hundreds of layers.
**[3:56]** But in order to introduce notation
**[4:00]** to help us distinguish between the different layers,
**[4:03]** I'm going to use superscript square bracket
**[4:07]** 1 to index into different layers.
**[4:11]** In particular, a superscript
**[4:14]** in square brackets 1, I'm going to use,
**[4:17]** that's a notation to denote the output of
**[4:20]** layer 1 of this hidden layer of this neural network,
**[4:24]** and similarly, w_1,
**[4:26]** b_1 here are the parameters of
**[4:29]** the first unit in layer 1 of the neural network,
**[4:33]** so I'm also going to add
**[4:34]** a superscript in square brackets 1
**[4:36]** here, and w_2,
**[4:40]** b_2 are the parameters of
**[4:41]** the second hidden unit
**[4:44]** or the second hidden neuron in layer 1.
**[4:47]** Its parameters are also denoted here w^[1] like so.
**[4:54]** Similarly, I can add
**[4:57]** superscripts square brackets like
**[4:59]** so to denote that these are
**[5:00]** the activation values of
**[5:02]** the hidden units of layer 1 of this neural network.
**[5:08]** I know maybe this notation
**[5:10]** is getting a little bit cluttered.
**[5:12]** But the thing to remember is whenever
**[5:15]** you see this superscript square bracket 1,
**[5:19]** that just refers to a quantity
**[5:22]** that is associated with layer 1 of the neural network.
**[5:26]** If you see superscript square bracket 2,
**[5:29]** that refers to a quantity associated with layer
**[5:33]** 2 of the neural network
**[5:35]** and similarly for other layers as well,
**[5:37]** including layer 3,
**[5:38]** layer 4 and so on for neural networks with more layers.
**[5:42]** That's the computation of layer 1 of this neural network.
**[5:47]** Its output is this activation vector,
**[5:51]** a^[1] and I'm going to copy this over here
**[5:56]** because this output a_1 becomes the input to layer 2.
**[6:03]** Now let's zoom into
**[6:06]** the computation of layer 2 of this neural network,
**[6:09]** which is also the output layer.
**[6:12]** The input to layer 2 is the output of layer 1,
**[6:17]** so a_1 is this vector 0.3, 0.7,
**[6:23]** 0.2 that we just computed
**[6:26]** on the previous part of this slide.
**[6:30]** Because the output layer has just a single neuron,
**[6:35]** all it does is it computes a_1 that is
**[6:40]** the output of this first and only neuron, as g,
**[6:44]** the sigmoid function applied to w
**[6:47]** _1 in a product with a^[1],
**[6:51]** so this is the input into this layer,
**[6:55]** and then plus b_1.
**[6:57]** Here, this is the quantity z that you familiar with
**[7:02]** and g as before is
**[7:04]** the sigmoid function that you apply to this.
**[7:07]** If this results in a number, say 0.84,
**[7:12]** then that becomes the output layer of the neural network.
**[7:17]** In this example, because
**[7:20]** the output layer has just a single neuron,
**[7:22]** this output is just a scalar,
**[7:24]** is a single number rather than a vector of numbers.
**[7:27]** Sticking with our notational convention from before,
**[7:31]** we're going to use a superscript in square brackets 2,
**[7:35]** to denote the quantities
**[7:37]** associated with layer 2 of this neural network,
**[7:40]** so a^[2] is the output of this layer,
**[7:46]** and so I'm going to also copy this
**[7:49]** here as the final output of the neural network.
**[7:53]** To make the notation consistent,
**[7:56]** you can also add these superscripts square bracket 2s
**[8:00]** to denote that these are
**[8:01]** the parameters and activation values
**[8:05]** associated with layer 2 of the neural network.
**[8:08]** Once the neural network has computed a_2,
**[8:11]** there's one final optional step that you
**[8:14]** can choose to implement or not,
**[8:17]** which is if you want a binary prediction,
**[8:21]** 1 or 0, is this a top seller?
**[8:23]** Yes or no? As you can take the number
**[8:26]** a superscript square brackets 2 subscript 1,
**[8:30]** and this is the number 0.84 that we computed,
**[8:34]** and threshold this at 0.5.
**[8:37]** If it's greater than 0.5,
**[8:39]** you can predict y hat
**[8:41]** equals 1 and if it is less than 0.5,
**[8:43]** then predict your y hat equals 0.
**[8:45]** We saw this thresholding as well when you learned about
**[8:49]** logistic regression in
**[8:50]** the first course of the specialization.
**[8:52]** If you wish, this then gives you
**[8:54]** the final prediction y hat as either one or zero,
**[8:58]** if you don't want just the probability
**[9:00]** of it being a top seller.
**[9:01]** So that's how a neural network works.
**[9:04]** Every layer inputs a vector of numbers and
**[9:07]** applies a bunch of logistic regression units to it,
**[9:10]** and then computes another vector of
**[9:12]** numbers that then gets passed from
**[9:14]** layer to layer until you
**[9:16]** get to the final output layers computation,
**[9:19]** which is the prediction of the neural network.
**[9:21]** Then you can either threshold at 0.5
**[9:23]** or not to come up with the final prediction.
**[9:27]** With that, let's go on to use this foundation we've
**[9:30]** built now to look at some even more complex,
**[9:34]** even larger neural network models.
**[9:37]** I hope that by seeing more examples,
**[9:39]** this concept of layers and how to put them
**[9:42]** together to build a neural network
**[9:44]** will become even clearer.
**[9:46]** So let's go on to the next video.
