---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 3
section: Detection Algorithms
item_title: Convolutional Implementation of Sliding Windows
duration: 11 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/6UnU4/convolutional-implementation-of-sliding-windows
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Convolutional Implementation of Sliding Windows — Transcript

**[0:00]** In the last video,
**[0:01]** you learned about the sliding windows
**[0:03]** object detection algorithm using a convnet but we saw that it was too slow.
**[0:08]** In this video, you'll learn how to implement that algorithm convolutionally.
**[0:13]** Let's see what this means.
**[0:14]** To build up towards the convolutional implementation of sliding windows let's first see
**[0:20]** how you can turn fully connected layers in neural network into convolutional layers.
**[0:25]** We'll do that first on this slide and then the next slide,
**[0:28]** we'll use the ideas from this slide to show you the convolutional implementation.
**[0:33]** So let's say that your object detection algorithm inputs 14 by 14 by 3 images.
**[0:39]** This is quite small but just for illustrative purposes,
**[0:42]** and let's say it then uses 5 by 5 filters,
**[0:45]** and let's say it uses 16 of them to map it from 14 by 14 by 3 to 10 by 10 by 16.
**[0:52]** And then does a 2 by 2 max pooling to reduce it to 5 by 5 by 16.
**[0:56]** Then has a fully connected layer to connect to 400 units.
**[1:01]** Then now they're fully connected layer and then finally outputs a Y using a softmax unit.
**[1:07]** In order to make the change we'll need to in a second,
**[1:11]** I'm going to change this picture a little bit and instead I'm
**[1:14]** going to view Y as four numbers,
**[1:18]** corresponding to the cause probabilities of
**[1:21]** the four causes that softmax units is classified amongst.
**[1:26]** And the full causes could be pedestrian,
**[1:31]** car, motorcycle, and background or something else.
**[1:35]** Now, what I'd like to do is show how
**[1:38]** these layers can be turned into convolutional layers.
**[1:43]** So, the convnet will draw same as before for the first few layers.
**[1:47]** And now, one way of implementing this next layer,
**[1:51]** this fully connected layer is to implement this as a 5 by 5
**[1:55]** filter and let's use 400 5 by 5 filters.
**[2:02]** So if you take a 5 by 5 by 16 image and convolve it with a 5 by 5 filter, remember,
**[2:08]** a 5 by 5 filter is implemented as 5 by 5 by
**[2:13]** 16 because our convention is that the filter looks across all 16 channels.
**[2:19]** So this 16 and this 16 must match and so the outputs will be 1 by 1.
**[2:25]** And if you have 400 of these 5 by 5 by 16 filters,
**[2:30]** then the output dimension is going to be 1 by 1 by 400.
**[2:36]** So rather than viewing these 400 as just a set of nodes,
**[2:41]** we're going to view this as a 1 by 1 by 400 volume.
**[2:44]** Mathematically, this is the same as a fully connected layer
**[2:50]** because each of these 400 nodes has a filter of dimension 5 by 5 by 16.
**[2:57]** So each of those 400 values is spme
**[2:59]** arbitrary linear function of these 5 by 5 by 16 activations from the previous layer.
**[3:07]** Next, to implement the next convolutional layer,
**[3:10]** we're going to implement a 1 by 1 convolution.
**[3:14]** If you have 400 1 by 1 filters then,
**[3:18]** with 400 filters the next layer will again be 1 by 1 by 400.
**[3:24]** So that gives you this next fully connected layer.
**[3:29]** And then finally, we're going to have another 1 by 1 filter,
**[3:35]** followed by a softmax activation.
**[3:37]** So as to give a 1 by 1 by 4 volume
**[3:40]** to take the place of these four numbers that the network was operating.
**[3:46]** So this shows how you can take these fully connected layers
**[3:50]** and implement them using convolutional layers so
**[3:54]** that these sets of units instead are not implemented
**[3:57]** as 1 by 1 by 400 and 1 by 1 by 4 volumes.
**[4:02]** After this conversion, let's see how you
**[4:06]** can have a convolutional implementation of sliding windows object detection.
**[4:11]** The presentation on this slide is based on the OverFeat paper,
**[4:16]** referenced at the bottom, by Pierre Sermanet,
**[4:18]** David Eigen, Xiang Zhang,
**[4:21]** Michael Mathieu, Robert Fergus and Yann Lecun.
**[4:24]** Let's say that your sliding windows convnet inputs 14 by 14 by 3 images and again,
**[4:31]** I'm just using small numbers like the 14 by 14 image
**[4:35]** in this slide mainly to make the numbers and illustrations simpler.
**[4:40]** So as before, you have a neural network as
**[4:44]** follows that eventually outputs a 1 by 1 by 4 volume,
**[4:49]** which is the output of your softmax.
**[4:52]** Again, to simplify the drawing here,
**[4:54]** 14 by 14 by 3 is technically a volume 5 by 5 or 10 by 10 by 16,
**[5:01]** the second clear volume.
**[5:02]** But to simplify the drawing for this slide,
**[5:04]** I'm just going to draw the front face of this volume.
**[5:07]** So instead of drawing 1 by 1 by 400 volume,
**[5:10]** I'm just going to draw the 1 by 1 cause of all of these.
**[5:14]** So just dropped the three components of these drawings, just for this slide.
**[5:19]** So let's say that your convnet inputs 14 by 14 images or 14 by
**[5:23]** 14 by 3 images and your tested image is 16 by 16 by 3.
**[5:29]** So now added that yellow stripe to the border of this image.
**[5:33]** In the original sliding windows algorithm,
**[5:36]** you might want to input the blue region into
**[5:41]** a convnet and run that once to generate a consecration 01 and then slightly down a bit,
**[5:46]** least he uses a stride of two pixels and then you might slide that to the right by
**[5:54]** two pixels to input
**[5:56]** this green rectangle into the convnet and
**[5:59]** we run the whole convnet and get another label, 01.
**[6:02]** Then you might input
**[6:05]** this orange region into the convnet and run it one more time to get another label.
**[6:12]** And then do it the fourth and final time with this lower right purple square.
**[6:21]** To run sliding windows on this 16 by 16 by 3 image is pretty small image.
**[6:26]** You run this convnet four times in order to get four labels.
**[6:32]** But it turns out a lot of this computation
**[6:34]** done by these four convnets is highly duplicative.
**[6:38]** So what the convolutional implementation of sliding windows does is it allows
**[6:42]** these four pauses in the convnet to share a lot of computation.
**[6:48]** Specifically, here's what you can do.
**[6:49]** You can take the convnet and just run it same parameters,
**[6:54]** the same 5 by 5 filters,
**[6:56]** also 16 5 by 5 filters and run it.
**[7:00]** Now, you can have a 12 by 12 by 16 output volume.
**[7:04]** Then do the max pool, same as before.
**[7:07]** Now you have a 6 by 6 by 16,
**[7:09]** runs through your same 400 5 by 5 filters to get now your 2 by 2 by 40 volume.
**[7:18]** So now instead of a 1 by 1 by 400 volume,
**[7:24]** we have instead a 2 by 2 by 400 volume.
**[7:29]** Run it through a 1 by 1 filter gives
**[7:32]** you another 2 by 2 by 400 instead of 1 by 1 like 400.
**[7:37]** Do that one more time and now you're left with a
**[7:40]** 2 by 2 by 4 output volume instead of 1 by 1 by 4.
**[7:44]** It turns out that this blue 1 by 1 by 4 subset gives
**[7:49]** you the result of running in the upper left hand corner 14 by 14 image.
**[7:54]** This upper right 1 by 1 by 4 volume gives you the upper right result.
**[8:01]** The lower left gives you the results of
**[8:04]** implementing the convnet on the lower left 14 by 14 region.
**[8:08]** And the lower right 1 by 1 by 4 volume gives you the same result
**[8:13]** as running the convnet on the lower right 14 by 14 medium.
**[8:18]** And if you step through all the steps of the calculation,
**[8:20]** let's look at the green example,
**[8:23]** if you had cropped out just this region
**[8:25]** and passed it through the convnet through the convnet on top,
**[8:29]** then the first layer's activations would have been exactly this region.
**[8:34]** The next layer's activation after max pooling would have been
**[8:37]** exactly this region and then the next layer,
**[8:40]** the next layer would have been as follows.
**[8:43]** So what this process does,
**[8:44]** what this convolution implementation does is,
**[8:47]** instead of forcing you to run four propagation
**[8:50]** on four subsets of the input image independently, Instead,
**[8:54]** it combines all four into one form of computation and shares
**[8:58]** a lot of the computation in the regions of image that are common.
**[9:02]** So all four of the 14 by 14 patches we saw here.
**[9:07]** Now let's just go through a bigger example.
**[9:09]** Let's say you now want to run sliding windows on a 28 by 28 by 3 image.
**[9:14]** It turns out If you run four from
**[9:16]** the same way then you end up with an 8 by 8 by 4 output.
**[9:21]** And just go small and surviving sliding windows with that 14 by 14 region.
**[9:27]** And that corresponds to running a sliding windows first on that region thus,
**[9:33]** giving you the output corresponding the upper left hand corner.
**[9:36]** Then using a slider too to shift one window over,
**[9:39]** one window over, one window over and so on and the eight positions.
**[9:43]** So that gives you this first row and then as you go down the image as well,
**[9:48]** that gives you all of these 8 by 8 by 4 outputs.
**[9:53]** Because of the max pooling up too that this corresponds to
**[9:58]** running your neural network with a stride of two on the original image.
**[10:04]** So just to recap,
**[10:05]** to implement sliding windows,
**[10:07]** previously, what you do is you crop out a region.
**[10:11]** Let's say this is 14 by 14
**[10:14]** and run that through your convnet and do that for the next region over,
**[10:18]** then do that for the next 14 by 14 region,
**[10:21]** then the next one, then the next one,
**[10:23]** then the next one, then the next one and so on,
**[10:25]** until hopefully that one recognizes the car.
**[10:29]** But now, instead of doing it sequentially,
**[10:31]** with this convolutional implementation that you saw in the previous slide,
**[10:35]** you can implement the entire image,
**[10:37]** all maybe 28 by 28 and convolutionally make all the predictions at
**[10:42]** the same time by one forward pass through this big convnet
**[10:46]** and hopefully have it recognize the position of the car.
**[10:50]** So that's how you implement sliding windows
**[10:53]** convolutionally and it makes the whole thing much more efficient.
**[10:57]** Now, this algorithm still has one weakness,
**[10:59]** which is the position of the bounding boxes is not going to be too accurate.
**[11:04]** In the next video,
**[11:05]** let's see how you can fix that problem.
