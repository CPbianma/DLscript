---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 3
section: Various Sequence To Sequence Architectures
item_title: Attention Model
duration: 12 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/lSwVa/attention-model
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Attention Model — Transcript

**[0:00]** In the last video, you saw how the attention model allows
**[0:04]** a neural network to pay attention to
**[0:06]** only part of an input sentence while it's generating a translation,
**[0:11]** much like a human translator might.
**[0:14]** Let's now formalize that intuition into
**[0:16]** the exact details of how you would implement an attention model.
**[0:20]** So same as in the previous video,
**[0:23]** let's assume you have an input sentence and you use a bidirectional RNN,
**[0:30]** or bidirectional GRU, or bidirectional LSTM to compute features on every word.
**[0:35]** In practice, GRUs and LSTMs are often used for this,
**[0:40]** with maybe LSTMs be more common.
**[0:43]** And so for the forward occurrence,
**[0:46]** you have a forward occurrence first time step.
**[0:51]** Activation backward occurrence, first time step.
**[0:55]** Activation forward occurrence, second time step.
**[0:58]** Activation backward and so on.
**[1:02]** For all of them in just a forward fifth time step a backwards fifth time step.
**[1:09]** We had a zero here technically we can also
**[1:13]** have I guess a backwards sixth as a vector of all zero,
**[1:19]** actually that's a factor of all zeroes.
**[1:22]** And then to simplify the notation going forwards at every time step,
**[1:29]** even though you have the features computed from
**[1:32]** the forward occurrence and from the backward occurrence in the bidirectional RNN.
**[1:37]** I'm just going to use a of t to represent both of these concatenated together.
**[1:46]** So a of t is going to be a feature vector for
**[1:50]** time step t. Although to be consistent with notation,
**[1:55]** we're using second, I'm going to call this t_prime.
**[1:58]** Actually, I'm going to use t_prime to index into the words in the French sentence.
**[2:04]** Next, we have our forward only,
**[2:08]** so it's a single direction RNN with state s to generate the translation.
**[2:16]** And so the first time step,
**[2:18]** it should generate y1 and just will have as input some context
**[2:24]** C. And if you want to index it with time I guess you
**[2:30]** could write a C1 but sometimes I just right C without the superscript one.
**[2:36]** And this will depend on the attention parameters so alpha_11,
**[2:43]** alpha_12 and so on tells us how much attention.
**[2:50]** And so these alpha parameters tells us how much the context would depend
**[2:57]** on the features we're getting or the activations we're
**[3:01]** getting from the different time steps.
**[3:05]** And so the way we define the context is actually be a weighted sum of
**[3:10]** the features from the different time steps weighted by these attention weights.
**[3:16]** So more formally the attention weights will satisfy this that they are all be non-negative,
**[3:25]** so it will be a zero positive and they'll sum to one.
**[3:29]** We'll see later how to make sure this is true.
**[3:32]** And we will have the context or the context at time one
**[3:36]** often drop that superscript that's going to be sum over t_prime,
**[3:41]** all the values of t_prime of this weighted
**[3:45]** sum of these activations.
**[3:54]** So this term here are the attention weights and this term here comes from here.
**[4:03]** So alpha(t_prime) is the amount of attention that's
**[4:14]** yt should pay to a of t_prime.
**[4:26]** So in other words,
**[4:27]** when you're generating the t of the output words,
**[4:30]** how much you should be paying attention to the t_primeth input to word.
**[4:35]** So that's one step of generating the output and then at the next time step,
**[4:41]** you generate the second output and is again done some of
**[4:47]** where now you have a new set of attention weights on they to find a new way to sum.
**[4:52]** That generates a new context.
**[4:55]** This is also input and that allows you to generate the second word.
**[5:00]** Only now just this way to sum becomes the context of
**[5:05]** the second time step is sum over t_prime alpha(2, t_prime).
**[5:12]** So using these context vectors.
**[5:16]** C1 right there back,
**[5:18]** C2, and so on.
**[5:24]** This network up here looks like a pretty standard RNN sequence
**[5:30]** with the context vectors as output and we
**[5:33]** can just generate the translation one word at a time.
**[5:37]** We have also define how to compute the context vectors in terms of
**[5:42]** these attention weights and those features of the input sentence.
**[5:46]** So the only remaining thing to do is to
**[5:49]** define how to actually compute these attention weights.
**[5:53]** Let's do that on the next slide.
**[5:55]** So just to recap, alpha(t,
**[5:57]** t_prime) is the amount of attention you should paid to
**[6:01]** a(t_prime ) when you're trying to generate the t th words in the output translation.
**[6:07]** So let me just write down the formula and we talk of how this works.
**[6:11]** This is formula you could use the compute alpha(t,
**[6:14]** t_prime) which is going to compute these terms e(t,
**[6:18]** t_prime) and then use essentially a softmax to make sure that
**[6:21]** these weights sum to one if you sum over t_prime.
**[6:25]** So for every fix value of t,
**[6:28]** these things sum to one if you're summing over t_prime.
**[6:34]** And using this soft max prioritization,
**[6:38]** just ensures this properly sums to one.
**[6:41]** Now how do we compute these factors e. Well,
**[6:44]** one way to do so is to use a small neural network as follows.
**[6:48]** So s t minus one was the neural network state from the previous time step.
**[6:56]** So here is the network we have.
**[6:59]** If you're trying to generate yt then st minus one was the hidden state from
**[7:04]** the previous step that's fed into st
**[7:07]** and that's one input to very small neural network.
**[7:12]** Usually, one hidden layer in neural network because you need to compute these a lot.
**[7:16]** And then a(t_prime) the features from time step t_prime is the other inputs.
**[7:23]** And the intuition is,
**[7:24]** if you want to decide how much attention to pay to the activation of t_prime.
**[7:31]** Well, the things that seems like it should depend the most on
**[7:35]** is what is your own hidden state activation from the previous time step.
**[7:39]** You don't have the current state activation yet
**[7:41]** because of context feeds into this so you haven't computed that.
**[7:43]** But look at whatever you're hidden states of this RNN generating
**[7:47]** the output translation and then for each of the positions,
**[7:51]** each of the words look at their features.
**[7:53]** So it seems pretty natural that alpha(t,
**[7:57]** t_prime) and e(t, t_prime) should depend on these two quantities.
**[8:03]** But we don't know what the function is.
**[8:04]** So one thing you could do is just train a very small neural network
**[8:07]** to learn whatever this function should be.
**[8:10]** And trust back propagation, trust gradient descent to learn the right function.
**[8:18]** And it turns out that if you implemented
**[8:21]** this whole model and train it with gradient descent,
**[8:25]** the whole thing actually works.
**[8:27]** This little neural network does a pretty decent job telling
**[8:31]** you how much attention yt should pay to
**[8:35]** a(t_prime) and this formula makes sure that
**[8:40]** the attention waits sum to one and then as you chug along generating one word at a time,
**[8:45]** this neural network actually pays attention to the right parts of
**[8:50]** the input sentence that learns all this automatically using gradient descent.
**[8:54]** Now, one downside to this algorithm is that
**[8:58]** it does take quadratic time or quadratic cost to run this algorithm.
**[9:03]** If you have tx words in the input and ty words in
**[9:09]** the output then the total number of
**[9:12]** these attention parameters are going to be tx times ty.
**[9:17]** And so this algorithm runs in quadratic cost.
**[9:21]** Although in machine translation applications where
**[9:26]** neither input nor output sentences is
**[9:29]** usually that long maybe quadratic cost is actually acceptable.
**[9:33]** Although, there is some research work on trying to reduce costs as well.
**[9:38]** Now, so far I've been describing the attention idea in the context of machine translation.
**[9:47]** Without going too much into detail this idea has been applied to other problems as well.
**[9:53]** So just image captioning.
**[9:55]** So in the image captioning problem the task is to
**[9:58]** look at the picture and write a caption for that picture.
**[10:02]** So in this paper set to the bottom by Kevin Chu,
**[10:06]** Jimmy Barr, Ryan Kiros, Kelvin Shaw, Aaron Korver,
**[10:08]** Russell Zarkutnov, Virta Zemo,
**[10:11]** and Yoshua Bengio they also showed that you could have a very similar architecture.
**[10:16]** Look at the picture and pay attention only to parts
**[10:21]** of the picture at a time while you're writing a caption for a picture.
**[10:26]** So if you're interested, then I encourage you to take a look at that paper as well.
**[10:30]** And you get to play with all this and more in the programming exercise.
**[10:36]** Whereas machine translation is a very complicated problem in the programming exercise you
**[10:42]** get to implement and play of the attention while you
**[10:44]** yourself for the date normalization problem.
**[10:48]** So the problem inputting a date like this.
**[10:50]** This actually has a date of the Apollo Moon landing and normalizing it into
**[10:55]** standard formats or a date like this and having a neural network a sequence,
**[11:01]** sequence model normalize it to this format.
**[11:04]** This by the way is the birthday of William Shakespeare.
**[11:07]** Also it's believed to be.
**[11:09]** And what you see in programming exercises as you can train
**[11:12]** a neural network to input dates in any of
**[11:15]** these formats and have it use an attention model
**[11:18]** to generate a normalized format for these dates.
**[11:23]** One other thing that sometimes fun to do is
**[11:26]** to look at the visualizations of the attention weights.
**[11:29]** So here's a machine translation example and here were plotted in different colors.
**[11:36]** the magnitude of the different attention weights.
**[11:39]** I don't want to spend too much time on this but you find that
**[11:42]** the corresponding input and output words
**[11:46]** you find that the attention waits will tend to be high.
**[11:51]** Thus, suggesting that when it's generating a specific word in output is,
**[11:56]** usually paying attention to the correct words in the input and all this including
**[12:01]** learning where to pay attention when was all
**[12:04]** learned using back propagation with an attention model.
**[12:08]** So that's it for the attention model
**[12:11]** really one of the most powerful ideas in deep learning.
**[12:15]** I hope you enjoy implementing and playing with
**[12:18]** these ideas yourself later in this week's programming exercises.
