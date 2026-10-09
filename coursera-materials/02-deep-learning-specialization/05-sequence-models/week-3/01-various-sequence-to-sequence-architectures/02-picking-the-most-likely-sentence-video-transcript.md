---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 3
section: Various Sequence To Sequence Architectures
item_title: Picking the Most Likely Sentence
duration: 9 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/v2pRn/picking-the-most-likely-sentence
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Picking the Most Likely Sentence — Transcript

**[0:00]** There are some similarities between the sequence to sequence machine translation model
**[0:05]** and the language models that you have worked within the first week of this course,
**[0:11]** but there are some significant differences as well.
**[0:14]** Let's take a look. So, you can think of
**[0:16]** machine translation as building a conditional language model.
**[0:20]** Here's what I mean, in language modeling,
**[0:23]** this was the network we had built in the first week.
**[0:27]** And this model allows you to estimate the probability of a sentence.
**[0:35]** That's what a language model does.
**[0:38]** And you can also use this to generate novel sentences,
**[0:42]** and sometimes when you are writing x1 and x2 here,
**[0:46]** where in this example,
**[0:47]** x2 would be equal to y1 or equal to y and one is just a feedback.
**[0:53]** But x1, x2, and so on were not important.
**[0:56]** So just to clean this up for this slide,
**[0:57]** I'm going to just cross these off.
**[0:59]** X1 could be the vector of all zeros and x2,
**[1:02]** x3 are just the previous output you are generating.
**[1:06]** So that was the language model.
**[1:09]** The machine translation model looks as follows,
**[1:12]** and I am going to use a couple different colors,
**[1:14]** green and purple, to denote respectively
**[1:17]** the encoder network in green and the decoder network in purple.
**[1:22]** And you notice that the decoded network looks pretty much
**[1:27]** identical to the language model that we had up there.
**[1:33]** So what the machine translation model is,
**[1:35]** is very similar to the language model,
**[1:38]** except that instead of always starting along with the vector of all zeros,
**[1:43]** it instead has an encoded network
**[1:46]** that figures out some representation for the input sentence,
**[1:49]** and it takes that input sentence and starts off the decoded network with
**[1:54]** representation of the input sentence rather than with the representation of all zeros.
**[2:01]** So, that's why I call this a conditional language model,
**[2:07]** and instead of modeling the probability of any sentence,
**[2:11]** it is now modeling the probability of, say,
**[2:14]** the output English translation,
**[2:17]** conditions on some input French sentence.
**[2:22]** So in other words, you're trying to estimate the probability of an English translation.
**[2:28]** Like, what's the chance that the translation is "Jane is visiting Africa in September,"
**[2:33]** but conditions on the input French sentence like,
**[2:38]** "Jane visite I'Afrique en septembre."
**[2:42]** So, this is really the probability of an English sentence conditions on
**[2:46]** an input French sentence which is why it is a conditional language model.
**[2:51]** Now, if you want to apply this model to actually
**[2:54]** translate a sentence from French into English,
**[2:58]** given this input French sentence,
**[3:02]** the model might tell you what is the probability
**[3:05]** of difference in corresponding English translations.
**[3:08]** So, x is the French sentence,
**[3:11]** "Jane visite l'Afrique en septembre."
**[3:13]** And, this now tells you what is the probability of
**[3:17]** different English translations of that French input.
**[3:22]** And, what you do not want is to sample outputs at random.
**[3:28]** If you sample words from this distribution,
**[3:31]** p of y given x, maybe one time you get a pretty good translation,
**[3:36]** "Jane is visiting Africa in September."
**[3:38]** But, maybe another time you get a different translation,
**[3:40]** "Jane is going to be visiting Africa in September. "
**[3:42]** Which sounds a little awkward but is not a terrible translation,
**[3:46]** just not the best one.
**[3:48]** And sometimes, just by chance,
**[3:49]** you get, say, others: "In September,
**[3:52]** Jane will visit Africa."
**[3:54]** And maybe, just by chance,
**[3:55]** sometimes you sample a really bad translation:
**[3:57]** "Her African friend welcomed Jane in September."
**[4:00]** So, when you're using this model for machine translation,
**[4:04]** you're not trying to sample at random from this distribution.
**[4:08]** Instead, what you would like is to find the English sentence,
**[4:13]** y, that maximizes that conditional probability.
**[4:16]** So in developing a machine translation system,
**[4:20]** one of the things you need to do is come up with an algorithm that can actually find
**[4:25]** the value of y that maximizes this term over here.
**[4:31]** The most common algorithm for doing this is called beam search,
**[4:34]** and it's something you'll see in the next video.
**[4:37]** But, before moving on to describe beam search,
**[4:39]** you might wonder, why not just use greedy search? So, what is greedy search?
**[4:43]** Well, greedy search is an algorithm from computer science which says to generate
**[4:49]** the first word just pick whatever is
**[4:50]** the most likely first word according to your conditional language model.
**[4:55]** Going to your machine translation model and then after having picked the first word,
**[5:01]** you then pick whatever is the second word that seems most likely,
**[5:04]** then pick the third word that seems most likely.
**[5:07]** This algorithm is called greedy search.
**[5:10]** And, what you would really like is to pick the entire sequence of words, y1,
**[5:16]** y2, up to yTy, that's there,
**[5:21]** that maximizes the joint probability of that whole thing.
**[5:27]** And it turns out that the greedy approach,
**[5:30]** where you just pick the best first word,
**[5:31]** and then, after having picked the best first word,
**[5:34]** try to pick the best second word,
**[5:36]** and then, after that,
**[5:37]** try to pick the best third word,
**[5:39]** that approach doesn't really work.
**[5:41]** To demonstrate that, let's consider the following two translations.
**[5:44]** The first one is a better translation,
**[5:46]** so hopefully, in our machine translation model,
**[5:50]** it will say that p of y given x is higher for the first sentence.
**[5:56]** It's just a better, more succinct translation of the French input.
**[5:59]** The second one is not a bad translation,
**[6:02]** it's just more verbose,
**[6:03]** it has more unnecessary words.
**[6:05]** But, if the algorithm has picked "Jane is" as the first two words,
**[6:10]** because "going" is a more common English word,
**[6:14]** probably the chance of "Jane is going," given the French input,
**[6:21]** this might actually be higher than the chance of "Jane is
**[6:26]** visiting," given the French sentence.
**[6:32]** So, it's quite possible that if you just pick
**[6:35]** the third word based on whatever maximizes the probability of just the first three words,
**[6:40]** you end up choosing option number two.
**[6:43]** But, this ultimately ends up resulting in a less optimal sentence,
**[6:50]** in a less good sentence as measured by this model for p of y given
**[6:55]** x. I know this was may be a slightly hand-wavey argument,
**[7:01]** but, this is an example of a broader phenomenon,
**[7:05]** where if you want to find the sequence of words, y1, y2,
**[7:08]** all the way up to the final word that together maximize the probability,
**[7:13]** it's not always optimal to just pick one word at a time.
**[7:17]** And, of course, the total number of combinations of
**[7:21]** words in the English sentence is exponentially larger.
**[7:25]** So, if you have just 10,000 words in a dictionary and if you're
**[7:30]** contemplating translations that are up to ten words long,
**[7:35]** then there are 10000 to the tenth possible sentences that are ten words long.
**[7:42]** Picking words from the vocabulary size,
**[7:44]** the dictionary size of 10000 words.
**[7:47]** So, this is just a huge space of possible sentences,
**[7:51]** and it's impossible to rate them all,
**[7:53]** which is why the most common thing to do is use an approximate search algorithm.
**[8:00]** And, what an approximate search algorithm does,
**[8:02]** is it will try,
**[8:03]** it won't always succeed,
**[8:05]** but it will to pick the sentence, y,
**[8:07]** that maximizes that conditional probability.
**[8:11]** And, even though it's not guaranteed to find the value of y that maximizes this,
**[8:16]** it usually does a good enough job.
**[8:19]** So, to summarize, in this video,
**[8:20]** you saw how machine translation can be posed as a conditional language modeling problem.
**[8:26]** But one major difference between this and
**[8:28]** the earlier language modeling problems is rather
**[8:31]** than wanting to generate a sentence at random,
**[8:34]** you may want to try to find the most likely English sentence,
**[8:37]** most likely English translation.
**[8:40]** But the set of all English sentences of a certain length
**[8:43]** is too large to exhaustively enumerate.
**[8:47]** So, we have to resort to a search algorithm.
**[8:51]** So, with that, let's go onto the next video where
**[8:53]** you'll learn about beam search algorithm.
