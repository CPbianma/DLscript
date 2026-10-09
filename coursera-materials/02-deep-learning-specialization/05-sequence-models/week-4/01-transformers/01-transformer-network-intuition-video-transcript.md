---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 4
section: Transformers
item_title: Transformer Network Intuition
duration: 5 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/YKatU/transformer-network-intuition
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Transformer Network Intuition — Transcript

**[0:03]** One of the most exciting developments in deep learning has been
**[0:07]** the transformer Network, or sometimes called Transformers.
**[0:11]** This is an architecture that has completely taken the NLP world by storm.
**[0:16]** And many of the most effective algorithms for
**[0:19]** NLP today are based on the transformer architecture.
**[0:24]** It is a relatively complex neural network architecture, but in this and
**[0:29]** the next three videos after this will go through it piece by piece.
**[0:34]** So that by the end of this next four videos, you have a good sense of how
**[0:38]** the transformer Network works and you'll be able to apply to your problems.
**[0:43]** As the complexity of your sequence task increases,
**[0:48]** so does the complexity of your model.
**[0:51]** We have started this course with the RNN and
**[0:54]** found that it had some problems with vanishing gradients,
**[0:59]** which made it hard to capture long range dependencies and sequences.
**[1:04]** We then looked at the GRU and then the LSTM model as a way to resolve many
**[1:10]** of those problems where you make use of gates to control the flow of information.
**[1:17]** And so each of these units had a few more computations.
**[1:22]** While these editions improved control over the flow of information,
**[1:26]** they also came with increased complexity.
**[1:30]** So as we move from our RNNs to GRU to LSTM ,the models became more complex.
**[1:39]** And all of these models are still sequential models in
**[1:44]** that they ingested the input,
**[1:46]** maybe the input sentence one word or one token at the time.
**[1:52]** And so, as as if each unit was like a bottleneck to the flow of information.
**[1:58]** Because to compute the output of this final unit, for example,
**[2:03]** you first have to compute the outputs of all of the units that come before.
**[2:08]** In this video, you learned about the transformer architecture, which allows you
**[2:13]** to run a lot more of these computations for an entire sequence in parallel.
**[2:18]** So you can ingest an entire sentence all at the same time,
**[2:22]** rather than just processing it one word at a time from left to right.
**[2:26]** The Transformer Network was published in a seminal paper by Ashish Vaswani
**[2:31]** , Noam Shazeer, Niki Parmar, Jakob Uszkoreit, Llion Jones,
**[2:36]** Aidan Gomez, Lukasz Kaiser and Illia Polosukhin.
**[2:39]** One of the inventors of the Transformer network, Lukasz Kaiser,
**[2:44]** is also co instructor of the NLP specialization with deep learning dot AI.
**[2:50]** So you can check that out as well when you're done with this deep learning
**[2:53]** specialization.
**[2:54]** The major innovation of the transformer architecture is
**[2:59]** combining the use of attention based representations and
**[3:04]** a CNN convolutional neural network style of processing.
**[3:10]** So an RNN may process one output at the time,
**[3:16]** and so maybe y(0) feeds in to them that you compute y(1) and
**[3:24]** then this is used to compute y(2).
**[3:30]** This is a very sequential way of processing tokens,
**[3:35]** and you might contrast this with a CNN or
**[3:38]** confident that can take input a lot of pixels.
**[3:43]** Yeah, or maybe a lot of words and
**[3:46]** can compute representations for them in parallel.
**[3:52]** So what you see in the Attention Network is a way of computing very rich,
**[3:58]** very useful representations of words.
**[4:01]** But with something more akin to this CNN style of parallel processing.
**[4:07]** To understand the attention network,
**[4:11]** there will be two key ideas will go through in the next few videos.
**[4:16]** The first is self attention.
**[4:19]** The goal of self attention is, if you have, say,
**[4:23]** a sentence of five words will end up computing five representations for
**[4:29]** these five words, was going to write A1,A2,A3, A4 and A5.
**[4:34]** And this will be an attention based way of computing representations for
**[4:40]** all the words in your sentence in parallel.
**[4:43]** Then multi headed attention is basically for loop over the self attention process.
**[4:50]** So you end up with multiple versions of these representations.
**[4:55]** And it turns out that these representations,
**[4:58]** which will be very rich representations, can be used for
**[5:02]** machine translation or other NLP tasks to great effectiveness.
**[5:07]** So in the next video, let's jump in to learn about self attention,
**[5:11]** to compute these rich representations.
**[5:14]** The video after that, we'll talk about multi headed attention.
**[5:18]** And then the final video on transforming networks will put all of these together so
**[5:22]** that you understand how the entire transformer architecture works into end.
**[5:27]** Let's go to the next video.
