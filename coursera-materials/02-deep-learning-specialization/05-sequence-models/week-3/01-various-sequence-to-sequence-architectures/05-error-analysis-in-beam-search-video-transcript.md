---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 3
section: Various Sequence To Sequence Architectures
item_title: Error Analysis in Beam Search
duration: 10 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/UfvRl/error-analysis-in-beam-search
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Error Analysis in Beam Search — Transcript

**[0:00]** In the third course of this sequence of five courses, you saw how error analysis
**[0:05]** can help you focus your time on doing the most useful work for your project.
**[0:11]** Now, beam search is an approximate search algorithm,
**[0:14]** also called a heuristic search algorithm.
**[0:16]** And so it doesn't always output the most likely sentence.
**[0:20]** It's only keeping track of B equals 3 or 10 or 100 top possibilities.
**[0:26]** So what if beam search makes a mistake?
**[0:29]** In this video, you'll learn how error analysis interacts with beam search and
**[0:33]** how you can figure out whether it is the beam search algorithm that's causing
**[0:38]** problems and worth spending time on.
**[0:40]** Or whether it might be your RNN model that is causing problems and
**[0:44]** worth spending time on.
**[0:46]** Let's take a look at how to do error analysis with beam search.
**[0:50]** Let's use this example of Jane visite l'Afrique en septembre.
**[0:56]** So let's say that in your machine translation dev set,
**[1:00]** your development set, the human provided this translation and
**[1:04]** Jane visits Africa in September, and I'm going to call this y*.
**[1:08]** So it is a pretty good translation written by a human.
**[1:11]** Then let's say that when you run beam search on your learned
**[1:16]** RNN model and your learned translation model, it ends up with this translation,
**[1:20]** which we will call y-hat, Jane visited Africa last September,
**[1:24]** which is a much worse translation of the French sentence.
**[1:28]** It actually changes the meaning, so it's not a good translation.
**[1:32]** Now, your model has two main components.
**[1:35]** There is a neural network model, the sequence to sequence model.
**[1:40]** We shall just call this your RNN model.
**[1:43]** It's really an encoder and a decoder.
**[1:45]** And you have your beam search algorithm,
**[1:49]** which you're running with some beam width b.
**[1:52]** And wouldn't it be nice if you could attribute this error,
**[1:56]** this not very good translation, to one of these two components?
**[2:00]** Was it the RNN or really the neural network that is more to blame, or
**[2:04]** is it the beam search algorithm, that is more to blame?
**[2:08]** And what you saw in the third course of the sequence is that
**[2:12]** it's always tempting to collect more training data that never hurts.
**[2:17]** So in similar way, it's always tempting to increase the beam width that never
**[2:21]** hurts or pretty much never hurts.
**[2:23]** But just as getting more training data by itself might not
**[2:28]** get you to the level of performance you want.
**[2:31]** In the same way,
**[2:32]** increasing the beam width by itself might not get you to where you want to go.
**[2:38]** But how do you decide whether or
**[2:40]** not improving the search algorithm is a good use of your time?
**[2:44]** So just how you can break the problem down and
**[2:46]** figure out what's actually a good use of your time.
**[2:50]** Now, the RNN, the neural network,
**[2:52]** what was called RNN really means the encoder and the decoder.
**[2:56]** It computes P(y given x).
**[3:02]** So for example, for a sentence, Jane visits Africa
**[3:07]** in September, you plug in Jane visits Africa.
**[3:11]** Again, I'm ignoring upper versus lowercase now, right, and so on.
**[3:15]** And this computes P(y given x).
**[3:18]** So it turns out that the most useful thing for
**[3:22]** you to do at this point is to compute using this model to compute
**[3:28]** P(y* given x) as well as to compute P(y-hat given x) using your RNN model.
**[3:36]** And then to see which of these two is bigger.
**[3:39]** So it's possible that the left side is bigger than the right hand side.
**[3:43]** It's also possible that P(y*) is less than P(y-hat) actually, or less than or
**[3:47]** equal to, right?
**[3:48]** Depending on which of these two cases hold true, you'd be able to more
**[3:53]** clearly ascribe this particular error, this particular bad translation
**[3:58]** to one of the RNN or the beam search algorithm being had greater fault.
**[4:04]** So let's take out the logic behind this.
**[4:07]** Here are the two sentences from the previous slide.
**[4:09]** And remember, we're going to compute P(y* given x) and
**[4:14]** P(y-hat given x) and see which of these two is bigger.
**[4:19]** So there are going to be two cases.
**[4:21]** In case 1, P(y* given x) as output by the RNN
**[4:26]** model is greater than P(y-hat given x).
**[4:31]** What does this mean?
**[4:32]** Well, the beam search algorithm chose y-hat, right?
**[4:37]** The way you got y-hat was you had an RNN that was computing P(y given x).
**[4:44]** And beam search's job was to try to find a value of y that gives that arg max.
**[4:51]** But in this case, y* actually attains a higher value for
**[4:57]** P(y given x) than the y-hat.
**[5:00]** So what this allows you to conclude is beam search is failing to actually give
**[5:05]** you the value of y that maximizes P(y given x) because the one
**[5:10]** job that beam search had was to find the value of y that makes this really big.
**[5:15]** But it chose y-hat, the y* actually gets a much bigger value.
**[5:19]** So in this case, you could conclude that beam search is at fault.
**[5:24]** Now, how about the other case?
**[5:26]** In case 2, P(y* given x) is less than or
**[5:30]** equal to P(y-hat given x), right?
**[5:34]** And then either this or this has gotta be true.
**[5:37]** So either case 1 or case 2 has to hold true.
**[5:40]** What do you conclude under case 2?
**[5:43]** Well, in our example,
**[5:47]** y* is a better translation than y-hat.
**[5:51]** But according to the RNN, P(y*) is less than P(y-hat),
**[5:57]** so saying that y* is a less likely output than y-hat.
**[6:02]** So in this case, it seems that the RNN model is
**[6:07]** at fault and it might be worth spending more time working on the RNN.
**[6:13]** There's some subtleties here pertaining to
**[6:16]** length normalizations that I'm glossing over.
**[6:18]** There's some subtleties pertaining to length normalizations that I'm
**[6:23]** glossing over.
**[6:24]** And if you are using some sort of length normalization,
**[6:28]** instead of evaluating these probabilities, you should be evaluating the optimization
**[6:32]** objective that takes into account length normalization.
**[6:36]** But ignoring that complication for now, in this case, what this tells you is that
**[6:41]** even though y* is a better translation,
**[6:46]** the RNN ascribed y* in lower probability than the inferior translation.
**[6:53]** So in this case, I will say the RNN model is at fault.
**[6:57]** So the error analysis process looks as follows.
**[7:01]** You go through the development set and
**[7:03]** find the mistakes that the algorithm made in the development set.
**[7:08]** And so in this example, let's say that P(y* given x) was 2 x 10 to the -10,
**[7:16]** whereas, P(y-hat given x) was 1 x 10 to the -10.
**[7:21]** Using the logic from the previous slide, in this case, we see that
**[7:26]** beam search actually chose y-hat, which has a lower probability than y*.
**[7:32]** So I will say beam search is at fault.
**[7:35]** So I'll abbreviate that B.
**[7:36]** And then you go through a second mistake or
**[7:39]** second bad output by the algorithm, look at these probabilities.
**[7:43]** And maybe for the second example, you think the model is at fault.
**[7:47]** I'm going to abbreviate the RNN model with R.
**[7:50]** And you go through more examples.
**[7:52]** And sometimes the beam search is at fault, sometimes the model is at fault,
**[7:57]** and so on.
**[7:58]** And through this process, you can then carry out error analysis to figure out
**[8:04]** what fraction of errors are due to beam search versus the RNN model.
**[8:10]** And with an error analysis process like this, for every example in your dev sets,
**[8:16]** where the algorithm gives a much worse output than the human translation,
**[8:23]** you can try to ascribe the error to either the search algorithm or
**[8:28]** to the objective function, or to the RNN model that generates
**[8:32]** the objective function that beam search is supposed to be maximizing.
**[8:37]** And through this, you can try to figure out which of these two components is
**[8:41]** responsible for more errors.
**[8:43]** And only if you find that beam search is responsible for a lot of errors,
**[8:46]** then maybe is we're working hard to increase the beam width.
**[8:51]** Whereas in contrast, if you find that the RNN model is at fault,
**[8:55]** then you could do a deeper layer of analysis to try to figure out if you want
**[8:59]** to add regularization, or get more training data, or
**[9:02]** try a different network architecture, or something else.
**[9:06]** And so a lot of the techniques that you saw in the third course in
**[9:10]** the sequence will be applicable there.
**[9:13]** So that's it for error analysis using beam search.
**[9:17]** I found this particular error analysis process very useful whenever you have
**[9:22]** an approximate optimization algorithm, such as beam search
**[9:25]** that is working to optimize some sort of objective, some sort of cost function
**[9:29]** that is output by a learning algorithm, such as a sequence-to-sequence model or
**[9:33]** a sequence-to-sequence RNN that we've been discussing in these lectures.
**[9:37]** So with that, I hope that you'll be more efficient at making these types of models
**[9:41]** work well for your applications.
