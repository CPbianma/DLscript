---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 2
section: Applications Using Word Embeddings
item_title: Sentiment Classification
duration: 8 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/Jxuhl/sentiment-classification
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Sentiment Classification — Transcript

**[0:00]** Sentiment classification is the task of looking at a piece of text
**[0:04]** and telling if someone likes or dislikes
**[0:07]** the thing they're talking about.
**[0:09]** It is one of the most important building blocks in NLP and is used in many applications.
**[0:14]** One of the challenges of sentiment classification
**[0:15]** is you might not have a huge label training set for it.
**[0:19]** But with word embeddings,
**[0:20]** you're able to build good sentiment classifiers
**[0:22]** even with only modest-size label training sets.
**[0:25]** Let's see how you can do that.
**[0:27]** So here's an example of a sentiment classification problem.
**[0:31]** The input X is a piece of text and the output Y
**[0:34]** that you want to predict is what is the sentiment,
**[0:38]** such as the star rating of,
**[0:40]** let's say, a restaurant review.
**[0:43]** So if someone says, "The dessert is excellent" and they give it a four-star review,
**[0:47]** "Service was quite slow" two-star review,
**[0:49]** "Good for a quick meal but nothing special" three-star review.
**[0:51]** And this is a pretty harsh review,
**[0:53]** "Completely lacking in good taste, good service, and good ambiance."
**[0:54]** That's a one-star review.
**[0:56]** So if you can train a system to map from X or Y based on a label data set like this,
**[1:02]** then you could use it to monitor comments that
**[1:05]** people are saying about maybe a restaurant that you run.
**[1:08]** So people might also post messages about your restaurant on social media,
**[1:13]** on Twitter, or Facebook,
**[1:14]** or Instagram, or other forms of social media.
**[1:17]** And if you have a sentiment classifier,
**[1:20]** they can look just a piece of text and figure out how
**[1:23]** positive or negative is the sentiment of the poster toward your restaurant.
**[1:27]** Then you can also be able to keep track of whether or not there are
**[1:30]** any problems or if your restaurant is getting better or worse over time.
**[1:35]** So one of the challenges of
**[1:38]** sentiment classification is you might not have a huge label data set.
**[1:43]** So for sentimental classification task,
**[1:45]** training sets with maybe anywhere from
**[1:47]** 10,000 to maybe 100,000 words would not be uncommon.
**[1:52]** Sometimes even smaller than 10,000 words and word embeddings that you can
**[1:57]** take can help you to much
**[2:00]** better understand especially when you have a small training set.
**[2:03]** So here's what you can do.
**[2:04]** We'll go for a couple different algorithms in this video.
**[2:08]** Here's a simple sentiment classification model.
**[2:11]** You can take a sentence like "dessert is excellent" and
**[2:13]** look up those words in your dictionary.
**[2:16]** We use a 10,000-word dictionary as usual.
**[2:18]** And let's build a classifier to map it to the output Y that this was four stars.
**[2:24]** So given these four words, as usual,
**[2:27]** we can take these four words and look up the one-hot vector.
**[2:33]** So there's 0 8 9 2 8 which is a one-hot vector multiplied by the embedding matrix E,
**[2:38]** which can learn from a much larger text corpus.
**[2:41]** It can learn in embedding from, say,
**[2:43]** a billion words or a hundred billion words,
**[2:45]** and use that to extract out the embedding vector for the word "the",
**[2:50]** and then do the same for "dessert",
**[2:52]** do the same for "is" and do the same for "excellent".
**[2:57]** And if this was trained on a very large data set,
**[3:02]** like a hundred billion words,
**[3:04]** then this allows you to take a lot of knowledge even from
**[3:06]** infrequent words and apply them to your problem,
**[3:10]** even words that weren't in your labeled training set.
**[3:15]** Now here's one way to build a classifier,
**[3:17]** which is that you can take these vectors,
**[3:19]** let's say these are 300-dimensional vectors,
**[3:22]** and you could then just sum or average them.
**[3:26]** And I'm just going to put a bigger average operator here and you could use sum or average.
**[3:34]** And this gives you a 300-dimensional feature vector
**[3:38]** that you then pass to a soft-max classifier which then outputs Y-hat.
**[3:44]** And so the softmax can output what are
**[3:47]** the probabilities of the five possible outcomes from one-star up to five-star.
**[3:50]** So this will be assortment of the five possible outcomes to predict what is Y.
**[3:57]** So notice that by using the average operation here,
**[4:01]** this particular algorithm works for reviews that are
**[4:04]** short or long because even if a review that is 100 words long,
**[4:08]** you can just sum or average all the feature vectors for all hundred words
**[4:11]** and so that gives you a representation,
**[4:15]** a 300-dimensional feature representation,
**[4:18]** that you can then pass into your sentiment classifier.
**[4:21]** So this average will work decently well.
**[4:23]** And what it does is it really averages the meanings of
**[4:27]** all the words or sums the meaning of all the words in your example.
**[4:33]** And this will work to [inaudible].
**[4:35]** So one of the problems with this algorithm is it ignores word order.
**[4:38]** In particular, this is a very negative review,
**[4:41]** "Completely lacking in good taste,
**[4:43]** good service, and good ambiance".
**[4:44]** But the word good appears a lot.
**[4:46]** This is a lot.
**[4:47]** Good, good, good.
**[4:48]** So if you use an algorithm like this that ignores word order
**[4:52]** and just sums or averages all of the embeddings for the different words,
**[4:56]** then you end up having a lot of the representation of good in
**[5:01]** your final feature vector and your classifier will probably
**[5:04]** think this is a good review even though this is actually very harsh.
**[5:07]** This is a one-star review.
**[5:08]** So here's a more sophisticated model which is that,
**[5:11]** instead of just summing all of your word embeddings,
**[5:14]** you can instead use a RNN for sentiment classification.
**[5:20]** So here's what you can do. You can take that review,
**[5:23]** "Completely lacking in good taste,
**[5:24]** good service, and good ambiance",
**[5:26]** and find for each of them, the one-hot vector.
**[5:29]** And so I'm going to just skip
**[5:31]** the one-hot vector representation but take the one-hot vectors,
**[5:34]** multiply it by the embedding matrix E as usual,
**[5:38]** then this gives you the embedding vectors and then you can feed these into an RNN.
**[5:48]** And the job of the RNN is to then compute
**[5:52]** the representation at the last time step that allows you to predict Y-hat.
**[5:57]** So this is an example of
**[5:59]** a many-to-one RNN architecture which we saw in the previous week.
**[6:07]** And with an algorithm like this,
**[6:08]** it will be much better at taking word sequence into account and realize that "things are
**[6:14]** lacking in good taste" is a negative review
**[6:16]** and "not good" a negative review unlike the previous algorithm,
**[6:20]** which just sums everything together into a big-word vector
**[6:24]** mush and doesn't realize that "not good" has a very different meaning
**[6:29]** than the words "good" or "lacking in good taste" and so on.
**[6:34]** And so if you train this algorithm,
**[6:35]** you end up with a pretty decent sentiment classification algorithm and
**[6:39]** because your word embeddings can be trained from a much larger data set,
**[6:45]** this will do a better job
**[6:46]** generalizing to maybe even new words now that you'll see in your training set,
**[6:49]** such as if someone else says,
**[6:51]** "Completely absent of good taste,
**[6:55]** good service, and good ambiance" or something,
**[6:57]** then even if the word "absent" is not in your label training set,
**[7:02]** if it was in your 1 billion or 100 billion word corpus used to train the word embeddings,
**[7:08]** it might still get this right and generalize much better even to words that were in
**[7:14]** the training set used to train the word embeddings but not
**[7:16]** necessarily in the label training set
**[7:19]** that you had for specifically the sentiment classification problem.
**[7:21]** So that's it for sentiment classification,
**[7:25]** and I hope this gives you a sense of how
**[7:27]** once you've learned or downloaded from online a word embedding,
**[7:31]** this allows you to quite quickly build pretty effective NLP systems.
