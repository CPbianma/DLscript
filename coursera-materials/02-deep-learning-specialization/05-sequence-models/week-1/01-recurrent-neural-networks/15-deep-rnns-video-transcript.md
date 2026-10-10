---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 1
section: Recurrent Neural Networks
item_title: Deep RNNs
duration: 5 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/ehs0S/deep-rnns
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Deep RNNs — Transcript

**[0:00]** The different versions of RNNs you've seen so far
**[0:02]** will already work quite well by themselves.
**[0:05]** But for learning very complex functions sometimes is useful to stack
**[0:09]** multiple layers of RNNs together to build even deeper versions of these models.
**[0:13]** In this video, you'll see how to build these deeper RNNs. Let's take a look.
**[0:19]** So you remember for a standard neural network,
**[0:20]** you will have an input X.
**[0:23]** And then that's stacked to some hidden layer and so that might have activations of say,
**[0:29]** a1 for the first hidden layer,
**[0:33]** and then that's stacked to the next layer with activations a2,
**[0:36]** then maybe another layer,
**[0:40]** activations a3 and then you make a prediction ŷ.
**[0:42]** So a deep RNN is a bit like this,
**[0:45]** by taking this network that I just drew by hand and
**[0:47]** unrolling that in time. So let's take a look.
**[0:51]** So here's the standard RNN that you've seen so far.
**[0:54]** But I've changed the notation a little bit which is that,
**[0:56]** instead of writing this as a0 for the activation time zero,
**[1:01]** I've added this square bracket 1 to denote that this is for layer one.
**[1:06]** So the notation we're going to use is a[l] to denote that it's an activation
**[1:12]** associated with layer l and then <t> to denote that that's associated over time t.
**[1:20]** So this will have an activation on a,
**[1:23]** this would be first layer type one, this would be first layer type two, first layer type three, first layer type four.
**[1:35]** And then we can just stack these things on
**[1:38]** top and so this will be a new network with three hidden layers.
**[1:45]** So let's look at an example of how this value is computed.
**[1:51]** So a[2] 3 has two inputs.
**[1:56]** It has the input coming from the bottom,
**[1:58]** and there's the input coming from the left.
**[2:03]** So the computer has an activation function g applied to a way matrix.
**[2:09]** This is going to be Wa because computing an a quantity, an activation quantity.
**[2:14]** And for the second layer,
**[2:16]** and so I'm going to give this a[2]<2>,
**[2:23]** there's that thing, comma a[1] 3, there's that thing,
**[2:31]** plus ba associated to the second layer.
**[2:34]** And that's how you get that activation value.
**[2:37]** And so the same parameters Wa[2] and
**[2:41]** ba[2] are used for every one of these computations at this layer.
**[2:48]** Whereas, in contrast, the first layer would have its own parameters Wa[1] and ba[1].
**[2:57]** So whereas for standard RNNs like the one on the left,
**[3:01]** you know we've seen neural networks that are very,
**[3:03]** very deep, maybe over 100 layers.
**[3:05]** For RNNs, having three layers is already quite a lot.
**[3:10]** Because of the temporal dimension,
**[3:12]** these networks can already get quite big even if you have just a small handful of layers.
**[3:17]** And you don't usually see these stacked up to be like 100 layers.
**[3:22]** One thing you do see sometimes is
**[3:26]** that you have recurrent layers that are stacked on top of each other.
**[3:30]** But then you might take the output here, let's get rid of this,
**[3:32]** and then just have a bunch of deep layers that are not connected
**[3:36]** horizontally but have a deep network here that then finally predicts y<1>.
**[3:41]** And you can have the same deep network here that predicts y<2>.
**[3:48]** So this is a type of network architecture that we're seeing a little bit more where you
**[3:51]** have three recurrent units that connected in time,
**[3:55]** followed by a network,
**[3:56]** followed by a network after that,
**[3:58]** as we seen for y<3> and y<4>, of course.
**[4:00]** There's a deep network, but that does not have the horizontal connections.
**[4:04]** So that's one type of architecture we seem to be seeing more of.
**[4:08]** And quite often, these blocks don't just have to be standard RNN,
**[4:12]** the simple RNN model.
**[4:14]** They can also be GRU blocks LSTM blocks.
**[4:17]** And finally, you can also build deep versions of the bidirectional RNN.
**[4:24]** Because deep RNNs are quite computationally expensive to train,
**[4:30]** there's often a large temporal extent already,
**[4:32]** though you just don't see as many deep recurrent layers.
**[4:37]** This has, I guess, three deep recurrent layers that are connected in time.
**[4:42]** You don't see as many deep recurrent layers as you would see
**[4:45]** in a number of layers in a deep conventional neural network.
**[4:48]** So that's it for deep RNNs.
**[4:51]** With what you've seen this week,
**[4:53]** ranging from the basic RNN,
**[4:55]** the basic recurrent unit,
**[4:57]** to the GRU, to the LSTM, to the bidirectional RNN,
**[4:58]** to the deep versions of this that you just saw,
**[5:01]** you now have a very rich toolbox for constructing
**[5:04]** very powerful models for learning sequence models.
**[5:08]** I hope you enjoyed this week's videos.
**[5:11]** Best of luck with the problem exercises and I look forward to seeing you next week.
