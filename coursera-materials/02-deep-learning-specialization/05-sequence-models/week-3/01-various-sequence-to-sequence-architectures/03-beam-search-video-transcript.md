---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 3
section: Various Sequence To Sequence Architectures
item_title: Beam Search
duration: 12 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/4EtHZ/beam-search
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Beam Search — Transcript

**[0:00]** In this video, you learn about the beam search algorithm.
**[0:04]** In the last video,
**[0:05]** you remember how for machine translation given an input French sentence,
**[0:09]** you don't want to output a random English translation,
**[0:12]** you want to output the best and the most likely English translation.
**[0:16]** The same is also true for speech recognition where given an input audio clip,
**[0:21]** you don't want to output a random text transcript of that audio,
**[0:24]** you want to output the best,
**[0:25]** maybe the most likely, text transcript.
**[0:28]** Beam search is the most widely used algorithm to do this.
**[0:30]** And in this video, you see how to get beam search to work for yourself.
**[0:33]** Let's just try Beam Search using our running example of the French sentence,
**[0:37]** "Jane, visite l'Afrique en Septembre".
**[0:39]** Hopefully being translated into,
**[0:41]** "Jane, visits Africa in September".
**[0:43]** The first thing Beam search has to do is try to pick
**[0:45]** the first words of the English translation,
**[0:48]** that's going to output.
**[0:50]** So here I've listed,
**[0:51]** say, 10,000 words into vocabulary.
**[0:54]** And to simplify the problem a bit,
**[0:56]** I'm going to ignore capitalization.
**[0:58]** So I'm just listing all the words in lower case.
**[1:00]** So, in the first step of Beam Search,
**[1:02]** I use this network fragment with the encoder in green and decoder in purple,
**[1:08]** to try to evaluate what is the probability of that first word.
**[1:12]** So, what's the probability of the first output y,
**[1:14]** given the input sentence x gives the French input.
**[1:18]** So, whereas greedy search will pick only the one most likely words and move on,
**[1:24]** Beam Search instead can consider multiple alternatives.
**[1:28]** So, the Beam Search algorithm has a parameter called B,
**[1:32]** which is called the beam width and for
**[1:33]** this example I'm going to set the beam width to be equal to three.
**[1:37]** And what this means is Beam search will consider
**[1:40]** not just one possibility but consider three at the time.
**[1:44]** So in particular, let's say evaluating
**[1:46]** this probability over different choices the first words,
**[1:50]** it finds that the choices in,
**[1:52]** Jane and September are
**[1:55]** the most likely three possibilities for the first words in the English outputs.
**[2:01]** Then Beam search will stowaway in
**[2:03]** computer memory that it wants to try all of three of these words,
**[2:07]** and if the beam width parameter were set differently,
**[2:10]** the beam width parameter was 10,
**[2:12]** then we keep track of not just three but of the ten,
**[2:15]** most likely possible choices for the first word.
**[2:18]** So, to be clear in order to perform this first step of Beam search,
**[2:23]** what you need to do is run the input French sentence through
**[2:26]** this encoder network and then this first step will then decode the network,
**[2:31]** this is a softmax output overall 10,000 possibilities.
**[2:35]** Then you would take those 10,000 possible
**[2:39]** outputs and keep in memory which were the top three.
**[2:44]** Let's go into the second step of Beam search.
**[2:47]** Having picked in, Jane and September as the three most likely choice of the first word,
**[2:53]** what Beam search will do now,
**[2:55]** is for each of these three choices consider what should be the second word,
**[2:59]** so after "in" maybe a second word is "a" or maybe as Aaron,
**[3:03]** I'm just listing words from the vocabulary,
**[3:05]** from the dictionary or somewhere down the list will be September,
**[3:10]** somewhere down the list there's visit and then all the way
**[3:13]** to z and then the last word is zulu.
**[3:16]** So, to evaluate the probability of second word,
**[3:19]** it will use this neural network fragments where is coder in
**[3:23]** green and for the decoder portion when trying to decide what comes after in.
**[3:28]** Remember the decoder first outputs, y hat one.
**[3:33]** So, I'm going to set to this y hat one to the word "in" as it goes back in.
**[3:39]** So there's the word "in" because it decided for now.
**[3:43]** That's because It trying to figure out that the first word was "in",
**[3:47]** what is the second word,
**[3:48]** and then this will output I guess y hat two.
**[3:53]** And so by hard wiring y hat one here,
**[3:58]** really the inputs here to be the first words
**[4:01]** "in" this network fragment can be used to evaluate whether it's
**[4:06]** the probability of the second word given
**[4:09]** the input french sentence and that
**[4:12]** the first words of the translation has been the word "in".
**[4:16]** Now notice that what we ultimately care about in this second step of
**[4:20]** beam search to find the pair of the first and second words that is most
**[4:24]** likely it's not just a second where is most
**[4:26]** likely that the pair of the first and second whereas
**[4:28]** the most likely and by the rules of conditional probability.
**[4:33]** This can be expressed as P of the first words
**[4:37]** times P of probability of the second word.
**[4:45]** Which you are getting from
**[4:48]** this network fragment and so if for each of the three words you've chosen "in",
**[4:55]** "Jane," and "September" you save away this probability then you can multiply them by
**[4:59]** this second probabilities to get the probability of the first and second words.
**[5:05]** So now you've seen how if the first word was
**[5:08]** "in" how you can evaluate the probability of the second word.
**[5:11]** Now at first it was "Jane" you do the same thing.
**[5:14]** The sentence could be "Jane a"," Jane Aaron",
**[5:17]** and so on down to "Jane is",
**[5:22]** "Jane visits" and so on.
**[5:26]** And you will use this in
**[5:30]** neural network fragments let me draw this in as well where here you will hardwire,
**[5:37]** Y hat One to be Jane.
**[5:39]** And so with the First word y one hat's hard wired
**[5:46]** as Jane than just the network fragments
**[5:51]** can tell you what's the probability of the second words to me.
**[5:54]** And given that the first word is "Jane".
**[5:57]** And then same as above you can multiply with P of Y1 to get the probability
**[6:05]** of Y1 and Y2 for each of these 10,000 different possible choices for the second word.
**[6:14]** And then finally do the same thing for
**[6:16]** September all the words from a down to Zulu and use this network fragment.
**[6:23]** That just goes in as well to see if the first word was September.
**[6:31]** What was the most likely options for the second words.
**[6:35]** So for this second step of beam search because we're
**[6:40]** continuing to use a beam width of three and because there are
**[6:44]** 10,000 words in the vocabulary you'd end up considering three times
**[6:48]** 10000 or thirty thousand possibilities because there are 10,000 here,
**[6:53]** 10,000 here, 10,000 here as
**[6:55]** the beam width times the number of words in the vocabulary and what you
**[7:01]** do is you evaluate all of these 30000 options
**[7:05]** according to the probably the first and second words and then pick the top three.
**[7:10]** So with a cut down,
**[7:12]** these 30,000 possibilities down to three again down
**[7:15]** the beam width rounded again so let's say that 30,000 choices,
**[7:19]** the most likely were in September and say Jane is,
**[7:26]** and Jane visits sorry this bit messy but those are the most likely three out of the
**[7:34]** 30,000 choices then that's what Beam's search would memorize
**[7:37]** away and take on to the next step beam search.
**[7:43]** So notice one thing if beam search decides that
**[7:47]** the most likely choices are the first and second words are in September,
**[7:52]** or Jane is, or Jane visits.
**[7:55]** Then what that means is that it is now rejecting September as
**[7:59]** a candidate for the first words of the output English translation
**[8:05]** so we're now down to two possibilities for the first words but we still have a beam width
**[8:12]** of three keeping track of three choices for pairs of Y1,
**[8:19]** Y2 before going onto the third step of beam search.
**[8:23]** Just want to notice that because of beam width is equal to three,
**[8:26]** every step you instantiate three copies of
**[8:31]** the network to evaluate these partial sentence fragments and the output.
**[8:38]** And it's because of beam width is equal to three that you have
**[8:42]** three copies of the network with different choices for the first words,
**[8:46]** but these three copies of the network can be very efficiently used to
**[8:50]** evaluate all 30,000 options for the second word.
**[8:56]** So just don't instantiate 30,000 copies of the network or three copies of the network to
**[9:02]** very quickly evaluate all 10,000 possible outputs at that softmax output say for Y2.
**[9:09]** Let's just quickly illustrate one more step of beam search.
**[9:14]** So said that the most likely choices for first two words were in September, Jane is,
**[9:18]** and Jane visits and for each of
**[9:21]** these pairs of words which we should have saved the way in computer memory
**[9:23]** the probability of Y1 and Y2 given the input X given the French sentence X.
**[9:31]** So similar to before,
**[9:33]** we now want to consider what is the third word.
**[9:35]** So in September a?
**[9:37]** In September Aaron?
**[9:38]** All the way down to is in
**[9:40]** September Zulu and to evaluate possible choices for the third word,
**[9:45]** you use this network fragments where you Hardwire
**[9:49]** the first word here to be in the second word to be September.
**[9:53]** And so this network fragment allows you to evaluate what's
**[9:56]** the probability of the third word given the input French sentence
**[9:59]** X and given that the first two words are in September and English output.
**[10:08]** And then you do the same thing for the second fragment.
**[10:13]** So like so.
**[10:15]** And same thing for
**[10:17]** Jane visits and so
**[10:23]** beam search will then once again pick
**[10:25]** the top three possibilities may be that things in September.
**[10:29]** Jane is a likely outcome or Jane is visiting is likely or maybe Jane visits
**[10:38]** Africa is likely for that first three words and then it keeps
**[10:42]** going and then you go onto the fourth step of
**[10:44]** beam search hat one more word and on it goes.
**[10:48]** And the outcome of this process hopefully will be
**[10:50]** that adding one word at a time that Beam search will decide that.
**[10:54]** Jane visits Africa in September will be terminated by
**[10:57]** the end of sentence symbol using that system is quite common.
**[11:02]** They'll find that this is a likely output English sentence
**[11:06]** and you'll see more details of this yourself.
**[11:08]** In this week's exercise as well where you get to play with beam search yourself.
**[11:15]** So with a beam of three beam search considers three possibilities at a time.
**[11:21]** Notice that if the beam width was said to be equal to one,
**[11:24]** say cause there's only one,
**[11:26]** then this essentially becomes
**[11:27]** the greedy search algorithm which we had discussed in the last video but by considering
**[11:34]** multiple possibilities say three or ten or some other number at
**[11:38]** the same time beam search will usually
**[11:40]** find a much better output sentence than greedy search.
**[11:43]** You've now seen how Beam Search works but it turns out there's
**[11:47]** some additional tips and tricks for refinements
**[11:49]** that help you to make beam search work even better.
**[11:52]** Let's go onto the next video to take a look.
