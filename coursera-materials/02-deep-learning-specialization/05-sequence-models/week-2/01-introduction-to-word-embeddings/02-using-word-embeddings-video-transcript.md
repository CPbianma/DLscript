---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 2
section: Introduction to Word Embeddings
item_title: Using Word Embeddings
duration: 9 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/qHMK5/using-word-embeddings
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Using Word Embeddings — Transcript

**[0:00]** In the last video, you saw what it might mean to learn
**[0:03]** a featurized representations of different words.
**[0:06]** In this video, you see how we can take these representations and
**[0:10]** plug them into NLP applications.
**[0:12]** Let's start with an example.
**[0:13]** Continuing with the named entity recognition example,
**[0:16]** if you're trying to detect people's names.
**[0:19]** Given a sentence like Sally Johnson is an orange farmer, hopefully, you'll figure
**[0:24]** out that Sally Johnson is a person's name, hence, the outputs 1 like that.
**[0:30]** And one way to be sure that Sally Johnson has to be a person, rather
**[0:34]** than say the name of the corporation is that you know orange farmer is a person.
**[0:39]** So previously, we had talked about one hot representations to represent these words,
**[0:44]** x(1), x(2), and so on.
**[0:46]** But if you can now use the featurized representations,
**[0:50]** the embedding vectors that we talked about in the last video.
**[0:54]** Then after having trained a model that uses word embeddings as the inputs,
**[0:59]** if you now see a new input, Robert Lin is an apple farmer.
**[1:03]** Knowing that orange and apple are very similar will make it easier for
**[1:07]** your learning algorithm to generalize to figure out that Robert Lin is also
**[1:12]** a human, is also a person's name.
**[1:15]** One of the most interesting cases will be, what if in your test set you see
**[1:20]** not Robert Lin is an apple farmer, but you see much less common words?
**[1:25]** What if you see Robert Lin is a durian cultivator?
**[1:31]** A durian is a rare type of fruit, popular in Singapore and a few other countries.
**[1:38]** But if you have a small label training set for the named entity recognition task,
**[1:43]** you might not even have seen the word durian or
**[1:45]** seen the word cultivator in your training set.
**[1:49]** I guess technically, this should be a durian cultivator.
**[1:53]** But if you have learned a word embedding that tells you that durian is a fruit,
**[1:58]** so it's like an orange, and a cultivator, someone that cultivates is like a farmer,
**[2:04]** then you might still be generalize from having seen an orange farmer in your
**[2:09]** training set to knowing that a durian cultivator is also probably a person.
**[2:14]** So one of the reasons that word embeddings will be able to do this is
**[2:18]** the algorithms to learning word embeddings can examine very large text corpuses,
**[2:23]** maybe found off the Internet.
**[2:24]** So you can examine very large data sets, maybe a billion words,
**[2:29]** maybe even up to 100 billion words would be quite reasonable.
**[2:33]** So very large training sets of just unlabeled text.
**[2:38]** And by examining tons of unlabeled text, which you can download more or
**[2:44]** less for free, you can figure out that orange and durian are similar.
**[2:49]** And farmer and cultivator are similar, and therefore,
**[2:52]** learn embeddings, that groups them together.
**[2:56]** Now having discovered that orange and
**[2:58]** durian are both fruits by reading massive amounts of Internet text,
**[3:04]** what you can do is then take this word embedding and apply it to your named
**[3:08]** entity recognition task, for which you might have a much smaller training set,
**[3:12]** maybe just 100,000 words in your training set, or even much smaller.
**[3:17]** And so this allows you to carry out transfer learning,
**[3:21]** where you take information you've learned from
**[3:25]** huge amounts of unlabeled text that you can suck down essentially for
**[3:29]** free off the Internet to figure out that orange, apple, and durian are fruits.
**[3:35]** And then transfer that knowledge to a task, such as named entity recognition,
**[3:40]** for which you may have a relatively small labeled training set.
**[3:45]** And, of course, for simplicity, l drew this for it only as a unidirectional RNN.
**[3:52]** If you actually want to carry out the named entity recognition task, you should,
**[3:55]** of course, use a bidirectional RNN rather than a simpler one I've drawn here.
**[4:00]** But to summarize,
**[4:01]** this is how you can carry out transfer learning using word embeddings.
**[4:05]** Step 1 is to learn word embeddings from a large text corpus, a very large
**[4:10]** text corpus or you can also download pre-trained word embeddings online.
**[4:16]** There are several word embeddings that you can find online
**[4:19]** under very permissive licenses.
**[4:23]** And you can then take these word embeddings and transfer
**[4:26]** the embedding to new task, where you have a much smaller labeled training sets.
**[4:30]** And use this, let's say, 300 dimensional embedding, to represent your words.
**[4:35]** One nice thing also about this is you can now use
**[4:40]** relatively lower dimensional feature vectors.
**[4:43]** So rather than using a 10,000 dimensional one-hot vector,
**[4:48]** you can now instead use maybe a 300 dimensional dense vector.
**[4:53]** Although the one-hot vector is fast and the 300 dimensional vector that
**[4:57]** you might learn for your embedding will be a dense vector.
**[5:01]** And then, finally, as you train your model on your new task,
**[5:06]** on your named entity recognition task with a smaller label data set,
**[5:10]** one thing you can optionally do is to continue to fine tune,
**[5:14]** continue to adjust the word embeddings with the new data.
**[5:20]** In practice, you would do this only if this task 2 has a pretty big data set.
**[5:26]** If your label data set for step 2 is quite small, then usually,
**[5:30]** I would not bother to continue to fine tune the word embeddings.
**[5:35]** So word embeddings tend to make the biggest difference when the task you're
**[5:39]** trying to carry out has a relatively smaller training set.
**[5:44]** So it has been useful for many NLP tasks.
**[5:47]** And I'll just name a few.
**[5:47]** Don't worry if you don't know these terms.
**[5:50]** It has been useful for named entity recognition, for text summarization, for
**[5:54]** co-reference resolution, for parsing.
**[5:57]** These are all maybe pretty standard NLP tasks.
**[6:00]** It has been less useful for language modeling, machine translation,
**[6:04]** especially if you're accessing a language modeling or machine translation task for
**[6:08]** which you have a lot of data just dedicated to that task.
**[6:11]** So as seen in other transfer learning settings,
**[6:15]** if you're trying to transfer from some task A to some task B,
**[6:19]** the process of transfer learning is just most useful when you happen to
**[6:24]** have a ton of data for A and a relatively smaller data set for B.
**[6:28]** And so that's true for a lot of NLP tasks, and just less true for
**[6:33]** some language modeling and machine translation settings.
**[6:38]** Finally, word embeddings has a interesting relationship to the face
**[6:42]** encoding ideas that you learned about in the previous course,
**[6:46]** if you took the convolutional neural networks course.
**[6:50]** So you will remember that for face recognition,
**[6:53]** we train this Siamese network architecture that would learn,
**[6:57]** say, a 128 dimensional representation for different faces.
**[7:02]** And then you can compare these encodings in order to figure out if
**[7:07]** these two pictures are of the same face.
**[7:10]** The words encoding and embedding mean fairly similar things.
**[7:16]** So in the face recognition literature, people also use the term
**[7:22]** encoding to refer to these vectors, f(x(i)) and f(x(j)).
**[7:27]** One difference between the face recognition literature and
**[7:30]** what we do in word embeddings is that, for face recognition,
**[7:34]** you wanted to train a neural network that can take as input any face picture,
**[7:40]** even a picture you've never seen before,
**[7:42]** and have a neural network compute an encoding for that new picture.
**[7:46]** Whereas what we'll do, and you'll understand this better when we go through
**[7:50]** the next few videos, whereas what we'll do for learning word embeddings is that
**[7:54]** we'll have a fixed vocabulary of, say, 10,000 words.
**[7:58]** And we'll learn a vector e1 through, say,
**[8:02]** e10,000 that just learns a fixed encoding or
**[8:06]** learns a fixed embedding for each of the words in our vocabulary.
**[8:12]** So that's one difference between the set of ideas you saw for face recognition
**[8:17]** versus what the algorithms we'll discuss in the next few videos.
**[8:21]** But the terms encoding and embedding are used somewhat interchangeably.
**[8:26]** So the difference I just described is not represented by the difference in
**[8:30]** terminologies.
**[8:31]** It's just a difference in how we need to use these algorithms in face recognition,
**[8:36]** where there's unlimited sea of pictures you could see in the future.
**[8:40]** Versus natural language processing, where there might be just a fixed vocabulary,
**[8:45]** and everything else like that we'll just declare as an unknown word.
**[8:50]** So in this video, you saw how using word embeddings allows you to
**[8:54]** implement this type of transfer learning.
**[8:56]** And how, by replacing the one-hot vectors we're using previously with the embedding
**[9:01]** vectors, you can allow your algorithms to generalize much better, or
**[9:05]** you can learn from much less label data.
**[9:07]** Next, I want to show you just a few more properties of these word embeddings.
**[9:11]** And then after that, we will talk about algorithms for
**[9:14]** actually learning these word embeddings.
**[9:16]** Let's go on to the next video,
**[9:18]** where you'll see how word embeddings can help with reasoning about analogies.
