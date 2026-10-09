---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 3
section: Various Sequence To Sequence Architectures
item_title: Bleu Score (Optional)
duration: 16 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/kC2HD/bleu-score-optional
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Bleu Score (Optional) — Transcript

**[0:00]** One of the challenges of machine translation is that,
**[0:03]** given a French sentence, there could be multiple English translations that
**[0:07]** are equally good translations of that French sentence.
**[0:11]** So how do you evaluate a machine translation system if there are multiple
**[0:15]** equally good answers,
**[0:16]** unlike, say, image recognition where there's one right answer?
**[0:20]** You just measure accuracy.
**[0:22]** If there are multiple great answers, how do you measure accuracy?
**[0:26]** The way this is done conventionally is through something called the BLEU score.
**[0:29]** So, in this optional video, I want to share with you,
**[0:33]** I want to give you a sense of how the BLEU score works.
**[0:37]** Let's say you are given a French sentence Le chat est sur le tapis.
**[0:40]** And you are given a reference, human generated translation of this,
**[0:46]** which is the the cat is on the mat.
**[0:49]** But there are multiple, pretty good translations of this.
**[0:51]** So a different human,
**[0:53]** different person might translate it as there is a cat on the mat.
**[0:57]** And both of these are actually just perfectly fine translations of
**[1:01]** the French sentence.
**[1:02]** What the BLEU score does is given a machine generated translation,
**[1:08]** it allows you to automatically compute a score that
**[1:12]** measures how good is that machine translation.
**[1:17]** And the intuition is so long as the machine generated translation is pretty close
**[1:21]** to any of the references provided by humans,
**[1:26]** then it will get a high BLEU score.
**[1:27]** BLEU, by the way, stands for bilingual evaluation,
**[1:37]** Understudy.
**[1:39]** So in the theater world,
**[1:41]** an understudy is someone that learns the role of a more senior actor so
**[1:46]** they can take over the role of the more senior actor, if necessary.
**[1:50]** And motivation for BLEU is that, whereas you could ask human
**[1:56]** evaluators to evaluate the machine translation system,
**[1:59]** the BLEU score is an understudy, could be a substitute for
**[2:04]** having humans evaluate every output of a machine translation system.
**[2:09]** So the BLEU score was due to Kishore Papineni, Salim Roukos,
**[2:17]** Todd Ward, and Wei-Jing Zhu.
**[2:20]** This paper has been incredibly influential, and is,
**[2:23]** actually, quite a readable paper.
**[2:27]** So I encourage you to take a look if you have time.
**[2:30]** So, the intuition behind the BLEU score is we're going to look
**[2:36]** at the machine generated output and see if the types of words it
**[2:39]** generates appear in at least one of the human generated references.
**[2:46]** And so these human generated references would be provided as part
**[2:50]** of the dev set or as part of the test set.
**[2:54]** Now, let's look at a somewhat extreme example.
**[2:57]** Let's say that the machine translation system abbreviating
**[3:01]** machine translation is MT.
**[3:04]** So the machine translation, or the MT output, is the the the the the the the.
**[3:08]** So this is clearly a pretty terrible translation.
**[3:12]** So one way to measure how good the machine translation output is,
**[3:18]** is to look at each the words in the output and see if it appears in the references.
**[3:25]** And so, this would be called a precision of the machine translation output.
**[3:31]** And in this case, there are seven words in the machine translation output.
**[3:37]** And every one of these 7 words appears in either Reference 1 or Reference 2, right?
**[3:44]** So the word the appears in both references.
**[3:48]** So each of these words looks like a pretty good word to include.
**[3:50]** So this will have a precision of 7 over 7.
**[3:54]** It looks like it was a great precision.
**[3:56]** So this is why the basic precision measure of what fraction of
**[4:00]** the words in the MT output also appear in the references.
**[4:04]** This is not a particularly useful measure,
**[4:06]** because it seems to imply that this MT output has very high precision.
**[4:10]** So instead, what we're going to use is a modified precision
**[4:14]** measure in which we will give each word credit only up to the maximum
**[4:21]** number of times it appears in the reference sentences.
**[4:25]** So in Reference 1, the word, the, appears twice.
**[4:29]** In Reference 2, the word, the, appears just once.
**[4:32]** So 2 is bigger than 1, and so we're going to say that the word,
**[4:38]** the, gets credit up to twice.
**[4:40]** So, with a modified precision, we will say that,
**[4:46]** it gets a score of 2 out of 7, because out of 7 words,
**[4:51]** we'll give it a 2 credits for appearing.
**[4:58]** So here, the denominator is the count of the number of times the word,
**[5:04]** the, appears of 7 words in total.
**[5:09]** And the numerator is the count of the number of times the word, the, appears.
**[5:15]** We clip this count, we take a max, or we clip this count, at 2.
**[5:19]** So this gives us the modified precision measure.
**[5:24]** Now, so far, we've been looking at words in isolation.
**[5:28]** In the BLEU score, you don't want to just look at isolated words.
**[5:31]** You maybe want to look at pairs of words as well.
**[5:34]** Let's define a portion of the BLEU score on bigrams.
**[5:39]** And bigrams just means pairs of words appearing next to each other.
**[5:42]** So now, let's see how we could use bigrams to define the BLEU score.
**[5:49]** And this will just be a portion of the final BLEU score.
**[5:53]** And we'll take unigrams, or single words, as well as bigrams, which means pairs
**[5:56]** of words into account as well as maybe even longer sequences of words,
**[6:01]** such as trigrams, which means three words pairing together.
**[6:05]** So, let's continue our example from before.
**[6:11]** We have to same Reference 1 and Reference 2.
**[6:13]** But now let's say the machine translation or
**[6:15]** the MT System has a slightly better output.
**[6:19]** The cat the cat on the mat.
**[6:20]** Still not a great translation, but maybe better than the last one.
**[6:23]** So here, the possible bigrams are, well there's the cat, but ignore case.
**[6:31]** And then there's cat the, that's another bigram.
**[6:34]** And then there's the cat again, but I've already had that, so let's skip that.
**[6:39]** And then cat on is the next one.
**[6:42]** And then on the, and the mat.
**[6:45]** So these are the bigrams in the machine translation output.
**[6:48]** And so let's count up, How many times each of these bigrams appear.
**[6:59]** The cat appears twice, cat the appears once, and the others all appear just once.
**[7:05]** And then finally, let's define the clipped count, so count, and then subscript clip.
**[7:14]** And to define that, let's take this column of numbers, but
**[7:18]** give our algorithm credit only up to the maximum number of times
**[7:22]** that that bigram appears in either Reference 1 or Reference 2.
**[7:26]** So the cat appears a maximum of once in either of the references.
**[7:34]** So I'm going to clip that count to 1.
**[7:37]** Cat the, well, it doesn't appear in Reference 1 or Reference 2, so
**[7:41]** I clip that to 0.
**[7:45]** Cat on, yep, that appears once.
**[7:47]** We give it credit for once.
**[7:49]** On the appears once, give that credit for once, and the mat appears once.
**[7:50]** So these are the clipped counts.
**[7:53]** We're taking all the counts and clipping them, really reducing them to be no
**[7:59]** more than the number of times that bigram appears in at least one of the references.
**[8:08]** And then, finally,
**[8:09]** our modified bigram precision will be the sum of the count clipped.
**[8:15]** So that's 1, 2, 3, 4 divided by the total number of bigrams.
**[8:20]** That's 2, 3, 4, 5, 6, so 4 out of 6 or
**[8:25]** two-thirds is the modified precision on bigrams.
**[8:30]** So let's just formalize this a little bit further.
**[8:35]** With what we had developed on unigrams,
**[8:41]** we defined this modified precision computed on unigrams as P subscript 1.
**[8:49]** The P stands for precision and
**[8:51]** the subscript 1 here means that we're referring to unigrams.
**[8:55]** But that is defined as sum over the unigrams.
**[8:58]** So that just means sum over the words that appear in the machine translation output.
**[9:05]** So this is called y hat of count clip, Of that unigram.
**[9:14]** Divided by sum of our unigrams in the machine translation output of count,
**[9:28]** number of counts of that unigram, right?
**[9:32]** And so this is what we had gotten I guess
**[9:37]** is 2 out of 7, 2 slides back.
**[9:40]** So the 1 here refers to unigram,
**[9:44]** meaning we're looking at single words in isolation.
**[9:47]** You can also define Pn as the n-gram version,
**[9:54]** Instead of unigram, for n-gram.
**[9:59]** So this would be sum over the n-grams
**[10:03]** in the machine translation output
**[10:07]** of count clip of that n-gram divided by
**[10:14]** sum over n-grams of the count of that n-gram.
**[10:24]** And so these precisions, or these modified precision scores,
**[10:36]** measured on unigrams or on bigrams, which we did on a previous slide,
**[10:40]** or on trigrams, which are triples of words,
**[10:43]** or even higher values of n for other n-grams.
**[10:48]** This allows you to measure the degree to which the machine translation
**[10:53]** output is similar or maybe overlaps with the references.
**[11:03]** And one thing that you could probably convince yourself of is if the MT
**[11:07]** output is exactly the same as either Reference 1 or Reference 2,
**[11:11]** then all of these values P1, and P2 and so on, they'll all be equal to 1.0.
**[11:19]** So to get a modified precision of 1.0,
**[11:26]** you just have to be exactly equal to one of the references.
**[11:30]** And sometimes it's possible to achieve this even if you aren't
**[11:33]** exactly the same as any of the references.
**[11:35]** But you kind of combine them in a way that hopefully still
**[11:38]** results in a good translation.
**[11:40]** Finally, Finally,
**[11:43]** let's put this together to form the final BLEU score.
**[11:47]** So P subscript n is the BLEU score computed on n-grams only.
**[11:53]** Also the modified precision computed on n-grams only.
**[11:57]** And by convention to compute one number, you compute P1,
**[12:04]** P2, P3 and P4, and combine them together using the following formula.
**[12:11]** It's going to be the average, so sum from n = 1 to 4 of Pn and divide that by 4.
**[12:19]** So basically taking the average.
**[12:21]** By convention the BLEU score is defined as, e to the this, then exponentiations,
**[12:27]** and linear operate, exponentiation is strictly monotonically increasing
**[12:32]** operation and then we actually adjust this with one more factor called the,
**[12:38]** BP penalty.
**[12:41]** So BP, Stands
**[12:45]** for brevity penalty.
**[12:47]** The details maybe aren't super important.
**[12:52]** But to just give you a sense, it turns out that if you output very short
**[12:57]** translations, it's easier to get high precision.
**[13:00]** Because probably most of the words you output appear in the references.
**[13:06]** But we don't want translations that are very short.
**[13:09]** So the BP, or the brevity penalty, is an adjustment factor that penalizes
**[13:15]** translation systems that output translations that are too short.
**[13:19]** So the formula for the brevity penalty is the following.
**[13:21]** It's equal to 1 if your machine translation system actually outputs
**[13:27]** things that are longer than the human generated reference outputs.
**[13:33]** And otherwise is some formula like that that
**[13:36]** overall penalizes shorter translations.
**[13:41]** So, in the details you can find in this paper.
**[13:45]** So, once again, earlier in this set of courses,
**[13:50]** you saw the importance of having a single real number evaluation metric.
**[13:55]** Because it allows you to try out two ideas, see which one achieves a higher
**[13:58]** score, and then try to stick with the one that achieved the higher score.
**[14:03]** So the reason the BLEU score was revolutionary for
**[14:06]** machine translation was because this gave a pretty good, by no means perfect, but
**[14:11]** pretty good single real number evaluation metric.
**[14:14]** And so that accelerated the progress of the entire field of machine translation.
**[14:19]** I hope this video gave you a sense of how the BLEU score works.
**[14:22]** In practice, few people would implement a BLEU score from scratch.
**[14:27]** There are open source implementations that you can download and
**[14:30]** just use to evaluate your own system.
**[14:32]** But today, BLEU score is used to evaluate many systems that generate text,
**[14:37]** such as machine translation systems, as well as the example I showed briefly
**[14:42]** earlier of image captioning systems where you would have a system,
**[14:47]** have a neural network generated image caption.
**[14:49]** And then use the BLEU score to see how much that overlaps with maybe a reference
**[14:54]** caption or multiple reference captions that were generated by people.
**[14:59]** So the BLEU score is a useful single real number evaluation metric to use
**[15:04]** whenever you want your algorithm to generate a piece of text.
**[15:07]** And you want to see whether it has similar meaning as a reference
**[15:12]** piece of text generated by humans.
**[15:14]** This is not used for speech recognition, because in speech recognition,
**[15:18]** there's usually one ground truth.
**[15:19]** And you just use other measures to see if you got the speech transcription on
**[15:25]** pretty much, exactly word for word correct.
**[15:27]** But for things like image captioning, and multiple captions for a picture,
**[15:30]** it could be about equally good or for machine translations.
**[15:34]** There are multiple translations, but equally good.
**[15:38]** The BLEU score gives you a way to evaluate that automatically and
**[15:42]** therefore speed up your development.
**[15:44]** So with that, I hope you have a sense of how the BLEU score works.
