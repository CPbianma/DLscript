---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 1
section: Recurrent Neural Networks
item_title: Why Sequence Models?
duration: 3 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/0h7gT/why-sequence-models
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Why Sequence Models? — Transcript

**[0:00]** Welcome to this fifth course on deep learning.
**[0:02]** In this course, you learn about sequence models,
**[0:05]** one of the most exciting areas in deep learning.
**[0:07]** Models like recurrent neural networks or RNNs have transformed speech recognition,
**[0:13]** natural language processing and other areas.
**[0:15]** And in this course, you learn how to build these models for yourself.
**[0:18]** Let's start by looking at a few examples of where sequence models can be useful.
**[0:22]** In speech recognition you are given
**[0:25]** an input audio clip X and asked to map it to a text transcript Y.
**[0:31]** Both the input and the output here are sequence data,
**[0:34]** because X is an audio clip and so that plays out over time and Y,
**[0:38]** the output, is a sequence of words.
**[0:41]** So sequence models such as a recurrent neural networks and other variations,
**[0:45]** you'll learn about in a little bit have been very useful for speech recognition.
**[0:48]** Music generation is another example of a problem with sequence data.
**[0:53]** In this case, only the output Y is a sequence,
**[0:57]** the input can be the empty set,
**[1:00]** or it can be a single integer,
**[1:02]** maybe referring to the genre of music you want to
**[1:04]** generate or maybe the first few notes of the piece of music you want.
**[1:07]** But here X can be nothing or maybe just an integer and output Y is a sequence.
**[1:15]** In sentiment classification the input X is a sequence,
**[1:19]** so given the input phrase like,
**[1:20]** "There is nothing to like in this movie" how many stars do you think this review will be?
**[1:26]** Sequence models are also very useful for DNA sequence analysis.
**[1:31]** So your DNA is represented via the four alphabets A, C,
**[1:35]** G,and T. And so given a DNA sequence can you label
**[1:39]** which part of this DNA sequence say corresponds to a protein.
**[1:43]** In machine translation you are given an input sentence,
**[1:47]** voulez-vou chante avec moi?
**[1:48]** And you're asked to output the translation in a different language.
**[1:53]** In video activity recognition you might be given
**[1:56]** a sequence of video frames and asked to recognize the activity.
**[2:01]** And in name entity recognition you might be given
**[2:04]** a sentence and asked to identify the people in that sentence.
**[2:08]** So all of these problems can be addressed as supervised learning with label data X,
**[2:16]** Y as the training set.
**[2:18]** But, as you can tell from this list of examples,
**[2:20]** there are a lot of different types of sequence problems.
**[2:22]** In some, both the input X and the output Y are sequences,
**[2:26]** and in that case,
**[2:28]** sometimes X and Y can have different lengths,
**[2:30]** or in this example and this example,
**[2:34]** X and Y have the same length.
**[2:35]** And in some of these examples only either X or only the opposite Y is a sequence.
**[2:41]** So in this course you learn about sequence models are applicable,
**[2:44]** so all of these different settings.
**[2:46]** So I hope this gives you a sense of the exciting set of
**[2:49]** problems that sequence models might be able to help you to address. With that
**[2:53]** let us go on to the next video where we start to define
**[2:56]** the notation we use to define these sequence problems.
