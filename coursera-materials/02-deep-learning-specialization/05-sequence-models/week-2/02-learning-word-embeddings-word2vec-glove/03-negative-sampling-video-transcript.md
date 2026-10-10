---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 2
section: "Learning Word Embeddings: Word2vec & GloVe"
item_title: Negative Sampling
duration: 12 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/Iwx0e/negative-sampling
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Negative Sampling — Transcript

**[0:00]** In the last video, you saw how
**[0:01]** the Skip-Gram model allows you to construct
**[0:04]** a supervised learning tasks
**[0:06]** so you map from context to target
**[0:08]** words and how that allows you
**[0:09]** to learn a useful word embedding.
**[0:12]** But the downside of that was
**[0:13]** the sock max objective was slow to compute.
**[0:16]** In this video, you see
**[0:18]** a modified learning problem called negative
**[0:21]** sampling that allows you to do something
**[0:23]** similar to the skip-gram model you saw just now,
**[0:26]** but with a much more efficient learning algorithm.
**[0:29]** Let's see how you could do that.
**[0:30]** Most of the ideas presented in
**[0:32]** this video are due to Thomas Mikolov,
**[0:34]** Sasaki, Chen Greco, and Jeff Dean.
**[0:38]** What we're going to do in
**[0:40]** this algorithm is create
**[0:41]** a new supervised learning problem.
**[0:43]** The problem is, given a pair of words
**[0:46]** like orange and juice,
**[0:50]** we're going to predict, is this a context target pair?
**[0:56]** In this example, orange juice was a positive example.
**[1:00]** How about Orange and King?
**[1:04]** Well, that's a negative example
**[1:06]** so I'm going to write zero for the target.
**[1:09]** What we're going to do is we're actually going to
**[1:11]** sample a context and a target word.
**[1:14]** In this case, we had orange and juice and
**[1:17]** we'll associate that with a Label 1.
**[1:20]** Let's just put word in the middle.
**[1:23]** Then having generated a positive example,
**[1:26]** the positive examples generated exactly how
**[1:29]** we generated it in the previous
**[1:30]** videos sample context word,
**[1:32]** look around a window of say,
**[1:34]** +-10 words, and pick a target word.
**[1:37]** That's how you generate the first row of
**[1:39]** this table with orange juice one.
**[1:41]** Then to generate the negative examples,
**[1:44]** you're going to take the same context word and
**[1:46]** then just pick a word at random from the dictionary.
**[1:48]** In this case, I chose the word king at
**[1:50]** random and label that as zero.
**[1:53]** Then let's take orange and let's pick
**[1:56]** another random word from
**[1:58]** the dictionary under the assumption
**[2:00]** that if we pick a random word,
**[2:01]** it probably won't be associated with the word orange,
**[2:05]** so book, zero.
**[2:07]** Let's pick a few others, orange,
**[2:10]** maybe just by chance we'll pick the zero,
**[2:14]** and then orange, and maybe just by chance,
**[2:17]** we'll pick the word of and we'll put a zero there.
**[2:21]** Notice that all of these labeled as zero even though
**[2:26]** the word of actually appears next to orange as well.
**[2:30]** To summarize the way we
**[2:32]** generated this dataset is we'll pick
**[2:35]** a context word and then pick a target word
**[2:40]** and that is the first row of this table,
**[2:45]** that gives us a positive example.
**[2:46]** Context target, and then give that a label of one.
**[2:50]** Then what we do is for some number of times,
**[2:53]** say k times, we're going to take
**[2:56]** the same context words and
**[2:57]** then pick random words from the dictionary.
**[2:59]** King, book, the, of,
**[3:01]** whatever comes out at random from
**[3:02]** the dictionary and label all those zero,
**[3:05]** and those will be our negative examples.
**[3:09]** It's okay if just by chance,
**[3:12]** one of those words we picked at random from
**[3:14]** the dictionary happens to appear in a window,
**[3:16]** in a plus-minus ten-word windows,
**[3:19]** say next to the context word orange.
**[3:22]** Then we're going to create a supervised learning problem,
**[3:25]** where the algorithm inputs x inputs this pair of words,
**[3:31]** and then has to predict
**[3:33]** the target label to predict the output Y.
**[3:37]** The problem is really given a pair of
**[3:40]** words like orange and juice,
**[3:43]** do you think they appear together?
**[3:44]** Do you think I got these two words by
**[3:46]** sampling two words close to each other?
**[3:48]** Or do you think I got them as
**[3:50]** one word from the text and
**[3:52]** one word chosen at random from the dictionary?
**[3:55]** Is really to try to distinguish
**[3:57]** between these two types of
**[3:58]** distributions from which you
**[4:00]** might sample a pair of words.
**[4:03]** This is how you generate the training set.
**[4:06]** How do you choose Mikolov at
**[4:09]** all that recommend that maybe k is
**[4:12]** 5-20 for smaller datasets
**[4:16]** and if you have a very large dataset,
**[4:18]** then choose k to be smaller so k=2-5 for
**[4:23]** larger datasets and larger values
**[4:28]** of k for smaller datasets.
**[4:33]** In this example, I've just used k=4.
**[4:37]** Next, let's describe the supervised learning model
**[4:41]** for learning and mapping from x-y.
**[4:44]** Here was the SoftMax model you
**[4:46]** saw from the previous video
**[4:49]** and here's the training set we
**[4:51]** got from the previous slide where again,
**[4:54]** this is going to be the new input x and this is going to
**[4:57]** be the value of y you're trying to predict.
**[5:00]** To define the model, I'm going to use this
**[5:03]** to denote this with c for the context word,
**[5:06]** this to denote the possible target word
**[5:08]** t and this I'll use y to denote 01.
**[5:11]** This is a context target pair.
**[5:13]** What we're going to do
**[5:16]** is define a logistic regression model.
**[5:19]** We say that the chance that y=1
**[5:21]** given the input c,t pair,
**[5:25]** we're going to model this
**[5:27]** as basically a logistic regression model.
**[5:29]** But the specific formula we use is sigmoid applied to
**[5:32]** Theta t transpose ec.
**[5:39]** The parameters are similar as before.
**[5:42]** You have one parameter vector Theta
**[5:45]** for each possible target word and
**[5:47]** a separate parameter vector really
**[5:49]** the embedding vector for each possible context word.
**[5:54]** We're going to use this formula
**[5:56]** to estimate the probability that y=1.
**[6:00]** If you have k examples here.
**[6:05]** Then if you can think of this as having
**[6:08]** a k:1 ratio of negative to positive examples.
**[6:12]** For every positive examples,
**[6:14]** you will have k negative examples with
**[6:17]** which to train this logistic regression model.
**[6:21]** To draw this as a neural network,
**[6:24]** if the input word is orange,
**[6:29]** which is word 6,257,
**[6:33]** then what you do is input their
**[6:37]** one hot vector passes through E,
**[6:41]** do the multiplication to get the embedding vector 6,257.
**[6:45]** Then what you have is really
**[6:48]** 10,000 possible logistic regression
**[6:51]** classification problems where one of these
**[6:55]** will be the classifier corresponding to.
**[6:59]** Well, is the target word juice
**[7:03]** or not. Then there'll be other words.
**[7:05]** For example, there may be one somewhere
**[7:06]** down here which is predicting is
**[7:09]** the word king or not and so on for these
**[7:11]** are possible words in your vocabulary.
**[7:15]** Think of this as having
**[7:17]** 10,000 binary logistic regression classifiers.
**[7:21]** But instead of training all
**[7:23]** 10,000 of them on every iteration,
**[7:25]** we're only going to train five of them.
**[7:27]** We're going to train the one corresponding to
**[7:28]** the actual target word we got and then
**[7:30]** train four randomly chosen negative examples,
**[7:36]** and this is for the case where K = 4.
**[7:39]** Instead of having one giant 10,000 way softmax,
**[7:46]** which is very expensive to compute,
**[7:49]** we've instead turned it into
**[7:51]** 10,000 binary classification problems.
**[7:55]** Each of which is quite cheap to
**[7:57]** compute and on every iteration,
**[8:00]** we're only going to train five of them,
**[8:02]** or more generally, k+1 of them,
**[8:05]** with k negative examples and
**[8:06]** one positive examples and this
**[8:08]** is why the computational cost of this algorithm
**[8:10]** is much lower because you're
**[8:12]** updating k+1 binary classification problems,
**[8:18]** which is relatively cheap to do on every iteration,
**[8:21]** rather than updating a 10,000 way softmax classifier.
**[8:26]** This technique is called
**[8:27]** negative sampling because what you're
**[8:29]** doing is you had a positive example,
**[8:33]** the orange and the juice.
**[8:34]** Then you would go and deliberately
**[8:36]** generate a bunch of negative examples.
**[8:39]** We've negative samplings, hence the negative sampling,
**[8:42]** which to train four more of these binary classifiers,
**[8:47]** and on every iteration you choose
**[8:50]** four different random negative words
**[8:53]** with which to train your algorithm on.
**[8:55]** Now, before wrapping up,
**[8:57]** one more important detail of this algorithm is,
**[8:59]** how do you choose the negative examples?
**[9:02]** After having chosen the context word orange,
**[9:05]** how do you sample
**[9:07]** these words to generate the negative examples?
**[9:11]** One thing you could do is sample the words in the middle,
**[9:15]** the candidate target words.
**[9:20]** One thing you could do is sample it according to
**[9:22]** the empirical frequency of words in your corpus.
**[9:26]** Just sample it according
**[9:27]** to how often different words appears.
**[9:30]** But the problem with that is that you end up with
**[9:32]** a very high representation of words like the,
**[9:35]** of, and, and so on.
**[9:37]** One other extreme will be let say,
**[9:40]** you use one over the vocab_size.
**[9:42]** Sample the negative examples uniformly random.
**[9:45]** But that's also very non representative
**[9:47]** of the distribution of English words.
**[9:50]** The authors [inaudible] reported that empirically
**[9:54]** what they found to work best was
**[9:56]** to take this heuristic value,
**[9:58]** which is a little bit in between
**[10:00]** the two extremes of
**[10:02]** sampling from the empirical frequencies,
**[10:04]** meaning from whatever is the observed distribution in
**[10:07]** English text to the uniform distribution,
**[10:09]** and what they did was they sampled
**[10:12]** proportional to the frequency
**[10:15]** of a word to the power of three forms.
**[10:18]** If f(w_i) is the observed frequency of
**[10:22]** a particular word in
**[10:24]** the English language or in your training set corpus,
**[10:26]** then by taking it to the power of 3/4.
**[10:30]** This is somewhere in between the extreme of taking
**[10:34]** uniform distribution and the other extreme of
**[10:37]** just taking whatever was
**[10:38]** the observed distribution in your training set.
**[10:40]** I'm not sure this is very theoretically justified,
**[10:45]** but multiple researchers are now using
**[10:47]** this heuristic and it seems to work decently well.
**[10:50]** To summarize, you've seen how you can
**[10:53]** learn word vectors of a software classified,
**[10:55]** but it's very competition expensive and in this video,
**[10:57]** you saw how by changing that to
**[10:59]** a bunch of binary classification problems,
**[11:01]** you can very efficiently learn word vectors,
**[11:05]** and if you run this album,
**[11:06]** you will be able to learn pretty good word vectors.
**[11:09]** Now, of course, as is the case in
**[11:10]** other areas of deep learning as well,
**[11:13]** there are open source implementations and there are also
**[11:15]** pretrained word vectors that others have trained and
**[11:18]** released online under permissive licenses.
**[11:21]** If you want to get going quickly on a NLP problem,
**[11:25]** it'd be reasonable to download
**[11:27]** someone else's word vectors
**[11:29]** and use that as a starting point.
**[11:31]** That's it for the skip-gram model.
**[11:34]** In the next video, I want to share with
**[11:36]** you yet another version of
**[11:38]** a word embedding learning algorithm
**[11:40]** that is maybe even simpler than what you've seen so far.
**[11:43]** In the next video, let's learn
**[11:44]** about the GloVe algorithm.
