---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 1
section: Neural network implementation in Python
item_title: General implementation of forward propagation
duration: 8 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/fZYiN/general-implementation-of-forward-propagation
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# General implementation of forward propagation — Transcript

**[0:01]** In the last video, you saw how to
**[0:04]** implement forward prop in Python,
**[0:06]** but by hard coding lines of code for every single neuron.
**[0:10]** Let's now take a look at
**[0:11]** the more general implementation
**[0:13]** of forward prop in Python.
**[0:15]** Similar to the previous video,
**[0:17]** my goal in this video is to show you the code so that
**[0:20]** when you see it again in their practice lab,
**[0:23]** in the optional labs, you know how to interpret it.
**[0:26]** As we walk through this example,
**[0:28]** don't worry about taking
**[0:29]** notes on every single line of code.
**[0:31]** If you can read through the code and
**[0:33]** understand it, that's definitely enough.
**[0:36]** What you can do is write
**[0:37]** a function to implement a dense layer,
**[0:41]** that is a single layer of a neural network.
**[0:44]** I'm going to define the dense function,
**[0:47]** which takes as input
**[0:48]** the activation from the previous layer,
**[0:51]** as well as the parameters w and
**[0:54]** b for the neurons in a given layer.
**[0:58]** Using the example from the previous video,
**[1:01]** if layer 1 has three neurons,
**[1:06]** and if w_1 and w_2 and w_3 are these,
**[1:13]** then what we'll do is
**[1:15]** stack all of these wave vectors into a matrix.
**[1:19]** This is going to be a two by three matrix,
**[1:25]** where the first column is
**[1:27]** the parameter w_1,1 the second column
**[1:30]** is the parameter w_1,
**[1:31]** 2, and the third column is the parameter w_1,3.
**[1:36]** Then in a similar way,
**[1:38]** if you have parameters be,
**[1:42]** b_1,1 equals negative one,
**[1:44]** b_1,2 equals one, and so on,
**[1:46]** then we're going to stack these three numbers into
**[1:49]** a 1D array b as follows,
**[1:52]** negative one, one, two.
**[1:54]** What the dense function will do is take as
**[1:57]** inputs the activation from the previous layer,
**[2:00]** and a here could be a_0,
**[2:02]** which is equal to x,
**[2:04]** or the activation from a later layer,
**[2:07]** as well as the w parameters stacked in columns,
**[2:12]** like shown on the right,
**[2:14]** as well as the b parameters
**[2:16]** also stacked into a 1D array,
**[2:19]** like shown to the left over there.
**[2:22]** What this function would do is input a to
**[2:28]** activation from the previous layer and will
**[2:30]** output the activations from the current layer.
**[2:34]** Let's step through the code for doing this.
**[2:37]** Here's the code. First, units equals W.shape,1.
**[2:41]** W here is a two-by-three matrix,
**[2:47]** and so the number of columns is three.
**[2:50]** That's equal to the number of units in this layer.
**[2:53]** Here, units would be equal to three.
**[2:56]** Looking at the shape of w,
**[2:58]** is just a way of pulling out the number of
**[3:01]** hidden units or the number of units in this layer.
**[3:05]** Next, we set a to be an array of
**[3:08]** zeros with as many elements as there are units.
**[3:12]** In this example, we need
**[3:14]** to output three activation values,
**[3:16]** so this just initializes a to be zero,
**[3:19]** zero, zero, an array of three zeros.
**[3:22]** Next, we go through a for loop to compute the first,
**[3:26]** second, and third elements of a.
**[3:28]** For j in range units,
**[3:30]** so j goes from zero to units minus one.
**[3:33]** It goes from 0, 1,
**[3:34]** 2 indexing from zero and Python as usual.
**[3:37]** This command w equals W colon comma j,
**[3:42]** this is how you pull out
**[3:45]** the jth column of a matrix in Python.
**[3:49]** The first time through this loop,
**[3:52]** this will pull the first column of w,
**[3:55]** and so will pull out w_1,1.
**[3:58]** The second time through this loop,
**[4:00]** when you're computing the activation of the second unit,
**[4:03]** will pull out the second column corresponding to w_1,
**[4:06]** 2, and so on for the third time through this loop.
**[4:10]** Then you compute z using the usual formula,
**[4:14]** is a dot product between
**[4:16]** that parameter w and
**[4:18]** the activation that you have received,
**[4:20]** plus b, j.
**[4:22]** And then you compute the activation a, j,
**[4:25]** equals g sigmoid function applied to z.
**[4:29]** Three times through this loop and you compute it,
**[4:31]** the values for all three values
**[4:33]** of this vector of activation is a.
**[4:35]** Then finally you return a.
**[4:38]** What the dense function does is it
**[4:41]** inputs the activations from the previous layer,
**[4:43]** and given the parameters for the current layer,
**[4:46]** it returns the activations for the next layer.
**[4:50]** Given the dense function,
**[4:52]** here's how you can string
**[4:53]** together a few dense layers sequentially,
**[4:56]** in order to implement forward prop in the neural network.
**[4:59]** Given the input features x,
**[5:03]** you can then compute
**[5:05]** the activations a_1 to be a_1 equals dense of x,
**[5:11]** w_1, b_1, where here w_1,
**[5:14]** b_1 are the parameters,
**[5:16]** sometimes also called the weights
**[5:18]** of the first hidden layer.
**[5:20]** Then you can compute a_2 as dense of now a_1,
**[5:26]** which you just computed above.
**[5:29]** W_2, b-2 which are the parameters or
**[5:32]** weights of this second hidden layer.
**[5:35]** Then compute a_3 and a_4.
**[5:38]** If this is a neural network with four layers,
**[5:42]** then define the output f of x is just equal to a_4,
**[5:46]** and so you return f of x.
**[5:49]** Notice that here I'm using W,
**[5:53]** because under the notational conventions
**[5:55]** from linear algebra is to use uppercase or
**[5:58]** a capital alphabet is when it's referring to
**[6:01]** a matrix and lowercase refer to vectors and scalars.
**[6:05]** So because it's a matrix,
**[6:06]** this is W. That's it.
**[6:09]** You now know how to implement
**[6:11]** forward prop yourself from scratch.
**[6:13]** You get to see all this code and run it and practice it
**[6:17]** yourself in the practice lab coming off to this as well.
**[6:20]** I think that even when you're using
**[6:22]** powerful libraries like TensorFlow,
**[6:25]** it's helpful to know how it works under the hood.
**[6:27]** Because in case something goes wrong,
**[6:30]** in case something runs really slowly,
**[6:32]** or you have a strange result,
**[6:33]** or it looks like there's a bug,
**[6:35]** your ability to understand what's actually going on
**[6:38]** will make you much more effective
**[6:40]** when debugging your code.
**[6:41]** When I run machine learning algorithms a lot of the time,
**[6:45]** frankly, it doesn't work.
**[6:46]** Sophie, not the first time.
**[6:48]** I find that my ability to debug
**[6:50]** my code to be a TensorFlow code or something else,
**[6:53]** is really important to being
**[6:55]** an effective machine learning engineer.
**[6:58]** Even when you're using
**[6:59]** TensorFlow or some other framework,
**[7:02]** I hope that you find this deeper understanding useful for
**[7:06]** your own applications and for debugging
**[7:08]** your own machine learning algorithms as well.
**[7:11]** That's it. That's the last required video
**[7:15]** of this week with code in it.
**[7:17]** In the next video,
**[7:18]** I'd like to dive into what I think is
**[7:20]** a fun and fascinating topic, which is,
**[7:22]** what is the relationship between neural networks and
**[7:25]** AI or AGI, artificial general intelligence?
**[7:30]** This is a controversial topic,
**[7:32]** but because it's been so widely discussed,
**[7:34]** I want to share with you some thoughts on this.
**[7:37]** When you are asked,
**[7:39]** are neural networks at all
**[7:41]** on the path to human level intelligence?
**[7:44]** You have a framework for thinking about that question.
**[7:47]** Let's go take a look at that fun topic,
**[7:49]** I think, in the next video.
