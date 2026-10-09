---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 1
section: Recurrent Neural Networks
item_title: Different Types of RNNs
duration: 10 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/BO8PS/different-types-of-rnns
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Different Types of RNNs — Transcript

**[0:00]** So far, you've seen an RNN architecture where the number of inputs,
**[0:04]** Tx, is equal to the number of outputs, Ty.
**[0:08]** It turns out that for other applications,
**[0:10]** Tx and Ty may not always be the same,
**[0:13]** and in this video,
**[0:14]** you'll see a much richer family of RNN architectures.
**[0:18]** You might remember this slide from the first video of this week,
**[0:22]** where the input x and the output y can be many different types.
**[0:29]** And it's not always the case that Tx has to be equal to Ty.
**[0:34]** In particular, in this example,
**[0:36]** Tx can be length one or even an empty set.
**[0:40]** And then, an example like movie sentiment classification,
**[0:44]** the output y could be just an integer from 1 to 5,
**[0:47]** whereas the input is a sequence.
**[0:49]** And in name entity recognition,
**[0:52]** in the example we're using,
**[0:53]** the input length and the output length are identical,
**[0:57]** but there are also some problems were the input length and the output length can
**[1:00]** be different.They're both our sequences but have different lengths,
**[1:04]** such as machine translation where a French sentence and
**[1:08]** English sentence can mean two different numbers of words to say the same thing.
**[1:14]** So it turns out that we could modify
**[1:16]** the basic RNN architecture to address all of these problems.
**[1:20]** And the presentation in this video was inspired by a blog post by Andrej Karpathy,
**[1:25]** titled, The Unreasonable Effectiveness of Recurrent Neural Networks.
**[1:30]** Let's go through some examples.
**[1:32]** The example you've seen so far use Tx equals Ty,
**[1:36]** where we had an input sequence x(1),
**[1:40]** x(2) up to x(Tx),
**[1:43]** and we had a recurrent neural network that works as
**[1:48]** follows when we would input x(1) to compute y hat (1),
**[1:55]** y hat (2), and so on up to y hat (Ty), as follows.
**[2:03]** And in early diagrams,
**[2:07]** I was drawing a bunch of circles here to denote neurons but I'm just going
**[2:11]** to make those little circles for most of this video,
**[2:15]** just to make the notation simpler.
**[2:17]** So, this is what you might call a many-to-many architecture
**[2:23]** because the input sequence has many inputs as
**[2:27]** a sequence and the outputs sequence is also has many outputs.
**[2:31]** Now, let's look at a different example.
**[2:34]** Let's say, you want to address sentiments classification.
**[2:38]** Here, x might be a piece of text,
**[2:42]** such as it might be a movie review that says,
**[2:45]** "There is nothing to like in this movie."
**[2:46]** So x is going to be sequenced,
**[2:49]** and y might be a number from 1 to 5,
**[2:51]** or maybe 0 or 1.
**[2:53]** This is a positive review or a negative review,
**[2:55]** or it could be a number from 1 to 5.
**[2:58]** Do you think this is a one-star,
**[3:00]** two-star, three, four, or five-star review?
**[3:02]** So in this case, we can simplify the neural network architecture as follows.
**[3:07]** I will input x(1), x(2).
**[3:12]** So, input the words one at a time.
**[3:15]** So if the input text was,
**[3:18]** "There is nothing to like in this movie."
**[3:21]** So "There is nothing to like in this movie," would be the input.
**[3:26]** And then rather than having to use an output at every single time-step,
**[3:30]** we can then just have the RNN read into entire sentence and have it output
**[3:35]** y at the last time-step when it has already input the entire sentence.
**[3:40]** So, this neural network would be a many-to-one architecture.
**[3:47]** Because as many inputs,
**[3:48]** it inputs many words and then it just outputs one number.
**[3:53]** For the sake of completeness,
**[3:56]** there is also a one-to-one architecture.
**[4:01]** So this one is maybe less interesting.
**[4:07]** The smaller the standard neural network,
**[4:09]** we have some input x and we just had some output y.
**[4:12]** And so, this would be the type of neural network that we covered
**[4:14]** in the first two courses in this sequence.
**[4:18]** Now, in addition to many-to-one,
**[4:20]** you can also have a one-to-many architecture.
**[4:24]** So an example of a one-to-many neural network architecture will be music generation.
**[4:33]** And in fact, you get to implement this yourself in one of
**[4:37]** the primary exercises for this course where you go is have a neural network,
**[4:41]** output a set of notes corresponding to a piece of music.
**[4:48]** And the input x could be maybe just an integer,
**[4:51]** telling it what genre of music you want or what is the first note of the music you want,
**[4:56]** and if you don't want to input anything,
**[4:58]** x could be a null input, could always be the vector zeroes as well.
**[5:02]** For that, the neural network architecture would be your input x.
**[5:07]** And then, have your RNN output.
**[5:10]** The first value, and then,
**[5:13]** have that, with no further inputs, output.
**[5:17]** The second value and then go on to output.
**[5:20]** The third value, and so on,
**[5:24]** until you synthesize the last notes of the musical piece.
**[5:29]** If you want, you can have this input a(0) as well.
**[5:34]** One technical now what you see in the later video is that,
**[5:38]** when you're actually generating sequences,
**[5:40]** often you take these first synthesized output and feed it to the next layer as well.
**[5:45]** So the network architecture actually ends up looking like that.
**[5:50]** So, we've talked about many-to- many,
**[5:52]** many-to-one, one-to-many, as well as one-to-one.
**[5:55]** It turns out there's one more interesting example of
**[5:59]** many-to-many which is worth describing.
**[6:03]** Which is when the input and the output length are different.
**[6:07]** So, in the many-to-many example,
**[6:09]** you saw just now, the input length and the output length have to be exactly the same.
**[6:14]** For an application like machine translation,
**[6:17]** the number of words in the input sentence,
**[6:20]** say a French sentence,
**[6:21]** and the number of words in the output sentence,
**[6:23]** say the translation into English,
**[6:26]** those sentences could be different lengths.
**[6:28]** So here's an alternative new network architecture where you might have a neural network,
**[6:33]** first, reading the sentence.
**[6:36]** So first, reading the input,
**[6:38]** say French sentence that you want to translate to English.
**[6:41]** And having done that, you then,
**[6:44]** have the neural network output the translation.
**[6:49]** As all those y hat of (Ty).
**[6:54]** And so, with this architecture,
**[6:56]** Tx and Ty can be different lengths.
**[6:59]** And again, you could draw on the a(0) [inaudible].
**[7:02]** And so, this that collinear network architecture has two distinct parts.
**[7:07]** There's the encoder which takes as input,
**[7:10]** say a French sentence, and then,
**[7:13]** there's is a decoder,
**[7:14]** which having read in the sentence,
**[7:17]** outputs the translation into a different language.
**[7:21]** So this would be an example of a many-to-many architecture.
**[7:26]** So by the end of this week,
**[7:27]** you have a good understanding of all the components
**[7:31]** needed to build these types of architectures.
**[7:35]** And then, technically, there's
**[7:37]** one other architecture which we'll talk about only in week four,
**[7:41]** which is attention based architectures.
**[7:42]** Which maybe isn't clearly captured by one of the diagrams we've drawn so far.
**[7:50]** So, to summarize the wide range of RNN architectures,
**[7:55]** there is one-to-one, although if it's one-to-one,
**[8:00]** we could just give it this,
**[8:02]** and this is just a standard generic neural network.
**[8:04]** Well, you don't need an RNN for this.
**[8:06]** But there is one-to-many.
**[8:10]** So, this was a music generation or sequenced generation as example.
**[8:15]** And then, there's many-to-one,
**[8:17]** that would be an example of sentiment classification.
**[8:20]** Where you might want to read as input all the text with a movie review.
**[8:24]** And then, try to figure out that they liked the movie or not.
**[8:28]** There is many-to-many, so the name entity recognition, the example we've been using,
**[8:32]** was this where Tx is equal to Ty.
**[8:37]** And then, finally, there's this other version of many-to-many,
**[8:42]** where for applications like machine translation,
**[8:45]** Tx and Ty no longer have to be the same.
**[8:48]** So, now you know most of the building blocks,
**[8:51]** the building are pretty much all of these neural networks
**[8:54]** except that there are some subtleties with sequence generation,
**[8:58]** which is what we'll discuss in the next video.
**[9:01]** So, I hope you saw from this video that using the basic building blocks of an RNN,
**[9:06]** there's already a wide range of models that you might be able put together.
**[9:11]** But as I mentioned, there are some subtleties to sequence generation,
**[9:15]** which you'll get to implement yourself as well in
**[9:17]** this week's primary exercise where you implement a language model and hopefully,
**[9:21]** generate some fun sequences or some fun pieces of text.
**[9:25]** So, what I want to do in the next video,
**[9:28]** is go deeper into sequence generation.
**[9:31]** Let's see the details in the next video.
