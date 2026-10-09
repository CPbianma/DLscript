---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 1
section: Recurrent Neural Networks
item_title: Sampling Novel Sequences
duration: 9 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/MACos/sampling-novel-sequences
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Sampling Novel Sequences — Transcript

**[0:01]** After you train a sequence model, one of the ways you can informally get a sense of
**[0:06]** what is learned is to have a sample novel sequences.
**[0:09]** Let's take a look at how you could do that.
**[0:12]** So remember that a sequence model, models the chance of any
**[0:17]** particular sequence of words as follows, and so what we like to do is
**[0:22]** sample from this distribution to generate noble sequences of words.
**[0:28]** So the network was trained using this structure shown at the top.
**[0:35]** But to sample, you do something slightly different, so what you want to
**[0:40]** do is first sample what is the first word you want your model to generate.
**[0:45]** And so for that you input the usual x1 equals 0, a0 equals 0.
**[0:50]** And now your first time stamp
**[0:54]** will have some max probability over possible outputs.
**[0:58]** So what you do is you then randomly sample according to this soft max distribution.
**[1:05]** So what the soft max distribution gives you is it tells you what is the chance
**[1:09]** that it refers to this a, what is the chance that it refers to this Aaron?
**[1:13]** What's the chance it refers to Zulu,
**[1:16]** what is the chance that the first word is the Unknown word token.
**[1:20]** Maybe it was a chance it was a end of sentence token.
**[1:23]** And then you take this vector and use, for example, the numpy command
**[1:29]** np.random.choice to sample according to distribution
**[1:35]** defined by this vector probabilities, and that lets you sample the first words.
**[1:40]** Next you then go on to the second time step, and
**[1:45]** now remember that the second time step is expecting this y1 as input.
**[1:53]** But what you do is you then take the y1 hat that you just sampled and
**[1:58]** pass that in here as the input to the next timestep.
**[2:02]** So whatever works,
**[2:03]** you just chose the first time step passes this input in the second position, and
**[2:08]** then this soft max will make a prediction for what is y hat 2.
**[2:14]** Example, let's say that after you sample the first word,
**[2:17]** the first word happened to be "the", which is very common choice of first word.
**[2:21]** Then you pass in "the" as x2,
**[2:26]** which is now equal to y hat 1.
**[2:32]** And now you're trying to figure out what is the chance of what
**[2:37]** the second word is given that the first word is "the".
**[2:40]** And this is going to be y hat 2.
**[2:42]** Then you again use this type of sampling function to sample y hat 2.
**[2:48]** And then at the next time stamp,
**[2:51]** you take whatever choice you had represented say as a one hard encoding.
**[2:55]** And pass that to next timestep and
**[3:00]** then you sample the third word to that whatever you chose, and
**[3:05]** you keep going until you get to the last time step.
**[3:08]** And so how do you know when the sequence ends?
**[3:11]** Well, one thing you could do is if the end of sentence token is part
**[3:16]** of your vocabulary, you could keep sampling until you generate an EOS token.
**[3:21]** And that tells you you've hit the end of a sentence and you can stop.
**[3:25]** Or alternatively, if you do not include this in your vocabulary
**[3:28]** then you can also just decide to sample 20 words or 100 words or something, and
**[3:33]** then keep going until you've reached that number of time steps.
**[3:37]** And this particular procedure will sometimes generate an unknown word token.
**[3:43]** If you want to make sure that your algorithm never generates this token,
**[3:47]** one thing you could do is just reject any
**[3:51]** sample that came out as unknown word token and just keep resampling from the rest of
**[3:55]** the vocabulary until you get a word that's not an unknown word.
**[3:59]** Or you can just leave it in the output as well if you don't mind having an unknown
**[4:02]** word output.
**[4:04]** So this is how you would generate a randomly chosen sentence
**[4:08]** from your RNN language model.
**[4:11]** Now, so far we've been building a words level RNN,
**[4:15]** by which I mean the vocabulary are words from English.
**[4:19]** Depending on your application,
**[4:21]** one thing you can do is also build a character level RNN.
**[4:26]** So in this case your vocabulary will just be the alphabets.
**[4:30]** Up to z, and as well as maybe space,
**[4:35]** punctuation if you wish, the digits 0 to 9.
**[4:40]** And if you want to distinguish the uppercase and lowercase,
**[4:44]** you can include the uppercase alphabets as well, and
**[4:47]** one thing you can do as you just look at your training set and
**[4:52]** look at the characters that appears there and use that to define the vocabulary.
**[4:57]** And if you build a character level language model rather than a word level
**[5:02]** language model, then your sequence y1, y2, y3,
**[5:06]** would be the individual characters in your training data,
**[5:12]** rather than the individual words in your training data.
**[5:15]** So for our previous example, the sentence cats average 15 hours of sleep a day.
**[5:22]** In this example, c would be y1, a would be y2,
**[5:27]** t will be y3, the space will be y4 and so on.
**[5:33]** Using a character level language model has some pros and cons.
**[5:37]** One is that you don't ever have to worry about unknown word tokens.
**[5:40]** In particular, a character level language model
**[5:44]** is able to assign a sequence like mau, a non-zero probability.
**[5:48]** Whereas if mau was not in your vocabulary for the word level language model,
**[5:53]** you just have to assign it the unknown word token.
**[5:56]** But the main disadvantage of the character level language model
**[6:01]** is that you end up with much longer sequences.
**[6:04]** So many english sentences will have 10 to 20 words but
**[6:08]** may have many, many dozens of characters.
**[6:11]** And so character language models are not as good as word level language models at
**[6:16]** capturing long range dependencies between how
**[6:19]** the the earlier parts of the sentence also affect the later part of the sentence.
**[6:23]** And character level models are also just more computationally expensive to train.
**[6:28]** So the trend I've been seeing in natural language processing is that for
**[6:32]** the most part, word level language model are still used, but
**[6:36]** as computers gets faster there are more and more applications where people are,
**[6:41]** at least in some special cases, starting to look at more character level models.
**[6:47]** But they tend to be much hardware, much more computationally expensive to train,
**[6:50]** so they are not in widespread use today.
**[6:53]** Except for maybe specialized applications where you might need to deal with
**[6:57]** unknown words or other vocabulary words a lot.
**[7:00]** Or they are also used in more specialized applications where you
**[7:02]** have a more specialized vocabulary.
**[7:06]** So under these methods,
**[7:08]** what you can now do is build an RNN to look at the purpose of English text,
**[7:13]** build a word level, build a character
**[7:18]** language model, sample from the language model that you've trained.
**[7:23]** So here are some examples of text thatwere examples from a language model,
**[7:27]** actually from a culture level language model.
**[7:30]** And you get to implement something like this yourself in the [INAUDIBLE] exercise.
**[7:34]** If the model was trained on news articles,
**[7:36]** then it generates texts like that shown on the left.
**[7:39]** And this looks vaguely like news text, not quite grammatical,
**[7:44]** but maybe sounds a little bit like things that could be appearing news,
**[7:48]** concussion epidemic to be examined.
**[7:50]** And it was trained on Shakespearean text and
**[7:52]** then it generates stuff that sounds like Shakespeare could have written it.
**[7:55]** The mortal moon hath her eclipse in love.
**[7:57]** And subject of this thou art another this fold.
**[8:00]** When besser be my love to me see sabl's.
**[8:02]** For whose are ruse of mine eyes heaves.
**[8:06]** So that's it for the basic RNN, and how you can build a language model using it,
**[8:11]** as well as sample from the language model that you've trained.
**[8:15]** In the next few videos, I want to discuss further some of the challenges of training
**[8:20]** RNNs, as well as how to adjust some of these challenges, specifically vanishing
**[8:24]** gradients by building even more powerful models of the RNN.
**[8:28]** So in the next video let's talk about the problem of vanishing the gradient and
**[8:32]** we will go on to talk about the GRU, Gate Recurring Unit as well as the LSTM models.
