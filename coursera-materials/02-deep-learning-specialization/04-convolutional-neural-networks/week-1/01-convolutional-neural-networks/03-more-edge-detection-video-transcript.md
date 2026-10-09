---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 1
section: Convolutional Neural Networks
item_title: More Edge Detection
duration: 8 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/8Donz/more-edge-detection
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# More Edge Detection — Transcript

**[0:02]** You've seen how the convolution operation allows you to implement a vertical
**[0:06]** edge detector.
**[0:07]** In this video, you'll learn the difference between positive and negative edges, that
**[0:12]** is, the difference between light to dark versus dark to light edge transitions.
**[0:16]** And you'll also see other types of edge detectors,
**[0:19]** as well as how to have an algorithm learn,
**[0:21]** rather than have us hand code an edge detector as we've been doing so far.
**[0:26]** So let's get started.
**[0:31]** Here's the example you saw from the previous video, where you have this image,
**[0:36]** six by six, there's light on the left and dark on the right,
**[0:39]** and convolving it with the vertical edge detection filter results in detecting
**[0:43]** the vertical edge down the middle of the image.
**[0:47]** What happens in an image where the colors are flipped,
**[0:51]** where it is darker on the left and brighter on the right?
**[0:55]** So the 10s are now on the right half of the image and the 0s on the left.
**[0:59]** If you convolve it with the same edge detection filter,
**[1:03]** you end up with negative 30s, instead of 30 down the middle, and
**[1:07]** you can plot that as a picture that maybe looks like that.
**[1:12]** So because the shade of the transitions is reversed,
**[1:15]** the 30s now gets reversed as well.
**[1:18]** And the negative 30s
**[1:21]** shows that this is a dark to light rather than a light to dark transition.
**[1:26]** And if you don't care which of these two cases it is,
**[1:30]** you could take absolute values of this output matrix.
**[1:34]** But this particular filter does make a difference between the light to dark
**[1:39]** versus the dark to light edges.
**[1:42]** Let's see some more examples of edge detection.
**[1:45]** This three by three filter we've seen allows you to detect vertical edges.
**[1:49]** So maybe it should not surprise you too much that this
**[1:53]** three by three filter will allow you to detect horizontal edges.
**[1:58]** So as a reminder, a vertical edge according to this filter, is a three by
**[2:02]** three region where the pixels are relatively bright on the left part and
**[2:06]** relatively dark on the right part.
**[2:08]** So similarly, a horizontal edge would be a three by three region where the pixels
**[2:13]** are relatively bright on top and relatively dark in the bottom row.
**[2:18]** So here's one example, this is a more complex one,
**[2:22]** where you have here 10s in the upper left and lower right-hand corners.
**[2:27]** So if you draw this as an image, this would be an image which is going to be
**[2:32]** darker where there are 0s, so I'm going to shade in the darker regions, and
**[2:37]** then lighter in the upper left and lower right-hand corners.
**[2:41]** And if you convolve this with a horizontal edge detector, you end up with this.
**[2:48]** And so just to take a couple of examples,
**[2:51]** this 30 here corresponds to this three by three region,
**[2:55]** where indeed there are bright pixels on top and darker pixels on the bottom.
**[3:01]** It's kind of over here.
**[3:04]** And so it finds a strong positive edge there.
**[3:08]** And this -30 here corresponds to this region,
**[3:12]** which is actually brighter on the bottom and darker on top.
**[3:16]** So that is a negative edge in this example.
**[3:21]** And again, this is kind of an artifact of the fact that we're working
**[3:26]** with relatively small images, that this is just a six by six image.
**[3:31]** But these intermediate values, like this -10, for
**[3:34]** example, just reflects the fact that that filter here, it captures part
**[3:39]** of the positive edge on the left and part of the negative edge on the right, and
**[3:44]** so blending those together gives you some intermediate value.
**[3:47]** But if this was a very large,
**[3:49]** say a thousand by a thousand image with this type of checkerboard pattern,
**[3:54]** then you won't see these transitions regions of the 10s.
**[3:58]** The intermediate values would be quite small relative to the size of the image.
**[4:02]** So in summary, different filters allow you to find vertical and horizontal edges.
**[4:10]** It turns out that the three by three vertical edge detection filter
**[4:15]** we've used is just one possible choice.
**[4:17]** And historically, in the computer vision literature,
**[4:20]** there was a fair amount of debate about what is the best set of numbers to use.
**[4:24]** So here's something else you could use, which is maybe 1, 2,
**[4:29]** 1, 0, 0, 0, -1, -2, -1.
**[4:32]** This is called a Sobel filter.
**[4:35]** And the advantage of this is it puts a little bit more weight to the central row,
**[4:40]** the central pixel, and this makes it maybe a little bit more robust.
**[4:46]** But computer vision researchers will use other sets of numbers as well,
**[4:50]** like maybe instead of a 1, 2, 1, it should be a 3, 10, 3, right?
**[4:54]** And then -3, -10, -3.
**[4:59]** And this is called a Scharr filter.
**[5:01]** And this has yet other slightly different properties.
**[5:06]** And this is just for vertical edge detection.
**[5:10]** And if you flip it 90 degrees, you get horizontal edge detection.
**[5:13]** And with the rise of deep learning, one of the things we learned is that when
**[5:18]** you really want to detect edges in some complicated image, maybe you don't
**[5:23]** need to have computer vision researchers handpick these nine numbers.
**[5:29]** Maybe you can just learn them and treat the nine numbers of this matrix
**[5:33]** as parameters, which you can then learn using back propagation.
**[5:37]** And the goal is to learn nine parameters so that when you take the image,
**[5:42]** the six by six image, and convolve it with your three by three filter,
**[5:46]** that this gives you a good edge detector.
**[5:50]** And what you see in later videos is that by just treating these nine numbers as
**[5:54]** parameters, the backprop can choose to learn 1, 1, 1, 0, 0, 0,
**[5:59]** -1,-1, if it wants, or learn the Sobel filter or learn the Scharr filter,
**[6:04]** or more likely learn something else that's even better at
**[6:08]** capturing the statistics of your data than any of these hand coded filters.
**[6:13]** And rather than just vertical and horizontal edges,
**[6:17]** maybe it can learn to detect edges that are at 45 degrees or
**[6:21]** 70 degrees or 73 degrees or at whatever orientation it chooses.
**[6:26]** And so by just letting all of these numbers be parameters and learning them
**[6:30]** automatically from data, we find that neural networks can actually learn low
**[6:35]** level features, can learn features such as edges, even more robustly than
**[6:39]** computer vision researchers are generally able to code up these things by hand.
**[6:45]** But underlying all these computations is still this convolution operation,
**[6:51]** Which allows back propagation to learn whatever three by three filter it wants
**[6:56]** and then to apply it throughout the entire image, at this position, at this position,
**[7:02]** at this position, in order to output whatever feature it's trying to detect.
**[7:08]** Be it vertical edges, horizontal edges, or edges at some other angle or
**[7:13]** even some other filter that we might not even have a name for in English.
**[7:19]** So the idea you can treat these nine numbers as parameters to be
**[7:22]** learned has been one of the most powerful ideas in computer vision.
**[7:26]** And later in this course, later this week, we'll actually talk about the details of
**[7:31]** how you actually go about using back propagation to learn these nine numbers.
**[7:36]** But first, let's talk about some other details, some other variations,
**[7:39]** on the basic convolution operation.
**[7:41]** In the next two videos, I want to discuss with you how to use padding as well as
**[7:46]** different strides for convolutions.
**[7:48]** And these two will become important pieces of this convolutional building block of
**[7:52]** convolutional neural networks.
**[7:55]** So let's go on to the next video.
