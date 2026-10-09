---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 1
section: Convolutional Neural Networks
item_title: Convolutions Over Volume
duration: 11 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/ctQZz/convolutions-over-volume
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Convolutions Over Volume — Transcript

**[0:01]** You've seen how convolutions over 2D images works.
**[0:05]** Now, let's see how you can implement convolutions over,
**[0:08]** not just 2D images,
**[0:10]** but over three dimensional volumes.
**[0:13]** Let's start with an example,
**[0:15]** let's say you want to detect features,
**[0:17]** not just in a great scale image,
**[0:20]** but in a RGB image.
**[0:22]** So, an RGB image might be instead of a six by six image,
**[0:27]** it could be six by six by three,
**[0:29]** where the three here responds to the three color channels.
**[0:32]** So, you think of this as a stack of three six by six images.
**[0:37]** In order to detect edges or some other feature in this image,
**[0:41]** you can vault this,
**[0:43]** not with a three by three filter,
**[0:47]** as we have previously,
**[0:49]** but now with also with a 3D filter,
**[0:51]** that's going to be three by three by three.
**[0:54]** So the filter itself will also have three layers corresponding to the red,
**[1:01]** green, and blue channels.
**[1:04]** So to give these things some names,
**[1:07]** this first six here,
**[1:08]** that's the height of the image,
**[1:12]** that's the width, and this three is the number of channels.
**[1:19]** And your filter also similarly has a height,
**[1:24]** a width, and the number of channels.
**[1:27]** And the number of channels in
**[1:31]** your image must match the number of channels in your filter,
**[1:35]** so these two numbers have to be equal.
**[1:38]** We'll see on the next slide how this convolution operation actually works,
**[1:42]** but the output of this will be a four by four image.
**[1:46]** And notice this is four by four by one,
**[1:49]** there's no longer a three at the end.
**[1:53]** Let's go through in detail how this works but let's use a more nicely drawn image.
**[2:01]** So here's the six by six by three image,
**[2:05]** and here's a three by three by three filter,
**[2:10]** and this last number,
**[2:11]** the number of channels matches the 3D image and the filter.
**[2:17]** So to simplify the drawing of this three by three by three filter,
**[2:22]** instead of joining it is a stack of the matrices, I'm also going to,
**[2:26]** sometimes, just draw it as this three dimensional cube, like that.
**[2:32]** So to compute the output of this convolutional operation,
**[2:37]** what you would do is take the three by three by three filter and first,
**[2:42]** place it in that upper left most position.
**[2:45]** So, notice that this three by three by three filter has 27 numbers,
**[2:51]** or 27 parameters, that's three cubes.
**[2:53]** And so, what you do is take each of these
**[2:56]** 27 numbers and multiply them with the corresponding numbers from the red,
**[3:05]** green, and blue channels of the image,
**[3:07]** so take the first nine numbers from red channel,
**[3:09]** then the three beneath it to the green channel,
**[3:12]** then the three beneath it to the blue channel,
**[3:13]** and multiply it with the corresponding 27 numbers
**[3:17]** that gets covered by this yellow cube show on the left.
**[3:22]** Then add up all those numbers and this gives you this first number in the output,
**[3:28]** and then to compute the next output you take this cube and slide it over by one,
**[3:34]** and again, due to 27 multiplications,
**[3:38]** add up the 27 numbers,
**[3:40]** that gives you this next output,
**[3:42]** do it for the next number over,
**[3:44]** for the next position over,
**[3:45]** that gives the third output and so on.
**[3:49]** That gives you the forth and then one row down and then the next one,
**[3:54]** to the next one, to the next one,
**[3:55]** and so on, you get the idea,
**[3:58]** until at the very end,
**[4:02]** that's the position you'll have for that final output.
**[4:09]** So, what does this allow you to do?
**[4:10]** Well, here's an example,
**[4:12]** this filter is three by three by three.
**[4:15]** So, if you want to detect edges in the red channel of the image,
**[4:20]** then you could have the first filter, the one, one, one, one is one,
**[4:24]** one is one, one is one as usual,
**[4:27]** and have the green channel be all zeros,
**[4:31]** and have the blue filter be all zeros.
**[4:35]** And if you have these three stock together to form your three by three by three filter,
**[4:42]** then this would be a filter that detect edges,
**[4:46]** vertical edges but only in the red channel.
**[4:49]** Alternatively, if you don't care what color the vertical edge is in,
**[4:54]** then you might have a filter that's like this,
**[4:58]** whereas this one, one, one, minus one,
**[5:01]** minus one, minus one,
**[5:02]** in all three channels.
**[5:04]** So, by setting this second alternative, set the parameters,
**[5:08]** you then have a edge detector,
**[5:10]** a three by three by three edge detector,
**[5:12]** that detects edges in any color.
**[5:15]** And with different choices of these parameters you can get
**[5:19]** different feature detectors out of this three by three by three filter.
**[5:24]** And by convention, in computer vision,
**[5:27]** when you have an input with a certain height, a certain width,
**[5:31]** and a certain number of channels, then
**[5:33]** your filter will have a potential different height,
**[5:36]** different width, but the same number of channels.
**[5:39]** And in theory it's possible to have a filter that maybe only looks at the red channel
**[5:44]** or maybe a filter looks at only the green channel and a blue channel.
**[5:50]** And once again, you notice th\t convolving a volume,
**[5:54]** a six by six by three convolve with a three by three by three,
**[6:00]** that gives a four by four, a 2D output.
**[6:07]** Now that you know how to convolve on volumes,
**[6:10]** there is one last idea that will be crucial for building convolutional neural networks,
**[6:17]** which is what if we don't just wanted to detect vertical edges?
**[6:20]** What if we wanted to detect vertical edges and horizontal edges
**[6:23]** and maybe 45 degree edges and maybe 70 degree edges as well,
**[6:27]** but in other words, what if you want to use multiple filters at the same time?
**[6:32]** So, here's the picture we had from the previous slide,
**[6:35]** we had six by six by three convolved with the three by three by three,
**[6:38]** gets four by four,
**[6:39]** and maybe this is a vertical edge detector,
**[6:42]** or maybe it's run to detect some other feature.
**[6:46]** Now, maybe a second filter may be denoted by this orange-ish color,
**[6:52]** which could be a horizontal edge detector.
**[7:00]** So, maybe convolving it with the first filter gives you this first four by four output
**[7:05]** and convolving with the second filter gives you a different four by four output.
**[7:13]** And what we can do is then take these two four by four outputs,
**[7:16]** take this first one within the front, and you
**[7:20]** can take this second filter output and well, let me draw it here,
**[7:25]** put it at back as follows,
**[7:27]** so that by stacking these two together,
**[7:29]** you end up with a four by four by two output volume, right?
**[7:35]** And you can think of the volume as if we draw this is a box,
**[7:39]** I guess it would look like this.
**[7:41]** So this would be a four by four by two output volume,
**[7:45]** which is the result of taking your six by six by three image and
**[7:49]** convolving it or applying two different three by three filters to it,
**[7:54]** resulting in two four by four outputs that then gets
**[7:57]** stacked up to form a four by four by two volume.
**[8:02]** And the two here comes from the fact that we used two different filters.
**[8:07]** So, let's just summarize the dimensions,
**[8:14]** if you have a n by n by number of channels input image,
**[8:19]** so an example, there's a six by six by three,
**[8:22]** where n subscript C is the number of channels,
**[8:26]** and you convolve that with a f by f by, and again,
**[8:31]** this should be the same nC, so this was,
**[8:34]** three by three by three,
**[8:38]** and by convention this and this have to be the same number.
**[8:45]** Then, what you get is n minus f plus one
**[8:52]** by n minus f plus one by and you want to use this nC prime,
**[8:59]** or its really nC of the next layer,
**[9:02]** but this is the number of filters that you use.
**[9:06]** So this in our example would be be four by four by two.
**[9:11]** And I wrote this assuming that you use a stride of one and no padding.
**[9:16]** But if you used a different stride of padding
**[9:19]** than this n minus F plus one would be affected in a usual way,
**[9:22]** as we see in the previous videos.
**[9:26]** So this idea of convolution on volumes,
**[9:29]** turns out to be really powerful.
**[9:31]** Only a small part of it is that you can now operate
**[9:34]** directly on RGB images with three channels.
**[9:38]** But even more important is that
**[9:40]** you can now detect two features, like vertical, horizontal edges,
**[9:44]** or 10, or maybe a 128,
**[9:46]** or maybe several hundreds of different features.
**[9:49]** And the output will then have a number
**[9:53]** of channels equal to the number of filters you are detecting.
**[9:58]** And as a note of notation,
**[10:00]** I've been using your number of channels to denote this last dimension in the literature,
**[10:07]** people will also often call this the depth of this 3D volume and both notations,
**[10:14]** channels or depth, are commonly used in the literature.
**[10:17]** But they find depth more confusing
**[10:19]** because you usually talk about the depth of the neural network as well,
**[10:22]** so I'm going to use the term channels in these videos to refer
**[10:26]** to the size of this third dimension of these filters.
**[10:31]** So now that you know how to implement convolutions over volumes,
**[10:36]** you now are ready to implement one layer of the convolutional neural network.
**[10:41]** Let's see how to do that in the next video.
