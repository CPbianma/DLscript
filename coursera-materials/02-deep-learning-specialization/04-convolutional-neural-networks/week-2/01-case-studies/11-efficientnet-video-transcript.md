---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 2
section: Case Studies
item_title: EfficientNet
duration: 4 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/ZmOWP/efficientnet
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# EfficientNet — Transcript

**[0:02]** MobileNet V1 and V2 gave you
**[0:05]** a way to implement a neural network,
**[0:08]** that is more computationally efficient.
**[0:10]** But is there a way to tune MobileNet,
**[0:13]** or some other architecture,
**[0:15]** to your specific device?
**[0:17]** Maybe you're implementing a computer vision algorithm for
**[0:21]** different brands of mobile phones with
**[0:23]** different amounts of compute resources,
**[0:25]** or for different edge devices.
**[0:27]** If you have a little bit more computation,
**[0:29]** maybe you have a slightly bigger neural network
**[0:31]** and hopefully you get a bit more accuracy,
**[0:33]** or if you are more computationally constraint,
**[0:36]** maybe you want a slightly smaller neural network
**[0:39]** that runs a bit faster,
**[0:40]** at the cost of a little bit of accuracy.
**[0:42]** How can you automatically scale up or
**[0:45]** down neural networks for a particular device?
**[0:48]** EfficientNet, gives you a way to do so.
**[0:51]** Let's say you have
**[0:53]** a baseline neural network architecture,
**[0:56]** where the input image has a certain resolution r,
**[0:59]** and your new network has a certain depth,
**[1:03]** and the layers has a certain width.
**[1:07]** The authors of the EfficientNet paper,
**[1:10]** Mingxing Tan and my former PhD student, Quoc Le,
**[1:13]** observed that the three things you
**[1:16]** could do to scale things up or down,
**[1:18]** are, you could use a high resolution image.
**[1:21]** So a new image resolution
**[1:24]** r. I don't know
**[1:27]** how to denote a high resolution in a video like this.
**[1:30]** I'm using this blue glow here to denote,
**[1:33]** maybe high resolution image.
**[1:35]** Or you could make this network much deeper.
**[1:39]** You could vary d to depth of the neural network,
**[1:45]** or you can make the layers wider.
**[1:49]** You can also vary the width of these layers.
**[1:55]** The question is, given a particular computational budget,
**[2:00]** what's the good choice of r, d, and w?
**[2:04]** Or depending on the computational resources you have,
**[2:08]** you can also use compound scaling,
**[2:10]** where you might simultaneously scale up or
**[2:13]** simultaneously scale down the resolution of the image,
**[2:17]** and the depth, and the width of the neural network.
**[2:19]** Now the tricky part is,
**[2:21]** if you want to scale up r, d,
**[2:24]** and w, what's the rate at
**[2:26]** which you should scale up each of these?
**[2:28]** Should you double the resolution
**[2:29]** and leave depth with the same,
**[2:30]** or maybe you should double the depth,
**[2:33]** but leave the others the same,
**[2:34]** or increase resolution by 10 percent,
**[2:36]** increase depth by 50 percent,
**[2:37]** and width by 20 percent?
**[2:39]** What's the best trade-off between r, d, and w,
**[2:43]** to scale up or down your neural network,
**[2:46]** to get the best possible performance
**[2:48]** within your computational budget?
**[2:50]** If you are ever looking to adapt
**[2:52]** a neural network architecture for a particular device,
**[2:56]** look at one of the open
**[2:57]** source implementations of EfficientNet,
**[2:59]** which will help you to choose a good trade-off between r,
**[3:03]** d, and w. That's it.
**[3:06]** With MobileNet, you've learned how to build more
**[3:08]** computationally efficient layers, and with EfficientNet,
**[3:12]** you can also find a way to scale up or down
**[3:16]** these neural networks based on
**[3:18]** the resources of a device you may be working on.
**[3:21]** With this, I hope you have the skills
**[3:24]** needed in order to build neural networks for
**[3:27]** mobile devices and for embedded devices and for
**[3:30]** other devices where the computation
**[3:32]** in a memory maybe more limited.
**[3:34]** I hope this will open up a lot of
**[3:36]** possible applications that you may now be able to build.
