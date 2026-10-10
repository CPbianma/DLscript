---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 3
section: Speech Recognition - Audio Data
item_title: Speech Recognition
duration: 9 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/sjiUm/speech-recognition
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Speech Recognition — Transcript

**[0:00]** One of the most exciting developments with sequence-to-sequence
**[0:03]** models has been the rise of very accurate speech recognition.
**[0:08]** We're nearing the end of the course,
**[0:10]** we want to take just a couple of videos to give you a sense of how
**[0:13]** these sequence-to-sequence models are applied to audio data, such as the speech.
**[0:19]** So, what is the speech recognition problem?
**[0:22]** You're given an audio clip, x,
**[0:24]** and your job is to automatically find a text transcript, y.
**[0:31]** So, an audio clip,
**[0:32]** if you plot it looks like this,
**[0:34]** the horizontal axis here is time,
**[0:37]** and what a microphone does is it really measures minuscule changes in air pressure,
**[0:43]** and the way you're hearing my voice right now is that
**[0:46]** your ear is detecting little changes in air pressure,
**[0:50]** probably generated either by your speakers or by a headset.
**[0:55]** And some audio clips like this plots with the air pressure against time.
**[1:01]** And, if this audio clip is of me saying,
**[1:06]** "the quick brown fox", then hopefully,
**[1:08]** a speech recognition algorithm can input that audio clip and output that transcript.
**[1:14]** And because even the human ear doesn't process raw wave forms,
**[1:18]** but the human ear has physical structures that
**[1:21]** measures the amounts of intensity of different frequencies,
**[1:25]** there is, a common pre-processing step for audio data
**[1:29]** is to run your raw audio clip and generate a spectrogram.
**[1:34]** So, this is the plots where the horizontal axis is time,
**[1:39]** and the vertical axis is frequencies,
**[1:42]** and intensity of different colors shows the amount of energy.
**[1:46]** So, how loud is the sound at different frequencies? At different times?
**[1:51]** And so, these types of spectrograms,
**[1:55]** or you might also hear people talk about filter back outputs,
**[1:58]** is often commonly applied
**[2:01]** pre-processing step before audio is pass into in the running algorithm.
**[2:06]** And the human ear does a computation pretty similar to this pre-processing step.
**[2:12]** So, one of the most exciting trends in speech recognition is that,
**[2:18]** once upon a time,
**[2:19]** speech recognition systems used to be built using phonemes and this where,
**[2:27]** I want to say hand-engineered basic units of cells.
**[2:31]** So, the quick brown fox represented as phonemes.
**[2:34]** I'm going to simplify a bit, let say,
**[2:36]** "The" has a "de" and "e" sound and Quick,
**[2:38]** has a "ku" and "wu", "ik", "k" sound,
**[2:42]** and linguist used to write off these basic units of sound,
**[2:46]** and try to break language down to these basic units of sound.
**[2:50]** So, brown, this aren't
**[2:52]** the official phonemes which are written with more complicated notation,
**[2:57]** but linguists use to hypothesize that writing down audio in terms of
**[3:02]** these basic units of sound called
**[3:04]** phonemes would be the best way to do speech recognition.
**[3:08]** But with end-to-end deep learning,
**[3:10]** we're finding that phonemes representations are no longer necessary.
**[3:15]** But instead, you can built systems that input an audio clip and directly
**[3:21]** output a transcript without needing to use hand-engineered representations like these.
**[3:27]** One of the things that made this possible was going to much larger data sets.
**[3:33]** So, academic data sets on speech recognition might be as a 300 hours, and in academia,
**[3:43]** 3000 hour data sets of transcribed audio would be considered reasonable size,
**[3:49]** so lot of research has been done,
**[3:50]** a lot of research papers that are written on data sets there are several thousand hours.
**[3:56]** But, the best commercial systems are now trains
**[3:59]** on over 10,000 hours and sometimes over a 100,000 hours of audio.
**[4:04]** And, it's really moving to a much larger audio data sets,
**[4:10]** transcribe audio data sets where both x and y,
**[4:12]** together with deep learning algorithm,
**[4:15]** that has driven a lot of progress is speech recognition.
**[4:18]** So, how do you build a speech recognition system?
**[4:22]** In the last video,
**[4:23]** we're talking about the attention model.
**[4:25]** So, one thing you could do is actually do that,
**[4:28]** where on the horizontal axis,
**[4:30]** you take in different time frames of the audio input,
**[4:34]** and then you have an attention model try to output the transcript like,
**[4:38]** "the quick brown fox",
**[4:40]** or what it was said.
**[4:42]** One other method that seems to work well is to use the CTC cost for speech recognition.
**[4:47]** CTC stands for Connection is Temporal Classification and is due to Alex Graves,
**[4:53]** Santiago Fernandes, Faustino Gomez, and Jürgen Schmidhuber.
**[4:57]** So, here's the idea. Let's say the audio clip was someone saying,
**[5:01]** "the quick brown fox".
**[5:02]** We're going to use a neural network structured
**[5:07]** like this with an equal number of input x's and output y's,
**[5:11]** and I have drawn a simple of what uni-directional for the RNN for this, but in practice,
**[5:17]** this will usually be a bidirectional LSTM and
**[5:20]** bidirectional GRU and usually, a deeper model.
**[5:23]** But notice that the number of time steps here is very large and in speech recognition,
**[5:30]** usually the number of input time steps is much
**[5:32]** bigger than the number of output time steps.
**[5:35]** So, for example, if you have 10 seconds of audio and your features
**[5:39]** come at a 100 hertz so 100 samples per second,
**[5:44]** then a 10 second audio clip would end up with a thousand inputs.
**[5:48]** Right, so it's 100 hertz times 10 seconds,
**[5:51]** and so with a thousand inputs.
**[5:53]** But your output might not have a thousand alphabets,
**[5:56]** might not have a thousand characters.
**[5:59]** So, what do you do?
**[6:01]** The CTC cost function allows the RNN to generate an output like this ttt,
**[6:08]** there's a special character called
**[6:10]** the blank character, which we're going to write as an underscore here,
**[6:12]** h_eee___, and then maybe a space,
**[6:22]** we're going to write like this, so that a space and then ___ qqq__.
**[6:32]** And, this is considered a correct output for the first parts of the space,
**[6:40]** quick with the Q,
**[6:42]** and the basic rule for the CTC cost function is to collapse
**[6:46]** repeated characters not separated by "blank".
**[6:51]** So, to be clear,
**[6:52]** I'm using this underscore to denote
**[6:55]** a special blank character and that's different than the space character.
**[7:01]** So, there is a space here between the and quick,
**[7:05]** so I should output a space.
**[7:07]** But, by collapsing repeated characters,
**[7:09]** not separated by blank,
**[7:11]** it actually collapse the sequence into t, h,
**[7:18]** e, and then space, and q,
**[7:20]** and this allows your network
**[7:26]** to have a thousand outputs by repeating characters allow the times.
**[7:31]** So, inserting a bunch of blank characters and still ends
**[7:34]** up with a much shorter output text transcript.
**[7:38]** So, this phrase here "the quick brown fox" including spaces
**[7:42]** actually has 19 characters, and if somehow,
**[7:46]** the newer network is forced upwards of
**[7:48]** a thousand characters by allowing the network to insert blanks and
**[7:52]** repeated characters and can still represent
**[7:55]** this 19 character output with this 1000 outputs of values of Y.
**[8:00]** So, this paper by Alex Grace,
**[8:03]** as well as Baidu's deep speech recognition system,
**[8:08]** which I was involved in,
**[8:10]** used this idea to build effective Speech recognition systems.
**[8:14]** So, I hope that gives you a rough sense of how speech recognition models work.
**[8:19]** Attention like models work and CTC models work and
**[8:23]** present two different options of how to go about building these systems.
**[8:27]** Now, today, building effective or
**[8:30]** production scale speech recognition system is
**[8:33]** a pretty significant effort and requires a very large data set.
**[8:37]** But, what I like to do in the next video is share you,
**[8:40]** how you can build a trigger word detection system,
**[8:43]** where keyword detection system which is actually much easier and can
**[8:47]** be done with even a smaller or more reasonable amount of data.
**[8:50]** So, let's talk about that in the next video.
