---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 3
section: Detection Algorithms
item_title: U-Net Architecture
duration: 8 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/GIIWY/u-net-architecture
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# U-Net Architecture — Transcript

**[0:03]** I found the unit architecture useful for many applications I have worked on, and
**[0:07]** there's this one of the most important and
**[0:10]** foundational neural network architectures of computer vision today.
**[0:14]** So in this video, let's dig in the details of exactly how the U-Net works.
**[0:19]** This is what a U-Net looks like.
**[0:21]** I know there's a lot going on in this picture, is okay we'll break it down and
**[0:25]** step it through one step at the time.
**[0:27]** But I want to quickly show you the final outcome of what a unit
**[0:31]** architecture looks like.
**[0:33]** And this, by the way, is also why it's called a unit,
**[0:36]** because when you draw it like this, it looks a lot like a U.
**[0:40]** But let's break it down and build this back up one piece at a time.
**[0:45]** So we're going to make sure we know what all of the things going on in this diagram
**[0:49]** actually are doing.
**[0:50]** These ideas were due to Olaf Ranneberger for the Fisher and Thomas Bronx.
**[0:56]** Fun fact, when they wrote the original unit paper,
**[0:59]** they were thinking of the application of biomedical image segmentation,
**[1:04]** really segmenting medical images.
**[1:06]** But these ideas turned out to be useful for many other computer vision,
**[1:11]** semantic segmentation applications as well.
**[1:13]** So the input to the unit is an image, let's say,
**[1:17]** is h by w by three, for three channels RGB channels.
**[1:24]** I'm going to visualize this image as a thin layer like that.
**[1:30]** I know that previously we had taken neural network layers and drawn them,
**[1:36]** as three D blocks like this, where this might be rise of h by w by three.
**[1:42]** But in order to make the unit diagram look
**[1:46]** simpler going to imagine just looking at this edge on.
**[1:49]** So all you see is this.
**[1:51]** And the rest of this is hidden behind this dark blue rectangle that I've have drawn.
**[1:59]** And so that's what this is.
**[2:01]** The height of this is, the height h and the width of this is three, right,
**[2:06]** with the number of channels,the depth is 3.
**[2:10]** So it looks very thin.
**[2:12]** So to simplify the unit diagram, I'm going to use these rectangles rather than
**[2:17]** three D shapes to illustrate the algorithm.
**[2:20]** Now, the first part of the unit uses normal feed forward neural network
**[2:25]** convolutional layers.
**[2:26]** So I'm going to use a black arrow to denote a convolutional layer,
**[2:32]** followed by a value activation function.
**[2:35]** So the next layer, maybe we'll say that, we have increased the number of channels
**[2:40]** a little bit, but the dimension is still height by width by a little bit more
**[2:44]** channels and then another convolutional layer with a rather activation function.
**[2:51]** Now we're still in the first half of the neural network.
**[2:55]** We're going to use Max pooling to reduce the height and width.
**[2:59]** So maybe you end up with a set of activations where the height and
**[3:03]** width is lower, but maybe a sticker, so the number of channels is increasing.
**[3:09]** Then we have two more layers of normal feet forward convolutions with
**[3:14]** a radio activation function, and then the supply Max pooling again.
**[3:19]** And so you get that, right.
**[3:22]** And then you repeat again.
**[3:24]** And so you end up with this.
**[3:26]** So, so far, this is the normal convolution layers with activation functions that
**[3:32]** you've been used to from earlier videos with occasional max pooling layers.
**[3:38]** So notice that the height of this layer I deal with is now very small.
**[3:44]** So we're going to start to apply transpose convolution layers,
**[3:49]** which I'm going to note by the green arrow in order to build
**[3:54]** the dimension of this neural network back up.
**[3:57]** So with the first transpose convolutional layer or trans conv layer,
**[4:02]** you're going to get a set of activations that looks like that.
**[4:07]** In this example, we did not increase the height and width, but
**[4:12]** we did decrease the number of channels.
**[4:15]** But there's one more thing you need to do to build a unit, which is to add in
**[4:20]** that skip connection which I'm going to denote with this grey arrow.
**[4:25]** What the skip connection does is it takes this set of activations and
**[4:30]** just copies it over to the right.
**[4:32]** And so the set of activations you end up with is like this.
**[4:36]** The light blue part comes from the transpose convolution, and
**[4:40]** the dark blue part is just copied over from the left.
**[4:44]** To keep on building up the unit we are going to then apply a
**[4:49]** couple more layers of the regular convolutions,
**[4:52]** followed by our value activation function so denoted by the black arrows,
**[4:58]** like so, and then we apply another transpose convolutional layer.
**[5:03]** So green arrow and here we're going to start to increase the dimension,
**[5:08]** increase the height and width of this image.
**[5:11]** And so now the height is getting bigger.
**[5:15]** But here, too, we're going to apply a skip connection.
**[5:18]** So there's a grey arrow again where they take this set of activations and
**[5:23]** just copy it right there, over to the right.
**[5:28]** More convolutional layers and other transpose convolution, skip connection.
**[5:32]** Once again, we're going to take this set of activations and
**[5:36]** copy it over to the right and then more convolutional layers,
**[5:39]** followed by another transpose convolution.
**[5:42]** Skip connection, copy that over.
**[5:45]** And now we're back to a set of activations that is
**[5:49]** the original input images, height and width.
**[5:54]** We're going to have a couple more layers of a normal fee forward convolutions, and
**[6:00]** then finally, to take this and map this to our segmentation map,
**[6:06]** we're going to use a one by one convolution which I'm going to denote
**[6:11]** with that magenta arrow to finally give us this which is going to be our output.
**[6:18]** The dimensions of this output layer is going to be h by w, so
**[6:23]** the same dimensions as our original input by num classes.
**[6:29]** So if you have three classes to try and recognize, this will be three.
**[6:34]** If you have ten different classes to try to recognize in your
**[6:37]** segmentation at then that last number will be ten.
**[6:41]** And so what this does is for every one of your pixels you have h by w pixels you
**[6:46]** have, an array or a vector, essentially of n classes numbers that tells you for
**[6:53]** our pixel how likely is that pixel to come from each of these different classes.
**[6:57]** And if you take a arg max over these n classes,
**[7:00]** then that's how you classify each of the pixels into one of the classes,
**[7:04]** and you can visualize it like the segmentation map showing on the right.
**[7:10]** So that's it.
**[7:11]** You've learned about the transpose convolution and the unit architecture.
**[7:15]** Congrats getting to the end of this week's videos.
**[7:18]** I hope you also enjoy working through these ideas in the program exercise.
**[7:23]** Next week, we'll come back and talk about some specialized architecture for
**[7:28]** face recognition and for your style transfer where you get to create some
**[7:32]** really interesting artwork using neural networks.
**[7:36]** Have fun with pro exercise, and I look forward to seeing you next week.
