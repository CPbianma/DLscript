---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 2
section: Practical Advice for Using ConvNets
item_title: Using Open-Source Implementation
duration: 5 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/WzFCr/using-open-source-implementation
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Using Open-Source Implementation — Transcript

**[0:01]** You've now learned about several highly effective neural network and
**[0:05]** ConvNet architectures.
**[0:07]** What I want to do in the next few videos is share with you some practical advice on
**[0:12]** how to use them, first starting with using open-source implementations.
**[0:17]** It turns out that a lot of these neural networks are difficult or finicky
**[0:21]** to replicate because a lot of details about tuning of the hyperparameters such
**[0:26]** as learning decay and other things that make some difference to the performance.
**[0:31]** And so I've found that it's sometimes difficult even for,
**[0:34]** say, a higher deep loving PhD students, even at the top universities
**[0:40]** to replicate someone else's polished work just from reading their paper.
**[0:45]** Fortunately, a lot of deep learning researchers
**[0:47]** routinely open-source their work on the Internet, such as on GitHub.
**[0:52]** And as you do work yourself, I certainly encourage you
**[0:55]** to consider contributing back your code to the open-source community.
**[1:00]** But if you see a research paper whose results you would like to build on top of,
**[1:04]** one thing you should consider doing,
**[1:06]** one thing I do quite often it's just look online for an open-source implementation.
**[1:11]** Because if you can get the author's implementation, you can usually get going
**[1:15]** much faster than if you would try to reimplement it from scratch.
**[1:20]** Although sometimes reimplementing from scratch could be a good exercise
**[1:23]** to do as well.
**[1:24]** If you're already familiar with how to use GitHub,
**[1:27]** this video might be less necessary or less important for you.
**[1:32]** But if you aren't used to downloading open-source code from GitHub,
**[1:35]** let me quickly show you how easy it is.
**[1:42]** Let's say you're excited about residual networks, and you want to use it.
**[1:46]** So let's search for ResNet on GitHub.
**[1:50]** And so you actually see a lot of different implementations of ResNets on GitHub.
**[1:55]** And I'm just going to go to the first URL here.
**[1:58]** And this is a GitHub repo that implements ResNets.
**[2:02]** Along with the GitHub webpages if you scroll down we'll have some text
**[2:06]** describing the work or the particular implementation.
**[2:09]** On this particular repo, this particular GitHub
**[2:13]** repository was actually by the original authors of the ResNet paper.
**[2:19]** And this code, this license under an MIT license,
**[2:22]** you can click through to take a look at the implications of this license.
**[2:27]** The MIT License is one of the more permissive or
**[2:29]** one of the more open-source licenses.
**[2:32]** So I'm going to go ahead and download the code, and to do that, click on this link.
**[2:37]** This gives you the URL that you can use to download the code.
**[2:41]** I'm going to click on this button over here to copy the URL to my clipboard and
**[2:45]** then go over here.
**[2:46]** Then all you have to do is type git clone and then Ctrl+V for the URL and hit Enter.
**[2:53]** And so in a couples of seconds it has download,
**[2:55]** has cloned this repository to my local hard disk.
**[2:58]** So let's go into the directory and let's take a look.
**[3:03]** I'm more used in Mac than Windows, but I guess let's see, let's go to prototxt and
**[3:09]** I think this is where it has the files specifying the network.
**[3:15]** So let's take a look at this file, because this is a very long file that specifies
**[3:21]** the detail configurations of the ResNet with a 101 layers, all right?
**[3:28]** And it looks like from what I remember seeing from this webpage,
**[3:32]** this particular implementation uses the Cafe framework.
**[3:39]** But if you wanted implementation of this code using some other
**[3:42]** programming framework, you might be able to find it as well.
**[3:48]** So if you're developing a computer vision application,
**[3:51]** a very common workflow would be to pick an architecture that you like,
**[3:56]** maybe one of the ones you learned about in this course.
**[3:59]** Or maybe one that you heard about from a friend or from some literature.
**[4:03]** And look for an open source implementation and
**[4:06]** download it from GitHub to start building from there.
**[4:09]** One of the advantages of doing so also is that sometimes these networks take
**[4:14]** a long time to train, and someone else might have used multiple GPUs and
**[4:18]** a very large dataset to pretrain some of these networks.
**[4:22]** And that allows you to do transfer learning using these
**[4:25]** networks which we'll discuss in the next video as well.
**[4:28]** Of course, if you're computer vision researcher implementing these things from
**[4:33]** scratch, then your workflow will be different.
**[4:36]** And if you do that,
**[4:37]** then do contribute your work back to the open-source community.
**[4:40]** But because so many vision researchers have done so much work implementing these
**[4:45]** architectures, I found that often starting with open-source implementations
**[4:51]** is a better way, or certainly a faster way to get started on a new project.
