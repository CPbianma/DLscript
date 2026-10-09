---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 1
section: Convolutional Neural Networks
item_title: CNN Example
duration: 13 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/uRYL1/cnn-example
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# CNN Example — Transcript

**[0:00]** You now know pretty much all the building blocks of building
**[0:03]** a full convolutional neural network.
**[0:05]** Let's look at an example.
**[0:07]** Let's say you're inputting an image which is 32 x 32 x 3, so
**[0:14]** it's an RGB image and maybe you're trying to do handwritten digit recognition.
**[0:18]** So you have a number like 7 in a 32 x 32 RGB initiate trying
**[0:25]** to recognize which one of the 10 digits from zero to nine is this.
**[0:30]** Let's throw the neural network to do this.
**[0:32]** And what I'm going to use in this slide is inspired,
**[0:36]** it's actually quite similar to one of the classic neural networks called LeNet-5,
**[0:42]** which is created by Yann LeCun many years ago.
**[0:44]** What I'll show here isn't exactly LeNet-5 but
**[0:47]** it's inspired by it, but many parameter choices were inspired by it.
**[0:53]** So with a 32 x 32 x 3 input let's say that the first
**[0:57]** layer uses a 5 x 5 filter and a stride of 1, and no padding.
**[1:04]** So the output of this layer,
**[1:08]** if you use 6 filters would be 28 x 28 x 6,
**[1:13]** and we're going to call this layer conv 1.
**[1:18]** So you apply 6 filters, add a bias, apply the non-linearity,
**[1:23]** maybe a real non-linearity, and that's the conv 1 output.
**[1:28]** Next, let's apply a pooling layer, so
**[1:32]** I am going to apply mass pooling here and let's use a f=2, s=2.
**[1:40]** When I don't write a padding use a pad easy with a 0.
**[1:44]** Next let's apply a pooling layer, I am going to apply,
**[1:48]** let's see max pooling with a 2 x 2 filter and the stride equals 2.
**[1:54]** So this is should reduce the height and
**[1:57]** width of the representation by a factor of 2.
**[1:59]** So 28 x 28 now becomes 14 x 14, and
**[2:04]** the number of channels remains the same so 14 x 14 x 6,
**[2:10]** and we're going to call this the Pool 1 output.
**[2:15]** So, it turns out that in the literature of a ConvNet there are two
**[2:21]** conventions which are inside the inconsistent about what you call a layer.
**[2:25]** One convention is that this is called one layer.
**[2:30]** So this will be layer one of the neural network, and now the conversion
**[2:36]** will be to call they convey layer as a layer and the pool layer as a layer.
**[2:40]** When people report the number of layers in a neural network usually people just
**[2:45]** record the number of layers that have weight, that have parameters.
**[2:49]** And because the pooling layer has no weights, has no parameters,
**[2:53]** only a few hyper parameters, I'm going to use a convention that Conv 1 and
**[2:57]** Pool 1 shared together.
**[2:59]** I'm going to treat that as Layer 1, although sometimes you see people if you
**[3:04]** read articles online and read research papers, you hear about the conv layer and
**[3:08]** the pooling layer as if they are two separate layers.
**[3:11]** But this is maybe two slightly inconsistent notation terminologies,
**[3:16]** but when I count layers, I'm just going to count layers that have weights.
**[3:22]** So we treat both of these together as Layer 1.
**[3:25]** And the name Conv1 and Pool1 use here the 1 at the end also
**[3:30]** refers the fact that I view both of this is part of Layer 1 of the neural network.
**[3:37]** And Pool 1 is grouped into Layer 1 because it doesn't have its own weights.
**[3:42]** Next, given a 14 x 14 bx 6 volume, let's apply another
**[3:49]** convolutional layer to it, let's use a filter size that's 5 x 5,
**[3:53]** and let's use a stride of 1, and let's use 10 filters this time.
**[3:58]** So now you end up with, A 10 x 10
**[4:04]** x 10 volume, so I'll call this Comv 2,
**[4:09]** and then in this network let's do
**[4:14]** max pulling with f=2, s=2 again.
**[4:19]** So you could probably guess the output of this, f=2, s=2
**[4:23]** this should reduce the height and
**[4:26]** width by a factor of 2, so you're left with 5 x 5 x 10.
**[4:31]** And so I'm going to call this Pool 2, and
**[4:34]** in our convention this is Layer 2 of the neural network.
**[4:39]** Now let's apply another convolutional layer to this.
**[4:42]** I'm going to use a 5 x 5 filter, so f = 5, and let's try this,
**[4:48]** 1, and I don't write the padding, means there's no padding.
**[4:51]** And this will give you the Conv 2 output, and that's your 16 filters.
**[4:58]** So this would be a 10 x 10 x 16 dimensional output.
**[5:03]** So we look at that, and this is the Conv 2 layer.
**[5:10]** And then let's apply max pooling to this with f=2, s=2.
**[5:17]** You can probably guess the output of this,
**[5:19]** we're at 10 x 10 x 16 with max pooling with f=2, s=2.
**[5:24]** This will half the height and
**[5:27]** width, you can probably guess the result of this, right?
**[5:31]** Max pooling with f = 2, s = 2.
**[5:32]** This should halve the height and width so you end up with
**[5:37]** a 5 x 5 x 16 volume, same number of channels as before.
**[5:43]** We're going to call this Pool 2.
**[5:47]** And in our convention this is Layer 2 because this
**[5:54]** has one set of weights and your Conv 2 layer.
**[5:57]** Now 5 x 5 x 16, 5 x 5 x 16 is equal to 400.
**[6:03]** So let's now fatten our Pool 2 into a 400 x 1 dimensional vector.
**[6:10]** So think of this as fatting this up into these set of neurons, like so.
**[6:16]** And what we're going to do is then take these 400 units and
**[6:22]** let's build the next layer, As having 120 units.
**[6:30]** So this is actually our first fully connected layer.
**[6:33]** I'm going to call this FC3 because we have
**[6:38]** 400 units densely connected to 120 units.
**[6:46]** So this fully connected unit, this fully connected layer is just like
**[6:51]** the single neural network layer that you saw in Courses 1 and 2.
**[6:56]** This is just a standard neural network where you have
**[7:00]** a weight matrix that's called W3 of dimension 120 x 400.
**[7:08]** And this is fully connected because each of the 400 units here is connected
**[7:11]** to each of the 120 units here, and you also have the bias parameter,
**[7:18]** yes that's going to be just a 120 dimensional, this is 120 outputs.
**[7:23]** And then lastly let's take 120 units and add another layer,
**[7:28]** this time smaller but let's say we had 84 units here,
**[7:33]** I'm going to call this fully connected Layer 4.
**[7:36]** And finally we now have 84 real numbers that you can feed to a softnax unit.
**[7:44]** And if you're trying to do handwritten digital recognition,
**[7:47]** to recognize this hand it is 0, 1, 2, and so on up to 9.
**[7:51]** Then this would be a softmax with 10 outputs.
**[7:56]** So this is a reasonably typical example of what
**[8:02]** a convolutional neural network might look like.
**[8:05]** And I know this seems like there a lot of hyper parameters.
**[8:09]** We'll give you some more specific suggestions later for
**[8:12]** how to choose these types of hyper parameters.
**[8:15]** Maybe one common guideline is to actually not try to invent your own
**[8:21]** settings of hyper parameters, but
**[8:22]** to look in the literature to see what hyper parameters you work for others.
**[8:27]** And to just choose an architecture that has worked well for
**[8:30]** someone else, and there's a chance that will work for your application as well.
**[8:35]** We'll see more about that next week.
**[8:38]** But for now I'll just point out that as you go deeper in the neural network,
**[8:43]** usually nh and nw to height and width will decrease.
**[8:47]** Pointed this out earlier, but it goes from 32 x 32, to 20 x 20, to 14 x 14,
**[8:52]** to 10 x 10, to 5 x 5.
**[8:53]** So as you go deeper usually the height and width will decrease,
**[8:57]** whereas the number of channels will increase.
**[9:00]** It's gone from 3 to 6 to 16, and then your fully connected layer is at the end.
**[9:07]** And another pretty common pattern you see in neural networks is to have conv layers,
**[9:13]** maybe one or more conv layers followed by a pooling layer, and
**[9:17]** then one or more conv layers followed by pooling layer.
**[9:21]** And then at the end you have a few fully connected layers and
**[9:24]** then followed by maybe a softmax.
**[9:26]** And this is another pretty common pattern you see in neural networks.
**[9:32]** So let's just go through for
**[9:33]** this neural network some more details of what are the activation shape,
**[9:38]** the activation size, and the number of parameters in this network.
**[9:41]** So the input was 32 x 30 x 3, and
**[9:44]** if you multiply out those numbers you should get 3,072.
**[9:48]** So the activation, a0 has dimension 3072.
**[9:54]** Well it's really 32 x 32 x 3.
**[9:58]** And there are no parameters I guess at the input layer.
**[10:02]** And as you look at the different layers,
**[10:05]** feel free to work out the details yourself.
**[10:09]** These are the activation shape and
**[10:10]** the activation sizes of these different layers.
**[10:15]** So just to point out a few things.
**[10:16]** First, notice that the max pooling layers don't have any parameters.
**[10:23]** Second, notice that the conv layers tend to have relatively
**[10:28]** few parameters, as we discussed in early videos.
**[10:32]** And in fact, a lot of the parameters tend to be in the fully
**[10:36]** collected layers of the neural network.
**[10:39]** And then you notice also that the activation size tends to
**[10:44]** maybe go down gradually as you go deeper in the neural network.
**[10:50]** If it drops too quickly, that's usually not great for performance as well.
**[10:55]** So it starts first there with 6,000 and 1,600, and
**[11:00]** then slowly falls into 84 until finally you have your Softmax output.
**[11:06]** You find that a lot of will have properties will
**[11:10]** have patterns similar to these.
**[11:13]** So you've now seen the basic building blocks of neural networks,
**[11:16]** your convolutional neural networks, the conv layer, the pooling layer,
**[11:20]** and the fully connected layer.
**[11:21]** A lot of computer division research has gone into figuring out how to put together
**[11:25]** these basic building blocks to build effective neural networks.
**[11:29]** And putting these things together actually requires quite a bit of insight.
**[11:33]** I think that one of the best ways for
**[11:35]** you to gain intuition is about how to put these things together is a C a number of
**[11:39]** concrete examples of how others have done it.
**[11:41]** So what I want to do next week is show you a few concrete examples even beyond this
**[11:46]** first one that you just saw on how people have successfully put these
**[11:50]** things together to build very effective neural networks.
**[11:53]** And through those videos next week l hope you hold your own intuitions about how
**[11:58]** these things are built.
**[12:00]** And as we are given concrete examples that architectures that maybe you can just use
**[12:05]** here exactly as developed by someone else or your own application.
**[12:09]** So we'll do that next week, but
**[12:10]** before wrapping this week's videos just one last thing which is one I'll talk
**[12:15]** a little bit in the next video about why you might want to use convolutions.
**[12:19]** Some benefits and
**[12:20]** advantages of using convolutions as well as how to put them all together.
**[12:25]** How to take a neural network like the one you just saw and actually train it
**[12:29]** on a training set to perform image recognition for some of the tasks.
**[12:32]** So with that let's go on to the last video of this week.
