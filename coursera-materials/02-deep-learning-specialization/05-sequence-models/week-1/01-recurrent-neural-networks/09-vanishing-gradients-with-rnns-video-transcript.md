---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 1
section: Recurrent Neural Networks
item_title: Vanishing Gradients with RNNs
duration: 6 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/PKMRR/vanishing-gradients-with-rnns
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Vanishing Gradients with RNNs — Transcript

**[0:00]** You've learned about how RNNs work
**[0:02]** and how they can be applied
**[0:04]** to problems like name entity recognition
**[0:06]** as well as to language modeling.
**[0:09]** You saw how back propagation can be used to train an RNN.
**[0:13]** It turns out that one of the problems of
**[0:15]** the basic RNN algorithm is that it runs
**[0:17]** into vanishing gradient problems.
**[0:20]** Let's discuss that and in the next few videos we'll talk
**[0:23]** about some solutions that
**[0:25]** will help to address this problem.
**[0:27]** You've seen pictures of RNNs that look like this.
**[0:31]** Let's take a language modeling example.
**[0:34]** Let's say you see this sentence.
**[0:36]** The cat, which already
**[0:42]** ate and maybe already
**[0:43]** ate a bunch of food that was delicious,
**[0:45]** dot dot, dot, dot, dot was full.
**[0:50]** To be consistent is because the cat is singular,
**[0:53]** it should be the cat was where there was the cats,
**[0:58]** which already ate a bunch
**[1:00]** of food was delicious and the apples and
**[1:02]** pears and so on were full.
**[1:06]** To be consistent, it should be cat was or cats were.
**[1:14]** This is one example of when language can have
**[1:17]** very long-term dependencies where it
**[1:19]** worded as much earlier can
**[1:21]** affect what needs to come much later in the sentence.
**[1:25]** But it turns out that the basic RNN
**[1:27]** we've seen so far is not
**[1:29]** very good at capturing very long-term dependencies.
**[1:32]** To explain why, you might
**[1:34]** remember from our earlier discussions of training
**[1:38]** very deep neural networks
**[1:39]** that we talked about the vanishing gradients problem.
**[1:43]** This is a very, very deep neural network,
**[1:45]** say 100 years or even much deeper.
**[1:48]** Then you would carry out forward
**[1:51]** prop from left to right and then backprop.
**[1:54]** We said that if this is a very deep neural network,
**[1:57]** then the gradient from this output
**[1:59]** y would have a very hard time propagating
**[2:01]** back to affect the weights of these earlier layers,
**[2:05]** to affect the computations of the earlier layers.
**[2:07]** For an RNN with a similar problem,
**[2:10]** you have forward prop going from left to right and
**[2:13]** then backprop going from right to left.
**[2:17]** It can be quite difficult because of
**[2:20]** the same vanishing gradients problem for the outputs of
**[2:24]** the errors associated with the later timesteps to
**[2:28]** affect the computations that are earlier.
**[2:32]** In practice, what this means
**[2:34]** is it might be difficult to get
**[2:35]** a neural network to realize that it needs to memorize.
**[2:38]** Did you see a singular noun or
**[2:40]** a plural noun so that later
**[2:42]** on in the sequence it can generate either was or were,
**[2:45]** depending on whether it was singular or plural.
**[2:49]** Notice that in English this stuff in
**[2:51]** the middle could be arbitrarily long.
**[2:53]** You might need to memorize the singular plural for
**[2:57]** a very long time before you get
**[2:59]** to use that bit of information.
**[3:03]** Because of this problem,
**[3:05]** the basic RNN model has many local influences,
**[3:09]** meaning that the output y hat
**[3:12]** three is mainly influenced by
**[3:15]** values close to y hat three and
**[3:19]** a value here is mainly influenced
**[3:21]** by inputs that are somewhat close.
**[3:23]** It's difficult for the output here to be strongly
**[3:26]** influenced by an input that
**[3:27]** was very early in the sequence.
**[3:30]** This is because whatever the output is,
**[3:32]** whether this got it right, this got it wrong,
**[3:34]** it's just very difficult for the error to
**[3:36]** backpropagate all the way
**[3:38]** to the beginning of the sequence,
**[3:39]** and therefore to modify how
**[3:42]** the neural network is doing
**[3:43]** computations earlier in the sequence.
**[3:45]** This is a weakness of the basic RNN algorithm,
**[3:49]** one which will to address in the next few videos.
**[3:53]** But if we don't address it,
**[3:55]** then RNNs tend not to be
**[3:57]** very good at capturing long-range dependencies.
**[4:01]** Even though this discussion has focused
**[4:03]** on vanishing gradients, you remember,
**[4:06]** when we're talking about very deep neural networks that
**[4:08]** we also talked about exploding gradients.
**[4:11]** Where doing backprop,
**[4:12]** the ingredients should not
**[4:13]** just decrease exponentially they may
**[4:15]** also increase exponentially with
**[4:16]** the number of layers you go through.
**[4:18]** It turns out that vanishing gradients
**[4:20]** tends to be the biggest problem with training RNNs.
**[4:23]** Although when exploding gradients
**[4:25]** happens it can be catastrophic because
**[4:27]** the exponentially large gradients
**[4:29]** can cause your parameters to become
**[4:31]** so large that your neural network parameters
**[4:34]** get really messed up.
**[4:36]** It turns out that exploding gradients are easier
**[4:39]** to spot because the parameter has just blow up.
**[4:41]** You might often see NaNs, not a numbers,
**[4:45]** meaning results of a numerical overflow
**[4:48]** in your neural network computation.
**[4:51]** If you do see exploding gradients,
**[4:53]** one solution to that is apply gradients clipping.
**[4:57]** All that means is,
**[4:59]** look at your gradient vectors,
**[5:01]** and if it is bigger than some threshold,
**[5:06]** re-scale some of your gradient vectors
**[5:08]** so that it's not too big,
**[5:09]** so that is clipped according to some maximum value.
**[5:12]** If you see exploding gradients,
**[5:15]** if your derivatives do explore the resilience,
**[5:18]** just apply gradient clipping.
**[5:20]** That's a relatively robust solution
**[5:23]** that will take care of exploding gradients.
**[5:26]** But vanishing gradients is much harder to
**[5:28]** solve and it will be the subject of the next few videos.
**[5:33]** To summarize, in an earlier course,
**[5:35]** you saw how we're training a very deep neural network.
**[5:38]** You can run into vanishing gradient or exploding
**[5:41]** gradient problems where the
**[5:42]** derivative either decreases exponentially,
**[5:44]** or grows exponentially as
**[5:46]** a function of the number of layers.
**[5:48]** An RNN, say an RNN
**[5:51]** processing data over 1,000 times sets,
**[5:53]** or over 10,000 times sets,
**[5:55]** that's basically a 1,000 layer or
**[5:57]** like a 10,000 layer neural network.
**[5:59]** It too runs into these types of problems.
**[6:03]** Exploding gradients you could solve
**[6:05]** address by just using gradient clipping,
**[6:08]** but vanishing gradients will take way more to address.
**[6:11]** What we'll do in the next video is talk about GRUs,
**[6:14]** a greater recurrent units,
**[6:15]** which is a very effective solution for addressing
**[6:18]** the vanishing gradient problem and will allow
**[6:20]** your neural network to capture
**[6:22]** much longer range dependencies.
**[6:24]** Let's go on to the next video.
