---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 2
section: "Learning Word Embeddings: Word2vec & GloVe"
item_title: Learning Word Embeddings
duration: 10 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/APM5s/learning-word-embeddings
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Learning Word Embeddings — Transcript

**[0:00]** In this video, you'll start to learn
**[0:01]** some concrete algorithms for learning word embeddings.
**[0:04]** In the history of deep learning as applied to learning word embeddings,
**[0:09]** people actually started off with relatively complex algorithms.
**[0:13]** And then over time,
**[0:14]** researchers discovered they can use
**[0:16]** simpler and simpler and simpler algorithms and still
**[0:18]** get very good results especially for a large dataset.
**[0:21]** But what happened is,
**[0:23]** some of the algorithms that are most popular today,
**[0:26]** they are so simple that if I present them first,
**[0:28]** it might seem almost a little bit magical,
**[0:30]** how can something this simple work?
**[0:33]** So, what I'm going to do is start off with some of
**[0:35]** the slightly more complex algorithms because I think it's actually
**[0:38]** easier to develop intuition about why they should work,
**[0:41]** and then we'll move on to simplify these algorithms and show
**[0:44]** you some of the simple algorithms that also give very good results.
**[0:48]** So, let's get started.
**[0:50]** Let's say you're building a language model
**[0:53]** and you do it with a neural network.
**[0:58]** So, during training, you might want your neural network to do something like input,
**[1:01]** I want a glass of orange,
**[1:02]** and then predict the next word in the sequence.
**[1:05]** And below each of these words,
**[1:06]** I have also written down the index in the vocabulary of the different words.
**[1:12]** So it turns out that building
**[1:15]** a neural language model is the small way to learn a set of embeddings.
**[1:21]** And the ideas I present on this slide were due to Yoshua Bengio,
**[1:24]** Rejean Ducharme, Pascals Vincent, and Christian Jauvin.
**[1:28]** So, here's how you can build a neural network to predict the next word in the sequence.
**[1:34]** Let me take the list of words,
**[1:37]** I want a glass of orange,
**[1:39]** and let's start with the first word I.
**[1:42]** So I'm going to construct one add vector corresponding to the word I.
**[1:46]** So there's a one add vector with a one in position, 4343.
**[1:52]** So this is going to be 10,000 dimensional vector.
**[1:55]** And what we're going to do is then have a matrix of parameters E,
**[1:59]** and take E times O to get an embedding vector e4343,
**[2:08]** and this step really means that
**[2:09]** e4343 is obtained by the matrix E times the one add vector 43.
**[2:17]** And then we'll do the same for all of the other words.
**[2:21]** So the word want, is where 9665 one add vector,
**[2:24]** multiply by E to get the embedding vector.
**[2:27]** And similarly, for all the other words.
**[2:30]** A, is a first word in dictionary,
**[2:32]** alphabetic comes first, so there is O one, gets this E one.
**[2:35]** And similarly, for the other words in this phrase.
**[2:44]** So now you have a bunch of three dimensional embedding,
**[2:47]** so each of this is a 300 dimensional embedding vector.
**[2:52]** And what we can do,
**[2:54]** is fill all of them into a neural network. So here is the neural network layer.
**[3:01]** And then this neural network feeds to a softmax,
**[3:06]** which has it's own parameters as well.
**[3:09]** And a softmax classifies among the 10,000
**[3:14]** possible outputs in the vocab for those final word we're trying to predict.
**[3:19]** And so, if in the training slide we saw the word juice then,
**[3:22]** the target for the softmax in training repeat that it should predict
**[3:25]** the other word juice was what came after this.
**[3:28]** So this hidden name here will have his own parameters.
**[3:31]** So have some, I'm going to call this W1 and there's also B1.
**[3:36]** The softmax there was this own parameters W2, B2,
**[3:39]** and they're using 300 dimensional word embeddings,
**[3:44]** then here we have six words.
**[3:46]** So, this would be six times 300.
**[3:51]** So this layer or this input will be a 1,800 dimensional
**[3:55]** vector obtained by taking your six embedding vectors and stacking them together.
**[4:01]** Well, what's actually more commonly done is to have a fixed historical window.
**[4:07]** So for example, you might decide that you always want to predict
**[4:10]** the next word given say the previous four words,
**[4:14]** where four here is a hyperparameter of the algorithm.
**[4:17]** So this is how you adjust to
**[4:18]** either very long or very short sentences or you decide to
**[4:21]** always just look at the previous four words,
**[4:24]** so you say, I will still use those four words.
**[4:26]** And so, let's just get rid of these.
**[4:29]** And so, if you're always using a four word history,
**[4:33]** this means that your neural network will input a 1,200 dimensional feature vector,
**[4:41]** go into this layer,
**[4:43]** then have a softmax and try to predict the output.
**[4:45]** And again, variety of choices.
**[4:48]** And using a fixed history, just means that you can deal with even arbitrarily
**[4:52]** long sentences because the input sizes are always fixed.
**[4:56]** So, the parameters of this model will be this matrix E,
**[5:01]** and use the same matrix E for all the words.
**[5:04]** So you don't have different matrices for
**[5:06]** different positions in the proceedings four words,
**[5:09]** is the same matrix E. And then,
**[5:11]** these weights are also parameters of the algorithm
**[5:15]** and you can use that crop to perform gradient descent
**[5:19]** to maximize the likelihood of
**[5:22]** your training set to just repeatedly predict given four words in a sequence,
**[5:26]** what is the next word in your text corpus?
**[5:29]** And it turns out that this algorithm we'll learn pretty decent word embeddings.
**[5:35]** And the reason is, if you remember our orange juice, apple juice example,
**[5:41]** is in the algorithm's incentive to learn
**[5:44]** pretty similar word embeddings for orange and apple
**[5:47]** because doing so allows it to fit
**[5:50]** the training set better because it's going to see orange juice sometimes,
**[5:53]** or see apple juice sometimes, and so,
**[5:58]** if you have only a 300 dimensional feature vector to represent all of these words,
**[6:02]** the algorithm will find that it fits the training set best.
**[6:05]** If apples, oranges, and grapes, and pears,
**[6:07]** and so on and maybe also durians which is
**[6:10]** a very rare fruit and that with similar feature vectors.
**[6:13]** So, this is one of the earlier and pretty successful algorithms
**[6:18]** for learning word embeddings,
**[6:19]** for learning this matrix E. But now let's
**[6:23]** generalize this algorithm and see how we can derive even simpler algorithms.
**[6:27]** So, I want to illustrate the other algorithms
**[6:30]** using a more complex sentence as our example.
**[6:33]** Let's say that in your training set,
**[6:36]** you have this longer sentence,
**[6:37]** I want a glass of orange juice to go along with my cereal.
**[6:40]** So, what we saw on the last slide was
**[6:43]** that the job of the algorithm was to predict some word juice,
**[6:46]** which we are going to call the target words,
**[6:49]** and it was given some context which was the last four words.
**[6:57]** And so, if your goal is to learn
**[7:00]** a embedding of researchers I've experimented with many different types of context.
**[7:05]** If it goes to build a language model then is
**[7:08]** natural for the context to be a few words right before the target word.
**[7:12]** But if your goal isn't to learn the language model per se,
**[7:15]** then you can choose other contexts.
**[7:17]** For example, you can pose a learning problem
**[7:20]** where the context is the four words on the left and right.
**[7:24]** So, you can take the four words on the left and right as the context,
**[7:28]** and what that means is that we're posing a learning problem
**[7:31]** where the algorithm is given four words on the left.
**[7:35]** So, a glass of orange,
**[7:37]** and four words on the right,
**[7:40]** to go along with,
**[7:42]** and this has to predict the word in the middle.
**[7:44]** And posing a learning problem like this where you have the embeddings of
**[7:49]** the left four words and the right four words feed into a neural network,
**[7:52]** similar to what you saw in the previous slide,
**[7:56]** to try to predict the word in the middle,
**[7:58]** try to put it target word in the middle,
**[8:00]** this can also be used to learn word embeddings.
**[8:03]** Or if you want to use a simpler context,
**[8:05]** maybe you'll just use the last one word.
**[8:07]** So given just the word orange,
**[8:10]** what comes after orange?
**[8:12]** So this will be different learning problem where you tell it one word,
**[8:16]** orange, and will say well,
**[8:17]** what do you think is the next word.
**[8:17]** And you can construct a neural network that just fits in the word,
**[8:22]** the one previous word or the embedding
**[8:25]** of the one previous word to a neural network as you try to predict the next word.
**[8:28]** Or, one thing that works surprisingly well is to take a nearby one word.
**[8:35]** Some might tell you that, well,
**[8:37]** take the word glass, is somewhere close by.
**[8:39]** Some might say, I saw
**[8:41]** the word glass and then there's another words somewhere close to glass,
**[8:44]** what do you think that word is?
**[8:46]** So, that'll be using nearby one word as the context.
**[8:49]** And we'll formalize this in the next video but this is the idea of a Skip-Gram model,
**[8:56]** and just an example of a simpler algorithm where the context is now much simpler,
**[9:00]** is just one word rather than four words,
**[9:04]** but this works remarkably well.
**[9:06]** So what researchers found was that if you really want to build a language model,
**[9:09]** it's natural to use the last few words as a context.
**[9:13]** But if your main goal is really to learn a word embedding,
**[9:17]** then you can use all of these other contexts and they will
**[9:22]** result in very meaningful work embeddings as well.
**[9:24]** I will formalize the details of
**[9:26]** this in the next video where we talk about the Walter VEC model.
**[9:29]** To summarize, in this video you saw how the language modeling problem
**[9:34]** which causes the pose of machines learning problem where you input
**[9:38]** the context like the last four words and predicts some target words,
**[9:41]** how posing that problem allows you to learn input word embedding.
**[9:45]** In the next video,
**[9:47]** you'll see how using even simpler context and
**[9:49]** even simpler learning algorithms to mark from context to target word,
**[9:54]** can also allow you to learn a good word embedding.
**[9:57]** Let's go on to the next video where we'll discuss the Word2Vec model.
