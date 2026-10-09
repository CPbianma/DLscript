---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 1
section: Convolutional Neural Networks
item_title: Pooling Layers
duration: 10 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/hELHk/pooling-layers
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Pooling Layers — Transcript

**[0:00]** Other than convolutional layers,
**[0:02]** ConvNets often also use pooling layers to reduce the size of the representation,
**[0:07]** to speed the computation,
**[0:08]** as well as make some of the features that detects a bit more robust.
**[0:12]** Let's take a look. Let's go through an example of pooling,
**[0:16]** and then we'll talk about why you might want to do this.
**[0:20]** Suppose you have a four by four input,
**[0:24]** and you want to apply a type of pooling called max pooling.
**[0:28]** And the output of
**[0:30]** this particular implementation of max pooling will be a two by two output.
**[0:34]** And the way you do that is quite simple.
**[0:37]** Take your four by four input and break it into
**[0:40]** different regions and I'm going to color the four regions as follows.
**[0:44]** And then, in the output,
**[0:46]** which is two by two,
**[0:47]** each of the outputs will just be the max from the corresponding reshaded region.
**[0:53]** So the upper left, I guess,
**[0:54]** the max of these four numbers is nine.
**[0:57]** On upper right, the max of the blue numbers is two.
**[1:01]** Lower left, the biggest number is six,
**[1:04]** and lower right, the biggest number is three.
**[1:08]** So to compute each of the numbers on the right,
**[1:10]** we took the max over a two by two regions.
**[1:13]** So, this is as if you apply a filter size of two
**[1:18]** because you're taking a two by two regions and you're taking a stride of two.
**[1:25]** So, these are actually the hyperparameters of
**[1:30]** max pooling because we start from this filter size.
**[1:36]** It's like a two by two region that gives you the nine.
**[1:39]** And then, you step all over two steps to look at this region, to give you the two,
**[1:45]** and then for the next row,
**[1:46]** you step it down two steps to give you the six,
**[1:49]** and then step to the right by two steps to give you three.
**[1:52]** So because the squares are two by two, f is equal to two,
**[1:54]** and because you stride by two,
**[1:58]** s is equal to two.
**[2:00]** So here's the intuition behind what max pooling is doing.
**[2:09]** If you think of this four by four region as some set of features,
**[2:15]** the activations in some layer of the neural network,
**[2:19]** then a large number,
**[2:20]** it means that it's maybe detected a particular feature.
**[2:23]** So, the upper left-hand quadrant has this particular feature.
**[2:26]** It maybe a vertical edge or maybe a higher or whisker if you trying to detect a [inaudible].
**[2:32]** Clearly, that feature exists in the upper left-hand quadrant.
**[2:34]** Whereas this feature, maybe it isn't cat eye detector.
**[2:40]** Whereas this feature, it doesn't really exist in the upper right-hand quadrant.
**[2:43]** So what the max operation does is a lots of features detected anywhere,
**[2:47]** and one of these quadrants , it then remains preserved in the output of max pooling.
**[2:53]** So, what the max operates to does is really to say,
**[2:56]** if these features detected anywhere in this filter,
**[2:59]** then keep a high number.
**[3:01]** But if this feature is not detected,
**[3:03]** so maybe this feature doesn't exist in the upper right-hand quadrant.
**[3:07]** Then the max of all those numbers is still itself quite small.
**[3:11]** So maybe that's the intuition behind max pooling.
**[3:15]** But I have to admit,
**[3:16]** I think the main reason people use max pooling is
**[3:19]** because it's been found in a lot of experiments to work well,
**[3:23]** and the intuition I just described,
**[3:25]** despite it being often cited,
**[3:27]** I don't know of anyone fully knows if that is the real underlying reason.
**[3:33]** I don't have anyone knows if that's
**[3:34]** the real underlying reason that max pooling works well in ConvNets.
**[3:39]** One interesting property of max pooling is that it has
**[3:43]** a set of hyperparameters but it has no parameters to learn.
**[3:47]** There's actually nothing for gradient descent to learn.
**[3:50]** Once you fix f and s,
**[3:51]** it's just a fixed computation and gradient descent doesn't change anything.
**[3:56]** Let's go through an example with some different hyperparameters.
**[4:00]** Here, I am going to use, sure you have a five by five input
**[4:04]** and we're going to apply max pooling with a filter size that's three by three.
**[4:10]** So f is equal to three and let's use a stride of one.
**[4:13]** So in this case, the output size is going to be three by three.
**[4:18]** And the formulas we had developed in
**[4:20]** the previous videos for figuring out the output size for conv layer,
**[4:23]** those formulas also work for max pooling.
**[4:27]** So, that's n plus 2p minus f over s plus 1.
**[4:34]** That formula also works for figuring out the output size of max pooling.
**[4:38]** But in this example, let's compute each of the elements of this three by three output.
**[4:41]** The upper left-hand elements,
**[4:45]** we're going to look over that region.
**[4:46]** So notice this is a three by three region
**[4:48]** ,because the filter size is three and to the max there.
**[4:51]** So, that will be nine,
**[4:53]** and then we shifted over by one because which you can stride at one.
**[4:57]** So, that max in the blue box is nine.
**[5:00]** Let's shift that over again.
**[5:03]** The max of the blue box is five.
**[5:06]** And then let's go on to the next row, a stride of one.
**[5:09]** So we're just stepping down by one step.
**[5:12]** So max in that region is nine, max in that region is nine,
**[5:16]** max in that region,
**[5:19]** it's now with a two fives, we have maxes of five.
**[5:22]** And then finally, max in that is eight.
**[5:26]** Max in that is six,
**[5:28]** and max in that, this is 9 in the bottom right corner.
**[5:31]** Okay, so this, with this set of hyperparameters f equals three,
**[5:35]** s equals one gives that output shown.
**[5:40]** Now, so far, I've shown max pooling on a 2D inputs.
**[5:44]** If you have a 3D input,
**[5:47]** then the outputs will have the same dimension.
**[5:53]** So for example, if you have five by five by two,
**[5:56]** then the output will be three by three by two and the way you compute
**[6:02]** max pooling is you perform the computation
**[6:05]** we just described on each of the channels independently.
**[6:08]** So the first channel which is shown here on top is still the same,
**[6:11]** and then for the second channel, I guess,
**[6:13]** this one that I just drew at the bottom,
**[6:15]** you would do the same computation on that slice of
**[6:19]** this value and that gives you the second slice.
**[6:24]** And more generally, if this was five by five by some number of channels,
**[6:29]** the output would be three by three by that same number of channels.
**[6:34]** And the max pooling computation is done independently on each of these N_C channels.
**[6:44]** So, that's max pooling.
**[6:46]** This one is the type of pooling that isn't used very often,
**[6:49]** but I'll mention briefly which is average pooling.
**[6:52]** So it does pretty much what you'd expect which is,
**[6:56]** instead of taking the maxes within each filter,
**[6:59]** you take the average.
**[7:02]** So in this example,
**[7:03]** the average of the numbers in purple is 3.75,
**[7:07]** then there is 1.25,
**[7:09]** and four and two.
**[7:12]** And so, this is average pooling with hyperparameters f equals two,
**[7:17]** s equals two, we can choose other hyperparameters as well.
**[7:21]** So these days, max pooling is used much more
**[7:24]** often than average pooling with one exception,
**[7:28]** which is sometimes very deep in a neural network.
**[7:32]** You might use average pooling to collapse your representation from say,
**[7:36]** 7 by 7 by 1,000.
**[7:40]** An average over all the spacial sense ,
**[7:42]** you get 1 by 1 by 1,000.
**[7:45]** We'll see an example of this later.
**[7:47]** But you see, max pooling used much more in the neural network than average pooling.
**[7:54]** So just to summarize,
**[7:56]** the hyperparameters for pooling are f,
**[8:00]** the filter size and s, the stride,
**[8:02]** and maybe common choices of parameters might be f equals two, s equals two.
**[8:07]** This is used quite often and this has the effect
**[8:11]** of roughly shrinking the height and width by a factor of above two,
**[8:15]** and a common chosen hyperparameters might be f equals two, s equals two,
**[8:21]** and this has the effect of shrinking
**[8:23]** the height and width of the representation by a factor of two.
**[8:28]** I've also seen f equals three, s equals two used,
**[8:32]** and then the other hyperparameter is just like a binary bit that says,
**[8:37]** are you using max pooling or are you using average pooling.
**[8:40]** If you want, you can add an extra hyperparameter
**[8:43]** for the padding although this is very, very rarely used.
**[8:48]** When you do max pooling, usually,
**[8:50]** you do not use any padding,
**[8:51]** although there is one exception that we'll see next week as well.
**[8:55]** But for the most parts of max pooling,
**[8:57]** usually, it does not use any padding.
**[8:59]** So, the most common value of p by far is p equals zero.
**[9:05]** And the input of max pooling is that you input a volume of size that,
**[9:13]** N_H by N_W by N_C,
**[9:14]** and it would output a volume of size given by this.
**[9:21]** So assuming there's no padding by N_W minus f over s,
**[9:29]** this one for by N_C.
**[9:32]** So the number of input channels is equal to the number of output channels
**[9:35]** because pooling applies to each of your channels independently.
**[9:40]** One thing to note about pooling is that there are no parameters to learn.
**[9:47]** So, when we implement that crop,
**[9:50]** you find that there are no parameters that backdrop will adapt through max pooling.
**[9:55]** Instead, there are just these hyperparameters that you set once,
**[9:58]** maybe set ones by hand or set using cross-validation.
**[10:01]** And then beyond that, you are done.
**[10:03]** Its just a fixed function that the neural network computes in one of the layers,
**[10:07]** and there is actually nothing to learn.
**[10:09]** It's just a fixed function.
**[10:11]** So, that's it for pooling.
**[10:13]** You now know how to build convolutional layers and pooling layers.
**[10:15]** In the next video,
**[10:18]** let's see a more complex example of a ConvNet.
**[10:20]** One that will also allow us to introduce fully connected layers.
