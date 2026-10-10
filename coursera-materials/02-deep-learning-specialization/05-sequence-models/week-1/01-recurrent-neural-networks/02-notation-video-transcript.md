---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 1
section: Recurrent Neural Networks
item_title: Notation
duration: 9 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/aJT8i/notation
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Notation — Transcript

**[0:00]** In the last video, you saw some of
**[0:01]** the wide range of applications through which you can apply sequence models.
**[0:05]** Let's start by defining a notation that we'll use to build up these sequence models.
**[0:10]** As a motivating example,
**[0:12]** let's say you want to build a sequence model to input a sentence like this,
**[0:16]** Harry Potter and Hermione Granger invented a new spell.
**[0:19]** And these are characters by the way,
**[0:21]** from the Harry Potter sequence of novels by J. K. Rowling.
**[0:25]** And let say you want a sequence model to automatically tell
**[0:29]** you where are the peoples names in this sentence.
**[0:34]** So, this is a problem called Named-entity
**[0:36]** recognition and this is used by search engines for example,
**[0:40]** to index all of say the last 24 hours news of
**[0:43]** all the people mentioned in the news articles so that they can index them appropriately.
**[0:49]** And name into the recognition systems can be
**[0:52]** used to find people's names, companies names,
**[0:54]** times, locations, countries names,
**[0:57]** currency names, and so on in different types of text.
**[1:01]** Now, given this input x let's say that you want a model to operate
**[1:04]** y that has one outputs per input word
**[1:08]** and the target output the design y
**[1:11]** tells you for each of the input words is that part of a person's name. And technically
**[1:17]** this maybe isn't the best output representation, there are some more sophisticated
**[1:21]** output representations that tells you not just
**[1:23]** is a word part of a person's name, but tells you
**[1:26]** where are the start and ends of people's names their sentence, you want to know
**[1:30]** Harry Potter starts here, and ends here,
**[1:33]** starts here, and ends here. But for this
**[1:35]** motivating example, I'm just going to stick with
**[1:37]** this simpler output representation. Now, the input
**[1:41]** is the sequence of nine words. So, eventually
**[1:44]** we're going to have nine sets of features to represent these nine words, and index into
**[1:51]** the positions and sequence, I'm going to use
**[1:53]** X and then superscript angle brackets 1, 2, 3
**[1:59]** and so on up to X angle brackets nine to index into the different positions. I'm going to use
**[2:06]** X_t with the index t to index into positions, in the
**[2:13]** middle of the sequence. And t
**[2:15]** implies that these are temporal sequences
**[2:17]** although whether the sequences are temporal one or not, I'm going
**[2:21]** to use the index t to index into the positions in the sequence. And similarly
**[2:27]** for the outputs, we're going
**[2:29]** to refer to these outputs as y and go back at 1, 2,
**[2:34]** 3 and so on up to y nine. Let's also used
**[2:39]** T sub of x to denote the length of the input sequence, so in this case there are
**[2:44]** nine words. So T_x is
**[2:46]** equal to 9 and we used T_y to denote the length of the output sequence. In this example
**[2:53]** T_x is equal to T_y but you saw on the last video
**[2:56]** T_x and T_y can be different. So,
**[2:59]** you will remember that in the notation we've been using, we've been
**[3:03]** writing X round brackets i to denote the i training example. So, to
**[3:09]** refer to the TIF
**[3:10]** element or the TIF element in the sequence of training example i will use this notation
**[3:17]** and if Tx is the length of a sequence then
**[3:21]** different examples in your training set can have different lengths. And so Tx_i
**[3:26]** would be the input sequence length for training example i, and similarly
**[3:33]** y i t means the TIF element in the output sequence of the i for an example and
**[3:40]** Ty_i will be the length of the output sequence in the i training example. So into this
**[3:49]** example,
**[3:51]** Tx_i is equal to 9 would be the highly different training example with a sentence of 15 words and
**[3:57]** Tx_i will be close to 15 for that different training example.
**[4:03]** Now, this is our first serious foray into NLP or Natural Language Processing.
**[4:09]** Let's next talk about how we would represent individual words in a sentence.
**[4:15]** So, to represent a word in the sentence the first thing you
**[4:18]** do is come up with a Vocabulary.
**[4:22]** Sometimes also called a Dictionary and that means making
**[4:25]** a list of the words that you will use in your representations.
**[4:30]** So the first word in the vocabulary is a,
**[4:33]** that will be the first word in the dictionary.
**[4:35]** The second word is Aaron and then a little bit further down is the word and,
**[4:40]** and then eventually you get to the words Harry then eventually the word Potter,
**[4:47]** and then all the way down to maybe the last word in dictionary is Zulu.
**[4:58]** And so, a will be word one, Aaron is word two,
**[5:00]** and in my dictionary the word and appears in positional index 367.
**[5:12]** Harry appears in position 4075,
**[5:15]** Potter in position 6830,
**[5:18]** and Zulu is the last word to the dictionary is maybe word 10,000.
**[5:24]** So in this example,
**[5:26]** I'm going to use a dictionary with size 10,000 words.
**[5:30]** This is quite small by modern NLP applications.
**[5:35]** For commercial applications, for visual size commercial applications,
**[5:41]** dictionary sizes of 30 to 50,000 are more common and 100,000 is not uncommon.
**[5:47]** And then some of the large Internet companies will use
**[5:49]** dictionary sizes that are maybe a million words or even bigger than that.
**[5:53]** But you see a lot of commercial applications used dictionary sizes
**[5:57]** of maybe 30,000 or maybe 50,000 words.
**[6:01]** But I'm going to use 10,000 for illustration since it's a nice round number.
**[6:07]** So, if you have chosen a dictionary of 10,000 words and one way to build
**[6:12]** this dictionary will be be to look through
**[6:14]** your training sets and find the top 10,000 occurring words,
**[6:20]** also look through some of the online dictionaries that
**[6:23]** tells you what are the most common 10,000 words in the English Language saved
**[6:28]** What you can do is then use one hot representations to represent each of these words.
**[6:34]** For example, x-1 which represents the word Harry would be a vector with all zeros except
**[6:43]** for a 1 in position 4075 because that was the position of Harry in the dictionary.
**[6:51]** And then x_2 will be again similarly a vector of all zeros
**[6:57]** except for a 1 in position 6830 and then zeros everywhere else.
**[7:03]** The word and was represented as position 367 so x_3 would be
**[7:09]** a vector with zeros of 1 in position 367 and then zeros everywhere else.
**[7:17]** And each of these would be a 10,000
**[7:21]** dimensional vector if your vocabulary has 10,000 words.
**[7:25]** And this one A, I guess because A is the first whether the dictionary,
**[7:30]** then x_7 which corresponds to word a,
**[7:34]** that would be the vector 1.
**[7:38]** This is the first element of the dictionary and then zero everywhere else.
**[7:42]** So in this representation,
**[7:45]** x_t for each of the values of t in a sentence will be a one-hot vector,
**[7:52]** one-hot because there's exactly one one is on and zero everywhere
**[7:56]** else and you will have nine of them to represent the nine words in this sentence.
**[8:01]** And the goal is given this representation for X to learn
**[8:05]** a mapping using a sequence model to then target output y,
**[8:11]** I will do this as a supervised learning problem,
**[8:13]** I'm sure given the table data with both x and y.
**[8:17]** Then just one last detail,
**[8:19]** which we'll talk more about in a later video is,
**[8:22]** what if you encounter a word that is not in your vocabulary?
**[8:26]** Well the answer is, you create a new token or a new fake word called Unknown Word which
**[8:32]** under note as follows and go back as UNK to represent words not in your vocabulary,
**[8:38]** we'll come more to talk more about this later.
**[8:40]** So, to summarize in this video,
**[8:42]** we described a notation for describing
**[8:45]** your training set for both x and y for sequence data.
**[8:49]** In the next video let's start to describe
**[8:51]** a Recurrent Neural Networks for learning the mapping from X to Y.
