---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 2
section: "Learning Word Embeddings: Word2vec & GloVe"
item_title: GloVe Word Vectors
duration: 11 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/IxDTG/glove-word-vectors
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# GloVe Word Vectors — Transcript

**[0:00]** You learn about several algorithms for computing words embeddings.
**[0:04]** Another algorithm that has some momentum in the NLP community is the GloVe algorithm.
**[0:10]** This is not used as much as the Word2Vec or the skip-gram models,
**[0:14]** but it has some enthusiasts.
**[0:16]** Because I think, in part of its simplicity.
**[0:19]** Let's take a look.
**[0:21]** The GloVe algorithm was created by Jeffrey Pennington,
**[0:24]** Richard Socher, and Chris Manning.
**[0:25]** And GloVe stands for global vectors for word representation.
**[0:30]** So, previously, we were sampling pairs of words,
**[0:33]** context and target words,
**[0:35]** by picking two words that appear in close proximity to each other in our text corpus.
**[0:42]** So, what the GloVe algorithm does is,
**[0:43]** it starts off just by making that explicit.
**[0:46]** So, let's say X_ij be the number of times that
**[0:52]** a word i appears in the context of j.
**[1:01]** And so, here i and j play the role of t and c,
**[1:09]** so you can think of X_ij as being x subscript tc.
**[1:13]** But, you can go through your training corpus and just count up
**[1:17]** how many words does a word i appear in the context of a different word j.
**[1:22]** How many times does the word t appear in context of different words c. And
**[1:27]** depending on the definition of context and target words,
**[1:33]** you might have that X_ij equals X_ji.
**[1:37]** And in fact, if you're defining context and target in terms
**[1:40]** of whether or not they appear within plus minus 10 words of each other,
**[1:44]** then it would be a symmetric relationship.
**[1:47]** Although, if your choice of context was that,
**[1:50]** the context is always the word immediately before the target word,
**[1:54]** then X_ij and X_ji may not be symmetric like this.
**[1:59]** But for the purposes of the GloVe algorithm,
**[2:02]** we can define context and target as
**[2:05]** whether or not the two words appear in close proximity,
**[2:09]** say within plus or minus 10 words of each other.
**[2:13]** So, X_ij is a count that captures how often do words i and j appear with each other,
**[2:22]** or close to each other.
**[2:24]** So what the GloVe model does is,
**[2:26]** it optimizes the following.
**[2:28]** We're going to minimize the difference between theta i
**[2:36]** transpose e_j minus log of X_ij squared.
**[2:45]** I'm going to fill in some of the parts of this equation.
**[2:48]** But again, think of i and j as playing the role of t and c. So this is a bit
**[2:54]** like what you saw previously with theta t transpose e_c.
**[3:00]** And what you want is, for this to tell you how related are those two words?
**[3:05]** How related are words t and c?
**[3:07]** How related are words i and j as measured by how often they occur with each other?
**[3:12]** Which is affected by this X_ij.
**[3:17]** And so, what we're going to do is,
**[3:20]** solve for parameters theta and e using gradient descent to minimize the sum
**[3:28]** over i equals one to 10,000 sum over j from one to 10,000 of this difference.
**[3:36]** So you just want to learn vectors,
**[3:38]** so that their end product is a good predictor for how often the two words occur together.
**[3:44]** Now, just some additional details,
**[3:47]** if X_ij is equal to zero,
**[3:49]** then log of 0 is undefined, is negative infinity.
**[3:52]** And so, what we do is,
**[3:53]** we want sum over the terms where X_ij is equal to zero.
**[3:59]** And so, what we're going to do is,
**[4:00]** add an extra weighting term.
**[4:03]** So this is going to be a weighting term,
**[4:07]** and this will be equal to zero if X_ij is equal to zero.
**[4:17]** And we're going to use a convention that zero log zero is equal to zero.
**[4:26]** So what this means is,
**[4:27]** that if X_ij is equal to zero,
**[4:29]** just don't bother to sum over that X_ij pair.
**[4:32]** So then this log of zero term is not relevant.
**[4:35]** So this means the sum is sum only over the pairs of
**[4:40]** words that have co-occurred at least once in that context-target relationship.
**[4:46]** The other thing that F(X_ij) does is that,
**[4:48]** there are some words they just appear very often in the English language like,
**[4:52]** this, is, of, a, and so on.
**[4:55]** Sometimes we used to call them stop words but there's really
**[4:57]** a continuum between frequent and infrequent words.
**[4:59]** And then there are also some infrequent words like durian,
**[5:02]** which you actually still want to take into account,
**[5:04]** but not as frequently as the more common words.
**[5:09]** And so, the weighting factor can be a function
**[5:12]** that gives a meaningful amount of computation,
**[5:16]** even to the less frequent words like durian,
**[5:20]** and gives more weight but not an unduly large amount of weight to words like,
**[5:25]** this, is, of, a, which just appear lost in language.
**[5:28]** And so, there are various heuristics for choosing this weighting function F that
**[5:33]** need or gives these words too much weight
**[5:37]** nor gives the infrequent words too little weight.
**[5:41]** You can take a look at the GloVe paper,
**[5:43]** they are referenced in the previous slide,
**[5:45]** if you want the details of how F can be chosen to be a heuristic to accomplish this.
**[5:51]** And then, finally, one funny thing about this algorithm is
**[5:56]** that the roles of theta and e are now completely symmetric.
**[6:01]** So, theta i and e_j are symmetric in that,
**[6:07]** if you look at the math,
**[6:08]** they play pretty much the same role and you could reverse them or sort them around,
**[6:12]** and they actually end up with the same optimization objective.
**[6:17]** One way to train the algorithm is to initialize theta and e
**[6:21]** both uniformly around gradient descent to minimize its objective,
**[6:26]** and then when you're done for every word,
**[6:30]** to then take the average.
**[6:31]** For a given words w,
**[6:33]** you can have e final to be equal
**[6:36]** to the embedding that was trained through this gradient descent procedure,
**[6:41]** plus theta trained through this gradient descent procedure divided by two,
**[6:46]** because theta and e in this particular formulation play
**[6:50]** symmetric roles unlike the earlier models we saw in the previous videos,
**[6:54]** where theta and e actually play different roles and couldn't just be averaged like that.
**[6:59]** That's it for the GloVe algorithm.
**[7:02]** I think one confusing part of this algorithm is,
**[7:04]** if you look at this equation, it seems almost too simple.
**[7:07]** How could it be that just minimizing
**[7:09]** a square cost function like this allows you to learn meaningful word embeddings?
**[7:12]** But it turns out that this works.
**[7:15]** And the way that the inventors end up with this algorithm was,
**[7:18]** they were building on the history of
**[7:19]** much more complicated algorithms like the newer language model,
**[7:23]** and then later, there came the Word2Vec skip-gram model,
**[7:28]** and then this came later.
**[7:30]** And we really hope to simplify all of the earlier algorithms.
**[7:34]** Before concluding our discussion of algorithms concerning word embeddings,
**[7:41]** there's one more property of them that we should discuss briefly.
**[7:47]** Which is that? We started off with this featurization view
**[7:50]** as the motivation for learning word vectors.
**[7:54]** We said, "Well, maybe the first component of the embedding vector to represent gender,
**[7:58]** the second component to represent how royal it is,
**[8:02]** then the age and then whether it's a food, and so on."
**[8:06]** But when you learn a word embedding using one of the algorithms that we've seen,
**[8:10]** such as the GloVe algorithm that we just saw on the previous slide,
**[8:15]** what happens is, you cannot guarantee that
**[8:18]** the individual components of the embeddings are interpretable.
**[8:22]** Why is that? Well, let's say that there is some space where the first axis is
**[8:27]** gender and the second axis is royal.
**[8:32]** What you can do is guarantee that the first axis of the embedding vector is
**[8:37]** aligned with this axis of meaning, of gender, royal, age and food.
**[8:43]** And in particular,
**[8:46]** the learning algorithm might choose this to be axis of the first dimension.
**[8:51]** So, given maybe a context of words,
**[8:54]** so the first dimension might be this axis and the second dimension might be this.
**[8:58]** Or it might not even be orthogonal,
**[9:00]** maybe it'll be a second non-orthogonal axis,
**[9:05]** could be the second component of the word embeddings you actually learn.
**[9:09]** And when we see this,
**[9:10]** if you have a subsequent understanding of linear algebra is that,
**[9:17]** if there was some invertible matrix A,
**[9:19]** then this could just as easily be replaced with A times
**[9:26]** theta i transpose A inverse transpose e_j.
**[9:35]** Because we expand this out,
**[9:36]** this is equal to theta i transpose A transpose A inverse transpose times e_j.
**[9:44]** And so, the middle term cancels out and we're left
**[9:46]** with theta i transpose e_j, same as before.
**[9:49]** Don't worry if you didn't follow the linear algebra,
**[9:51]** but that's a brief proof that shows that with an algorithm like this,
**[9:56]** you can't guarantee that the axis used to represent
**[10:00]** the features will be well-aligned with what might be easily humanly interpretable axis.
**[10:06]** In particular, the first feature might be a combination of gender,
**[10:10]** and royal, and age, and food,
**[10:11]** and cost, and size,
**[10:14]** is it a noun or an action verb,
**[10:16]** and all the other features.
**[10:17]** It's very difficult to look at individual components,
**[10:21]** individual rows of the embedding matrix and assign the human interpretation to that.
**[10:27]** But despite this type of linear transformation,
**[10:30]** the parallelogram map that we worked out
**[10:33]** when we were describing analogies, that still works.
**[10:36]** And so, despite this potentially arbitrary linear transformation of the features,
**[10:42]** you end up learning the parallelogram map for figure analogies still works.
**[10:51]** So, that's it for learning word embeddings.
**[10:54]** You've now seen a variety of algorithms for learning these word embeddings and you get
**[10:57]** to play them more in this week's programming exercise as well.
**[11:01]** Next, I'd like to show you how you can use
**[11:03]** these algorithms to carry out sentiment classification.
**[11:06]** Let's go onto the next video.
