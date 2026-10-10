---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 2
section: Case Studies
item_title: Networks in Networks and 1x1 Convolutions
duration: 6 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/ZTb8x/networks-in-networks-and-1x1-convolutions
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Networks in Networks and 1x1 Convolutions — Transcript

**[0:00]** In terms of designing content architectures,
**[0:03]** one of the ideas that really help is
**[0:05]** using a one-by-one convolution.
**[0:08]** Now, you might be wondering,
**[0:10]** what does a one-by-one convolution do?
**[0:12]** Isn't that just multiplying by numbers.
**[0:15]** That seems like a funny thing to do.
**[0:16]** Turns out it's not quite like that.
**[0:18]** Let's take a look. Here's a one-by-one filter.
**[0:22]** I put a number 2 there.
**[0:24]** If you take this six-by-six image,
**[0:27]** six by six by one,
**[0:28]** and convolve it with this one-by-one-by-one filter,
**[0:31]** you end up just taking the emission multiplied by two.
**[0:33]** So 1, 2, 3 ends up being 2,
**[0:37]** 4, 6, and so on.
**[0:40]** A convolution by a one-by-one filter
**[0:43]** doesn't seem particularly useful.
**[0:45]** You just multiply it by some number.
**[0:47]** But that's the case of six by six by one channel images.
**[0:53]** If you have a six-by-six by 32 instead of by one,
**[0:58]** then a convolution with
**[1:00]** a one-by-one filter can do
**[1:02]** something that makes much more sense.
**[1:04]** In particular, what a one-by-one convolution
**[1:07]** will do is it will look
**[1:09]** at each of the 36 different positions here.
**[1:13]** It will take the element-wise product between
**[1:16]** 32 numbers on the left and the 32 numbers in the filter,
**[1:21]** and then apply a ReLU,
**[1:24]** nonlinearity to it after that.
**[1:26]** To look at one of the 36 positions,
**[1:29]** maybe one slice through this volume,
**[1:32]** you take these 36 numbers,
**[1:35]** multiply it by one by one slice through
**[1:40]** the volume like that and you end up
**[1:42]** with a single real number.
**[1:45]** Which then gets plotted in one of the outputs like that.
**[1:49]** In fact, one way to think about
**[1:52]** the 32 numbers you have in this one,
**[1:54]** a one by 32 filter is as if you have
**[1:57]** one neuron that is taking us input 32 numbers.
**[2:03]** Multiplying each of these 32 numbers
**[2:06]** in one slice in the same position,
**[2:09]** height, and width, but these 32 different channels,
**[2:12]** multiplying them by 32 weights.
**[2:14]** In applying a ReLU,
**[2:16]** nonlinearity to it and then
**[2:18]** outputting the corresponding thing over there.
**[2:22]** More generally, if you have not just one filter,
**[2:28]** but if you have multiple filters,
**[2:31]** then it's as if you have not just one unit,
**[2:34]** but multiple units to taking as input all the numbers in
**[2:39]** one slice and then building them up into an output,
**[2:45]** the 0.66 by six by number of filters.
**[2:49]** One way to think about a one-by-one convolution
**[2:52]** is that it is basically having
**[2:54]** a fully connected neural network
**[2:58]** that applies to each of the 62 different positions.
**[3:03]** What that fully connected neural network
**[3:05]** does is it inputs
**[3:06]** 32 numbers and outputs number of filters, outputs.
**[3:13]** I guess the payer notation,
**[3:14]** this is really a nc of 0 plus 1 if that's the next layer.
**[3:19]** By doing those at each of the 36 positions,
**[3:22]** each of the six by six positions,
**[3:24]** you end up with an output that is
**[3:25]** six-by-six by the number of filters.
**[3:29]** This can carry out
**[3:30]** a pretty non-trivial computation on your input volume.
**[3:35]** This idea is often called a one-by-one convolution,
**[3:40]** but it's sometimes also called network in network.
**[3:46]** It's described in this paper by M. Lin, Q. Chen, S. Yan.
**[3:53]** Even though the details of
**[3:55]** the architecture in this paper on views YZ,
**[3:58]** this idea of a one-by-one convolution
**[4:00]** of this sometimes called network and network
**[4:03]** idea has been very influential as
**[4:05]** influence many other neural network architectures,
**[4:08]** including the inception network
**[4:09]** which we'll see you in the next video.
**[4:11]** But to give you an example of where
**[4:14]** one-by-one convolution is useful,
**[4:16]** here's something you could do with it.
**[4:18]** Let's say you have a 28 by 28 by 192 volume.
**[4:23]** If you want to shrink the height and width,
**[4:25]** you can use a pooling layer,
**[4:27]** so we know how to do that.
**[4:28]** But one of the number of
**[4:30]** channels has gotten too big and you want to shrink that.
**[4:34]** How do you shrink it to a 28 by
**[4:36]** 28 by 32 dimensional volume?
**[4:40]** Well, what you can do is use,
**[4:43]** 32 filters that are one-by-one,
**[4:47]** and technically each filter would be of
**[4:50]** dimension one by one by 192,
**[4:53]** because the number of channels in your filter
**[4:56]** has to match the number of channels in your input volume.
**[4:59]** But you use 32 filters and the output
**[5:03]** of this process will be 28 by 28 by 32 volume.
**[5:08]** This is a way to let your strength and see as well.
**[5:13]** Whereas pooling layer are used just to
**[5:15]** shrink an h and nw,
**[5:18]** the height and width of these volumes.
**[5:20]** We'll see later how this idea of
**[5:22]** one-by-one convolutions allows you
**[5:25]** to shrink the number of channels
**[5:28]** and therefore save on computation in some networks.
**[5:31]** But of course, if you want to keep the number of channels
**[5:34]** to the 192, that's fine too.
**[5:37]** The effect of a one-by-one convolution
**[5:39]** is it just has nonlinearity.
**[5:41]** It allows you to learn
**[5:42]** a more complex function of
**[5:44]** your network by adding another layer,
**[5:46]** the inputs 20 by 20 by 192,
**[5:49]** and outputs 20 by 20 by 192.
**[5:52]** You've now seen how
**[5:54]** a one-by-one convolution operation
**[5:57]** is actually doing a pretty non-trivial operation
**[6:00]** and allows you to shrink the number of channels in
**[6:03]** your volumes or keep it the
**[6:04]** same or even increase it if you want.
**[6:07]** In the next video,
**[6:08]** you see that this can be used
**[6:11]** to help build up to the inception network.
**[6:14]** Let's go onto the next video.
