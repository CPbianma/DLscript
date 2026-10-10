---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 4
section: Deep Neural Network
item_title: Why Deep Representations?
duration: 11 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/rz9xJ/why-deep-representations
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Why Deep Representations? — Transcript

**[0:00]** We've all been hearing that deep neural networks work really well for
**[0:03]** a lot of problems, and it's not just that they need to be big neural networks,
**[0:07]** is that specifically, they need to be deep or to have a lot of hidden layers.
**[0:10]** So why is that?
**[0:12]** Let's go through a couple examples and try to gain some intuition for
**[0:15]** why deep networks might work well.
**[0:17]** So first, what is a deep network computing?
**[0:22]** If you're building a system for face recognition or
**[0:25]** face detection, here's what a deep neural network could be doing.
**[0:29]** Perhaps you input a picture of a face then the first layer of the neural network
**[0:35]** you can think of as maybe being a feature detector or an edge detector.
**[0:40]** In this example, I'm plotting what a neural network with maybe 20 hidden units,
**[0:45]** might be trying to compute on this image.
**[0:48]** So the 20 hidden units visualized by these little square boxes.
**[0:52]** So for example, this little visualization represents a hidden unit that's
**[0:57]** trying to figure out where the edges of that orientation are in the image.
**[1:01]** And maybe this hidden unit might be trying to figure out
**[1:06]** where are the horizontal edges in this image.
**[1:09]** And when we talk about convolutional networks in a later course,
**[1:13]** this particular visualization will make a bit more sense.
**[1:16]** But the form, you can think of the first layer of the neural network as looking at the
**[1:19]** picture and trying to figure out where are the edges in this picture.
**[1:22]** Now, let's think about where the edges in this picture by grouping together
**[1:27]** pixels to form edges.
**[1:28]** It can then detect the edges and group edges together to form parts of faces.
**[1:34]** So for example, you might have a low neuron trying to see if it's finding an eye,
**[1:40]** or a different neuron trying to find that part of the nose.
**[1:44]** And so by putting together lots of edges,
**[1:47]** it can start to detect different parts of faces.
**[1:50]** And then, finally, by putting together different parts of faces,
**[1:56]** like an eye or a nose or an ear or a chin, it can then try to recognize or
**[2:01]** detect different types of faces.
**[2:03]** So intuitively, you can think of the earlier layers of the neural network as
**[2:07]** detecting simple functions, like edges.
**[2:10]** And then composing them together in the later layers of a neural network so
**[2:14]** that it can learn more and more complex functions.
**[2:17]** These visualizations will make more sense when we talk about convolutional nets.
**[2:23]** And one technical detail of this visualization,
**[2:26]** the edge detectors are looking in relatively small areas of an image,
**[2:29]** maybe very small regions like that.
**[2:31]** And then the facial detectors you can look at maybe much larger areas of image.
**[2:37]** But the main intuition you take away from this is just finding simple things
**[2:41]** like edges and then building them up.
**[2:43]** Composing them together to detect more complex things like an eye or a nose
**[2:47]** then composing those together to find even more complex things.
**[2:50]** And this type of simple to complex hierarchical representation,
**[2:55]** or compositional representation,
**[2:58]** applies in other types of data than images and face recognition as well.
**[3:04]** For example, if you're trying to build a speech recognition system,
**[3:07]** it's hard to revisualize speech but
**[3:09]** if you input an audio clip then maybe the first level of a neural network might
**[3:14]** learn to detect low level audio wave form features, such as is this tone going up?
**[3:20]** Is it going down?
**[3:21]** Is it white noise or sniffling sound like [SOUND].
**[3:26]** And what is the pitch?
**[3:27]** When it comes to that, detect low level wave form features like that.
**[3:31]** And then by composing low level wave forms,
**[3:34]** maybe you'll learn to detect basic units of sound.
**[3:37]** In linguistics they call phonemes.
**[3:40]** But, for example, in the word cat, the C is a phoneme, the A is a phoneme,
**[3:45]** the T is another phoneme.
**[3:46]** But learns to find maybe the basic units of sound and
**[3:49]** then composing that together maybe learn to recognize words in the audio.
**[3:54]** And then maybe compose those together,
**[3:58]** in order to recognize entire phrases or sentences.
**[4:02]** So deep neural network with multiple hidden layers might be able to have the earlier
**[4:07]** layers learn these lower level simple features and
**[4:10]** then have the later deeper layers then put together the simpler things it's detected
**[4:15]** in order to detect more complex things like recognize specific words or
**[4:19]** even phrases or sentences.
**[4:21]** The uttering in order to carry out speech recognition.
**[4:24]** And what we see is that whereas the other layers are computing, what seems like
**[4:30]** relatively simple functions of the input such as where the edge is, by the time
**[4:35]** you get deep in the network you can actually do surprisingly complex things.
**[4:41]** Such as detect faces or detect words or phrases or sentences.
**[4:44]** Some people like to make an analogy between deep neural networks and
**[4:48]** the human brain, where we believe, or neuroscientists believe,
**[4:52]** that the human brain also starts off detecting simple things like edges in what
**[4:57]** your eyes see then builds those up to detect more complex
**[5:00]** things like the faces that you see.
**[5:02]** I think analogies between deep learning and
**[5:05]** the human brain are sometimes a little bit dangerous.
**[5:08]** But there is a lot of truth to, this being how we think that human brain works and
**[5:13]** that the human brain probably detects simple things like edges first
**[5:18]** then put them together to from more and more complex objects and so that
**[5:22]** has served as a loose form of inspiration for some deep learning as well.
**[5:27]** We'll see a bit more about the human brain or
**[5:29]** about the biological brain in a later video this week.
**[5:35]** The other piece of intuition about why deep networks seem to
**[5:40]** work well is the following.
**[5:42]** So this result comes from circuit theory of which pertains the thinking
**[5:47]** about what types of functions you can compute with
**[5:50]** different AND gates, OR gates, NOT gates, basically logic gates.
**[5:53]** So informally, their functions compute with a relatively small but deep neural
**[5:58]** network and by small I mean the number of hidden units is relatively small.
**[6:03]** But if you try to compute the same function with a shallow network,
**[6:07]** so if there aren't enough hidden layers,
**[6:09]** then you might require exponentially more hidden units to compute.
**[6:13]** So let me just give you one example and illustrate this a bit informally.
**[6:18]** But let's say you're trying to compute the exclusive OR, or
**[6:21]** the parity of all your input features.
**[6:23]** So you're trying to compute X1, XOR, X2, XOR,
**[6:26]** X3, XOR, up to Xn if you have n or n X features.
**[6:33]** So if you build in XOR tree like this, so for us it computes the XOR of X1 and
**[6:39]** X2, then take X3 and X4 and compute their XOR.
**[6:44]** And technically, if you're just using AND or NOT gate, you might need a
**[6:48]** couple layers to compute the XOR function rather than just one layer, but
**[6:54]** with a relatively small circuit, you can compute the XOR, and so on.
**[6:58]** And then you can build, really, an XOR tree like so,
**[7:03]** until eventually, you have a circuit here that outputs, well, lets call this Y.
**[7:12]** The outputs of Y hat equals Y.
**[7:15]** The exclusive OR, the parity of all these input bits.
**[7:18]** So to compute XOR, the depth of the network will be on the order of log N.
**[7:24]** We'll just have an XOR tree.
**[7:27]** So the number of nodes or the number of circuit components or
**[7:30]** the number of gates in this network is not that large.
**[7:33]** You don't need that many gates in order to compute the exclusive OR.
**[7:38]** But now, if you are not allowed to use a neural network with multiple
**[7:43]** hidden layers with, in this case, order log and hidden layers,
**[7:48]** if you're forced to compute this function with just one hidden layer,
**[7:53]** so you have all these things going into the hidden units.
**[7:57]** And then these things then output Y.
**[8:02]** Then in order to compute this XOR function, this hidden layer
**[8:07]** will need to be exponentially large, because essentially,
**[8:12]** you need to exhaustively enumerate our 2 to the N possible configurations.
**[8:18]** So on the order of 2 to the N, possible configurations of the input
**[8:23]** bits that result in the exclusive OR being either 1 or 0.
**[8:27]** So you end up needing a hidden layer that is exponentially large in
**[8:32]** the number of bits.
**[8:33]** I think technically, you could do this with 2 to the N minus 1 hidden units.
**[8:38]** But that's the older 2 to the N, so it's going to be exponentially larger on the number of bits.
**[8:43]** So I hope this gives a sense that there are mathematical functions,
**[8:49]** that are much easier to compute with deep networks than with shallow networks.
**[8:55]** Actually, I personally found the result from circuit theory less useful for
**[9:01]** gaining intuitions, but this is one of the results that people often cite
**[9:05]** when explaining the value of having very deep representations.
**[9:11]** Now, in addition to this reasons for
**[9:13]** preferring deep neural networks, to be perfectly honest,
**[9:17]** I think the other reasons the term deep learning has taken off is just branding.
**[9:22]** This things just we call neural networks with a lot of hidden layers, but
**[9:26]** the phrase deep learning is just a great brand, it's just so deep.
**[9:31]** So I think that once that term caught on that really neural networks rebranded or
**[9:36]** neural networks with many hidden layers rebranded,
**[9:39]** help to capture the popular imagination as well.
**[9:42]** But regardless of the PR branding, deep networks do work well.
**[9:47]** Sometimes people go overboard and insist on using tons of hidden layers.
**[9:51]** But when I'm starting out a new problem, I'll often really start out with
**[9:55]** even logistic regression then try something with one or
**[9:58]** two hidden layers and use that as a hyper parameter.
**[10:01]** Use that as a parameter or hyper parameter that you tune in order to try to find
**[10:05]** the right depth for your neural network.
**[10:07]** But over the last several years there has been a trend toward people finding that
**[10:12]** for some applications, very, very deep neural networks here with maybe many
**[10:17]** dozens of layers sometimes, can sometimes be the best model for a problem.
**[10:22]** So that's it for the intuitions for why deep learning seems to work well.
**[10:27]** Let's now take a look at the mechanics of how to implement not just front
**[10:31]** propagation, but also back propagation.
