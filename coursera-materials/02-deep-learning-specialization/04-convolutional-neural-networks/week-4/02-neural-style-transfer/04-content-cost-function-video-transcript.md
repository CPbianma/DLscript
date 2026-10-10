---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 4
section: Neural Style Transfer
item_title: Content Cost Function
duration: 4 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/CvHv6/content-cost-function
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Content Cost Function — Transcript

**[0:00]** The cost function of the neural style transfer algorithm had
**[0:03]** a content cost component and a style cost component.
**[0:07]** Let's start by defining the content cost component.
**[0:11]** Remember that this is the overall cost function of the neural style transfer algorithm.
**[0:17]** So, let's figure out what should the content cost function be.
**[0:21]** Let's say that you use hidden layer l to compute the content cost.
**[0:26]** If l is a very small number, if you use hidden layer one,
**[0:30]** then it will really force your generated image
**[0:34]** to pixel values very similar to your content image.
**[0:37]** Whereas, if you use a very deep layer,
**[0:39]** then it's just asking, "Well,
**[0:41]** if there is a dog in your content image,
**[0:43]** then make sure there is a dog somewhere in your generated image. "
**[0:46]** So in practice, layer l chosen somewhere in between.
**[0:50]** It's neither too shallow nor too deep in the neural network.
**[0:53]** And because you plan this yourself,
**[0:55]** in the problem exercise that you did at the end of this week,
**[0:58]** I'll leave you to gain some intuitions with
**[1:01]** the concrete examples in the problem exercise as well.
**[1:04]** But usually, I was chosen to be somewhere
**[1:06]** in the middle of the layers of the neural network,
**[1:09]** neither too shallow nor too deep.
**[1:12]** What you can do is then use a pre-trained ConvNet,
**[1:15]** maybe a VGG network,
**[1:17]** or could be some other neural network as well.
**[1:20]** And now, you want to measure,
**[1:22]** given a content image and given a generated image,
**[1:26]** how similar are they in content.
**[1:29]** So let's let this
**[1:31]** a_superscript_[l](c) and this be the activations of layer l on these two images,
**[1:39]** on the images C and G.
**[1:42]** So, if these two activations are similar,
**[1:47]** then that would seem to imply that both images have similar content.
**[1:52]** So, what we'll do is define
**[1:54]** J_content(C,G) as just how
**[2:01]** soon or how different are these two activations.
**[2:05]** So, we'll take the element-wise difference between
**[2:08]** these hidden unit activations in layer l,
**[2:12]** between when you pass in the content image compared
**[2:14]** to when you pass in the generated image,
**[2:17]** and take that squared.
**[2:19]** And you could have a normalization constant in front or not,
**[2:23]** so it's just one of the two or something else.
**[2:25]** It doesn't really matter since this can be adjusted as well by this hyperparameter alpha.
**[2:35]** So, just be clear
**[2:37]** on using this notation as if both of these have been unrolled into vectors,
**[2:42]** so then, this becomes the square root of the l_2 norm between this and this,
**[2:47]** after you've unrolled them both into vectors.
**[2:51]** There's really just the element-wise sum of
**[2:54]** squared differences between these two activation.
**[2:59]** But it's really just the element-wise sum of
**[3:03]** squares of differences between the activations in layer l,
**[3:06]** between the images in C and G. And so,
**[3:11]** when later you perform gradient descent on J_of_G to try to find a value of G,
**[3:17]** so that the overall cost is low,
**[3:19]** this will incentivize the algorithm to find an image G,
**[3:23]** so that these hidden layer activations are similar to what you got for the content image.
**[3:29]** So, that's how you define the content cost function for the neural style transfer.
**[3:33]** Next, let's move on to the style cost function.
