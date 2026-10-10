---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 3
section: Detection Algorithms
item_title: Object Detection
duration: 6 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/VgyWR/object-detection
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Object Detection — Transcript

**[0:00]** You've learned about Object Localization as well as Landmark Detection.
**[0:05]** Now, let's build up to other object detection algorithm.
**[0:09]** In this video, you'll learn how to use a ConvNet to perform
**[0:13]** object detection using something called the Sliding Windows Detection Algorithm.
**[0:18]** Let's say you want to build a car detection algorithm.
**[0:21]** Here's what you can do.
**[0:22]** You can first create a label training set,
**[0:24]** so x and y with closely cropped examples of cars.
**[0:29]** So, this is image x has a positive example, there's a car,
**[0:32]** here's a car, here's a car,
**[0:35]** and then there's not a car, there's not a car.
**[0:37]** And for our purposes in this training set,
**[0:39]** you can start off with the one with the car closely cropped images.
**[0:43]** Meaning that x is pretty much only the car.
**[0:47]** So, you can take a picture and crop out and just
**[0:49]** cut out anything else that's not part of a car.
**[0:52]** So you end up with the car centered in pretty much the entire image.
**[0:57]** Given this label training set,
**[1:01]** you can then train a ConvNet that inputs an image,
**[1:05]** like one of these closely cropped images.
**[1:07]** And then the job of the e is to output y,
**[1:12]** zero or one, is there a car or not.
**[1:15]** Once you've trained up this ConvNet
**[1:17]** you can then use it in Sliding Windows Detection. ConvNet 25 00:01:20,515 --> 00:01:21,870 So the way you do that is,
**[1:21]** if you have a test image like this what you do is you
**[1:25]** start by picking a certain window size, shown down there.
**[1:29]** And then you would input into this ConvNet a small rectangular region.
**[1:35]** So, take just this below red square,
**[1:38]** input that into the ConvNet,
**[1:41]** and have a ConvNet make a prediction.
**[1:43]** And presumably for that little region in the red square,
**[1:47]** it'll say, no that little red square does not contain a car.
**[1:50]** In the Sliding Windows Detection Algorithm,
**[1:52]** what you do is you then pass as input
**[1:56]** a second image now bounded by
**[2:00]** this red square shifted a little bit over and feed that to the ConvNet.
**[2:03]** So, you're feeding just the region of the image
**[2:06]** in the red squares of the ConvNet and run the ConvNet again.
**[2:10]** And then you do that with a third image and so on.
**[2:16]** And you keep going until you've slid the window across every position in the image.
**[2:23]** And I'm using a pretty large stride in this example just to make the animation go faster.
**[2:28]** But the idea is you basically go through every region of this size,
**[2:34]** and pass lots of little cropped images into
**[2:38]** the ConvNet and have it classified zero or one for each position as some stride.
**[2:45]** Now, having done this once
**[2:47]** with running this was called the sliding window through the image.
**[2:54]** You then repeat it,
**[2:55]** but now use a larger window.
**[2:57]** So, now you take a slightly larger region and run that region.
**[3:02]** So, resize this region into whatever input size the ConvNet is expecting,
**[3:06]** and feed that to the ConvNet and have it output zero or one.
**[3:10]** And then slide the window over again using some stride and so on.
**[3:15]** And you run that throughout your entire image until you get to the end.
**[3:20]** And then you might do the third time using even larger windows and so on.
**[3:26]** Right. And the hope is that if you do this,
**[3:29]** then so long as there's a car somewhere in the image that there will be a window where,
**[3:36]** for example if you are passing in this window into the ConvNet,
**[3:40]** hopefully the ConvNet will have outputs one for that input region.
**[3:44]** So then you detect that there is a car there.
**[3:47]** So this algorithm is called Sliding Windows Detection because you take these windows,
**[3:52]** these square boxes, and slide them across the entire image
**[3:58]** and classify every square region with some stride as containing a car or not.
**[4:05]** Now there's a huge disadvantage of Sliding Windows Detection,
**[4:10]** which is the computational cost.
**[4:12]** Because you're cropping out so many different square regions in
**[4:16]** the image and running each of them independently through a ConvNet.
**[4:21]** And if you use a very coarse stride,
**[4:24]** a very big stride, a very big step size,
**[4:26]** then that will reduce the number of windows you need to pass through the ConvNet,
**[4:31]** but that courser granularity may hurt performance.
**[4:35]** Whereas if you use a very fine granularity or a very small stride,
**[4:39]** then the huge number of all these little regions you're
**[4:44]** passing through the ConvNet means that means there is a very high computational cost.
**[4:48]** So, before the rise of Neural Networks people used to use much simpler classifiers like
**[4:54]** a simple linear classifier over hand
**[4:56]** engineer features in order to perform object detection.
**[5:00]** And in that era because each classifier was relatively cheap to compute,
**[5:04]** it was just a linear function,
**[5:06]** Sliding Windows Detection ran okay.
**[5:08]** It was not a bad method,
**[5:10]** but with ConvNet now running a single classification task is much
**[5:15]** more expensive and sliding windows this way is infeasibily slow.
**[5:21]** And unless you use a very fine granularity or a very small stride,
**[5:26]** you end up not able to localize the objects that accurately within the image as well.
**[5:32]** Fortunately however, this problem of computational cost has a pretty good solution.
**[5:38]** In particular, the Sliding Windows Object Detector
**[5:41]** can be implemented convolutionally or much more efficiently.
**[5:45]** Let's see in the next video how you can do that.
