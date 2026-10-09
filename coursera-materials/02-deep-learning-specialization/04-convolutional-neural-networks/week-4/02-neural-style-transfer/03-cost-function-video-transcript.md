---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 4
section: Neural Style Transfer
item_title: Cost Function
duration: 4 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/jOnEU/cost-function
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Cost Function — Transcript

**[0:00]** To build a Neural Style Transfer system,
**[0:02]** let's define a cost function for the generated image.
**[0:05]** What you see later is that by minimizing this cost function,
**[0:09]** you can generate the image that you want.
**[0:12]** Remember what the problem formulation is.
**[0:15]** You're given a content image C,
**[0:17]** given a style image S and you goal is to generate a new image
**[0:21]** G. In order to implement neural style transfer,
**[0:26]** what you're going to do is define a cost function J of G that measures how good is
**[0:34]** a particular generated image and we'll use gradient
**[0:37]** descent to minimize J of G in order to generate this image.
**[0:42]** How good is a particular image?
**[0:44]** Well, we're going to define two parts to this cost function.
**[0:48]** The first part is called the content cost.
**[0:52]** This is a function of the content image and of the generated image and
**[0:56]** what it does is it measures how similar is the contents of the generated image
**[1:00]** to the content of the content image C. And then going to
**[1:05]** add that to a style cost function which is now a function of
**[1:10]** (S,G) and what this does is it measures how similar is
**[1:14]** the style of the image G to the style of the image S. Finally,
**[1:20]** we'll weight these with two hyper parameters alpha and beta to
**[1:24]** specify the relative weighting between the content costs and the style cost.
**[1:29]** It seems redundant to use two different hyper parameters to specify
**[1:33]** the relative cost of the weighting.
**[1:44]** One hyper parameter seems like it would be enough but
**[1:47]** the original authors of the Neural Style Transfer Algorithm,
**[1:50]** use two different hyper parameters.
**[1:52]** I'm just going to follow their convention here.
**[1:55]** The Neural Style Transfer Algorithm I'm
**[1:57]** going to present in the next few videos is due to Leon Gatys,
**[2:01]** Alexander Ecker and Matthias.
**[2:04]** Their papers is not too hard to read so after watching these few videos if you wish,
**[2:09]** I certainly encourage you to take a look at their paper as well if you want.
**[2:14]** The way the algorithm would run is as follows,
**[2:17]** having to find the cost function J of G in
**[2:21]** order to actually generate a new image what you do is the following.
**[2:25]** You would initialize the generated image
**[2:29]** G randomly so it might be 100 by 100 by 3 or 500 by 500 by
**[2:30]** 3 or whatever dimension you want it to be.
**[2:37]** Then we'll define the cost function J of G on the previous slide.
**[2:41]** What you can do is use gradient descent to minimize this so you can update G as
**[2:47]** G minus the derivative respect to the cost function of J of G. In this process,
**[2:54]** you're actually updating the pixel values of this image G which is
**[2:58]** a 100 by 100 by 3 maybe rgb channel image.
**[3:04]** Here's an example, let's say you start with this content image and this style image.
**[3:10]** This is a another probably Picasso image.
**[3:13]** Then when you initialize G randomly,
**[3:15]** you're initial randomly generated image is
**[3:18]** just this white noise image with each pixel value chosen at random.
**[3:24]** As you run gradient descent,
**[3:25]** you minimize the cost function J of G slowly through the pixel value so then you get
**[3:32]** slowly an image that looks more and more like
**[3:36]** your content image rendered in the style of your style image.
**[3:40]** In this video, you saw the overall outline of
**[3:44]** the Neural Style Transfer Algorithm where you define
**[3:47]** a cost function for the generated image G and minimize it.
**[3:51]** Next, we need to see how to define
**[3:53]** the content cost function as well as the style cost function.
**[3:57]** Let's take a look at that starting in the next video.
