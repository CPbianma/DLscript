---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 1
section: Convolutional Neural Networks
item_title: Simple Convolutional Network Example
duration: 9 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/A9lXL/simple-convolutional-network-example
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Simple Convolutional Network Example — Transcript

**[0:00]** In the last video, you saw the building blocks of a single layer,
**[0:04]** of a single convolution layer in the ConvNet.
**[0:06]** Now let's go through a concrete example of a deep convolutional neural network.
**[0:12]** And this will give you some practice with the notation that we introduced toward
**[0:15]** the end of the last video as well.
**[0:19]** Let's say you have an image, and
**[0:22]** you want to do image classification, or image recognition.
**[0:26]** Where you want to take as input an image, x, and decide is this a cat or not, 0 or
**[0:31]** 1, so it's a classification problem.
**[0:34]** Let's build an example of a ConvNet you could use for this task.
**[0:38]** For the sake of this example, I'm going to use a fairly small image.
**[0:42]** Let's say this image is 39 x 39 x 3.
**[0:48]** This choice just makes some of the numbers work out a bit better.
**[0:51]** And so, nH in layer 0 will be equal to nW height and
**[0:57]** width are equal to 39 and
**[1:00]** the number of channels and layer 0 is equal to 3.
**[1:06]** Let's say the first layer uses a set of 3 by 3 filters
**[1:11]** to detect features, so f = 3 or really f1 = 3,
**[1:18]** because we're using a 3 by 3 process.
**[1:20]** And let's say we're using a stride of 1, and no padding.
**[1:26]** So using a same convolution, and let's say you have 10 filters.
**[1:34]** Then the activations in this next layer of
**[1:36]** the neutral network will be 37 x 37 x 10, and
**[1:44]** this 10 comes from the fact that you use 10 filters.
**[1:49]** And 37 comes from this formula
**[1:52]** n + 2p- f over s + 1.
**[1:58]** Right, then I guess you have 39
**[2:02]** + 0- 3 over 1 + 1 that's = to 37.
**[2:10]** So that's why the output is 37 by 37, it's a valid convolution and
**[2:15]** that's the output size.
**[2:17]** So in our notation you would have nh[1] = nw[1] = 37 and
**[2:27]** nc[1] = 10, so nc[1] is also equal
**[2:30]** to the number of filters from the first layer.
**[2:36]** And so this becomes the dimension of the activation at the first layer.
**[2:43]** Let's say you now have another convolutional layer and
**[2:45]** let's say this time you use 5 by 5 filters.
**[2:48]** So, in our notation f[2] at the next neural network = 5,
**[2:54]** and let's say use a stride of 2 this time.
**[2:59]** And maybe you have no padding and
**[3:03]** say, 20 filters.
**[3:09]** So then the output of this will be another volume,
**[3:15]** this time it will be 17 x 17 x 20.
**[3:20]** Notice that, because you're now using a stride of 2,
**[3:23]** the dimension has shrunk much faster.
**[3:25]** 37 x 37 has gone down in size by slightly more than a factor of 2, to 17 x 17.
**[3:32]** And because you're using 20 filters, the number of channels now is 20.
**[3:37]** So it's this activation a2
**[3:42]** would be that dimension
**[3:46]** and so nh[2] = nw[2] = 17 and
**[3:49]** nc[2] = 20.
**[3:55]** All right, let's apply one last convolutional layer.
**[3:58]** So let's say that you use a 5 by 5 filter again,
**[4:03]** and again, a stride of 2.
**[4:07]** So if you do that, I'll skip the math, but you end up with a 7 x 7, and
**[4:13]** let's say you use 40 filters, no padding, 40 filters.
**[4:19]** You end up with 7 x 7 x 40.
**[4:22]** So now what you've done is taken your 39 x 39 x 3 input
**[4:27]** image and computed your 7 x 7 x 40 features for this image.
**[4:34]** And then finally, what's commonly done is if you take this 7 x 7 x 40,
**[4:41]** 7 times 7 times 40 is actually 1,960.
**[4:45]** And so what we can do is take this volume and flatten it or
**[4:48]** unroll it into just 1,960 units, right?
**[4:55]** Just flatten it out into a vector, and
**[4:59]** then feed this to a logistic regression unit, or a softmax unit.
**[5:07]** Depending on whether you're trying to recognize cat or no cat or
**[5:11]** trying to recognize any one of key different objects and
**[5:15]** then just have this give the final predicted output for the neural network.
**[5:20]** So just be clear, this last step is just taking all of these numbers,
**[5:26]** all 1,960 numbers, and unrolling them into a very long vector.
**[5:32]** So then you just have one long vector that you can feed into softmax until it's just
**[5:36]** a regression in order to make prediction for the final output.
**[5:41]** So this would be a pretty typical example of a ConvNet.
**[5:47]** A lot of the work in designing convolutional neural net is selecting
**[5:51]** hyperparameters like these, deciding what's the total size?
**[5:54]** What's the stride?
**[5:55]** What's the padding and how many filters are used?
**[6:00]** And both later this week as well as next week, we'll give some suggestions and
**[6:03]** some guidelines on how to make these choices.
**[6:07]** But for now, maybe one thing to take away from this is that as you go
**[6:12]** deeper in a neural network, typically you start off with larger images, 39 by 39.
**[6:17]** And then the height and width will stay the same for
**[6:22]** a while and gradually trend down as you go deeper in the neural network.
**[6:25]** It's gone from 39 to 37 to 17 to 14.
**[6:29]** Excuse me, it's gone from 39 to 37 to 17 to 7.
**[6:33]** Whereas the number of channels will generally increase.
**[6:36]** It's gone from 3 to 10 to 20 to 40, and you see this general
**[6:43]** trend in a lot of other convolutional neural networks as well.
**[6:47]** So we'll get more guidelines about how to design these parameters in later videos.
**[6:52]** But you've now seen your first example of a convolutional neural network, or
**[6:57]** a ConvNet for short.
**[6:59]** So congratulations on that.
**[7:02]** And it turns out that in a typical ConvNet,
**[7:05]** there are usually three types of layers.
**[7:07]** One is the convolutional layer, and often we'll denote that as a Conv layer.
**[7:13]** And that's what we've been using in the previous network.
**[7:17]** It turns out that there are two other common types of layers that you haven't
**[7:20]** seen yet but we'll talk about in the next couple of videos.
**[7:23]** One is called a pooling layer, often I'll call this pool.
**[7:28]** And then the last is a fully connected layer called FC.
**[7:32]** And although it's possible to design a pretty good neural network using just
**[7:36]** convolutional layers, most neural network architectures will also have a few pooling
**[7:41]** layers and a few fully connected layers.
**[7:46]** Fortunately pooling layers and
**[7:48]** fully connected layers are a bit simpler than convolutional layers to define.
**[7:54]** So we'll do that quickly in the next two videos and then you have a sense
**[7:58]** of all of the most common types of layers in a convolutional neural network.
**[8:03]** And you will put together even more powerful networks than the one we
**[8:06]** just saw.
**[8:08]** So congrats again on seeing your first full convolutional neural network.
**[8:14]** We'll also talk later in this week about how to train these networks, but
**[8:18]** first let's talk briefly about pooling and fully connected layers.
**[8:22]** And then training these, we'll be using back propagation,
**[8:24]** which you're already familiar with.
**[8:26]** But in the next video, let's quickly go over how to implement a pooling layer for
**[8:30]** your ConvNet.
