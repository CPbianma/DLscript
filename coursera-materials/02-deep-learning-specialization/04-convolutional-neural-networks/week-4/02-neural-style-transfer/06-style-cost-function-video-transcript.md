---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 4
section: Neural Style Transfer
item_title: Style Cost Function
duration: 13 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/AzcCW/style-cost-function
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Style Cost Function — Transcript

**[0:00]** In the last video, you saw how to define
**[0:02]** the content cost function for the neural style transfer.
**[0:05]** Next, let's take a look at the style cost function.
**[0:09]** So, what is the style of an image mean?
**[0:12]** Let's say you have an input image like this,
**[0:14]** they used to seeing a convnet like that,
**[0:16]** compute features that there's different layers.
**[0:20]** And let's say you've chosen some layer L,
**[0:22]** maybe that layer to define the measure of the style of an image.
**[0:29]** What we need to do is define the style as the correlation between
**[0:34]** activations across different channels in this layer L activation.
**[0:40]** So here's what I mean by that.
**[0:42]** Let's say you take that layer L activation.
**[0:44]** So this is going to be nh by nw by nc block of activations,
**[0:50]** and we're going to ask how correlated are the activations across different channels.
**[0:55]** So to explain what I mean by this may be slightly cryptic phrase,
**[0:59]** let's take this block of activations
**[1:02]** and let me shade the different channels by a different colors.
**[1:06]** So in this below example,
**[1:08]** we have say five channels and which is why I have five shades of color here.
**[1:14]** In practice, of course,
**[1:15]** in neural network we usually have a lot more channels than five,
**[1:18]** but using just five makes it drawing easier.
**[1:22]** But to capture the style of an image,
**[1:24]** what you're going to do is the following.
**[1:26]** Let's look at the first two channels.
**[1:28]** Let's see for the red channel and the yellow channel and say
**[1:32]** how correlated are activations in these first two channels.
**[1:37]** So, for example, in the lower right hand corner,
**[1:40]** you have some activation in the first channel and some activation in the second channel.
**[1:45]** So that gives you a pair of numbers.
**[1:47]** And what you do is look at different positions across
**[1:51]** this block of activations and just look at those two pairs of numbers,
**[1:55]** one in the first channel, the red channel,
**[1:57]** one in the yellow channel, the second channel.
**[2:00]** And you just look at these two pairs of numbers and
**[2:02]** see when you look across all of these positions,
**[2:04]** all of these nh by nw positions,
**[2:07]** how correlated are these two numbers.
**[2:10]** So, why does this capture style?
**[2:12]** Let's look another example.
**[2:14]** Here's one of the visualizations from the earlier video.
**[2:17]** This comes from again the paper by
**[2:20]** Matthew Zeiler and Rob Fergus that I have reference earlier.
**[2:23]** And let's say for the sake of arguments,
**[2:25]** that the red neuron corresponds to,
**[2:28]** and let's say for the sake of arguments,
**[2:30]** that the red channel corresponds to this neurons so we're trying to figure out if there's
**[2:36]** this little vertical texture in
**[2:40]** a particular position in the nh and let's say that this second channel,
**[2:46]** this yellow second channel corresponds to this neuron,
**[2:51]** which is vaguely looking for orange colored patches.
**[2:56]** What does it mean for these two channels to be highly correlated?
**[3:01]** Well, if they're highly correlated what that means is whatever part of
**[3:04]** the image has this type of subtle vertical texture,
**[3:08]** that part of the image will probably have these orange-ish tint.
**[3:12]** And what does it mean for them to be uncorrelated?
**[3:15]** Well, it means that whenever there is this vertical texture,
**[3:19]** it's probably won't have that orange-ish tint.
**[3:22]** And so the correlation tells you which of
**[3:25]** these high level texture components tend to occur or not occur together
**[3:31]** in part of an image and that's the degree of correlation that gives you
**[3:35]** one way of measuring how often these different high level features,
**[3:40]** such as vertical texture or this orange tint or other things as well,
**[3:45]** how often they occur and how often they occur
**[3:48]** together and don't occur together in different parts of an image.
**[3:51]** And so, if we use the degree of correlation between channels as a measure of the style,
**[3:57]** then what you can do is measure the degree to which in your generated image,
**[4:02]** this first channel is correlated or uncorrelated with
**[4:06]** the second channel and that will tell you in the generated image how often
**[4:12]** this type of vertical texture occurs or doesn't
**[4:14]** occur with this orange-ish tint and this gives you a measure
**[4:18]** of how similar is the style of the generated image to the style of the input style image.
**[4:25]** So let's now formalize this intuition.
**[4:28]** So what you can to do is given an image computes something called a style matrix,
**[4:34]** which will measure all those correlations we talks about on the last slide.
**[4:38]** So, more formally, let's let a superscript l, subscript i,
**[4:44]** j,k denote the activation at position i,j,k in
**[4:47]** hidden layer l. So i indexes into the height,
**[4:53]** j indexes into the width,
**[4:54]** and k indexes across the different channels.
**[4:58]** So, in the previous slide,
**[5:00]** we had five channels that k will index across those five channels.
**[5:05]** So what the style matrix will do is you're going to compute a matrix clauses
**[5:09]** G superscript square bracketed l. This is going to be an nc by nc dimensional matrix,
**[5:17]** so it'd be a square matrix.
**[5:18]** Remember you have nc channels and so you have an
**[5:23]** nc by nc dimensional matrix in order to measure how correlated each pair of them is.
**[5:29]** So particular G, l, k,
**[5:32]** k prime will measure how correlated are the activations in
**[5:36]** channel k compared to the activations in channel k prime.
**[5:41]** Well here, k and k prime will range from 1 through nc,
**[5:46]** the number of channels they're all up in that layer.
**[5:49]** So more formally, the way you compute G,
**[5:55]** l and I'm just going to write down the formula for computing one elements.
**[6:00]** So the k, k prime elements of this.
**[6:03]** This is going to be sum of a i,
**[6:06]** sum of a j,
**[6:08]** of deactivation and that layer (i, j,
**[6:13]** k) times the activation at (i, j, k) prime.
**[6:22]** So, here, remember i and j index across to a different positions in the block,
**[6:27]** indexes over the height and width.
**[6:30]** So i is the sum from one to nh and j is a sum from one to nw
**[6:39]** and k here and k prime index over the channel so
**[6:45]** k and k prime range from one to
**[6:47]** the total number of channels in that layer of the neural network.
**[6:51]** So all this is doing
**[6:55]** is summing over the different positions that the image over the height and width and just
**[7:00]** multiplying the activations together of
**[7:03]** the channels k and k prime and that's the definition of G,k,k prime.
**[7:08]** And you do this for every value of k and k prime to compute this matrix G,
**[7:14]** also called the style matrix.
**[7:17]** And so notice that if both of these activations tend to be lashed together,
**[7:23]** then G, k, k prime will be large,
**[7:26]** whereas if they are uncorrelated then g,k,
**[7:28]** k prime might be small.
**[7:30]** And technically, I've been using
**[7:32]** the term correlation to convey intuition but this is actually
**[7:36]** the unnormalized cross of the areas because we're not
**[7:40]** subtracting out the mean and this is just multiplied by these elements directly.
**[7:46]** So this is how you compute the style of an image.
**[7:50]** And you'd actually do this for both the style image s,n for
**[7:54]** the generated image G. So just to distinguish that this is the style image,
**[8:01]** maybe let me add a round bracket S there,
**[8:07]** just to denote that this is the style image for the image
**[8:10]** S and those are the activations on the image
**[8:12]** S. And what you do is then compute the same thing for the generated image.
**[8:21]** So it's really the same thing summarized sum of a j, a, i,
**[8:28]** j, k, l, a,
**[8:32]** i, j,k,l and the summation indices are the same.
**[8:36]** Let's follow this and you want to just denote this is for the generated image,
**[8:46]** I'll just put the round brackets G there.
**[8:51]** So, now, you have two matrices they capture what is the style with
**[8:55]** the image s and what is the style of the image G. And,
**[8:59]** by the way, we've been using the alphabet capital G to denote these matrices.
**[9:05]** In linear algebra, these are also called the
**[9:09]** grand matrix of these in called grand matrices but in this video,
**[9:14]** I'm just going to use the term style matrix because this term grand
**[9:17]** matrix that most of these using capital G to denote these matrices.
**[9:23]** Finally, the cost function,
**[9:26]** the style cost function.
**[9:28]** If you're doing this on layer l between S and G,
**[9:34]** you can now define that to be
**[9:37]** just the difference
**[9:44]** between these two matrices,
**[9:48]** G l, G square and these are matrices.
**[9:54]** So just take it from the previous one.
**[9:55]** This is just the sum of squares of the element wise differences between
**[10:00]** these two matrices and just divides this out this is going to be sum over k,
**[10:07]** sum over k prime of these differences of s, k,
**[10:12]** k prime minus G l,
**[10:17]** G, k, k prime and then the sum of square of the elements.
**[10:24]** The authors actually used this for the normalization constants two times of nh,
**[10:32]** nw, in that layer,
**[10:34]** nc in that layer and I'll square this and you can put this up here as well.
**[10:40]** But a normalization constant doesn't matter that much because this
**[10:43]** causes multiplied by some hyperparameter b anyway.
**[10:47]** So just to finish up,
**[10:48]** this is the style cost function defined
**[10:51]** using layer l and as you saw on the previous slide,
**[10:55]** this is basically the Frobenius norm between the two star matrices computed on
**[11:02]** the image s and on the image G
**[11:05]** Frobenius on squared and never by the just low normalization constants,
**[11:10]** which isn't that important.
**[11:13]** And, finally, it turns out that you get more visually pleasing results if you
**[11:18]** use the style cost function from multiple different layers.
**[11:23]** So, the overall style cost function,
**[11:27]** you can define as sum over
**[11:31]** all the different layers of the style cost function for that layer.
**[11:37]** We should define the book weighted by some set of parameters,
**[11:41]** by some set of additional hyperparameters,
**[11:44]** which we'll denote as lambda l here.
**[11:46]** So what it does is allows you to use different layers in a neural network.
**[11:51]** Well of the early ones,
**[11:52]** which measure relatively simpler low level features
**[11:55]** like edges as well as some later layers,
**[11:59]** which measure high level features and cause a neural network to take
**[12:03]** both low level and high level correlations into account when computing style.
**[12:08]** And, in the following exercise,
**[12:10]** you gain more intuition about what might be
**[12:13]** reasonable choices for this type of parameter lambda as well.
**[12:19]** And so just to wrap this up,
**[12:20]** you can now define the overall cost function
**[12:24]** as alpha times the content cost between c and G plus
**[12:30]** beta times the style cost between s and G and then just create in the sense
**[12:37]** or a more sophisticated optimization algorithm if you want
**[12:40]** in order to try to find an image G that normalize,
**[12:44]** that tries to minimize this cost function j of G. And if you do that,
**[12:49]** you can generate pretty good looking neural artistic
**[12:53]** and if you do that you'll be able to generate some pretty nice novel artwork.
**[12:59]** So that's it for neural style transfer and I hope you have
**[13:02]** fun implementing it in this week's printing exercise.
**[13:05]** Before wrapping up this week,
**[13:06]** there's just one last thing I want to share of you,
**[13:08]** which is how to do convolutions over
**[13:11]** 1D or 3D data rather than over only 2D images. Let's go into the last video.
