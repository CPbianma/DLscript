---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 1
section: Convolutional Neural Networks
item_title: One Layer of a Convolutional Network
duration: 16 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/nsiuW/one-layer-of-a-convolutional-network
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# One Layer of a Convolutional Network — Transcript

**[0:03]** Get now ready to see how to build one layer of a convolutional neural network,
**[0:07]** let's go through an example.
**[0:12]** You've seen at the previous video how to take a 3D volume and
**[0:16]** convolve it with say two different filters.
**[0:21]** In order to get in this example to different 4 by 4 outputs.
**[0:30]** So let's say convolving with the first filter
**[0:34]** gives this first 4 by 4 output, and
**[0:40]** convolving with this second filter gives a different 4 by 4 output.
**[0:49]** The final thing to turn this into a convolutional neural net layer,
**[0:55]** is that for each of these we're going to add it bias,
**[1:00]** so this is going to be a real number.
**[1:03]** And where python broadcasting, you kind of have to add the same number
**[1:07]** so every one of these 16 elements.
**[1:11]** And then apply a non-linearity which for this illustration that says relative
**[1:16]** non-linearity, and this gives you a 4 by 4 output, all right?
**[1:23]** After applying the bias and the non-linearity.
**[1:27]** And then for this thing at the bottom as well, you add some different bias, again,
**[1:31]** this is a real number.
**[1:33]** So you add the single number to all 16 numbers, and
**[1:36]** then apply some non-linearity, let's say a real non-linearity.
**[1:40]** And this gives you a different 4 by 4 output.
**[1:47]** Then same as we did before, if we take this and stack it up
**[1:52]** as follows, so we ends up with a 4 by 4 by 2 outputs.
**[1:59]** Then this computation where you come from a 6 by 6 by 3 to 4 by 4 by 4,
**[2:06]** this is one layer of a convolutional neural network.
**[2:11]** So to map this back to one layer of four propagation in the standard
**[2:15]** neural network, in a non-convolutional neural network.
**[2:18]** Remember that one step before the prop was something like this, right?
**[2:23]** z1 = w1 times a0, a0 was also equal to x,
**[2:28]** and then plus b[1].
**[2:31]** And you apply the non-linearity to get a[1], so that's g(z[1]).
**[2:38]** So this input here, in this analogy this is a[0], this is x3.
**[2:44]** And these filters here,
**[2:46]** this plays a role similar to w1.
**[2:52]** And you remember during the convolution operation, you were taking these
**[2:56]** 27 numbers, or really well, 27 times 2, because you have two filters.
**[3:01]** You're taking all of these numbers and multiplying them.
**[3:03]** So you're really computing a linear function to get this 4 x 4 matrix.
**[3:09]** So that 4 x 4 matrix, the output of the convolution operation,
**[3:14]** that plays a role similar to w1 times a0.
**[3:19]** That's really maybe the output of this 4 x 4 as well as that 4 x 4.
**[3:25]** And then the other thing you do is add the bias.
**[3:29]** So, this thing here before applying value,
**[3:35]** this plays a role similar to z.
**[3:38]** And then it's finally by applying the non-linearity, this kind of this I guess.
**[3:43]** So, this output plays a role,
**[3:49]** this really becomes your activation at the next layer.
**[3:53]** So this is how you go from a0 to a1, as far as tthe linear operation
**[3:58]** and then convolution has all these multipled.
**[4:02]** So the convolution is really applying a linear operation and
**[4:05]** you have the biases and the applied value operation.
**[4:08]** And you've gone from a 6 by 6 by 3, dimensional a0,
**[4:14]** through one layer of neural network to,
**[4:18]** I guess a 4 by 4 by 2 dimensional a(1).
**[4:22]** And so 6 by 6 by 3 has gone to 4 by 4 by 2,
**[4:27]** and so that is one layer of convolutional net.
**[4:33]** Now in this example we have two filters, so we had two features of you will,
**[4:40]** which is why we wound up with our output 4 by 4 by 2.
**[4:45]** But if for example we instead had 10 filters instead of 2,
**[4:49]** then we would have wound up with the 4 by 4 by 10 dimensional output volume.
**[4:54]** Because we'll be taking 10 of these naps not just two of them, and stacking them
**[4:59]** up to form a 4 by 4 by 10 output volume, and that's what a1 would be.
**[5:05]** So, to make sure you understand this, let's go through an exercise.
**[5:09]** Let's suppose you have 10 filters, not just two filters, that are 3 by 3 by 3 and
**[5:14]** 1 layer of a neural network, how many parameters does this layer have?
**[5:21]** Well, let's figure this out.
**[5:22]** Each filter, is a 3 x 3 x 3 volume, so 3 x 3 x 3,
**[5:29]** so each fill has 27 parameters, all right?
**[5:35]** There's 27 numbers to be run, and plus the bias.
**[5:42]** So that was the b parameter, so this gives you 28 parameters.
**[5:50]** And then if you imagine that on the previous slide we had drawn two filters,
**[5:54]** but now if you imagine that you actually have ten of these, right?
**[5:58]** 1, 2..., 10 of these,
**[6:01]** then all together you'll have 28 times 10,
**[6:04]** so that will be 280 parameters.
**[6:10]** Notice one nice thing about this, is that no matter how big the input image is,
**[6:16]** the input image could be 1,000 by 1,000 or 5,000 by 5,000,
**[6:22]** but the number of parameters you have still remains fixed as 280.
**[6:26]** And you can use these ten filters to detect features, vertical edges,
**[6:31]** horizontal edges maybe other features anywhere even in a very,
**[6:35]** very large image is just a very small number of parameters.
**[6:40]** So these is really one property of convolution neural network that
**[6:44]** makes less prone to overfitting then if you could.
**[6:48]** So once you've learned 10 feature detectors that work,
**[6:51]** you could apply this even to large images.
**[6:54]** And the number of parameters still is fixed and relatively small,
**[6:58]** as 280 in this example.
**[7:00]** All right, so to wrap up this video let's just summarize the notation we
**[7:06]** are going to use to describe one layer to describe a covolutional layer in
**[7:09]** a convolutional neural network.
**[7:11]** So layer l is a convolution layer,
**[7:14]** l am going to use f superscript,[l] to denote the filter size.
**[7:18]** So previously we've been seeing the filters are f by f, and
**[7:23]** now this superscript square bracket l just denotes that this is
**[7:27]** a filter size of f by f filter layer l.
**[7:31]** And as usual the superscript square bracket l is the notation we're using to
**[7:34]** refer to particular layer l.
**[7:39]** going to use p[l] to denote the amount of padding.
**[7:42]** And again, the amount of padding can also be specified just by saying that you want
**[7:47]** a valid convolution, which means no padding, or
**[7:50]** a same convolution which means you choose the padding.
**[7:53]** So that the output size has the same height and width as the input size.
**[7:59]** And then you're going to use s[l] to denote the stride.
**[8:03]** Now, the input to this layer is going to be some dimension.
**[8:09]** It's going be some n by n by number of channels in the previous layer.
**[8:18]** Now, I'm going to modify this notation a little bit.
**[8:21]** I'm going to us superscript l- 1,
**[8:23]** because that's the activation from
**[8:27]** the previous layer, l- 1 times nc of l- 1.
**[8:35]** And in the example so far, we've been just using images of the same height and width.
**[8:40]** That in case the height and width might differ,
**[8:43]** l am going to use superscript h and superscript w, to denote the height and
**[8:47]** width of the input of the previous layer, all right?
**[8:51]** So in layer l, the size of the volume will be nh
**[8:56]** by nw by nc with superscript squared bracket l.
**[9:01]** It's just in layer l, the input to this layer Is whatever you had for
**[9:05]** the previous layer, so that's why you have l- 1 there.
**[9:09]** And then this layer of the neural network will itself output the value.
**[9:16]** So that will be nh of l by nw of l, by nc of l,
**[9:25]** that will be the size of the output.
**[9:28]** And so whereas we approve this set that the output volume size or
**[9:34]** at least the height and weight is given by this formula,
**[9:37]** n + 2p- f over s + 1, and then take the full of that and round it down.
**[9:47]** In this new notation what we have is that the outputs value that's in layer l,
**[9:55]** is going to be the dimension from the previous layer,
**[10:00]** plus the padding we're using in this layer l,
**[10:05]** minus the filter size we're using this layer l and so on.
**[10:11]** And technically this is true for the height, right?
**[10:16]** So the height of the output volume is given by this, and you can compute it
**[10:21]** with this formula on the right, and the same is true for the width as well.
**[10:24]** So you cross out h and
**[10:26]** throw in w as well, then the same formula with either the height or
**[10:30]** the width plugged in for computing the height or width of the output value.
**[10:36]** So that's how nhl -1 relates to nhl and wl- 1 relates to nwl.
**[10:44]** Now, how about the number of channels, where did those numbers come from?
**[10:48]** Let's take a look, if the output volume has this depth,
**[10:53]** while we know from the previous examples that that's equal
**[10:57]** to the number of filters we have in that layer, right?
**[11:02]** So we had two filters, the output value was 4 by 4 by 2, was 2 dimensional.
**[11:07]** And if you had 10 filters and your upper volume was 4 by 4 by 10.
**[11:11]** So, this the number of channels in the output value,
**[11:15]** that's just the number of filters we're using in this layer of the neural network.
**[11:23]** Next, how about the size of this filter?
**[11:26]** Well, each filter is going to be fl by fl by 100 number, right?
**[11:33]** So what is this last number?
**[11:34]** Well, we saw that you needed to convolve a 6 by 6 by 3 image,
**[11:39]** with a 3 by 3 by 3 filter.
**[11:43]** And so the number of channels in your filter, must match the number of channels
**[11:48]** in your input, so this number should match that number, right?
**[11:54]** Which is why each filter is going to be f(l) by f(l) by nc(l-1).
**[12:02]** And the output of this layer often apply devices in non-linearity,
**[12:07]** is going to be the activations of this layer al.
**[12:11]** And that we've already seen will be this dimension, right?
**[12:15]** The al will be a 3D volume,
**[12:18]** that's nHl by nwl by ncl.
**[12:25]** And when you are using a vectorized implementation or batch gradient
**[12:29]** descent or mini batch gradient descent, then you actually outputs Al,
**[12:33]** which is a set of m activations, if you have m examples.
**[12:40]** So that would be M by nHl, by nwl by ncl right?
**[12:48]** If say you're using bash grading decent and
**[12:51]** in the programming sizes this will be ordering of the variables.
**[12:55]** And we have the index and the trailing examples first,
**[12:59]** and then these three variables.
**[13:02]** Next how about the weights or the parameters, or kind of the w parameter?
**[13:07]** Well we saw already what the filter dimension is.
**[13:10]** So the filters are going to be f[l] by f[l] by nc [l- 1],
**[13:17]** but that's the dimension of one filter.
**[13:20]** How many filters do we have?
**[13:22]** Well, this is a total number of filters, so
**[13:25]** the weights really all of the filters put together will have dimension given by this
**[13:30]** times the total number of filters, right?
**[13:33]** Because this, Last quantity is the number of
**[13:38]** filters, In layer l.
**[13:45]** And then finally, you have the bias parameters, and
**[13:48]** you have one bias parameter, one real number for each filter.
**[13:54]** So you're going to have, the bias will have this many variables,
**[13:57]** it's just a vector of this dimension.
**[14:00]** Although later on we'll see that the code will be
**[14:03]** more convenient represented as 1 by 1 by 1 by nc[l]
**[14:09]** four dimensional matrix, or four dimensional tensor.
**[14:16]** So I know that was a lot of notation, and
**[14:19]** this is the convention I'll use for the most part.
**[14:23]** I just want to mention in case you search online and look at open source code.
**[14:27]** There isn't a completely universal standard convention about the ordering of
**[14:32]** height, width, and channel.
**[14:34]** So If you look on source code on GitHub or these open source implementations,
**[14:39]** you'll find that some authors use this order instead, where you first put
**[14:43]** the channel first, and you sometimes see that ordering of the variables.
**[14:48]** And in fact in some common frameworks, actually in multiple common frameworks,
**[14:52]** there's actually a variable or a parameter.
**[14:54]** Why do you want to list the number of channels first, or
**[14:57]** list the number of channels last when indexing into these volumes.
**[15:02]** I think both of these conventions work okay, so long as you're consistent.
**[15:08]** And unfortunately maybe this is one piece of annotation where
**[15:13]** there isn't consensus in the deep learning literature but
**[15:17]** i'm going to use this convention for these videos.
**[15:24]** Where we list height and width and then the number of channels last.
**[15:30]** So I know there was certainly a lot of new notations you could use, but you're
**[15:34]** thinking wow, that's a long notation, how do I need to remember all of these?
**[15:38]** Don't worry about it, you don't need to remember all of this notation, and
**[15:41]** through this week's exercises you become more familiar with it at that time.
**[15:46]** But the key point I hope you take a way from this video,
**[15:49]** is just one layer of how convolutional neural network works.
**[15:52]** And the computations involved in taking the activations of one layer and
**[15:57]** mapping that to the activations of the next layer.
**[16:00]** And next, now that you know how one layer of the compositional neural network works,
**[16:04]** let's stack a bunch of these together to actually form a deeper compositional
**[16:07]** neural network.
**[16:09]** Let's go on to the next video to see,
