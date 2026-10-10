---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 1
section: Recurrent Neural Networks
item_title: Language Model and Sequence Generation
duration: 12 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/gw1Xw/language-model-and-sequence-generation
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Language Model and Sequence Generation — Transcript

**[0:00]** Language modeling is one of
**[0:01]** the most basic and important task
**[0:03]** in natural language processing.
**[0:05]** It is also one that RNNs do very well.
**[0:09]** In this video, you'll learn about how to
**[0:11]** build a language model using an RNN,
**[0:14]** and this will lead up toward
**[0:16]** a fun programming exercise at the end of this week,
**[0:18]** where you build a language model and use it to
**[0:21]** generate Shakespeare like texts and other types of texts.
**[0:24]** Let's get started.
**[0:25]** What is a language model?
**[0:27]** Let's say you're building a speech recognition system
**[0:30]** and you hear the sentence,
**[0:31]** the apple and pear salad was delicious.
**[0:35]** What did you just hear me say?
**[0:37]** Did I say the apple and pair salad?
**[0:40]** Or did I say the apple and pear salad?
**[0:44]** You probably think the second sentence
**[0:48]** is much more likely.
**[0:49]** In fact, that's what a good speech
**[0:51]** recognition system would output,
**[0:53]** even though these two sentences sound exactly the same.
**[0:57]** The way a speech recognition system
**[0:59]** picks the second sentence is by using
**[1:02]** a language model which tells it what is
**[1:04]** the probability of either of these two sentences.
**[1:08]** For example, a language model
**[1:10]** might say that the chance of
**[1:11]** the first sentences is 3.2 by 10 to the negative 13,
**[1:15]** and the chance of the second sentence is say
**[1:19]** 5.7 by 10 to the negative 10,
**[1:22]** and so with these probabilities,
**[1:25]** the second sentence is much more likely by over
**[1:28]** a factor of 10^3 compared to the first sentence,
**[1:32]** and that's why a speech recognition system
**[1:34]** will pick the second choice.
**[1:36]** What a language model does is,
**[1:38]** given any sentence,
**[1:40]** its job is to tell you what is
**[1:42]** the probability of that particular sentence,
**[1:46]** and by probability of sentence, I mean,
**[1:49]** if you were to pick up a random newspaper,
**[1:52]** open a random email,
**[1:53]** or pick a random webpage,
**[1:54]** or listen to the next thing someone says,
**[1:56]** the friend of you says,
**[1:57]** what is the chance that the next sentence
**[1:59]** you read somewhere out there in
**[2:01]** the world will be
**[2:02]** a particular sentence like the apple and pear salad?
**[2:07]** This is a fundamental component for
**[2:10]** both speech recognition systems as you've just seen,
**[2:13]** as well as for machine translation systems,
**[2:16]** where translation systems want to output
**[2:18]** only sentences that are likely.
**[2:21]** So the basic job of a language model is to input
**[2:25]** the sentence which I'm going to write as a sequence y^1,
**[2:29]** y^2 up to y^ty,
**[2:33]** and for language model,
**[2:35]** it'll be useful to represent the sentences
**[2:38]** as outputs y rather than as inputs x.
**[2:42]** But what a language model does is it
**[2:44]** estimates the probability of
**[2:47]** that particular sequence of words.
**[2:52]** How do you build a language model?
**[2:57]** To build such a model using a RNN,
**[3:01]** you will first need a training
**[3:03]** set comprising a large corpus of
**[3:05]** English text or text from
**[3:07]** whatever language you want to build a language model of.
**[3:10]** The word corpus is an NLP terminology that just means
**[3:14]** a large body or a very large tens of English sentences.
**[3:19]** Let's say you get
**[3:20]** a sentence in your training set as follows,
**[3:23]** cats average 15 hours of sleep a day.
**[3:25]** The first thing you would do is tokenize the sentence,
**[3:29]** and that means you would form
**[3:31]** a vocabulary as we saw in an earlier video,
**[3:35]** and then map each of these words to say
**[3:39]** one-hot vectors or to indices in your vocabulary.
**[3:43]** One thing you might also want to do
**[3:45]** is model when sentences end.
**[3:48]** So another common thing to do is to add
**[3:50]** an extra token called
**[3:52]** EOS that stands for end of sentence,
**[3:56]** that can help you figure out when a sentence ends.
**[4:00]** We'll talk more about this later.
**[4:01]** But the EOS token can be
**[4:03]** appended to the end of every sentence in
**[4:05]** your training set if you want your model to
**[4:07]** explicitly capture when sentences end.
**[4:11]** We won't use the end-of-sentence token
**[4:13]** for the problem exercise at the end of this week.
**[4:16]** But for some applications,
**[4:17]** you might want to use this,
**[4:19]** and we'll see later where this comes in handy.
**[4:22]** In this example, we have y^1,
**[4:25]** y^2, y^3, 4, 5, 6, 7, 8, 9.
**[4:28]** Nine inputs in this example if you
**[4:30]** append the end of sentence token to the end.
**[4:33]** Doing the tokenization step,
**[4:34]** you can decide whether or not
**[4:36]** the period should be a token as well.
**[4:38]** In this example, I'm just ignoring punctuation,
**[4:41]** so I'm just using day
**[4:42]** as another token and omitting the period.
**[4:45]** If you want to treat the period
**[4:47]** or other punctuation as the explicit token,
**[4:50]** then you could add the period to your vocabulary as well.
**[4:53]** Now, one other detail would be,
**[4:56]** what if some of the words in
**[4:57]** your training set are not in your vocabulary?
**[4:59]** If your vocabulary uses 10,000 words,
**[5:02]** maybe the 10,000 most common words in English,
**[5:05]** then the term Mau as a decision,
**[5:07]** Mau's breed of cat, that might not be
**[5:09]** in one of your top 10,000 tokens.
**[5:12]** In that case, you could take the word Mau and replace
**[5:15]** it with a unique token called UNK,
**[5:18]** which stands for unknown words,
**[5:20]** and we just model the chance of
**[5:22]** the unknown word instead of the specific word, Mau.
**[5:26]** Having carried out the tokenization step,
**[5:29]** which basically means taking
**[5:30]** the input sentence and map here to
**[5:32]** the individual tokens or
**[5:33]** the individual words in your vocabulary,
**[5:36]** next, let's build an RNN to
**[5:38]** model the chance of these different sequences.
**[5:41]** One of the things we'll see on
**[5:43]** the next slide is that you end up setting
**[5:45]** the inputs x^t to be equal to y of t minus 1.
**[5:51]** But you'll see that in a little bit.
**[5:53]** Let's go on to build the RNN model,
**[5:55]** and I'm going to continue to use
**[5:57]** this sentence as the running example.
**[6:00]** This will be the RNN architecture.
**[6:03]** At time zero,
**[6:06]** you're going to end up computing
**[6:08]** some activation a_1 as a function of some input x_1,
**[6:13]** and x_1 would just be set to zero vector.
**[6:19]** The previous a_0 by convention,
**[6:22]** also set that to vector zeros.
**[6:25]** But what a_1 does is it will make
**[6:27]** a Softmax prediction to try to
**[6:30]** figure out what is the probability of the first word y,
**[6:36]** so that's going to be y_1.
**[6:40]** What this step does is really it has a Softmax,
**[6:44]** so it's trying to predict what is
**[6:45]** the probability of any word in a dictionary,
**[6:47]** what's the chance that the first word is a,
**[6:50]** what's the chance that the first word is Aaron,
**[6:53]** and then what's the chance that the first word is cats,
**[6:58]** all the way up to what's the chance
**[7:00]** the first word is Zulu,
**[7:01]** or what's the chance that
**[7:03]** the first word is an unknown word,
**[7:05]** or what's the chance that
**[7:06]** the first words is in
**[7:08]** a sentence though or shouldn't happen really.
**[7:12]** Y hat 1 is output according to a Softmax,
**[7:15]** it just predicts what's the chance that
**[7:17]** the first word being whatever it ends up being.
**[7:19]** In our example, one of the bigger the word cats.
**[7:23]** This would be a 10,000 way Softmax output.
**[7:26]** If you have 10,000 word vocabulary or 10,002,
**[7:30]** I guess you can't unknown word and
**[7:32]** the sentence has two additional tokens.
**[7:35]** Then the RNN steps forward to
**[7:38]** the next step and has
**[7:40]** some activation a_2 in the next step.
**[7:43]** At this step, it's job is to try to
**[7:45]** figure out what is the second word.
**[7:48]** But now we will also give it the correct first word.
**[7:54]** We'll tell it that G in reality,
**[7:57]** the first word was actually cats,
**[7:59]** so that's y_1,
**[8:01]** so tell it cats.
**[8:03]** This is why y_1 is equal to x_2.
**[8:10]** At the second step,
**[8:11]** the output is again predicted by Softmax,
**[8:14]** the RNN's job is to predict what's
**[8:16]** the chance of it being whatever word it is,
**[8:18]** is it A or Aaron,
**[8:20]** or cats or Zulu,
**[8:21]** or unknown word or EOS or whatever,
**[8:23]** given what had come previously.
**[8:26]** In this case, I guess the right answer was
**[8:29]** average since the sentence starts with cats average.
**[8:32]** Then you go on to the next step of
**[8:35]** the RNN where you now compute a_3.
**[8:39]** But to predict what is the third word which is 15,
**[8:42]** we can now give it the first two words.
**[8:44]** We're going to tell cats average of the first two words.
**[8:48]** This next input here,
**[8:50]** x_3 will be equal to y_2,
**[8:54]** so the word average is input and its job is to
**[8:56]** figure out what is the next word in the sequence.
**[9:00]** Another was trying to figure out what is the probability
**[9:02]** of any words in the dictionary given that
**[9:04]** what just came before was cats average?
**[9:09]** In this case, the right answer is 15 and so on.
**[9:13]** Until at the end,
**[9:16]** you end up at I guess time step nine,
**[9:20]** you end up feeding
**[9:22]** it x_9 which is equal to y_8 which is the word day.
**[9:30]** Then this has a_9 and its job is to open y hat nine,
**[9:38]** and this happens to be the EOS tokens.
**[9:40]** What's the chance of whatever it is
**[9:42]** given everything that's come before?
**[9:45]** Hopefully you'll predict that there's a high chance
**[9:47]** of EOS in the sentence token.
**[9:50]** But so, each step in the RNN will look at
**[9:53]** some set of preceding words such as,
**[9:56]** given the first three words,
**[9:58]** what is the distribution over the next word?
**[10:01]** This RNN learns to predict
**[10:03]** one word at a time going from left to right.
**[10:06]** Next, to train this through a network,
**[10:08]** we're going to define the cost function.
**[10:11]** At a certain time t,
**[10:12]** if the true word was yt
**[10:16]** and your network Softmax predicted some y hat t,
**[10:20]** then this is the Softmax loss function
**[10:23]** that you'll already be familiar with,
**[10:24]** and then the overall loss is just the sum over
**[10:28]** all time steps of the losses
**[10:29]** associated with the individual predictions.
**[10:32]** If you train this RNN on a large training set,
**[10:35]** what it will be able to do is,
**[10:37]** given any initial set of words such as
**[10:40]** cats average 15 or cats average 15 hours of,
**[10:43]** it can predict what is the chance of the next word.
**[10:47]** Given a new sentence, say y_1,
**[10:52]** y_2, y_3,
**[10:54]** with just three words for simplicity,
**[10:57]** the way you can figure out what is the chance of
**[11:00]** this entire sentence would be, well,
**[11:02]** the first Softmax tells you what's the chance of y_1,
**[11:05]** that would be this first output.
**[11:08]** Then the second one can tell you what's
**[11:10]** the chance of p of y_2 given y_1.
**[11:14]** Then the third one tells you what's the chance of y_3
**[11:18]** given y_1 and y_2,
**[11:23]** and so it's by multiplying out these three probabilities.
**[11:27]** You see much more of
**[11:29]** the details of this in [inaudible] exercise,
**[11:31]** it's by multiplying out these three that you end up with
**[11:34]** the probability of this three words sentence.
**[11:39]** That's the basic structure of how you can
**[11:42]** train a language model using an RNN.
**[11:45]** If some of these ideas still seem a
**[11:46]** little bit abstract, don't worry about it.
**[11:49]** You get to practice all of
**[11:50]** these ideas in the coming exercise.
**[11:52]** But next it turns out,
**[11:53]** one of the most fun things you can do with
**[11:55]** a language model is to sample sequences from the model.
**[11:58]** Let's take a look at that in the next video.
