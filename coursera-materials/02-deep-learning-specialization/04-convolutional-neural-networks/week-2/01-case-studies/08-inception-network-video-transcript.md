---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 2
section: Case Studies
item_title: Inception Network
duration: 9 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/piR0x/inception-network
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Inception Network — Transcript

**[0:00]** In a previous video,
**[0:01]** you've already seen all the basic building blocks of the Inception network.
**[0:06]** In this video, let's see how you can put these building blocks together
**[0:10]** to build your own Inception network.
**[0:13]** So the inception module takes as input the activation or
**[0:17]** the output from some previous layer.
**[0:20]** So let's say for the sake of argument this is 28 by 28 by 192,
**[0:25]** same as our previous video.
**[0:28]** The example we worked through in depth was the 1 by 1 followed by 5 by 5 layer.
**[0:36]** So maybe the 1 by 1 has 16 channels and
**[0:41]** then the 5 by 5 will output a 28 by 28 by, let's say, 32 channels.
**[0:49]** And this is the example we worked through on the last slide of the previous video.
**[0:54]** Then to save computation on your 3 by 3 convolution you can also do the same here.
**[1:02]** And then the 3 by 3 outputs, 28 by 28 by 1 by 28.
**[1:09]** And then maybe you want to consider a 1 by 1 convolution as well.
**[1:14]** There's no need to do a 1 by 1 conv followed by another 1 by 1 conv so
**[1:18]** there's just one step here and let's say these outputs 28 by 28 by 64.
**[1:27]** And then finally is the pulling layer.
**[1:34]** So here I'm going to do something funny.
**[1:35]** In order to really concatenate all of these outputs at the end
**[1:40]** we are going to use the same type of padding for pooling.
**[1:44]** So that the output height and width is still 28 by 28.
**[1:48]** So we can concatenate it with these other outputs.
**[1:53]** But notice that if you do max-pooling, even with same padding,
**[1:57]** 3 by 3 filter is tried at 1.
**[1:59]** The output here will be 28 by 28, By 192.
**[2:07]** It will have the same number of channels and
**[2:10]** the same depth as the input that we had here.
**[2:15]** So, this seems like is has a lot of channels.
**[2:19]** So what we're going to do is actually add one more 1 by 1 conv
**[2:23]** layer to then to what we saw in the one by one convilational video,
**[2:28]** to strengthen the number of channels.
**[2:31]** So it gets us down to 28 by 28 by let's say, 32.
**[2:37]** And the way you do that, is to use 32 filters,
**[2:44]** of dimension 1 by 1 by 192.
**[2:49]** So that's why the output dimension has a number of channels shrunk down to 32.
**[2:54]** So then we don't end up with the pulling layer
**[2:58]** taking up all the channels in the final output.
**[3:02]** And finally you take all of these blocks and you do channel concatenation.
**[3:08]** Just concatenate across this 64 plus 128 plus
**[3:12]** 32 plus 32 and this if you add it up this gives you
**[3:18]** a 28 by 28 by 256 dimension output.
**[3:24]** Concat is just this concatenating the blocks that we saw in the previous video.
**[3:33]** So this is one inception module, and what the inception network does,
**[3:39]** is, more or less, put a lot of these modules together.
**[3:45]** Here's a picture of the inception network, taken from the paper by Szegedy et al.
**[3:53]** And you notice a lot of repeated blocks in this.
**[3:56]** Maybe this picture looks really complicated.
**[3:58]** But if you look at one of the blocks there, that block is basically
**[4:03]** the inception module that you saw on the previous slide.
**[4:10]** And subject to little details I won't discuss, this is another inception block.
**[4:17]** This is another inception block.
**[4:19]** There's some extra max pooling layers here to change the dimension
**[4:24]** of the heightened width.
**[4:25]** But that's another inception block.
**[4:28]** And then there's another max put here to change the height and width but
**[4:31]** basically there's another inception block.
**[4:33]** But the inception network is just a lot of these blocks that you've learned about
**[4:37]** repeated to different positions of the network.
**[4:40]** But so you understand the inception block from the previous slide,
**[4:44]** then you understand the inception network.
**[4:49]** It turns out that there's one last detail to the inception network if we read
**[4:53]** the optional research paper.
**[4:55]** Which is that there are these additional side-branches that I just added.
**[5:01]** So what do they do?
**[5:03]** Well, the last few layers of the network is a fully connected layer
**[5:07]** followed by a softmax layer to try to make a prediction.
**[5:11]** What these side branches do is it takes some hidden layer and
**[5:15]** it tries to use that to make a prediction.
**[5:17]** So this is actually a softmax output and so is that.
**[5:22]** And this other side branch,
**[5:23]** again it is a hidden layer passes through a few layers like a few connected layers.
**[5:29]** And then has the softmax try to predict what's the output label.
**[5:35]** And you should think of this as maybe just another detail of the inception
**[5:38]** that's worked.
**[5:40]** But what is does is it helps to ensure that the features computed.
**[5:44]** Even in the heading units, even at intermediate layers.
**[5:48]** That they're not too bad for protecting the output cause of a image.
**[5:52]** And this appears to have a regularizing effect on the inception network and
**[5:56]** helps prevent this network from overfitting.
**[6:03]** And by the way, this particular Inception network
**[6:07]** was developed by authors at Google.
**[6:11]** Who called it GoogleNet, spelled like that, to pay homage to the network.
**[6:18]** That you learned about in an earlier video as well.
**[6:23]** So I think it's actually really nice that the Deep Learning Community is so
**[6:29]** collaborative.
**[6:30]** And that there's such strong healthy respect for
**[6:32]** each other's' work in the Deep Learning Learning community.
**[6:35]** FInally here's one fun fact.
**[6:37]** Where does the name inception network come from?
**[6:41]** The inception paper actually cites this meme for we need to go deeper.
**[6:47]** And this URL is an actual reference in the inception paper,
**[6:52]** which links to this image.
**[6:54]** And if you've seen the movie titled The Inception,
**[6:57]** maybe this meme will make sense to you.
**[7:00]** But the authors actually cite this meme as motivation for
**[7:05]** needing to build deeper new networks.
**[7:09]** And that's how they came up with the inception architecture.
**[7:12]** So I guess it's not often that research papers get to cite Internet memes
**[7:17]** in their citations.
**[7:19]** But in this case, I guess it worked out quite well.
**[7:23]** So to summarize, if you understand the inception module,
**[7:27]** then you understand the inception network.
**[7:29]** Which is largely the inception module repeated a bunch of times
**[7:33]** throughout the network.
**[7:35]** Since the development of the original inception module, the author and
**[7:40]** others have built on it and come up with other versions as well.
**[7:43]** So there are research papers on newer versions of the inception algorithm.
**[7:49]** And you sometimes see people use some of these later versions as well
**[7:53]** in their work, like inception v2, inception v3, inception v4.
**[7:57]** There's also an inception version.
**[7:59]** This combined with the resonant idea of having skipped connections,
**[8:02]** and that sometimes works even better.
**[8:05]** But all of these variations are built on the basic idea that you learned about
**[8:10]** this in the previous video of coming up with the inception module and
**[8:14]** then stacking up a bunch of them together.
**[8:17]** And with these videos you should be able to read and
**[8:20]** understand, I think, the inception paper,
**[8:23]** as well as maybe some of the papers describing the later derivation as well.
**[8:28]** So that's it,
**[8:30]** you've gone through quite a lot of specialized neural network architectures.
**[8:34]** In the next video, I want to start showing you some more practical advice on how you
**[8:39]** actually use these algorithms to build your own computer vision system.
**[8:43]** Let's go on to the next video.
