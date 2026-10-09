---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 2
section: Case Studies
item_title: Classic Networks
duration: 18 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/MmYe2/classic-networks
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Classic Networks — Transcript

**[0:00]** In this video, you'll learn about some of
**[0:02]** the classic neural network architecture starting with LeNet-5,
**[0:06]** and then AlexNet, and then VGGNet. Let's take a look.
**[0:10]** Here is the LeNet-5 architecture.
**[0:12]** You start off with an image which say,
**[0:15]** 32 by 32 by 1.
**[0:17]** And the goal of LeNet-5 was to recognize handwritten digits,
**[0:21]** so maybe an image of a digits like that.
**[0:25]** And LeNet-5 was trained on grayscale images,
**[0:28]** which is why it's 32 by 32 by 1.
**[0:32]** This neural network architecture is actually quite
**[0:34]** similar to the last example you saw last week.
**[0:38]** In the first step,
**[0:39]** you use a set of six,
**[0:41]** 5 by 5 filters with a stride of one because you use
**[0:45]** six filters you end up with a 20 by 20 by 6 over there.
**[0:50]** And with a stride of one and no padding,
**[0:52]** the image dimensions reduces from 32 by 32 down to 28 by 28.
**[0:58]** Then the LeNet neural network applies pooling.
**[1:02]** And back then when this paper was written,
**[1:04]** people use average pooling much more.
**[1:07]** If you're building a modern variant,
**[1:09]** you probably use max pooling instead.
**[1:12]** But in this example,
**[1:13]** you average pool and with a filter width two and a stride of two,
**[1:17]** you wind up reducing the dimensions,
**[1:20]** the height and width by a factor of two,
**[1:22]** so we now end up with a 14 by 14 by 6 volume.
**[1:28]** I guess the height and width of these volumes aren't entirely drawn to scale.
**[1:32]** Now technically, if I were drawing these volumes to scale,
**[1:35]** the height and width would be stronger by a factor of two.
**[1:38]** Next, you apply another convolutional layer.
**[1:41]** This time you use a set of 16 filters,
**[1:44]** the 5 by 5, so you end up with 16 channels to the next volume.
**[1:48]** And back when this paper was written in 1998,
**[1:52]** people didn't really use padding or you always using valid convolutions,
**[1:57]** which is why every time you apply convolutional layer,
**[1:59]** they heightened with strengths.
**[2:01]** So that's why, here,
**[2:03]** you go from 14 to 14 down to 10 by 10.
**[2:06]** Then another pooling layer,
**[2:08]** so that reduces the height and width by a factor of two,
**[2:11]** then you end up with 5 by 5 over here.
**[2:13]** And if you multiply all these numbers 5 by 5 by 16,
**[2:16]** this multiplies up to 400.
**[2:20]** That's 25 times 16 is 400.
**[2:24]** And the next layer is then a fully connected layer that fully connects each of
**[2:29]** these 400 nodes with every one of 120 neurons,
**[2:36]** so there's a fully connected layer.
**[2:38]** And sometimes, that would draw out exclusively
**[2:41]** a layer with 400 nodes, I'm skipping that here.
**[2:46]** There's a fully connected layer and then another a fully connected layer.
**[2:49]** And then the final step is it uses
**[2:51]** these essentially 84 features and uses it with one final output.
**[2:57]** I guess you could draw one more node here to make a prediction for ŷ.
**[3:01]** And ŷ took on 10 possible values
**[3:04]** corresponding to recognising each of the digits from 0 to 9.
**[3:09]** A modern version of this neural network,
**[3:11]** we'll use a softmax layer with a 10 way classification output.
**[3:17]** Although back then, LeNet-5 actually use a different classifier at the output layer,
**[3:23]** one that's useless today.
**[3:25]** So this neural network was small by modern standards,
**[3:29]** had about 60,000 parameters.
**[3:32]** And today, you often see neural networks with
**[3:35]** anywhere from 10 million to 100 million parameters,
**[3:39]** and it's not unusual to see networks that are
**[3:41]** literally about a thousand times bigger than this network.
**[3:45]** But one thing you do see is that as you go deeper in a network,
**[3:49]** so as you go from left to right,
**[3:51]** the height and width tend to go down.
**[3:55]** So you went from 32 by 32, to 28 to 14,
**[3:57]** to 10 to 5, whereas the number of channels does increase.
**[4:03]** It goes from 1 to 6 to 16 as you go deeper into the layers of the network.
**[4:11]** One other pattern you see in this neural network that's still often repeated today is
**[4:15]** that you might have some one or more conu layers followed by pooling layer,
**[4:20]** and then one or sometimes more than one conu layer followed by a pooling layer,
**[4:25]** and then some fully connected layers and then the outputs.
**[4:29]** So this type of arrangement of layers is quite common.
**[4:34]** Now finally, this is maybe only for those of you that want to try reading the paper.
**[4:39]** There are a couple other things that were different.
**[4:41]** The rest of this slide,
**[4:43]** I'm going to make a few more advanced comments,
**[4:47]** only for those of you that want to try to read this classic paper.
**[4:52]** And so, everything I'm going to write in red,
**[4:54]** you can safely skip on the slide,
**[4:57]** and there's maybe an interesting historical footnote
**[5:00]** that is okay if you don't follow fully.
**[5:04]** So it turns out that if you read the original paper, back then,
**[5:07]** people used sigmoid and tanh nonlinearities,
**[5:12]** and people weren't using value nonlinearities back then.
**[5:16]** So if you look at the paper, you see sigmoid and tanh referred to.
**[5:20]** And there are also some funny ways about
**[5:23]** this network was wired that is funny by modern standards.
**[5:26]** So for example, you've seen how if you have a nh by nw by nc network with
**[5:33]** nc channels then you use f by f by nc dimensional filter,
**[5:40]** where everything looks at every one of these channels.
**[5:44]** But back then, computers were much slower.
**[5:47]** And so to save on computation as well as some parameters,
**[5:50]** the original LeNet-5 had some crazy complicated way
**[5:53]** where different filters would look at different channels of the input block.
**[5:58]** And so the paper talks about those details,
**[6:00]** but the more modern implementation wouldn't have that type of complexity these days.
**[6:07]** And then one last thing that was done back then I guess but isn't really done right
**[6:12]** now is that the original LeNet-5 had a non-linearity after pooling,
**[6:19]** and I think it actually uses sigmoid non-linearity after the pooling layer.
**[6:25]** So if you do read this paper,
**[6:27]** and this is one of the harder ones to read than
**[6:29]** the ones we'll go over in the next few videos,
**[6:32]** the next one might be an easy one to start with.
**[6:34]** Most of the ideas on the slide I just tried in sections two and three of the paper,
**[6:40]** and later sections of the paper talked about some other ideas.
**[6:44]** It talked about something called the graph transformer network,
**[6:47]** which isn't widely used today.
**[6:49]** So if you do try to read this paper,
**[6:50]** I recommend focusing really on section two which talks about this architecture,
**[6:55]** and maybe take a quick look at section three
**[6:58]** which has a bunch of experiments and results, which is pretty interesting.
**[7:01]** The second example of a neural network I want to show you is AlexNet,
**[7:06]** named after Alex Krizhevsky, who was the first author of the paper describing this work.
**[7:12]** The other author's were Ilya Sutskever and Geoffrey Hinton.
**[7:16]** So, AlexNet input starts with 227 by 227 by 3 images.
**[7:21]** And if you read the paper,
**[7:22]** the paper refers to 224 by 224 by 3 images.
**[7:27]** But if you look at the numbers,
**[7:28]** I think that the numbers make sense only of actually 227 by 227.
**[7:33]** And then the first layer applies a set of 96 11 by 11 filters with a stride of four.
**[7:40]** And because it uses a large stride of four,
**[7:42]** the dimensions shrinks to 55 by 55.
**[7:45]** So roughly, going down by a factor of 4 because of a large stride.
**[7:50]** And then it applies max pooling with a 3 by 3 filter.
**[7:55]** So f equals three and a stride of two.
**[7:57]** So this reduces the volume to 27 by 27 by 96,
**[8:04]** and then it performs a 5 by 5 same convolution,
**[8:08]** same padding, so you end up with 27 by 27 by 276.
**[8:14]** Max pooling again, this reduces the height and width to 13.
**[8:20]** And then another same convolution, so same padding.
**[8:23]** So it's 13 by 13 by now 384 filters.
**[8:29]** And then 3 by 3, same convolution again, gives you that.
**[8:35]** Then 3 by 3, same convolution, gives you that.
**[8:39]** Then max pool, brings it down to 6 by 6 by 256.
**[8:45]** If you multiply all these numbers,6 times 6 times 256, that's 9216.
**[8:52]** So we're going to unroll this into 9216 nodes.
**[8:56]** And then finally, it has a few fully connected layers.
**[9:00]** And then finally, it uses a softmax to output
**[9:04]** which one of 1000 causes the object could be.
**[9:09]** So this neural network actually had a lot of similarities to LeNet,
**[9:16]** but it was much bigger.
**[9:20]** So whereas the LeNet-5 from previous slide had about 60,000 parameters,
**[9:27]** this AlexNet that had about 60 million parameters.
**[9:31]** And the fact that they could take
**[9:34]** pretty similar basic building blocks that
**[9:36]** have a lot more hidden units and training on a lot more data,
**[9:40]** they trained on the image that dataset that
**[9:42]** allowed it to have a just remarkable performance.
**[9:46]** Another aspect of this architecture that made it much
**[9:49]** better than LeNet was using the value activation function.
**[9:53]** And then again, just if you read the bay paper
**[9:56]** some more advanced details that you don't really need
**[9:59]** to worry about if you don't read the paper, one is that,
**[10:01]** when this paper was written,
**[10:03]** GPUs was still a little bit slower,
**[10:06]** so it had a complicated way of training on two GPUs.
**[10:11]** And the basic idea was that,
**[10:13]** a lot of these layers was actually split across two different GPUs and there was
**[10:18]** a thoughtful way for when the two GPUs would communicate with each other.
**[10:23]** And the paper also,
**[10:25]** the original AlexNet architecture also had another set of a layer
**[10:29]** called a Local Response Normalization.
**[10:34]** And this type of layer isn't really used much,
**[10:36]** which is why I didn't talk about it.
**[10:38]** But the basic idea of Local Response Normalization is,
**[10:42]** if you look at one of these blocks,
**[10:44]** one of these volumes that we have on top,
**[10:46]** let's say for the sake of argument, this one,
**[10:49]** 13 by 13 by 256,
**[10:52]** what Local Response Normalization,
**[10:54]** (LRN) does, is you look at one position.
**[10:57]** So one position height and width,
**[10:59]** and look down this across all the channels,
**[11:02]** look at all 256 numbers and normalize them.
**[11:07]** And the motivation for this Local Response Normalization was that for
**[11:10]** each position in this 13 by 13 image,
**[11:14]** maybe you don't want too many neurons with a very high activation.
**[11:20]** But subsequently, many researchers have found that this doesn't help that much so this is
**[11:25]** one of those ideas I guess I'm drawing in red
**[11:27]** because it's less important for you to understand this one.
**[11:31]** And in practice, I don't really use
**[11:33]** local response normalizations really in the networks language trained today.
**[11:38]** So if you are interested in the history of deep learning,
**[11:41]** I think even before AlexNet,
**[11:43]** deep learning was starting to gain traction in speech recognition and a few other areas,
**[11:48]** but it was really just paper that convinced a lot of
**[11:52]** the computer vision community to take a serious look at
**[11:56]** deep learning to convince them that deep learning really works in computer vision.
**[12:00]** And then it grew on to have a huge impact not
**[12:02]** just in computer vision but beyond computer vision as well.
**[12:05]** And if you want to try reading some of these papers
**[12:08]** yourself and you really don't have to for this course,
**[12:11]** but if you want to try reading some of these papers,
**[12:14]** this one is one of the easier ones to read so this might be a good one to take a look at.
**[12:19]** So whereas AlexNet had a relatively complicated architecture,
**[12:23]** there's just a lot of hyperparameters, right?
**[12:25]** Where you have all these numbers
**[12:28]** that Alex Krizhevsky and his co-authors had to come up with.
**[12:33]** Let me show you a third and final example on this video called the VGG or VGG-16 network.
**[12:39]** And a remarkable thing about the VGG-16 net is that they said,
**[12:44]** instead of having so many hyperparameters,
**[12:46]** let's use a much simpler network where you focus on just having conv-layers
**[12:52]** that are just three-by-three filters with a stride of one and always use same padding.
**[12:58]** And make all your max pulling layers two-by-two with a stride of two.
**[13:03]** And so, one very nice thing about
**[13:06]** the VGG network was it really simplified this neural network architectures.
**[13:12]** So, let's go through the architecture.
**[13:14]** So, you solve up with an image for them and then the first two layers are convolutions,
**[13:19]** which are therefore these three-by-three filters.
**[13:24]** And in the first two layers use 64 filters.
**[13:27]** You end up with a 224 by 224 because using same convolutions and then with 64 channels.
**[13:35]** So because VGG-16 is a relatively deep network,
**[13:39]** am going to not draw all the volumes here.
**[13:42]** So what this little picture denotes is what we would previously have
**[13:46]** drawn as this 224 by 224 by 3.
**[13:50]** And then a convolution that results in I guess a 224
**[13:55]** by 224 by 64 is to be drawn as a deeper volume,
**[14:00]** and then another layer that results in 224 by 224 by 64.
**[14:07]** So this conv64 times two represents that you're doing two conv-layers with 64 filters.
**[14:15]** And as I mentioned earlier,
**[14:17]** the filters are always three-by-three
**[14:20]** with a stride of one and they are always same convolutions.
**[14:24]** So rather than drawing all these volumes,
**[14:26]** am just going to use text to represent this network.
**[14:28]** Next, then uses are pulling layer,
**[14:31]** so the pulling layer will reduce.
**[14:33]** I think it goes from 224 by 224 down to what?
**[14:36]** Right. Goes to 112 by 112 by 64.
**[14:40]** And then it has a couple more conv-layers.
**[14:44]** So this means it has 128 filters and because these are the same convolutions,
**[14:50]** let's see what is the new dimension.
**[14:52]** Right? It will be 112 by 112 by 128 and then
**[14:57]** pulling layer so you can figure out what's the new dimension of that.
**[15:02]** And now, three conv-layers with
**[15:07]** 256 filters to the pulling layer and then a few more conv-layers,
**[15:14]** pulling layer, more conv-layers, pulling layer.
**[15:18]** And then it takes this final 7 by 7 by 512 these in to fully connected layer,
**[15:26]** fully connected with four thousand ninety six
**[15:30]** units and then a softmax output one of a thousand classes.
**[15:36]** By the way, the 16 in the VGG-16
**[15:39]** refers to the fact that this has 16 layers that have weights.
**[15:45]** And this is a pretty large network,
**[15:47]** this network has a total of about 138 million parameters.
**[15:52]** And that's pretty large even by modern standards.
**[15:55]** But the simplicity of the VGG-16 architecture made it quite appealing.
**[16:00]** You can tell his architecture is really quite uniform.
**[16:03]** There is a few conv-layers followed by a pulling layer,
**[16:07]** which reduces the height and width, right?
**[16:09]** So the pulling layers reduce the height and width.
**[16:13]** You have a few of them here.
**[16:15]** But then also, if you look at the number of filters in the conv-layers,
**[16:20]** here you have 64 filters and then you double to 128 double to 256 doubles to 512.
**[16:28]** And then I guess the authors thought 512 was big enough and did double on the game here.
**[16:33]** But this sort of roughly doubling on every step,
**[16:36]** or doubling through every stack of conv-layers was
**[16:39]** another simple principle used to design the architecture of this network.
**[16:45]** And so I think the relative uniformity of
**[16:48]** this architecture made it quite attractive to researchers.
**[16:52]** The main downside was that it was
**[16:54]** a pretty large network in terms of the number of parameters you had to train.
**[16:58]** And if you read the literature,
**[17:00]** you sometimes see people talk about the VGG-19,
**[17:04]** that is an even bigger version of this network.
**[17:08]** And you could see the details in the paper cited at
**[17:11]** the bottom by Karen Simonyan and Andrew Zisserman.
**[17:16]** But because VGG-16 does almost as well as VGG-19.
**[17:20]** A lot of people will use VGG-16.
**[17:23]** But the thing I liked most about this was that,
**[17:26]** this made this pattern of how,
**[17:28]** as you go deeper and height and width goes down,
**[17:31]** it just goes down by a factor of two each time for
**[17:33]** the pulling layers whereas the number of channels increases.
**[17:36]** And here roughly goes up by a factor of two every time you have a new set of conv-layers.
**[17:42]** So by making the rate at which it goes down and that go up very systematic,
**[17:49]** I thought this paper was very attractive from that perspective.
**[17:54]** So that's it for the three classic architecture's.
**[17:57]** If you want, you should really now read some of these papers.
**[18:00]** I recommend starting with the AlexNet paper followed by the VGG net paper and
**[18:05]** then the LeNet paper is a bit harder to
**[18:07]** read but it is a good classic once you go over that.
**[18:09]** But next, let's go beyond these classic networks and look at some even more advanced,
**[18:14]** even more powerful neural network architectures. Let's go onto the next video.
