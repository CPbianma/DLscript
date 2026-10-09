---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 2
section: Case Studies
item_title: Why look at case studies?
duration: 3 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/KvAM9/why-look-at-case-studies
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Why look at case studies? — Transcript

**[0:00]** Hello. Welcome back. This week,
**[0:02]** the first thing we'll do is show you a number of
**[0:04]** case studies of effective convolutional neural networks.
**[0:08]** Why look at case studies?
**[0:10]** Last week we learned about the basic building blocks,
**[0:12]** such as convolutional layers, pooling layers,
**[0:14]** and fully connected layers of convnet.
**[0:16]** It turns out the past few years
**[0:19]** of computer vision research has been on how to
**[0:21]** put together these basic building blocks to
**[0:23]** form effective convolutional neural networks.
**[0:26]** One of the best ways for user gain intuition
**[0:29]** yourself is to see some of these examples.
**[0:31]** I think just as many of you may have learned
**[0:34]** to write code by reading other people's codes,
**[0:37]** I think that a good way to gain
**[0:38]** intuition and how the build confidence is
**[0:41]** to read or to see other examples of effective confidence.
**[0:45]** It turns out that a
**[0:48]** neural network architecture that works
**[0:50]** well on one computer vision tasks
**[0:51]** often works well on other tasks as well,
**[0:54]** such as maybe on your task.
**[0:55]** If someone else's train
**[0:57]** a neural network or has
**[0:58]** figured out a neural network architecture,
**[1:00]** there's very good at recognizing
**[1:02]** cats and dogs and people.
**[1:03]** But you have a different computer vision tasks like
**[1:05]** maybe you're trying to build a self-driving car,
**[1:07]** you might well be able to take
**[1:08]** someone else's neural network architecture
**[1:10]** and apply that to your problem.
**[1:13]** Finally, after the next few videos,
**[1:16]** you'll be able to read some of
**[1:18]** the research papers from the field of computer vision,
**[1:20]** and I hope that you might find it satisfying as well.
**[1:24]** You don't have to do this as class
**[1:26]** where you might find it satisfying,
**[1:27]** typically read some of
**[1:29]** these several computer vision research paper
**[1:31]** and see yourself able to understand them.
**[1:34]** With that, let's get started.
**[1:36]** As an outline for what we'll do in the next few videos,
**[1:39]** we'll first show you a few classic networks.
**[1:43]** LeNet-5 network which came from, I guess,
**[1:46]** in 1980s, AlexNet which
**[1:49]** is often cited in the VGG network.
**[1:52]** These are examples of pretty effective neural networks,
**[1:56]** and you see ideas from these papers that will
**[1:58]** probably be useful for your own work as well.
**[2:01]** Then I want to show you
**[2:03]** the ResNet or called residual network.
**[2:06]** You might have heard that neural networks
**[2:08]** and getting deeper and deeper,
**[2:10]** the ResNet neural network trained
**[2:13]** a very deep 152 layer neural network.
**[2:16]** It has some very interesting tricks,
**[2:18]** interesting ideas how they do that effectively.
**[2:21]** Then finally, you also
**[2:23]** see a case study of the Inception neural network.
**[2:27]** After seeing these neural networks,
**[2:29]** I think you have much better intuition
**[2:32]** about how to build
**[2:33]** effective convolutional neural networks.
**[2:36]** Even if you end up not working computer vision yourself,
**[2:39]** you find a lot of the ideas from some of these examples,
**[2:42]** such as ResNet, Inception network,
**[2:44]** many of these ideas are cross fertilizing,
**[2:46]** are making their way into other disciplines.
**[2:49]** Even if you don't end up building
**[2:51]** computer vision applications yourself,
**[2:52]** I think you'll find some of these ideas
**[2:54]** very interesting and helpful for your work.
