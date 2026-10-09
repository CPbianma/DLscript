---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 4
section: Deep Neural Network
item_title: Building Blocks of Deep Neural Networks
duration: 9 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/uGCun/building-blocks-of-deep-neural-networks
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Building Blocks of Deep Neural Networks — Transcript

**[0:00]** In the earlier videos from this week,
**[0:02]** as well as from the videos from the past several weeks,
**[0:05]** you've already seen the basic building blocks of forward propagation and
**[0:09]** back propagation, the key components you need to implement a deep neural network.
**[0:14]** Let's see how you can put these components together to build your deep net.
**[0:18]** Here's a network of a few layers.
**[0:20]** Let's pick one layer.
**[0:22]** And look into the computations focusing on just that layer for now.
**[0:27]** So for layer L, you have some parameters wl and
**[0:33]** bl and for the forward prop, you will input
**[0:37]** the activations a l-1 from your previous layer and
**[0:44]** output a l.
**[0:48]** So the way we did this previously was you compute z l =
**[0:54]** w l times al - 1 + b l.
**[0:59]** And then al = g of z l.
**[1:07]** All right.
**[1:08]** So, that's how you go from the input al minus one to the output al.
**[1:13]** And, it turns out that for later use it'll be useful to also cache the value zl.
**[1:20]** So, let me include this on cache as well because storing the value zl
**[1:25]** would be useful for backward, for the back propagation step later.
**[1:30]** And then for the backward step or for the back propagation step, again,
**[1:35]** focusing on computation for this layer l,
**[1:37]** you're going to implement a function that inputs da(l).
**[1:45]** And outputs da(l-1), and just to flesh out the details,
**[1:53]** the input is actually da(l), as well as the cache so
**[1:59]** you have available to you the value of zl that you computed and
**[2:04]** then in addition, outputing da(l) minus 1 you bring the output or
**[2:10]** the gradients you want in order to implement gradient descent for
**[2:13]** learning, okay?
**[2:14]** So this is the basic structure of how you implement this forward step,
**[2:19]** what we call the forward function as well as this backward step,
**[2:23]** which we'll call backward function.
**[2:25]** So just to summarize, in layer l,
**[2:28]** you're going to have the forward step or the forward prop of the forward function.
**[2:32]** Input al- 1 and output, al, and
**[2:39]** in order to make this computation you need to use wl and bl.
**[2:45]** And also output a cache, which contains zl, right?
**[2:52]** And then the backward function, using the back prop step,
**[2:56]** will be another function that now
**[3:01]** inputs da(l) and outputs da(l-1).
**[3:08]** So it tells you, given the derivatives respect to these activations,
**[3:14]** that's da(l), what are the derivatives?
**[3:17]** How much do I wish?
**[3:18]** You know, al- 1 changes the computed derivatives respect to deactivations
**[3:23]** from a previous layer.
**[3:25]** Within this box, right?
**[3:26]** You need to use wl and bl, and it turns out along the way you end up
**[3:31]** computing dzl, and then this box,
**[3:36]** this backward function can also output dwl and
**[3:42]** dbl, but I was sometimes using red arrows to denote the backward iteration.
**[3:47]** So if you prefer, we could draw these arrows in red.
**[3:51]** So if you can implement these two functions
**[3:55]** then the basic computation of the neural network will be as follows.
**[3:59]** You're going to take the input features a0, feed that in, and
**[4:05]** that would compute the activations of the first layer, let's call that a1 and
**[4:10]** to do that, you need a w1 and b1 and then will also,
**[4:16]** you know, cache away z1, right?
**[4:21]** Now having done that, you feed that to the second layer and then using w2 and b2,
**[4:26]** you're going to compute deactivations in the next layer a2 and so on.
**[4:34]** Until eventually, you end up outputting
**[4:38]** a l which is equal to y hat.
**[4:43]** And along the way, we cached all of these values z.
**[4:52]** So that's the forward propagation step.
**[4:55]** Now, for the back propagation step, what we're going to do
**[4:59]** will be a backward sequence of iterations
**[5:05]** in which you are going backwards and computing gradients like so.
**[5:12]** So what you're going to feed in here, da(l) and
**[5:17]** then this box will give us da(l- 1) and so on until we get da(2) da(1).
**[5:30]** You could actually get one more output to compute da(0) but
**[5:36]** this is derivative with respect to your
**[5:38]** input features, which is not useful at least for
**[5:40]** training the weights of these supervised neural networks.
**[5:46]** So you could just stop it there. But along the way,
**[5:49]** back prop also ends up outputting dwl, dbl.
**[5:54]** I just used the prompt as wl and bl.
**[5:59]** This would output dw3, db3 and so on.
**[6:10]** So you end up computing all the derivatives you need.
**[6:16]** And so just to maybe fill in the structure of this a little bit more,
**[6:21]** these boxes will use those parameters as well.
**[6:26]** wl, bl and it turns out that
**[6:31]** we'll see later that inside these boxes we end up computing the dz's as well.
**[6:37]** So one iteration of training through a neural network involves: starting with
**[6:42]** a(0) which is x and going through forward prop as follows.
**[6:46]** Computing y hat and then using that to compute this and
**[6:50]** then back prop, right, doing that and
**[6:56]** now you have all these derivative terms and so, you know,
**[7:01]** w would get updated as w1 = the learning rate times dw, right?
**[7:06]** For each of the layers and similarly for b rate.
**[7:13]** Now the computed back prop have all these derivatives.
**[7:17]** So that's one iteration of gradient descent for your neural network.
**[7:21]** Now before moving on, just one more informational detail.
**[7:25]** Conceptually, it will be useful to think of the cache here as
**[7:30]** storing the value of z for the backward functions.
**[7:34]** But when you implement this, and you see this in the programming exercise,
**[7:37]** When you implement this, you find that the cache may be
**[7:40]** a convenient way to get to this value of the parameters of w1, b1,
**[7:43]** into the backward function as well. So for
**[7:46]** this exercise you actually store in your cache to z as well as w
**[7:51]** and b. So this stores z2, w2, b2. But from an implementation standpoint,
**[7:59]** I just find it a convenient way to just get the parameters,
**[8:03]** copy to where you need to use them later when you're computing back propagation.
**[8:08]** So that's just an implementational detail that you see when
**[8:12]** you do the programming exercise.
**[8:15]** So you've now seen what are the basic building blocks for
**[8:18]** implementing a deep neural network.
**[8:19]** In each layer there's a forward propagation step and
**[8:22]** there's a corresponding backward propagation step.
**[8:24]** And has a cache to pass information from one to the other.
**[8:27]** In the next video,
**[8:28]** we'll talk about how you can actually implement these building blocks.
**[8:32]** Let's go on to the next video.
