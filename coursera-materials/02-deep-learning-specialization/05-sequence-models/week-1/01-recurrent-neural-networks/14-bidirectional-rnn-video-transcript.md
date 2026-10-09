---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 1
section: Recurrent Neural Networks
item_title: Bidirectional RNN
duration: 8 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/fyXnn/bidirectional-rnn
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Bidirectional RNN — Transcript

**[0:00]** By now you've seen most of the key building blocks of our RNN.
**[0:04]** But there are just two more ideas that let you build much more powerful models.
**[0:09]** One is bidirectional RNN, which lets
**[0:12]** you at the point in time to take information from both earlier and later
**[0:16]** in the sequence. So talk about that in this video.
**[0:19]** And the second is deep RNN, which you see in the next video.
**[0:23]** So that starts with bidirectional RNN.
**[0:27]** So to motivate bidirectional RNN, let's look at this network which you've seen
**[0:31]** a few times before in the context of named entity recognition.
**[0:34]** And one of the problems of this network is that,
**[0:37]** to figure out whether the third word Teddy is a part of a person's name,
**[0:42]** it's not enough to just look at the first part of the sentence.
**[0:46]** So to tell if y3 should be 01,
**[0:48]** you need more information than just the first few words.
**[0:51]** Because the first three words doesn't tell you if they're talking about Teddy
**[0:57]** bears, or talk about the former US President, Teddy Roosevelt.
**[1:03]** So this is a unidirectional or four directional only RNN.
**[1:08]** And this comment I just made is true whether these cells
**[1:13]** are standard RNN blocks, or whether there are
**[1:18]** GRU units, or whether they're LSTM blocks, right?
**[1:22]** But all these blocks are in a forward only direction
**[1:26]** What a bidirection RNN does or a BRNN is fix this issue
**[1:32]** A birectional RNN works as follows.  I'm going to simplify to use a simplified four input sentence
**[1:42]** So we have four inputs, X1 through X4.
**[1:47]** So this network's hidden there will have a forward recurring components.
**[1:54]** So I'm going to call this a1,
**[2:00]** a2, a3, and a4.
**[2:07]** And I'm going to draw a right arrow over
**[2:10]** that to the notices the four recurrent component.
**[2:14]** And so w connected as follows.
**[2:20]** And so each of these four recurrent units influence the current X.
**[2:27]** And then on feeds in,
**[2:34]** To help predict y hat 1, y hat 2,
**[2:38]** y hat 3, and y hat 4.
**[2:42]** So far I haven't done anything, right?
**[2:47]** Basically, we draw on the RNN from the previous slide, but
**[2:51]** with the arrows place in slightly funny positions.
**[2:55]** But I drew the arrows in these slightly funny positions because what
**[3:00]** we're going to do is add a backward recurrent there.
**[3:04]** That would have a1, left arrow to denote
**[3:09]** this is a backward connection, and then a2 backwards,
**[3:16]** a3 backwards, and a4 backwards.
**[3:20]** So the left arrow denotes it is a backward connection.
**[3:24]** And so we're then going to connect the network up as follows.
**[3:30]** And these a backward connections will be connected
**[3:35]** to each other, going backwards in time.
**[3:39]** So notice that this network defines a cyclic draft.
**[3:46]** And so, given an input sequence X1 to X4, the four sequence we first compute a for
**[3:51]** (1), then use that to compute a for (2), then a for (3), then a for (4).
**[3:57]** Whereas the backward sequence will start by computing a backward four and
**[4:01]** then go back and compute a backward three.
**[4:03]** And notice your computing network activations.
**[4:06]** This is not background, this is for a problem but the for profit goals has
**[4:10]** partially but the forward problem has part of the complication going from left to
**[4:14]** right and positive competition going from right to left in this diagram.
**[4:19]** But I havent computed a backward three.
**[4:20]** You can then use those activations completely backward two, and
**[4:24]** then a backward one.
**[4:25]** And then finally, you haven't computed all your hidden their activations.
**[4:28]** You can then make your predictions.
**[4:31]** And so for example, to make the predictions
**[4:37]** your network would have something like y hat
**[4:42]** at time T is an activation function apply to WY
**[4:47]** with both the forward activation at time T.
**[4:53]** And the backward activation at time T being fed in,
**[4:59]** to make that prediction at time T.
**[5:05]** So if you look at the prediction at times set 3 for example,
**[5:10]** then information from X1 can flow through here for one to for
**[5:15]** 2, that also takes an information here, to for 3, so y had three.
**[5:22]** So information from X1, X2,
**[5:24]** X3 are all taking account with information from X4 can
**[5:30]** flow through a backward four to a backward three 2y.
**[5:35]** So this allows the production and
**[5:37]** tie three to take his input both information from the past,
**[5:40]** as well as information from the present, which goes into both the forward and
**[5:45]** backward things at this step, as well as information from the future.
**[5:50]** So in particular, given a phrase like
**[5:55]** he said Teddy Roosevelt...to predict
**[6:00]** whether Teddy was part of a person's name.
**[6:06]** You give to take into account information from the past and from the future.
**[6:13]** So this is the bidirectional recurrent neural network.
**[6:17]** And these blocks here can be not just the standard RNN block,
**[6:22]** but they can also be GRU blocks, or LSTM blocks.
**[6:26]** In fact, for a lot of NLP problems, for a lot of text or
**[6:30]** natural language processing problems,
**[6:33]** a bidirectional RNN with a LSTM appears to be commonly used.
**[6:38]** So, if you have an NLP problem, and you have a complete sentence,
**[6:42]** you're trying to label things in the sentence, a bidirectional RNN with LSTM
**[6:47]** blocks before then backward would be a pretty reasonable first thing to try.
**[6:52]** So that's it for the bidirectional RNN.
**[6:56]** And this is a modification they can make to the basic RNN architecture,
**[7:01]** or the GRU, or the LSTM.
**[7:03]** And by making this change, you can have a model that uses RNN, or GRU, LSTM,
**[7:07]** and is able to make predictions anywhere even in the middle of the sequence, but
**[7:12]** take into account information potentially from the entire sequence.
**[7:16]** The disadvantage of the bidirectional RNN is that,
**[7:19]** you do need the entire sequence of data before you can make predictions anywhere.
**[7:24]** So, for example, if you're building a speech recognition system then BRNN will
**[7:29]** let you take into account the entire speech other friends.
**[7:32]** But if you use this straightforward implementation,
**[7:35]** you need to wait for the person to stop talking to get the entire utterance before
**[7:40]** you can actually process it, and make a speech recognition prediction.
**[7:44]** So the real time speech recognition applications,
**[7:47]** there is somewhat more complex models as well rather than just using the standard
**[7:51]** by the rational RNN as you're seeing here.
**[7:54]** But for a lot of natural language processing applications where you can get
**[7:58]** the entire sentence all at the same time, the standard BRN and
**[8:01]** algorithm is actually very effective.
**[8:04]** So that's it for BRNN in the Nixon final video for this week.
**[8:07]** Let's talk about how to take all of these ideas RNN, LSTM, GRUz,
**[8:12]** and bidirectional versions, and construct deep versions of them.
