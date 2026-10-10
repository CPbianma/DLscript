---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 4
section: Transformers
item_title: Self-Attention
duration: 12 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/lsvRK/self-attention
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Self-Attention — Transcript

**[0:02]** Let's jump in to talk about
**[0:05]** the self-attention mechanism of transformers.
**[0:09]** If you can get the main idea behind this video,
**[0:12]** you'll understand the most important core idea
**[0:15]** behind what makes transformer networks
**[0:17]** work. Let's jump in.
**[0:19]** You've seen how attention is used with
**[0:21]** sequential neural networks such as RNNs.
**[0:24]** To use attention with a style more late CNNs,
**[0:28]** you need to calculate self-attention,
**[0:30]** where you create attention-based representations
**[0:33]** for each of the words in your input sentence.
**[0:36]** Let's use our running example,
**[0:39]** Jane, visite, l'Afrique, en, septembre,
**[0:41]** our goal will be for each word to
**[0:45]** compute an attention-based representation like this.
**[0:51]** So we'll end up with five of these,
**[0:55]** since our sentence has five words.
**[0:58]** When we've computed them we'll
**[1:00]** call the five representations with
**[1:02]** these five words A1through A5.
**[1:07]** I know you're starting to see a bunch
**[1:09]** of symbols Q, K, and V,
**[1:12]** we'll explain what these symbols mean
**[1:15]** in a later slide so don't worry about them for now.
**[1:17]** The running example I'm going to use
**[1:20]** is take the word l'Afrique in this sentence.
**[1:24]** We'll step through on the next slide how
**[1:27]** the transformer network's self-attention mechanism
**[1:31]** allows you to compute A3 for this word,
**[1:36]** and then you do the same thing for
**[1:38]** the other words in the sentence as well.
**[1:39]** Now you learn previously about word embeddings.
**[1:43]** One way to represent l'Afrique would be to just
**[1:45]** look up the word embedding for l'Afrique.
**[1:49]** But depending on the context,
**[1:51]** are we thinking of l'Afrique or Africa as a site of
**[1:55]** historical interests or as a holiday destination,
**[2:00]** or as the world's second largest continent.
**[2:04]** Depending on how you're thinking of l'Afrique,
**[2:07]** you may choose to represent it differently,
**[2:10]** and that's what this representation A(3) will do.
**[2:13]** It will look at the surrounding words
**[2:16]** to try to figure out what's
**[2:18]** actually going on in how
**[2:20]** we're talking about Africa in this sentence,
**[2:22]** and find the most appropriate representation for this.
**[2:26]** In terms of the actual calculation,
**[2:29]** it won't be too different from
**[2:31]** the attention mechanism you saw
**[2:33]** previously as applied in the context of RNNs,
**[2:36]** except we'll compute these representations
**[2:39]** in parallel for all five words in a sentence.
**[2:42]** When we're building attention on top of RNNs,
**[2:45]** this was the equation we used.
**[2:48]** With the self-attention mechanism,
**[2:50]** the attention equation is
**[2:53]** instead going to look like this.
**[2:55]** You can see the equations have some similarity.
**[2:59]** The inner term here also involves a softmax,
**[3:03]** just like this term over here on the left,
**[3:06]** and you can think of
**[3:07]** the exponent terms as being akin to attention values.
**[3:14]** Exactly how these terms are worked
**[3:16]** out you'll see in the next slide.
**[3:19]** So again, don't worry about the details just yet.
**[3:22]** But the main difference is that for
**[3:24]** every word, say for l'Afrique,
**[3:27]** you have three values called the query, key, and value.
**[3:36]** These vectors are the key inputs to
**[3:39]** computing the attention value for each words.
**[3:45]** Now, let's step through the steps
**[3:48]** needed to actually calculate A3.
**[3:52]** On this slide, let's step through
**[3:54]** the computations you need to go from the words
**[3:57]** l'Afrique to the self-attention representation A3.
**[4:02]** For reference, I've also printed up here on
**[4:04]** the upper-right that softmax-like
**[4:07]** equation from the previous slide.
**[4:09]** First, we're going to associate each of the words with
**[4:13]** three values called the query key and value pairs.
**[4:18]** If X3 is the word embedding for l'Afrique,
**[4:24]** the way that's Q3 is computed is as a learned matrix,
**[4:32]** which I'm going to write as WQ times X3,
**[4:38]** and similarly for the key and value pairs,
**[4:41]** so K3 is WK times
**[4:47]** X3 and V3 is WV times X3.
**[4:56]** These matrices, WQ, WK, and WV,
**[5:01]** are parameters of this learning algorithm,
**[5:04]** and they allow you to pull off these query,
**[5:07]** key, and value vectors for each word.
**[5:10]** So what are these query key
**[5:12]** and value vectors supposed to do?
**[5:14]** They were named using a loose analogy to a concept in
**[5:17]** databases where you can have
**[5:19]** queries and also key-value pairs.
**[5:22]** If you're familiar with those types of databases,
**[5:25]** the analogy may make sense to you,
**[5:27]** but if you're not familiar with
**[5:28]** that database concept, don't worry about it.
**[5:31]** Let me give one intuition
**[5:33]** behind the intent of these query,
**[5:36]** key, and value of vectors.
**[5:39]** Q3 is a question that you get to ask about l'Afrique.
**[5:45]** Q3 may represent a question like, what's happening there?
**[5:52]** Africa, l'Afrique is a destination.
**[5:55]** You might want to know when
**[5:57]** computing A^3, what's happening there.
**[6:01]** What we're going to do is compute
**[6:05]** the inner product between q^3 and k^1,
**[6:09]** between Query 3 and Key 1,
**[6:12]** and this will tell us how good is an answer
**[6:15]** where it's one to
**[6:17]** the question of what's happening in Africa.
**[6:19]** Then we compute the inner product between
**[6:22]** q^3 and k^2 and this is intended to tell
**[6:26]** us how good is visite an answer to the question of
**[6:31]** what's happening in Africa and so
**[6:33]** on for the other words in the sequence.
**[6:36]** The goal of this operation is to
**[6:39]** pull up the most information that's needed
**[6:42]** to help us compute
**[6:44]** the most useful representation A^3 up here.
**[6:49]** Again, just for intuition building
**[6:52]** if k^1 represents that this word is a person,
**[6:57]** because Jane is a person,
**[6:58]** and k^2 represents that the second word,
**[7:01]** visite, is an action,
**[7:04]** then you may find that q^3 inter producted
**[7:07]** with k^2 has the largest value,
**[7:10]** and this may be intuitive example,
**[7:13]** might suggest that visite,
**[7:15]** gives you the most relevant contexts
**[7:17]** for what's happening in Africa.
**[7:18]** Which is that, it's viewed as a destination for a visit.
**[7:22]** What we will do is take
**[7:25]** these five values in
**[7:28]** this row and compute a Softmax over them.
**[7:32]** There's actually this Softmax over here,
**[7:36]** and in the example that we've been talking about,
**[7:39]** q^3 times k^2 corresponding
**[7:42]** to word visite maybe has the largest value.
**[7:46]** I'm going to shade that blue over here.
**[7:48]** Then finally, we're going to take
**[7:50]** these Softmax values and multiply them with v^1,
**[7:54]** which is the value for word 1,
**[7:56]** the value for word 2, and so on,
**[8:00]** and so these values correspond to that value up there.
**[8:08]** Finally, we sum it all up.
**[8:11]** This summation corresponds to
**[8:13]** this summation operator and so adding up
**[8:16]** all of these values gives you A^3,
**[8:20]** which is just equal to this value here.
**[8:23]** Another way to write A^3 is really as A,
**[8:28]** this A up here of q^3,
**[8:33]** k, v. But sometimes it will be
**[8:36]** more convenient to just write A^3 like that.
**[8:41]** The key advantage of this representation is
**[8:45]** the word of l'Afrique isn't some fixed word embedding.
**[8:50]** Instead, it lets the self-attention mechanism
**[8:54]** realize that l'Afrique is the destination of a visite,
**[8:58]** of a visit, and thus compute a richer,
**[9:01]** more useful representation for this word.
**[9:05]** Now, I've been using the third word,
**[9:07]** l'Afrique as a running example
**[9:09]** but you could use this process for all five
**[9:12]** words in your sequence to get
**[9:14]** similarly rich representations for Jane,
**[9:17]** visite, l'Afrique, en, septembre.
**[9:22]** If you put all of these five computations together,
**[9:27]** denotation used in literature looks like this,
**[9:32]** where you can summarize all
**[9:33]** of these computations that we just talked
**[9:35]** about for all the words in
**[9:36]** the sequence by writing Attention(Q,
**[9:39]** K, V) where Q, K,
**[9:42]** V matrices with all of these values,
**[9:46]** and this is just
**[9:47]** a compressed or vectorized representation
**[9:51]** of this equation up here.
**[9:54]** The term in the denominator
**[9:57]** is just to scale the dot-product,
**[9:59]** so it doesn't explode.
**[10:00]** You don't really need to worry about it.
**[10:02]** But another name for this type of attention
**[10:05]** is the scaled dot-product attention.
**[10:09]** This is the one represented in
**[10:11]** the original transformer architecture paper,
**[10:13]** Attention Is All You Need As Well.
**[10:16]** That's the self-attention mechanism
**[10:19]** of the transformer network.
**[10:21]** To recap, associated with each of
**[10:24]** the five words you end up with a query,
**[10:27]** a key, and a value.
**[10:29]** The query lets you ask a question about that word,
**[10:33]** such as what's happening in Africa.
**[10:35]** The key looks at all of the other words,
**[10:38]** and by the similarity to the query,
**[10:41]** helps you figure out which words gives
**[10:43]** the most relevant answer to that question.
**[10:46]** In this case, visite is what's
**[10:48]** happening in Africa, someone's visiting Africa.
**[10:51]** Then finally, the value allows the representation to
**[10:56]** plug in how visite should be represented within A^3,
**[11:00]** within the representation of Africa.
**[11:03]** This allows you to come up with
**[11:05]** a representation for the word
**[11:06]** Africa that says this is
**[11:09]** Africa and someone is visiting Africa.
**[11:11]** This is a much more nuanced,
**[11:13]** much richer representation for the world than if you
**[11:16]** just had to pull up the same fixed word embedding
**[11:18]** for every single word
**[11:19]** without being able to adapt it based
**[11:22]** on what words are to
**[11:23]** the left and to the right of that word.
**[11:25]** We've all got to take into account and in the context.
**[11:28]** Now, you have learned about the self-attention mechanism.
**[11:33]** We're going to put a big for-loop
**[11:34]** over this whole thing and that
**[11:36]** will be the multi-headed attention mechanism.
**[11:39]** Let's dive into the details of that in the next video.
