---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 3
section: Detection Algorithms
item_title: U-Net Architecture Intuition
duration: 3 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/Vw8sl/u-net-architecture-intuition
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# U-Net Architecture Intuition — Transcript

**[0:02]** Armed of the transfers convolution,
**[0:04]** you're now ready to dive into the details of the unit architecture.
**[0:08]** In this video, let's first go over the architecture quickly to
**[0:12]** build intuition about how the unit works.
**[0:15]** And in the next video, we'll go through the details together.
**[0:19]** Let's dig in.
**[0:20]** Here's a rough diagram of the neural network architecture
**[0:26]** for semantic segmentation.
**[0:28]** And so we use normal convolutions for the first part of the neural network.
**[0:34]** And similar to the earlier neural networks that you've seen.
**[0:37]** This part of the neural network will sort of compress the image.
**[0:41]** You've gone from a very large image to one where the heightened whiff
**[0:46]** of this activation is much smaller.
**[0:48]** So you've lost a lot of spatial information because the dimension is much
**[0:53]** smaller, but it's much deeper.
**[0:55]** So, for example, this middle layer may represent that looks like
**[0:59]** there's a cat roughly in the lower right hand portion of the image.
**[1:04]** But the detailed spatial information is lost because
**[1:07]** of heightened with is much smaller.
**[1:09]** Then the second half of this neural network uses the transports convolution
**[1:14]** to blow the representation size up back to the size of the original input image.
**[1:20]** Now it turns out that there's one modification to this architecture that
**[1:24]** would make it work much better.
**[1:25]** And that's what we turn this into the unit architecture, which is
**[1:31]** that skip connections from the earlier layers to the later layers like this.
**[1:37]** So that this earlier block of activations is copied directly to this later block.
**[1:44]** So why do we want to do this?
**[1:46]** It turns out that for this, next final layer to decide which region is a cat.
**[1:53]** Two types of information are useful.
**[1:55]** One is the high level, spatial,
**[1:59]** high level contextual information which it gets from this previous layer.
**[2:03]** Where hopefully the neural network,
**[2:05]** we have figured out that in the lower right hand corner of the image or
**[2:10]** maybe in the right part of the image, there's some cat like stuff going on.
**[2:14]** But what is missing is a very detailed, fine grained spatial information.
**[2:20]** Because this set of activations here has lower spatial
**[2:24]** resolution to heighten with is just lower.
**[2:28]** So what the skip connection does is it allows the neural network to take this
**[2:33]** very high resolution, low level feature information where it could capture for
**[2:39]** every pixel position, how much fairy stuff is there in this pixel?
**[2:44]** And used to skip connection to pause that directly to this later layer.
**[2:48]** And so this way this layer has both the lower resolution, but high level,
**[2:54]** spatial, high level contextual information, as well as the low level.
**[3:00]** But more detailed texture like information in order to make
**[3:05]** a decision as to whether a certain pixel is part of a cat or not.
**[3:10]** In this video, you saw just a brief, high level intuition about how unit works.
**[3:16]** Let's go on to the next video to see the details of how you can implement it.
