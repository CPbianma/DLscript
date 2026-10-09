---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 2
section: Case Studies
item_title: Why ResNets Work?
duration: 9 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/XAKNO/why-resnets-work
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Why ResNets Work? — Transcript

**[0:00]** So, why do ResNets work so well?
**[0:02]** Let's go through one example that illustrates why ResNets work so well,
**[0:07]** at least in the sense of how you can make them deeper and deeper without really
**[0:12]** hurting your ability to at least get them to do well on the training set.
**[0:17]** And hopefully as you've understood from the third course in this sequence,
**[0:22]** doing well on the training set is usually a prerequisite to doing
**[0:25]** well on your hold up or on your depth or on your test sets.
**[0:29]** So, being able to at least train ResNet to do well on
**[0:33]** the training set is a good first step toward that. Let's look at an example.
**[0:38]** What we saw on the last video was that if you make a network deeper,
**[0:43]** it can hurt your ability to train the network to do well on the training set.
**[0:49]** And that's why sometimes you don't want a network that is too deep.
**[0:53]** But this is not true or at least is much less true when you training a ResNet.
**[0:58]** So let's go through an example.
**[1:01]** Let's say you have X feeding in to
**[1:04]** some big neural network and just outputs some activation a[l].
**[1:10]** Let's say for this example that you are going to modify
**[1:14]** the neural network to make it a little bit deeper.
**[1:19]** So, use the same big NN,
**[1:20]** and this output's a[l],
**[1:24]** and we're going to add a couple extra layers to this network so
**[1:28]** let's add one layer there and another layer there.
**[1:33]** And just for output a[l+2].
**[1:38]** Only let's make this a ResNet block,
**[1:40]** a residual block with that extra short cut.
**[1:46]** And for the sake our argument,
**[1:47]** let's say throughout this network we're using the value activation functions.
**[1:52]** So, all the activations are going to be greater than or equal to zero,
**[1:58]** with the possible exception of the input X.
**[2:01]** Right. Because the value activation output's numbers that are either zero or positive.
**[2:07]** Now, let's look at what's a[l+2] will be.
**[2:10]** To copy the expression from the previous video,
**[2:15]** a[l+2] will be value apply to z[l+2],
**[2:21]** and then plus a[l] where is this addition of a[l]
**[2:26]** comes from the short circuit from the skip connection that we just added.
**[2:31]** And if we expand this out,
**[2:33]** this is equal to g of w[l+2],
**[2:34]** times a of [l+1], plus b[l+2].
**[2:43]** So that's z[l+2] is equal to that, plus a[l].
**[2:48]** Now notice something, if you are using L two regularisation away to K,
**[2:53]** that will tend to shrink the value of w[l+2].
**[2:58]** If you are applying way to K to B that will also shrink this although
**[3:02]** I guess in practice sometimes you do and sometimes you don't apply way to K to B,
**[3:06]** but W is really the key term to pay attention to here.
**[3:12]** And if w[l+2] is equal to zero.
**[3:16]** And let's say for the sake of argument that B is also equal to zero,
**[3:20]** then these terms go away because they're equal to zero,
**[3:25]** and then g of a[l],
**[3:27]** this is just equal to a[l] because we assumed we're using the value activation function.
**[3:36]** And so all of the activations are all negative and so,
**[3:39]** g of a[l] is the value applied to a non-negative quantity,
**[3:43]** so you just get back, a[l].
**[3:46]** So, what this shows is that the identity function is easy for residual block to learn.
**[3:56]** And it's easy to get a[l+2] equals to a[l] because of this skip connection.
**[4:03]** And what that means is that adding these two layers in your neural network,
**[4:08]** it doesn't really hurt your neural network's ability to do as
**[4:11]** well as this simpler network without these two extra layers,
**[4:16]** because it's quite easy for it to learn the identity function to just copy
**[4:20]** a[l] to a[l+2] using despite the addition of these two layers.
**[4:26]** And this is why adding two extra layers,
**[4:30]** adding this residual block to somewhere in
**[4:34]** the middle or the end of this big neural network it doesn't hurt performance.
**[4:40]** But of course our goal is to not just not hurt performance,
**[4:43]** is to help performance and so you can imagine that if all of
**[4:48]** these heading units if they actually learned something useful then
**[4:51]** maybe you can do even better than learning the identity function.
**[4:55]** And what goes wrong in very deep plain nets in very deep network without
**[5:00]** this residual of the skip connections is
**[5:03]** that when you make the network deeper and deeper,
**[5:06]** it's actually very difficult for it to choose parameters that learn
**[5:10]** even the identity function which is why a lot of layers
**[5:14]** end up making your result worse rather than making your result better.
**[5:19]** And I think the main reason the residual network works is
**[5:22]** that it's so easy for these extra layers to learn
**[5:26]** the identity function that you're kind of guaranteed that it doesn't hurt
**[5:30]** performance and then a lot the time you maybe get lucky and then even helps performance.
**[5:35]** At least is easier to go from a decent baseline of not
**[5:39]** hurting performance and then great in decent can only improve the solution from there.
**[5:44]** So, one more detail in the residual network that's
**[5:46]** worth discussing which is through this edition here,
**[5:50]** we're assuming that z[l+2] and a[l] have the same dimension.
**[5:54]** And so what you see in ResNet is a lot of use of same convolutions
**[6:01]** so that the dimension of this is
**[6:03]** equal to the dimension I guess of this layer or the outputs layer.
**[6:08]** So that we can actually do this short circle connection,
**[6:12]** because the same convolution preserve dimensions,
**[6:15]** and so makes that easier for you to carry out
**[6:19]** this short circle and then carry out this addition of two equal dimension vectors.
**[6:25]** In case the input and output have different dimensions so for example,
**[6:30]** if this is a 128 dimensional and Z or therefore,
**[6:36]** a[l] is 256 dimensional as an example.
**[6:40]** What you would do is add an extra matrix and then call that Ws over here,
**[6:46]** and Ws in this example would be a[l] 256 by 128 dimensional matrix.
**[6:54]** So then Ws times a[l] becomes 256 dimensional and
**[6:59]** this addition is now between
**[7:01]** two 256 dimensional vectors and there are few things you could do with Ws,
**[7:05]** it could be a matrix of parameters we learned,
**[7:07]** it could be a fixed matrix that just implements
**[7:10]** zero paddings that takes a[l] and then zero
**[7:13]** pads it to be 256 dimensional and either of those versions I guess could work.
**[7:20]** So finally, let's take a look at ResNets on images.
**[7:23]** So these are images I got from the paper by Harlow.
**[7:27]** This is an example of a plain network and in which you input an image
**[7:35]** and then have a number of conv layers
**[7:39]** until eventually you have a softmax output at the end.
**[7:44]** To turn this into a ResNet,
**[7:46]** you add those extra skip connections.
**[7:50]** And I'll just mention a few details,
**[7:53]** there are a lot of three by three convolutions here and most of these are
**[7:57]** three by three same convolutions
**[8:01]** and that's why you're adding equal dimension feature vectors.
**[8:05]** So rather than a fully connected layer,
**[8:08]** these are actually convolutional layers but because the same convolutions,
**[8:11]** the dimensions are preserved and so the z[l+2] plus a[l] by addition makes sense.
**[8:21]** And similar to what you've seen in a lot of NetRes before,
**[8:25]** you have a bunch of convolutional layers and then there are
**[8:29]** occasionally pulling layers as well or pulling a pulling likely is.
**[8:34]** And whenever one of those things happen,
**[8:36]** then you need to make an adjustment to the dimension which we saw on the previous slide.
**[8:42]** You can do of the matrix Ws,
**[8:44]** and then as is common in these networks,
**[8:46]** you have Conv Conv Conv pull,Conv Conv Conv pull, Conv Conv Conv pull
**[8:50]** and then at the end you now have
**[8:52]** a fully connected layer that then makes a prediction using a softmax.
**[8:56]** So that's it for ResNet.
**[8:58]** Next, there's a very interesting idea
**[9:02]** behind using neural networks with one by one filters,
**[9:05]** one by one convolutions.
**[9:07]** So, one could use a one by one convolution.
**[9:10]** Let's take a look at the next video.
