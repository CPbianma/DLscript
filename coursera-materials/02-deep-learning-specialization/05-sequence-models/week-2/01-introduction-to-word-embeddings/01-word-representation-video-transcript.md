---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 2
section: Introduction to Word Embeddings
item_title: Word Representation
duration: 10 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/6Oq70/word-representation
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Word Representation — Transcript

**[0:00]** Hello, and welcome back.
**[0:03]** Last week, we learned about RNNs, GRUs, and LSTMs.
**[0:06]** In this week, you see how many of these ideas can be applied to NLP,
**[0:11]** to Natural Language Processing,
**[0:13]** which is one of the features of AI because it's
**[0:14]** really being revolutionized by deep learning.
**[0:17]** One of the key ideas you learn about is word embeddings,
**[0:20]** which is a way of representing words.
**[0:22]** The less your algorithms automatically understand analogies like that,
**[0:26]** man is to woman, as king is to queen,
**[0:28]** and many other examples.
**[0:30]** And through these ideas of word embeddings,
**[0:32]** you'll be able to build NLP applications,
**[0:35]** even with models the size of,
**[0:37]** usually of relatively small label training sets.
**[0:40]** Finally towards the end of the week,
**[0:41]** you'll see how to debias word embeddings.
**[0:44]** That's to reduce undesirable gender or
**[0:48]** ethnicity or other types of bias that learning algorithms can sometimes pick up.
**[0:52]** So with that, let's get started with a discussion on word representation.
**[0:57]** So far, we've been representing words using a vocabulary of words,
**[1:03]** and a vocabulary from the previous week might be say, 10,000 words.
**[1:08]** And we've been representing words using a one-hot vector.
**[1:13]** So for example, if man is word number 5391 in this dictionary,
**[1:18]** then you represent him with a vector with one in position 5391.
**[1:24]** And I'm also going to use O subscript 5391 to represent this factor,
**[1:31]** where O here stands for one-hot.
**[1:34]** And then, if woman is word number 9853,
**[1:38]** then you represent it with O subscript
**[1:42]** 9853 which just has a one in position 9853 and zeros elsewhere.
**[1:49]** And then other words king, queen,
**[1:51]** apple, orange will be similarly represented with one-hot vector.
**[1:56]** One of the weaknesses of this representation is
**[2:00]** that it treats each word as a thing unto itself,
**[2:05]** and it doesn't allow an algorithm to easily generalize the cross words.
**[2:10]** For example, let's say you have a language model that has learned
**[2:13]** that when you see I want a glass of orange blank.
**[2:17]** Well, what do you think the next word will be?
**[2:19]** Very likely, it'll be juice.
**[2:22]** But even if the learning algorithm has learned that
**[2:25]** I want a glass of orange juice is a likely sentence,
**[2:29]** if it sees I want a glass of apple blank.
**[2:31]** As far as it knows the relationship between apple and
**[2:35]** orange is not any closer as the relationship between any of the other words man,
**[2:40]** woman, king, queen, and orange.
**[2:42]** And so, it's not easy for the learning algorithm to generalize
**[2:45]** from knowing that orange juice is a popular thing,
**[2:49]** to recognizing that apple juice might also be a popular thing or a popular phrase.
**[2:55]** And this is because the any product between any two different one-hot vector is zero.
**[3:02]** If you take any two vectors say,
**[3:04]** queen and king and any product of them,
**[3:06]** the end product is zero.
**[3:07]** If you take apple and orange and any product of them, the end product is zero.
**[3:12]** And you couldn't distance between any pair of these vectors is also the same.
**[3:16]** So it just doesn't know that somehow apple and orange are
**[3:20]** much more similar than king and orange or queen and orange.
**[3:23]** So, won't it be nice if instead of a one-hot presentation we
**[3:27]** can instead learn a featurized representation with each of these words,
**[3:32]** a man, woman, king, queen, apple,
**[3:33]** orange or really for every word in the dictionary,
**[3:36]** we could learn a set of features and values for each of them.
**[3:40]** So for example, each of these words,
**[3:43]** we want to know what is the gender associated with each of these things.
**[3:46]** So, if gender goes from minus one for male to plus one for female,
**[3:51]** then the gender associated with man might be minus one,
**[3:54]** for woman might be plus one.
**[3:57]** And then eventually, learning these things maybe for king you get minus 0.95,
**[4:00]** for queen plus 0.97,
**[4:02]** and for apple and orange sort of genderless.
**[4:06]** Another feature might be,
**[4:09]** well how royal are these things.
**[4:11]** And so the terms,
**[4:12]** man and woman are not really royal,
**[4:15]** so they might have feature values close to zero.
**[4:18]** Whereas king and queen are highly royal.
**[4:21]** And apple and orange are not really royal.
**[4:25]** How about age?
**[4:26]** Well, man and woman doesn't connotes much about age.
**[4:30]** Maybe men and woman implies that they're adults,
**[4:33]** but maybe neither necessarily young nor old.
**[4:37]** So maybe values close to zero.
**[4:40]** Whereas kings and queens are always almost always adults.
**[4:44]** And apple and orange might be more neutral with respect to age.
**[4:48]** And then, another feature for here,
**[4:50]** is this is a food?
**[4:51]** Well, man is not a food,
**[4:53]** woman is not a food,
**[4:56]** neither are kings and queens,
**[4:58]** but apples and oranges are foods.
**[5:00]** And they can be many other features as well ranging from,
**[5:04]** what is the size of this?
**[5:06]** What is the cost?
**[5:08]** Is this something that is a live?
**[5:10]** Is this an action,
**[5:12]** or is this a noun, or is this a verb,
**[5:14]** or is it something else?
**[5:16]** And so on. So you can imagine coming up with many features.
**[5:20]** And for the sake of the illustration let's say,
**[5:23]** 300 different features, and what that does is,
**[5:27]** it allows you to take this list of numbers,
**[5:29]** I've only written four here,
**[5:31]** but this could be a list of 300 numbers,
**[5:34]** that then becomes a 300 dimensional vector for representing the word man.
**[5:40]** And I'm going to use the notation e
**[5:45]** subscript 5391 to denote a representation like this.
**[5:52]** And similarly, this vector,
**[5:55]** this 300 dimensional vector or 300 dimensional vector like this,
**[5:58]** I would denote e9853
**[6:02]** to denote a 300 dimensional vector we could use to represent the word woman.
**[6:07]** And similarly, for the other examples here.
**[6:11]** Now, if you use this representation to represent the words orange and apple,
**[6:17]** then notice that the representations for orange and apple are now quite similar.
**[6:23]** Some of the features will differ because of the color of an orange,
**[6:27]** the color an apple, the taste,
**[6:29]** or some of the features would differ.
**[6:31]** But by a large,
**[6:32]** a lot of the features of apple and orange are actually the same,
**[6:36]** or take on very similar values.
**[6:38]** And so, this increases the odds of
**[6:40]** the learning algorithm that has figured out that orange juice is a thing,
**[6:44]** to also quickly figure out that apple juice is a thing.
**[6:47]** So this allows it to generalize better across different words.
**[6:52]** So over the next few videos,
**[6:53]** we'll find a way to learn words embeddings.
**[6:56]** We just need you to learn high dimensional feature vectors like these,
**[6:59]** that gives a better representation than one-hot vectors for representing different words.
**[7:05]** And the features we'll end up learning,
**[7:07]** won't have a easy to interpret interpretation like that component one is gender,
**[7:13]** component two is royal,
**[7:14]** component three is age and so on.
**[7:16]** Exactly what they're representing will be a bit harder to figure out.
**[7:20]** But nonetheless, the featurized representations we will learn,
**[7:24]** will allow an algorithm to quickly figure out that
**[7:27]** apple and orange are more similar than say,
**[7:30]** king and orange or queen and orange.
**[7:33]** If we're able to learn
**[7:35]** a 300 dimensional feature vector or 300 dimensional embedding for each words,
**[7:42]** one of the popular things to do is also to
**[7:44]** take this 300 dimensional data and embed it say,
**[7:48]** in a two dimensional space so that you can visualize them.
**[7:52]** And so, one common algorithm for doing this is
**[7:55]** the t-SNE algorithm due to Laurens van der Maaten and Geoff Hinton.
**[8:02]** And if you look at one of these embeddings,
**[8:04]** one of these representations,
**[8:06]** you find that words like man and woman tend to get grouped together,
**[8:11]** king and queen tend to get grouped together,
**[8:13]** and these are the people which tends to get grouped together.
**[8:17]** Those are animals who can get grouped together.
**[8:20]** Fruits will tend to be close to each other.
**[8:21]** Numbers like one, two, three, four,
**[8:23]** will be close to each other.
**[8:25]** And then, maybe the animate objects as whole will also tend to be grouped together.
**[8:31]** But you see plots like these sometimes on the internet to visualize
**[8:35]** some of these 300 or higher dimensional embeddings.
**[8:40]** And maybe this gives you a sense that,
**[8:42]** word embeddings algorithms like this can learn
**[8:46]** similar features for concepts that feel like they should be more related,
**[8:51]** as visualized by that concept that seem to you and me like they should be more similar,
**[8:56]** end up getting mapped to a more similar feature vectors.
**[9:01]** And these representations will use these sort of
**[9:04]** featurized representations in maybe a 300 dimensional space,
**[9:08]** these are called embeddings.
**[9:10]** And the reason we call them embeddings is,
**[9:13]** you can think of a 300 dimensional space.
**[9:16]** And again, they can't draw out here in two dimensional space because it's a 3D one.
**[9:20]** And what you do is you take every words like orange,
**[9:22]** and have a three dimensional feature vector so that word
**[9:26]** orange gets embedded to a point in this 300 dimensional space.
**[9:32]** And the word apple, gets embedded to a different point in this 300 dimensional space.
**[9:38]** And of course to visualize it, algorithms like t-SNE,
**[9:41]** map this to a much lower dimensional space,
**[9:43]** you can actually plot the 2D data and look at it.
**[9:47]** But that's what the term embedding comes from.
**[9:50]** Word embeddings has been one of the most important ideas in NLP,
**[9:54]** in Natural Language Processing.
**[9:56]** In this video, you saw why you might want to learn or use word embeddings.
**[10:01]** In the next video, let's take a deeper look at how you'll be able
**[10:04]** to use these algorithms, to build NLP algorithms.
