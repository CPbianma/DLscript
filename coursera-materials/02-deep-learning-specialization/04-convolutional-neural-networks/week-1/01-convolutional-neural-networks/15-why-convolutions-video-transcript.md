---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 1
section: Convolutional Neural Networks
item_title: Why Convolutions?
duration: 10 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/Xv7B5/why-convolutions
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Why Convolutions? — Transcript

**[0:00]** For this final video for this week,
**[0:02]** let's talk a bit about why convolutions are so
**[0:05]** useful when you include them in your neural networks.
**[0:08]** And then finally, let's briefly talk about how to put this all together and how
**[0:13]** you could train a convolution neural network when you have a label training set.
**[0:20]** I think there are two main advantages of
**[0:23]** convolutional layers over just using fully connected layers.
**[0:29]** And the advantages are parameter sharing and sparsity of connections.
**[0:34]** Let me illustrate with an example.
**[0:36]** Let's say you have a 32 by 32 by 3 dimensional image,
**[0:42]** and this actually comes from the example from the previous video,
**[0:49]** but let's say you use five by five filter with six filters.
**[0:54]** And so, this gives you a 28 by 28 by 6 dimensional output.
**[1:04]** So, 32 by 32 by 3 is 3,072,
**[1:09]** and 28 by 28 by 6 if you multiply all those numbers is 4,704.
**[1:17]** And so, if you were to create a neural network with 3,072 units in one layer,
**[1:24]** and with 4,704 units in the next layer,
**[1:27]** and if you were to connect every one of these neurons,
**[1:31]** then the weight matrix,
**[1:32]** the number of parameters in a weight matrix would be 3,072
**[1:35]** times 4,704 which is about 14 million.
**[1:42]** So, that's just a lot of parameters to train.
**[1:44]** And today you can train neural networks with even more parameters than 14 million,
**[1:49]** but considering that this is just a pretty small image,
**[1:52]** this is a lot of parameters to train.
**[1:54]** And of course, if this were to be 1,000 by 1,000 image,
**[2:00]** then your display matrix will just become invisibly large.
**[2:04]** But if you look at the number of parameters in this convolutional layer,
**[2:10]** each filter is five by five.
**[2:12]** So, each filter has 25 parameters,
**[2:15]** plus a bias parameter miss of 26 parameters per a filter,
**[2:19]** and you have six filters, so,
**[2:21]** the total number of parameters is that,
**[2:23]** which is equal to 156 parameters.
**[2:26]** And so, the number of parameters in this conv layer remains quite small.
**[2:31]** And the reason that a convnet has run to these small parameters is really two reasons.
**[2:37]** One is parameter sharing.
**[2:40]** And parameter sharing is motivated by the observation
**[2:43]** that feature detector such as vertical edge detector,
**[2:47]** that's useful in one part of the image is probably useful in another part of the image.
**[2:51]** And what that means is that,
**[2:52]** if you've figured out say a three by three filter for detecting vertical edges,
**[2:56]** you can then apply the same three by three filter over here,
**[3:01]** and then the next position over,
**[3:03]** and the next position over, and so on.
**[3:06]** And so, each of these feature detectors,
**[3:09]** each of these outputs can use the same parameters in lots of
**[3:13]** different positions in your input image in order to
**[3:17]** detect say a vertical edge or some other feature.
**[3:21]** And I think this is true for low-level features like edges,
**[3:25]** as well as the higher level features, like maybe,
**[3:28]** detecting the eye that indicates a face or a cat or something there.
**[3:32]** But being with a share in this case
**[3:34]** the same nine parameters to compute all 16 of these outputs,
**[3:39]** is one of the ways the number of parameters is reduced.
**[3:43]** And it also just seems intuitive that a feature detector
**[3:47]** like a vertical edge detector computes it for the upper left-hand corner of the image.
**[3:52]** The same feature seems like it will probably be useful,
**[3:55]** has a good chance of being useful for the lower right-hand corner of the image.
**[3:59]** So, maybe you don't need to learn
**[4:00]** separate feature detectors for
**[4:02]** the upper left and the lower right-hand corners of the image.
**[4:05]** And maybe you do have a dataset where you have
**[4:07]** the upper left-hand corner and lower right-hand corner have different distributions, so,
**[4:12]** they maybe look a little bit different but they might be similar enough,
**[4:15]** they're sharing feature detectors all across the image, works just fine.
**[4:20]** The second way that convnet get away with
**[4:23]** having relatively few parameters is by having sparse connections.
**[4:27]** So, here's what I mean,
**[4:28]** if you look at the zero,
**[4:30]** this is computed via three by three convolution.
**[4:32]** And so, it depends only on this three by three inputs grid or cells.
**[4:38]** So, it is as if this output units on the right is connected only
**[4:43]** to nine out of these six by six, 36 input features.
**[4:50]** And in particular, the rest of these pixel values,
**[4:54]** all of these pixel values do not have any effects on the other output.
**[5:02]** So, that's what I mean by sparsity of connections.
**[5:04]** As another example, this output depends only on these nine input features.
**[5:15]** And so, it's as if only those nine input features are connected to this output,
**[5:20]** and the other pixels just don't affect this output at all.
**[5:23]** And so, through these two mechanisms,
**[5:25]** a neural network has a lot fewer parameters which allows it
**[5:30]** to be trained with smaller training cells and is less prone to be over 30.
**[5:35]** And so, sometimes you also hear about
**[5:37]** convolutional neural networks being very good at capturing translation invariance.
**[5:42]** And that's the observation that
**[5:44]** a picture of a cat shifted a couple of pixels to the right,
**[5:48]** is still pretty clearly a cat.
**[5:50]** And convolutional structure helps the neural network encode the fact that an image
**[5:58]** shifted a few pixels should result in pretty similar features and
**[6:02]** should probably be assigned the same oval label.
**[6:07]** And the fact that you are applying to same filter,
**[6:10]** knows all the positions of the image,
**[6:13]** both in the early layers and in the late layers that
**[6:16]** helps a neural network automatically learn to be more
**[6:20]** robust or to better capture the desirable property of translation invariance.
**[6:28]** So, these are maybe a couple of the reasons why
**[6:32]** convolutions or convolutional neural network work so well in computer vision.
**[6:37]** Finally, let's put it all together and see how you can train one of these networks.
**[6:43]** Let's say you want to build a cat detector and you
**[6:45]** have a labeled training sets as follows,
**[6:48]** where now, X is an image.
**[6:52]** And the y's can be binary labels,
**[6:54]** or one of K causes.
**[6:57]** And let's say you've chosen a convolutional neural network structure,
**[7:02]** may be inserted the image and then having neural convolutional and pulling layers
**[7:06]** and then some fully connected layers
**[7:09]** followed by a software output that then operates Y hat.
**[7:13]** The conv layers and the fully connected layers will have various parameters,
**[7:20]** W, as well as bias's B.
**[7:23]** And so, any setting of the parameters, therefore,
**[7:26]** lets you define a cost function similar to what we have seen in the previous courses,
**[7:32]** where we've randomly initialized parameters W and B.
**[7:37]** You can compute the cause J,
**[7:40]** as the sum of losses of the neural networks predictions on your entire training set,
**[7:46]** maybe divide it by M. So,
**[7:50]** to train this neural network,
**[7:52]** all you need to do is then use gradient descents or some of
**[7:56]** the algorithm like, gradient descent momentum,
**[7:59]** or RMSProp or Adam, or something else,
**[8:03]** in order to optimize all the parameters of
**[8:05]** the neural network to try to reduce the cost function J.
**[8:09]** And you find that if you do this,
**[8:11]** you can build a very effective cat detector or some other detector.
**[8:18]** So, congratulations on finishing this week's videos.
**[8:21]** You've now seen all the basic building blocks of a convolutional neural network,
**[8:25]** and how to put them together into an effective image recognition system.
**[8:30]** In this week's program exercises,
**[8:32]** I think all of these things will come more concrete,
**[8:34]** and you'll get the chance to practice implementing
**[8:36]** these things yourself and seeing it work for yourself.
**[8:39]** Next week, we'll continue to go deeper into convolutional neural networks.
**[8:43]** I mentioned earlier, that there're just a lot of
**[8:45]** the hyperparameters in convolution neural networks.
**[8:48]** So, what I want to do next week,
**[8:49]** is show you a few concrete examples of some of
**[8:52]** the most effective convolutional neural networks,
**[8:54]** so you can start to recognize the patterns
**[8:57]** of what types of network architectures are effective.
**[9:00]** And one thing that people often do is just take the architecture that
**[9:04]** someone else has found and published in
**[9:05]** a research paper and just use that for your application.
**[9:08]** And so, by seeing some more concrete examples next week,
**[9:12]** you also learn how to do that better.
**[9:15]** And beyond that, next week,
**[9:16]** we'll also just get that intuitions about what makes confinet work well,
**[9:21]** and then in the rest of the course,
**[9:23]** we'll also see a variety of other computer vision applications such as,
**[9:27]** object detection, and neural store transfer.
**[9:30]** How they create new forms of artwork using these set of algorithms.
**[9:34]** So, that's over this week,
**[9:35]** best of luck with the home works,
**[9:37]** and I look forward to seeing you next week.
