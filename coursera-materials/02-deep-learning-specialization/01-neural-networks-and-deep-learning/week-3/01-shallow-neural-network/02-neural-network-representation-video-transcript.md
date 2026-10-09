---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 3
section: Shallow Neural Network
item_title: Neural Network Representation
duration: 5 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/GyW9e/neural-network-representation
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Neural Network Representation — Transcript

**[0:00]** You see me draw a few pictures of neural networks.
**[0:03]** In this video, we'll talk about exactly what those pictures means.
**[0:05]** In other words,
**[0:06]** exactly what those neural networks that we've been drawing represent.
**[0:11]** And we'll start with focusing on the case of neural networks with
**[0:15]** what was called a single hidden layer.
**[0:17]** Here's a picture of a neural network.
**[0:19]** Let's give different parts of these pictures some names.
**[0:22]** We have the input features, x1, x2, x3 stacked up vertically.
**[0:27]** And this is called the input layer of the neural network.
**[0:30]** So maybe not surprisingly, this contains the inputs to the neural network.
**[0:35]** Then there's another layer of circles.
**[0:37]** And this is called a hidden layer of the neural network.
**[0:41]** I'll come back in a second to say what the word hidden means.
**[0:45]** But the final layer here is formed by, in this case, just one node.
**[0:49]** And this single-node layer is called the output layer, and is responsible for
**[0:53]** generating the predicted value y hat.
**[0:57]** In a neural network that you train with supervised learning,
**[0:59]** the training set contains values of the inputs x as well as the target outputs y.
**[1:05]** So the term hidden layer refers to the fact that in the training set,
**[1:09]** the true values for these nodes in the middle are not observed.
**[1:12]** That is, you don't see what they should be in the training set.
**[1:15]** You see what the inputs are.
**[1:16]** You see what the output should be.
**[1:18]** But the things in the hidden layer are not seen in the training set.
**[1:20]** So that kind of explains the name hidden layer; just because you
**[1:25]** don't see it in the training set.
**[1:27]** Let's introduce a bit more notation.
**[1:28]** Whereas previously, we were using the vector X to denote the input features and
**[1:34]** alternative notation for
**[1:36]** the values of the input features will be A superscript square bracket 0.
**[1:41]** And the term A also stands for activations, and
**[1:44]** it refers to the values that different layers
**[1:47]** of the neural network are passing on to the subsequent layers.
**[1:51]** So the input layer passes on the value x to the hidden layer, so
**[1:55]** we're going to call that activations of the input layer A super script 0.
**[2:01]** The next layer, the hidden layer, will in turn generate some set of activations,
**[2:05]** which I'm going to write as A superscript square bracket 1.
**[2:09]** So in particular, this first unit or this first node,
**[2:13]** we generate a value A superscript square bracket 1 subscript 1.
**[2:17]** This second node we generate a value.
**[2:20]** Now we have a subscript 2 and so on.
**[2:23]** And so, A superscript square bracket 1,
**[2:26]** this is a four dimensional vector you want in Python
**[2:30]** because the 4x1 matrix, or a 4 column vector, which looks like this.
**[2:34]** And it's four dimensional, because in this case we have four nodes, or
**[2:39]** four units, or four hidden units in this hidden layer.
**[2:43]** And then finally, the open layer regenerates some value A2,
**[2:46]** which is just a real number.
**[2:48]** And so y hat is going to take on the value of A2.
**[2:53]** So this is analogous to how in logistic regression we have y hat equals a and
**[2:57]** in logistic regression which we only had that one output layer, so
**[3:02]** we don't use the superscript square brackets.
**[3:04]** But with our neural network, we now going to use the superscript square
**[3:07]** bracket to explicitly indicate which layer it came from.
**[3:11]** One funny thing about notational conventions in neural networks
**[3:15]** is that this network that you've seen here is called a two layer neural network.
**[3:20]** And the reason is that when we count layers in neural networks,
**[3:24]** we don't count the input layer.
**[3:25]** So the hidden layer is layer one and the output layer is layer two.
**[3:30]** In our notational convention, we're calling the input layer layer zero, so
**[3:34]** technically maybe there are three layers in this neural network.
**[3:37]** Because there's the input layer, the hidden layer, and the output layer.
**[3:40]** But in conventional usage, if you read research papers and elsewhere in
**[3:44]** the course, you see people refer to this particular neural network as a two layer
**[3:48]** neural network, because we don't count the input layer as an official layer.
**[3:52]** Finally, something that we'll get to later is that the hidden layer and
**[3:55]** the output layers will have parameters associated with them.
**[3:59]** So the hidden layer will have associated with it parameters w and b.
**[4:04]** And I'm going to write superscripts square bracket 1 to indicate that these
**[4:08]** are parameters associated with layer one with the hidden layer.
**[4:12]** We'll see later that w will be a 4 by 3 matrix and
**[4:15]** b will be a 4 by 1 vector in this example.
**[4:19]** Where the first coordinate four comes from the fact that we have
**[4:22]** four nodes of our hidden units and a layer, and
**[4:25]** three comes from the fact that we have three input features.
**[4:28]** We'll talk later about the dimensions of these matrices.
**[4:31]** And it might make more sense at that time.
**[4:33]** But in some of the output layers has associated with it also, parameters w
**[4:37]** superscript square bracket 2 and b superscript square bracket 2.
**[4:42]** And it turns out the dimensions of these are 1 by 4 and 1 by 1.
**[4:45]** And these 1 by 4 is because the hidden layer has four hidden units,
**[4:49]** the output layer has just one unit.
**[4:51]** But we will go over the dimension of these matrices and vectors in a later video.
**[4:56]** So you've just seen what a two layered neural network looks like.
**[4:59]** That is a neural network with one hidden layer.
**[5:03]** In the next video,
**[5:04]** let's go deeper into exactly what this neural network is computing.
**[5:08]** That is how this neural network inputs x and
**[5:11]** goes all the way to computing its output y hat.
