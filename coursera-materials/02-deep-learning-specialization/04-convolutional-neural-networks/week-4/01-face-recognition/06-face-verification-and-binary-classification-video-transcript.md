---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 4
section: Face Recognition
item_title: Face Verification and Binary Classification
duration: 6 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/xTihv/face-verification-and-binary-classification
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Face Verification and Binary Classification — Transcript

**[0:00]** The Triplet Loss is one good way to learn
**[0:02]** the parameters of a continent for face recognition.
**[0:05]** There's another way to learn these parameters.
**[0:08]** Let me show you how face recognition can also be posed
**[0:11]** as a straight binary classification problem.
**[0:15]** Another way to train a neural network,
**[0:17]** is to take this pair of neural networks to take
**[0:19]** this Siamese Network and have them both compute these embeddings,
**[0:25]** maybe 128 dimensional embeddings,
**[0:27]** maybe even higher dimensional,
**[0:28]** and then have these be input to
**[0:31]** a logistic regression unit to then just make a prediction.
**[0:36]** Where the target output will be one if both of these are the same persons,
**[0:42]** and zero if both of these are of different persons.
**[0:46]** So, this is a way to treat face recognition just as a binary classification problem.
**[0:52]** And this is an alternative to the triplet loss for training a system like this.
**[0:58]** Now, what does this final logistic regression unit actually do?
**[1:03]** The output y hat will be a sigmoid function,
**[1:08]** applied to some set of features but rather than just feeding in,
**[1:12]** these encodings, what you can do is take the differences between the encodings.
**[1:18]** So, let me show you what I mean.
**[1:20]** Let's say, I write a sum over K equals 1 to 128 of the absolute value,
**[1:30]** taken element-wise between the two different encodings.
**[1:35]** Let me just finish writing this out and then we'll see what this means.
**[1:39]** In this notation, f of x i is the encoding of the image x i
**[1:45]** ,and the substitute k means to just select out the cave components of this vector.
**[1:52]** This is taking the element Y's difference in absolute values between these two encodings.
**[1:59]** And what you might do is think of these 128 numbers
**[2:03]** as features that you then feed into logistic regression.
**[2:07]** And, you'll find that little regression can have additional parameters w,
**[2:11]** i, and b similar to a normal logistic regression unit.
**[2:16]** And you would train appropriate waiting on these 128 features in
**[2:21]** order to predict whether or not
**[2:24]** these two images are of the same person or of different persons.
**[2:28]** So, this will be one pretty useful way to
**[2:31]** learn to predict zero or one whether these are the same person or different persons.
**[2:37]** And there are a few other variations on how you can
**[2:40]** compute this formula that I had underlined in green.
**[2:44]** For example, another formula could be this k minus f of x j,
**[2:51]** k squared divided by f of x i
**[2:56]** plus f of x j k. This is sometimes called the chi-square form.
**[3:02]** This is the Greek alphabet chi.
**[3:05]** But this is sometimes called a chi-square similarity.
**[3:08]** And this and other variations are explored in this deep face paper,
**[3:15]** which I referenced earlier as well.
**[3:18]** So in this learning formulation,
**[3:20]** the input is a pair of images,
**[3:23]** so this is really your training input x and the output y
**[3:28]** is either zero or one depending on whether you're inputting
**[3:32]** a pair of similar or dissimilar images.
**[3:35]** And same as before,
**[3:37]** you're training is Siamese Network so that means that,
**[3:40]** this neural network up here has parameters that are what they're
**[3:44]** really tied to the parameters in this lower neural network.
**[3:48]** And this system can work pretty well as well.
**[3:52]** Lastly, just to mention,
**[3:53]** one computational trick that can help neural deployment significantly, which is that,
**[3:58]** if this is the new image,
**[4:00]** so this is an employee walking in hoping that the turnstile
**[4:03]** the doorway will open for them and that this is from your database image.
**[4:08]** Then instead of having to compute,
**[4:11]** this embedding every single time,
**[4:17]** where you can do is actually pre-compute that,
**[4:20]** so, when the new employee walks in,
**[4:22]** what you can do is use this upper components to compute that encoding and use it,
**[4:29]** then compare it to
**[4:31]** your pre-computed encoding and then use that to make a prediction y hat.
**[4:36]** Because you don't need to store the raw images and
**[4:40]** also because if you have a very large database of employees,
**[4:44]** you don't need to compute these encodings every single time for every employee database.
**[4:50]** This idea of free computing,
**[4:52]** some of these encodings can save a significant computation.
**[4:56]** And this type of pre-computation works both for this type of
**[5:00]** Siamese Central architecture where you
**[5:02]** treat face recognition as a binary classification problem,
**[5:07]** as well as, when you were learning encodings maybe using
**[5:11]** the Triplet Loss function as described in the last couple of videos.
**[5:15]** And so just to wrap up,
**[5:16]** to treat face verification supervised learning,
**[5:19]** you create a training set of just pairs of images now is
**[5:23]** of triplets of pairs of images where the target label is one.
**[5:28]** When these are a pair of pictures of the same person and where the tag label is zero,
**[5:34]** when these are pictures of different persons and you use
**[5:38]** different pairs to train
**[5:40]** the neural network to train the scientists that were using backpropagation.
**[5:45]** So, this version that you just saw of treating face verification
**[5:49]** and by extension face recognition as a binary classification problem,
**[5:53]** this works quite well as well.
**[5:55]** And so with that, I hope that you now know,
**[5:57]** what it would take to train
**[5:59]** your own face verification or your own face recognition system, one that can do one-shot learning.
