---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 2
section: Introduction to Word Embeddings
item_title: Embedding Matrix
duration: 4 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/K604Z/embedding-matrix
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Embedding Matrix — Transcript

**[0:01]** Let's start to formalize the problem of learning a good word embedding. When you implement an algorithm to
**[0:06]** learn a word embedding, what you end up learning is an
**[0:09]** embedding matrix. Let's take a look at what that means.
**[0:12]** Let's say, as usual we're using
**[0:14]** our 10,000-word vocabulary. So, the vocabulary has A,
**[0:19]** Aaron, Orange, Zulu, maybe also unknown word as a token.
**[0:21]** What we're going to do is
**[0:29]** learn embedding matrix E, which is going
**[0:34]** to be a 300 dimensional by 10,000 dimensional matrix, if you have 10,000 words vocabulary
**[0:43]** or maybe 10,001 is unknown word token,there's one extra token.
**[0:48]** And the columns of this matrix would be the
**[0:51]** different embeddings for the
**[0:54]** 10,000 different words you have in your vocabulary. So, Orange was word number
**[0:58]** 6257 in our vocabulary of 10,000 words. So, one piece of notation
**[1:05]** we'll use is that 06257 was the one-hot vector with
**[1:12]** zeros everywhere and a one in position 6257. And so, this will be a
**[1:20]** 10,000-dimensional vector with a one in just one position.
**[1:25]** So, this isn't quite a drawn scale. Yes, this should be as tall
**[1:29]** as the embedding matrix on the left is wide.
**[1:32]** And if the embedding matrix is called capital E then notice that if you take E
**[1:40]** and multiply it by just one-hot vector by 0 of 6257,
**[1:46]** then this will be a 300-dimensional vector.
**[1:52]** So, E is 300 by 10,000 and 0 is 10,000 by 1.
**[2:00]** So, the product will be 300 by 1,
**[2:05]** so with 300-dimensional vector and notice that
**[2:08]** to compute the first element of this vector,
**[2:12]** of this 300-dimensional vector,
**[2:14]** what you do is you will multiply the first row of the matrix E with this.
**[2:19]** But all of these elements are zero except for
**[2:22]** element 6257 and so you end up with zero times this,
**[2:27]** zero times this, zero times this, and so on.
**[2:29]** And then, 1 times whatever this is,
**[2:32]** and zero times this, zero times this, zero times and so on.
**[2:35]** And so, you end up with the first element as whatever is that elements up there,
**[2:42]** under the Orange column.
**[2:44]** And then, for the second element of this 300-dimensional vector we're computing,
**[2:48]** you would take the vector
**[2:50]** 0657 and multiply it by the second row with the matrix E. So again,
**[2:57]** you have zero times this,
**[2:58]** plus zero times this,
**[3:00]** plus zero times all of these are the elements and then one times this,
**[3:05]** and then zero times everything else and add that together.
**[3:09]** So you end up with this and so on as you go down the rest of this column.
**[3:17]** So, that's why the embedding matrix E times this one-hot vector here winds up
**[3:23]** selecting out this 300-dimensional column corresponding to the word Orange.
**[3:30]** So, this is going to be equal to E 6257 which
**[3:36]** is the notation we're going to use to represent
**[3:39]** the embedding vector that 300 by one dimensional vector for the word Orange.
