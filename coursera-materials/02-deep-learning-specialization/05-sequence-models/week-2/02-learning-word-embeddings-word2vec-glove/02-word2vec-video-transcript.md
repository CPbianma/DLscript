---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 2
section: Learning Word Embeddings: Word2vec & GloVe
item_title: Word2Vec
duration: 13 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/8CZiw/word2vec
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Word2Vec — Transcript

**[0:00]** In the last video, you saw how you can learn a neural language model
**[0:04]** in order to get good word embeddings.
**[0:07]** In this video, you see the Word2Vec algorithm which is simpler and
**[0:11]** comfortably more efficient way to learn this types of embeddings.
**[0:15]** Lets take a look.
**[0:16]** Most of the ideas I'll present in this video are due to Tomas Mikolov, Kai Chen, Greg Corrado, and Jeff Dean.
**[0:20]** Let's say you're given this sentence in your training set.
**[0:27]** In the skip-gram model, what we're going to do is come up with a few context
**[0:33]** to target errors to create our supervised learning problem.
**[0:39]** So rather than having the context be always the last four words or
**[0:44]** the last end words immediately before the target word, what I'm going to do is, say,
**[0:48]** randomly pick a word to be the context word.
**[0:51]** And let's say we chose the word orange.
**[0:54]** And what we're going to do is randomly pick another word within some window.
**[0:59]** Say plus minus five words or
**[1:00]** plus minus ten words of the context word and we choose that to be target word.
**[1:05]** So maybe just by chance you might pick juice to be a target word,
**[1:10]** that's just one word later.
**[1:12]** Or you might choose two words before.
**[1:14]** So you have another pair where the target could be glass or,
**[1:25]** Maybe just by chance you choose the word my as the target.
**[1:29]** And so we'll set up a supervised learning problem where given the context word,
**[1:35]** you're asked to predict what is a randomly chosen word within say, a plus minus
**[1:40]** ten word window, or plus minus five or ten word window of that input context word.
**[1:46]** And obviously, this is not a very easy learning problem, because within
**[1:51]** plus minus 10 words of the word orange, it could be a lot of different words.
**[1:56]** But a goal that's setting up this supervised learning problem,
**[2:00]** isn't to do well on the supervised learning problem per se,
**[2:03]** it is that we want to use this learning problem to learn good word embeddings.
**[2:09]** So, here are the details of the model.
**[2:11]** Let's say that we'll continue to our vocab of 10,000 words.
**[2:16]** And some have been on vocab sizes that exceeds a million words.
**[2:21]** But the basic supervised learning problem we're going to solve is that we want to
**[2:25]** learn the mapping from some Context c, such as the word orange to some
**[2:33]** target, which we will call t, which might be the word juice or
**[2:38]** the word glass or the word my, if we use the example from the previous slide.
**[2:43]** So in our vocabulary, orange is word 6257, and the word
**[2:48]** juice is the word 4834 in our vocab of 10,000 words.
**[2:55]** And so that's the input x that you want to learn to map to that open y.
**[3:00]** So to represent the input such as the word orange, you can start out with some one
**[3:05]** hot vector which is going to be write as O subscript C, so
**[3:08]** there's a one hot vector for the context words.
**[3:11]** And then similar to what you saw on the last video you can take
**[3:15]** the embedding matrix E, multiply E by the vector O subscript C, and
**[3:20]** this gives you your embedding vector for the input context word,
**[3:25]** so here EC is equal to capital E times that one hot vector.
**[3:29]** Then in this new network that we formed we're going to take this vector EC and
**[3:34]** feed it to a softmax unit.
**[3:36]** So I've been drawing softmax unit as a node in a neural network.
**[3:40]** That's not an o, that's a softmax unit.
**[3:43]** And then there's a drop in the softmax unit to output y hat.
**[3:49]** So to write out this model in detail.
**[3:52]** This is the model, the softmax model,
**[3:57]** probability of different tanka words
**[4:02]** given the input context word as e to the e,
**[4:07]** theta t transpose, ec.
**[4:10]** Divided by some over all words, so we're going to say,
**[4:14]** sum from J equals one to all 10,000 words of e to the theta j transposed ec.
**[4:19]** So here theta T is the parameter associated with,
**[4:25]** I'll put t, but really there's a chance
**[4:31]** of a particular word, t, being the label.
**[4:39]** So I've left off the biased term to solve mass but
**[4:43]** we could include that too if we wish.
**[4:49]** And then finally the loss function for softmax will be the usual.
**[4:57]** So we use y to represent the target word.
**[5:02]** And we use a one-hot representation for y hat and y here.
**[5:05]** Then the lost would be The negative log
**[5:10]** liklihood, so sum from i equals 1
**[5:16]** to 10,000 of yi log yi hat.
**[5:20]** So that's a usual loss for softmax where
**[5:24]** we're representing the target y as a one hot vector.
**[5:29]** So this would be a one hot vector with just 1 1 and the rest zeros.
**[5:34]** And if the target word is juice, then it'd be element 4834 from up here.
**[5:42]** That is equal to 1 and the rest will be equal to 0.
**[5:44]** And similarly Y hat will be a 10,000 dimensional vector output by the softmax
**[5:50]** unit with probabilities for all 10,000 possible targets words.
**[5:55]** So to summarize, this is the overall little model, little neural
**[6:00]** network with basically looking up the embedding and then just a soft max unit.
**[6:06]** And the matrix E will have a lot of parameters, so the matrix E has parameters
**[6:11]** corresponding to all of these embedding vectors, E subscript C.
**[6:16]** And then the softmax unit also has parameters that gives the theta
**[6:21]** T parameters but if you optimize this loss function with respect to the all of
**[6:27]** these parameters, you actually get a pretty good set of embedding vectors.
**[6:33]** So this is called the skip-gram model because is taking as input one word
**[6:38]** like orange and then trying to predict some words skipping a few words from
**[6:43]** the left or the right side.
**[6:45]** To predict what comes little bit before little bit after the context words.
**[6:50]** Now, it turns out there are a couple problems with using this algorithm.
**[6:54]** And the primary problem is computational speed.
**[6:58]** In particular, for the softmax model, every time you want to evaluate this
**[7:03]** probability, you need to carry out a sum over all 10,000 words in your vocabulary.
**[7:09]** And maybe 10,000 isn't too bad, but
**[7:12]** if you're using a vocabulary of size 100,000 or a 1,000,000,
**[7:16]** it gets really slow to sum up over this denominator every single time.
**[7:20]** And, in fact, 10,000 is actually already that will be quite slow, but
**[7:24]** it makes even harder to scale to larger vocabularies.
**[7:27]** So there are a few solutions to this, one which you see in the literature
**[7:32]** is to use a hierarchical softmax classifier.
**[7:36]** And what that means is,
**[7:38]** instead of trying to categorize something into all 10,000 carries on one go.
**[7:44]** Imagine if you have one classifier,
**[7:46]** it tells you is the target word in the first 5,000 words in the vocabulary?
**[7:51]** Or is in the second 5,000 words in the vocabulary?
**[7:54]** And let's say this binary cost that it tells you this is in the first 5,000
**[7:58]** words, think of second class to tell you that this in the first 2,500
**[8:03]** words of vocab or in the second 2,500 words vocab and so on.
**[8:07]** Until eventually you get down to classify exactly what word it is, so
**[8:12]** that the leaf of this tree, and so having a tree of classifiers like this,
**[8:18]** means that each of the retriever nodes of the tree can be just a binding classifier.
**[8:25]** And so you don't need to sum over all 10,000 words or
**[8:28]** else it will capsize in order to make a single classification.
**[8:32]** In fact, the computational classifying tree like this
**[8:35]** scales like log of the vocab size rather than linear in vocab size.
**[8:40]** So this is called a hierarchical softmax classifier.
**[8:44]** I should mention in practice, the hierarchical softmax classifier doesn't
**[8:48]** use a perfectly balanced tree or this perfectly symmetric tree,
**[8:54]** with equal numbers of words on the left and right sides of each branch.
**[8:58]** In practice, the hierarchical software classifier can be developed so
**[9:03]** that the common words tend to be on top,
**[9:06]** whereas the less common words like durian can be buried much deeper in the tree.
**[9:12]** Because you see the more common words more often, and so
**[9:15]** you might need only a few traversals to get to common words like the and of.
**[9:19]** Whereas you see less frequent words like durian much less often, so it says
**[9:22]** okay that are buried deep in the tree because you don't need to go that deep.
**[9:26]** So there are various heuristics for
**[9:28]** building the tree how you used to build the hierarchical software spire.
**[9:36]** So this is one idea you see in the literature,
**[9:38]** the speeding up the softmax classification.
**[9:41]** And you can read more details of this on the paper that I referenced by Thomas Mikolov
**[9:47]** and others, on the first slide. But I won't spend too much more time.
**[9:51]** Because in the next video, where she talk about a different method,
**[9:56]** called nectar sampling, which I think is even simpler.
**[9:59]** And also works really well for speeding up the softmax classifier and
**[10:05]** the problem of needing the sum over the entire cap size in the denominator.
**[10:08]** So you see more of that in the next video.
**[10:11]** But before moving on, one quick Topic I want you to understand
**[10:15]** is how to sample the context C.
**[10:18]** So once you sample the context C, the target T can be sampled within,
**[10:23]** say, a plus minus ten word window of the context C, but
**[10:27]** how do you choose the context C?
**[10:29]** One thing you could do is just sample uniformly, at random,
**[10:32]** When we do that, you find that there are some words like the, of, a,
**[10:38]** and, to and so on that appear extremely frequently.
**[10:43]** And so, if you do that, you find that in your context to target mapping pairs just
**[10:48]** get these these types of words extremely frequently, whereas there are other words
**[10:52]** like orange, apple, and also durian that don't appear that often.
**[10:58]** And maybe you don't want your training site to be dominated by these extremely
**[11:02]** frequently or current words, because then you spend almost all the effort updating
**[11:07]** EC, for those frequently occurring words.
**[11:10]** But you want to make sure that you spend some time updating the embedding, even for
**[11:15]** these less common words like e durian.
**[11:18]** So in practice the distribution of words pc isn't taken
**[11:22]** just entirely uniformly at random for the training set purpose, but
**[11:26]** instead there are different heuristics that you could use in order to balance out
**[11:31]** something from the common words together with the less common words.
**[11:35]** So that's it for the Word2Vec skip-gram model.
**[11:39]** If you read the original paper by that I referenced earlier, you find that that
**[11:45]** paper actually had two versions of this Word2Vec model, the skip gram was one.
**[11:48]** And the other one is called the CBow, the continuous backwards model,
**[11:53]** which takes the surrounding contexts from middle word, and
**[11:55]** uses the surrounding words to try to predict the middle word,
**[11:58]** and that algorithm also works, it has some advantages and disadvantages.
**[12:02]** But the key problem with this algorithm with the skip-gram model as presented so
**[12:07]** far is that the softmax step is very expensive to calculate because needing to
**[12:12]** sum over your entire vocabulary size into the denominator of the soft packs.
**[12:17]** In the next video I show you an algorithm that modifies the training objective
**[12:22]** that makes it run much more efficiently therefore lets you apply this in a much
**[12:27]** bigger training set as well and therefore learn much better word embeddings.
**[12:31]** Lets go onto the next video.
