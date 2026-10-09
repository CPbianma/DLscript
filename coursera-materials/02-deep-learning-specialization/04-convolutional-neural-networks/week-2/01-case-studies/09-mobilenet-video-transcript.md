---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 2
section: Case Studies
item_title: MobileNet
duration: 16 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/B1kPZ/mobilenet
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# MobileNet — Transcript

**[0:02]** Hi and welcome back.
**[0:05]** You've learned about the ResNet architecture,
**[0:08]** you've learned about Inception net.
**[0:10]** In this video, you'll learn about MobileNets,
**[0:13]** which is another foundational
**[0:15]** convolutional neural network architecture
**[0:18]** used for computer vision.
**[0:19]** Using MobileNets will allow you to build and deploy
**[0:23]** new networks that work even in low compute environment,
**[0:26]** such as a mobile phone. Let's dive in.
**[0:29]** Why do you need another neural network architecture?
**[0:33]** It turns out in other
**[0:35]** neural networks you've learned about
**[0:36]** so far are quite computationally expensive.
**[0:39]** If you want your neural network to run on a device with
**[0:43]** less powerful CPU or a GPU at deployment,
**[0:47]** then there's another neural network architecture called
**[0:50]** the MobileNet that could perform much better.
**[0:53]** I hope to share a view into this video how
**[0:56]** the depthwise separable convolution works.
**[1:00]** Let's first revisit what the normal convolution does,
**[1:03]** and then we'll modify it to build
**[1:05]** the depthwise separable convolution.
**[1:08]** In the normal convolution,
**[1:10]** you may have an input image that is some n by n by n_c,
**[1:18]** where n_c is the number of channels.
**[1:21]** Six by six by three channels in this case,
**[1:24]** and you want to convolve it with a filter that
**[1:28]** is f by f by n_c,
**[1:32]** and in this case is three by three by three.
**[1:36]** The way you do this is you would take
**[1:39]** this filter which I'm going to draw as
**[1:42]** a three-dimensional yellow block
**[1:46]** and put the yellow filter over there.
**[1:48]** There are 27 multiplications you have to do,
**[1:53]** sum it up, and then that gives you this value.
**[1:56]** Then shift a filter over,
**[1:58]** multiply the 27 pairs of numbers,
**[2:01]** add that up that gives you this number,
**[2:03]** and you keep going to get this,
**[2:06]** to get this, and then this,
**[2:10]** and so on, until you have
**[2:14]** computed all four by four output values.
**[2:18]** We didn't use padding in this case,
**[2:21]** and we use a stride of one,
**[2:22]** which is why the output size a n out by
**[2:25]** a n out is a bit smaller than the input size.
**[2:30]** That is this four by four instead of six by six.
**[2:33]** Rather than just having one of
**[2:36]** these three by three by three filters,
**[2:38]** you may have some n_c prime filters
**[2:44]** and if you have five of them,
**[2:45]** then the output will be four by four by five,
**[2:50]** or a n out by a n out by n_c prime.
**[2:55]** Let's figure out what is the computational cost
**[2:58]** of what we just did.
**[2:59]** It turns out the total number of computations
**[3:02]** needed to compute this output is given
**[3:05]** by the number of filter parameters which is
**[3:09]** three by three by three in this case,
**[3:13]** multiplied by the number of filter positions.
**[3:17]** That is a number of places where we
**[3:19]** place this big yellow block,
**[3:21]** which is four by four,
**[3:24]** and then multiplied by the number of filters,
**[3:27]** which is five in this case.
**[3:29]** You can check for yourself that this is
**[3:32]** the total number of multiplications we need to do,
**[3:36]** because at each of
**[3:37]** the locations we plopped down the filter,
**[3:39]** we need to do this many multiplications,
**[3:41]** and then we have this many filters.
**[3:44]** If you multiply these numbers out,
**[3:46]** this turns out to be 2,160. We'll come back.
**[3:52]** You see this number again later in this video,
**[3:54]** when we come up with
**[3:55]** the depthwise separable convolution
**[3:58]** that will be able to take as input
**[4:00]** a six by six by three image and outputs four by four by
**[4:05]** five set of activations that were
**[4:07]** fewer computations than 2,160.
**[4:10]** Let us see how the depthwise
**[4:12]** separable convolution does that.
**[4:14]** In contrast to the normal convolution which you just saw,
**[4:17]** the depthwise separable convolution has two steps.
**[4:21]** You're going to first use a depthwise convolution,
**[4:26]** followed by a pointwise convolution.
**[4:29]** It is these two steps which together make
**[4:32]** up this depthwise separable convolution.
**[4:36]** Let's see how each of these two steps work.
**[4:39]** In particular, let's flesh out
**[4:41]** the details of how the depthwise convolution,
**[4:45]** the first of these two steps works.
**[4:47]** As before we have an input that is six by six by three,
**[4:52]** so n by n by n_c, three channels.
**[4:57]** The filter and depthwise
**[4:59]** convolution is going to be f by f,
**[5:03]** not f by f by n_c,
**[5:05]** but just f by f. The number of
**[5:08]** filters is going to be n_c,
**[5:13]** which in this case is three.
**[5:16]** The way that you will compute the four by four
**[5:19]** by three output is that you
**[5:22]** apply one of each of
**[5:24]** these filters to one of each of these input channels.
**[5:29]** Let's step through this.
**[5:31]** Let's focus on the first of
**[5:34]** the three filters, just the red one.
**[5:36]** Then take the red filter and position it there,
**[5:39]** carry out the nine multiplications.
**[5:42]** Notice this, on nine numbers means multiply,
**[5:44]** not 27, but nine, and add them up.
**[5:47]** That will give you this value.
**[5:49]** Then shift it over,
**[5:50]** multiply the nine corresponding pairs of numbers,
**[5:53]** that gives you this value over here,
**[5:57]** gives you that, gives you that,
**[6:00]** and so on, until you get to the last of these 16 values.
**[6:08]** Next, we go to the second channel,
**[6:12]** and let's look at the green filter.
**[6:14]** The green filter, you position there,
**[6:16]** carry out the nine multiplications to compute this value,
**[6:19]** shift it over by one to compute this value,
**[6:22]** shift over by one, and so on.
**[6:25]** You do that 16 times until you've computed all of
**[6:28]** these values in the second channel of the outputs.
**[6:32]** Finally, you do this for the third channel,
**[6:35]** there's a blue filter,
**[6:36]** position it there to compute this value, shift it over,
**[6:40]** shift it over, shift it over, and so on,
**[6:44]** until you've computed all 16 outputs
**[6:49]** in that third channel as well.
**[6:52]** The size of the output after this step will
**[6:55]** be n out by n out,
**[6:59]** four-by-four, by nc, where nc is the same as this nc;
**[7:04]** the number of channels in your original input.
**[7:06]** Let's look at the computational cost
**[7:09]** of what we've just done.
**[7:11]** Because to generate each of these output values,
**[7:13]** each of these 4 by 4 by 3 output values,
**[7:16]** it required nine multiplications.
**[7:19]** The total computational cost is 3 by 3
**[7:22]** times the number of filter positions,
**[7:26]** that is, the number of positions each of
**[7:29]** these filters was placed on top of the image on the left.
**[7:33]** There was 4 by 4, and then finally,
**[7:36]** times the number of filters, which is 3.
**[7:39]** Another way to look at this is that you
**[7:41]** have 4 by 4 by 3 outputs,
**[7:45]** and for each of those outputs,
**[7:47]** you needed to carry out nine multiplications.
**[7:51]** The total computational cost is 3 times
**[7:54]** 3 times 4 times 4 times 3.
**[7:57]** If you multiply all these numbers,
**[7:59]** it turns out to be 432.
**[8:02]** But we're not yet done.
**[8:04]** This is a depth-wise convolution part
**[8:07]** of the depth wise separable convolution.
**[8:10]** There's one more step, which is,
**[8:12]** we need to take this 4 by 4 by 3 intermediate value
**[8:17]** and carry out one more step.
**[8:20]** The remaining step is to take this 4 by
**[8:23]** 4 by 3 set of values,
**[8:28]** or n out by n out by nc set of
**[8:30]** values and apply a pointwise convolution in
**[8:33]** order to get the output we want which will
**[8:36]** be 4 by 4 by 5.
**[8:39]** Let's see how the pointwise convolution works.
**[8:42]** Here's the pointwise convolution.
**[8:45]** We are going to take the intermediate set of values,
**[8:49]** which is n out by n out by nc,
**[8:55]** and convolve it with a filter that is 1 by 1 by nc,
**[9:02]** 1 by 1 by 3 in this case.
**[9:04]** Well, you take this pink filter,
**[9:07]** this pink 1 by 1 by 3 block,
**[9:10]** and apply it to upper left-most position,
**[9:13]** carry out the three multiplications,
**[9:16]** add them up, and that gives you this value,
**[9:19]** shift it over by one,
**[9:21]** multiply the three pairs of numbers, add them up,
**[9:24]** that gives you that value, and so on.
**[9:27]** You keep going until you've filled
**[9:31]** out all 16 values of this output.
**[9:34]** Now, we've done this with just one filter in
**[9:38]** order to get another 4 by 4 output,
**[9:41]** by the 4 by 4 by 5 dimensional outputs,
**[9:44]** you would actually do this with nc prime filters,
**[9:49]** in this case nc prime will set to 5.
**[9:52]** So a five of these 1 by 1 by 3 filters,
**[9:55]** you end up with a 4 by 4 by 5 output as follows,
**[10:01]** to give you an n out by n
**[10:04]** out by nc prime dimensional output.
**[10:08]** The pointwise convolution gives
**[10:11]** you the 4 by 4 by 5 output.
**[10:14]** Let's figure out the computational cost
**[10:17]** of what we just did.
**[10:18]** For every one of these four
**[10:20]** by four by five output values,
**[10:22]** we had to apply this pink filter to part of the input.
**[10:27]** That cost three operations or 1 by 1 by 1,
**[10:33]** which is number of filter parameters.
**[10:35]** The filtered had to be placed in
**[10:38]** 4 by 4 different positions,
**[10:41]** and we had five filters.
**[10:44]** To tell the cost of what we just did here is,
**[10:47]** 1 times 1 times 3 times 4 times 4 times 5,
**[10:50]** which is 240 multiplications.
**[10:54]** In the example we just walked
**[10:56]** through, the normal convolution,
**[10:58]** took as input a six by six by three input,
**[11:01]** and wound up with a four by four by five outwards.
**[11:05]** Same for the depthwise separable convolution,
**[11:09]** except we did it in two steps
**[11:11]** with a depthwise convolution,
**[11:13]** followed by a pointwise convolution.
**[11:16]** Now, what were the computational costs
**[11:20]** of all of these operations?
**[11:22]** In the case of the normal convolution,
**[11:25]** we needed 2160 multiplications to compute the output.
**[11:30]** For the depthwise separable convolution,
**[11:33]** there was first, the depthwise step,
**[11:37]** where we had from earlier in the video,
**[11:40]** 432 multiplications and then the pointwise step,
**[11:45]** where we had 240 multiplications,
**[11:49]** and so adding these up,
**[11:51]** we wind up with 672 multiplications.
**[11:57]** If we look the ratio between these two numbers,
**[12:00]** 672 over 2160, this turns out to be about 0.31.
**[12:07]** In this example, the depthwise separable convolution
**[12:10]** was about 31 percent
**[12:12]** as computationally expensive as
**[12:14]** the normal convolution, roughly [inaudible] savings.
**[12:18]** The authors of the MobileNets paper
**[12:22]** showed that in general,
**[12:24]** the ratio of the cost of
**[12:27]** the depthwise separable convolution
**[12:30]** compared to the normal convolution,
**[12:32]** that turns out to be equal to one over
**[12:35]** n_c prime plus one over f squared in the general case.
**[12:41]** In our case, this was one over five plus
**[12:44]** one over three squared or one over nine, which is 0.31.
**[12:48]** In a more typical neural network example,
**[12:51]** n_c prime will be much bigger.
**[12:54]** so It may be, say, one over 512.
**[12:59]** If you have 512 channels in
**[13:02]** your output plus one over three squared,
**[13:05]** this would be a fairly typical parameters or new network.
**[13:10]** This is really small and this is one-ninth.
**[13:13]** So very roughly,
**[13:15]** the depthwise separable convolution
**[13:17]** may be about one-ninth,
**[13:20]** rounding up roughly 10
**[13:22]** times cheaper in computational costs.
**[13:27]** That's why the depthwise separable convolution
**[13:30]** as a building block of a convnet,
**[13:33]** allows you to carry out inference much
**[13:35]** more efficiently than using a normal convolution.
**[13:38]** Now, there's just one more detail I want to
**[13:41]** share with you before we wrap up this video.
**[13:44]** In the example that we went through,
**[13:46]** the input here was six by six by n_c,
**[13:50]** where n_c was equal to three and thus you
**[13:54]** had three by three by n_c filters here.
**[13:58]** Now, the depthwise separable convolution works
**[14:01]** for any number of input channels.
**[14:03]** So if you had six input channels,
**[14:06]** then n_c would be equal to six and you
**[14:10]** would also then have to have
**[14:12]** three by three by six filters.
**[14:15]** The intermediate outputs will continue to
**[14:17]** be four by four by n_c,
**[14:20]** that becomes four by four by six.
**[14:25]** Now, something looks wrong with this diagram, doesn't it?
**[14:28]** Which is that this should be three
**[14:31]** by three by six not three by three by three.
**[14:34]** But in order to make the diagrams
**[14:36]** in the next video look a little bit simpler,
**[14:38]** even when the number of channels is greater than three,
**[14:41]** I'm still going to draw
**[14:43]** the depthwise convolution operation as
**[14:46]** if it was this stack of three filters.
**[14:49]** When you see this exact icon later,
**[14:54]** think of that as the icon we're
**[14:56]** using to denote a depthwise convolution,
**[14:58]** rather than a very literal exact visualization
**[15:02]** of the number of channels at
**[15:04]** the depthwise convolution filter.
**[15:06]** Going to use a similar icon
**[15:08]** to denote pointwise convolution.
**[15:11]** In this example, the input here would
**[15:13]** be four by four by n_c,
**[15:17]** so it's really this value from up here.
**[15:20]** Rather than expanding the stack of values to
**[15:23]** be one by one by n_c,
**[15:27]** I'm going to continue to use
**[15:28]** this pink set of filters that looks like that.
**[15:31]** Even if n_c is much larger,
**[15:34]** I'm still going to draw it as if it looks
**[15:36]** like it only has three filters to make
**[15:38]** some of the diagrams looks simpler and this can give
**[15:41]** you the outputs of whatever's necessary dimensions,
**[15:44]** such as four by four by eight,
**[15:47]** by some of the value of n_c prime in this case.
**[15:50]** That's it. You've learned about
**[15:52]** the depthwise separable convolution,
**[15:55]** which comprises two main steps,
**[15:56]** the depthwise convolution and the pointwise convolution.
**[16:00]** This operation can be
**[16:02]** designed to have the same inputs and
**[16:04]** output dimensions as the normal convolutional operation,
**[16:07]** but it can be done in much lower computational cost.
**[16:11]** Let's now take this building block and
**[16:13]** use it to build the MobileNet,
**[16:15]** we'll do that in the next video.
