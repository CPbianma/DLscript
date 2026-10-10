---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 4
section: Face Recognition
item_title: Triplet Loss
duration: 15 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/HuUtN/triplet-loss
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Triplet Loss — Transcript

**[0:00]** One way to learn the parameters of the neural network,
**[0:03]** so that it gives you a good encoding
**[0:06]** for your pictures of faces,
**[0:07]** is to define and apply
**[0:09]** gradient descent on the triplet loss function.
**[0:11]** Let's see what that means.
**[0:13]** To apply the triplet loss you
**[0:15]** need to compare pairs of images.
**[0:18]** For example, given this picture,
**[0:21]** to learn the parameters of the neural network,
**[0:24]** you have to look at several pictures at the same time.
**[0:27]** For example, given this pair of images,
**[0:29]** you want their encodings to be
**[0:31]** similar because these are the same person.
**[0:33]** Whereas given this pair of images,
**[0:35]** you want their encodings to be quite
**[0:38]** different because these are different persons.
**[0:41]** In the terminology of the triplet loss,
**[0:44]** what you're going to do is always
**[0:46]** look at one anchor image,
**[0:48]** and then you want to distance between
**[0:51]** the anchor and a positive image,
**[0:53]** really a positive example,
**[0:55]** meaning is the same person, to be similar.
**[0:57]** Whereas you want the anchor
**[0:59]** when pairs are compared to have
**[1:01]** a negative example for
**[1:03]** their distances to be much further apart.
**[1:07]** This is what gives rise to the term triplet loss,
**[1:10]** which is that you always be looking
**[1:12]** at three images at a time.
**[1:14]** You'll be looking at an anchor image,
**[1:17]** a positive image, as well as a negative image.
**[1:22]** I'm going to abbreviate anchor, positive,
**[1:24]** and negative as A, P,
**[1:26]** and N. To formalize this,
**[1:29]** what you want is for the parameters of
**[1:32]** your neural network or for your encoding
**[1:34]** to have the following property;
**[1:36]** which is that you want the encoding
**[1:39]** between the anchor minus
**[1:41]** the encoding of the positive example,
**[1:44]** you want this to be small, and in particular,
**[1:47]** you want this to be less than or equal to
**[1:50]** the distance or the squared norm
**[1:52]** between the encoding of
**[1:54]** the anchor and the encoding of the negative,
**[1:59]** whereof course this is d of A,
**[2:02]** P and this is d of A,
**[2:06]** N. You can think of d as a distance function,
**[2:11]** which is why we named it with the alphabet d. Now,
**[2:14]** if we move the term from
**[2:16]** the right side of this equation to the left side,
**[2:18]** what you end up with is f of
**[2:21]** A minus f of P squared minus,
**[2:25]** I'm going to take the right-hand side now,
**[2:27]** minus f of N squared,
**[2:31]** you want it to be less than or equal to zero.
**[2:34]** But now we're going to make a slight change
**[2:37]** to this expression, which is;
**[2:38]** one trivial way to make sure this is satisfied
**[2:41]** is to just learn everything equals zero.
**[2:44]** If f always output zero,
**[2:46]** then this is 0 minus 0, which is 0,
**[2:48]** this is 0 minus 0, which is 0, and so, well,
**[2:51]** by saying f of any image equals a vector of all zero's,
**[2:57]** you can see almost trivially satisfy this equation.
**[3:01]** To make sure that the neural network
**[3:03]** doesn't just output zero,
**[3:05]** for all the encodings,
**[3:07]** or to make sure that it doesn't set
**[3:09]** all the encodings equal to each other.
**[3:12]** Another way for the neural network
**[3:14]** to give a trivial outputs is
**[3:16]** if the encoding for every image was
**[3:18]** identical to the encoding to every other image,
**[3:20]** in which case you again get 0 minus 0.
**[3:25]** To prevent your neural network from doing that,
**[3:28]** what we're going to do is modify this objective to say
**[3:31]** that this doesn't need to be
**[3:33]** just less than equal to zero,
**[3:36]** it needs to be quite a bit smaller than zero.
**[3:40]** In particular, if we say this needs to
**[3:43]** be less than negative Alpha,
**[3:45]** where Alpha is another hyperparameter
**[3:49]** then this prevents a neural network
**[3:51]** from outputting the trivial solutions.
**[3:53]** By convention, usually, we write
**[3:55]** plus Alpha instead of negative Alpha there.
**[3:59]** This is also called a margin,
**[4:02]** which is terminology that you'd be familiar with
**[4:06]** if you've also seen the literature
**[4:08]** on support vector machines,
**[4:10]** but don't worry about it if you haven't.
**[4:12]** We can also modify this equation on top
**[4:15]** by adding this margin parameter.
**[4:18]** Given example, let's say the margin is set to 0.2.
**[4:23]** If in this example d of
**[4:25]** the anchor and the positive is equal to 0.5,
**[4:29]** then you won't be satisfied if
**[4:31]** d between the anchor and the negative,
**[4:34]** was just a little bit bigger, say 0.51.
**[4:36]** Of one. Even though 0.51 is bigger than 0.5,
**[4:41]** you're saying that's not good enough.
**[4:43]** We want d of A,N to be much bigger than d of A,P.
**[4:48]** In particular, you want this to be
**[4:50]** at least 0.7 or higher.
**[4:53]** Alternatively,
**[4:54]** to achieve this margin or this gap of at least 0.2,
**[4:58]** you could either push this up or push this down
**[5:02]** so that there is at least this gap of
**[5:05]** this hyperparameter Alpha 0.2 between
**[5:09]** the distance between the anchor and the
**[5:11]** positive versus the anchor and the negative.
**[5:14]** That's what having a margin parameter here does.
**[5:17]** Which is it pushes
**[5:18]** the anchor-positive pair and
**[5:21]** the anchor-negative pair further away from each other.
**[5:25]** Let's take this equation we have here at
**[5:28]** the bottom and on the next slide,
**[5:31]** formalize it and define the triplet loss function.
**[5:35]** The triplet loss function is
**[5:37]** defined on triples of images.
**[5:40]** Given three images: A,
**[5:44]** P, and N, the anchor positive and negative examples,
**[5:48]** so the positive examples is of
**[5:51]** the same person as the anchor,
**[5:53]** but the negative is of
**[5:54]** a different person than the anchor.
**[5:57]** We're going to define the loss as follows.
**[6:01]** The loss on this example,
**[6:03]** which is really defined on a triplet of images is,
**[6:06]** let me first copy over what we had on the previous slide.
**[6:10]** That was f A minus f P squared
**[6:16]** minus f A minus f N squared,
**[6:23]** and then plus alpha, the margin parameter.
**[6:26]** What you want is for this to
**[6:28]** be less than or equal to zero.
**[6:32]** To define the loss function,
**[6:34]** let's take the max between this and zero.
**[6:39]** The effect of taking the max here is that
**[6:42]** so long as this is less than zero,
**[6:45]** then the loss is zero
**[6:47]** because the max is something less than equal
**[6:48]** to zero with zero is going to be zero.
**[6:52]** So long as you achieve the goal of
**[6:54]** making this thing I've underlined in green,
**[6:56]** so long as you've achieved the objective of
**[6:58]** making that less than or equal to zero,
**[7:00]** then the loss on this example is equal to zero.
**[7:04]** But if on the other hand,
**[7:05]** if this is greater than zero,
**[7:07]** then if you take the max,
**[7:09]** the max will end up selecting
**[7:10]** this thing I've underlined in
**[7:11]** green and so you'd have a positive loss.
**[7:15]** By trying to minimize this,
**[7:17]** this has the effect of trying to send
**[7:19]** this thing to be zero or less than equal to zero.
**[7:23]** Then so long as this zero or less than equal to zero,
**[7:26]** the neural network doesn't care
**[7:28]** how much further negative it is.
**[7:31]** This is how you define the loss on
**[7:33]** a single triplet and the
**[7:36]** overall cost function for your neural network can
**[7:38]** be sum over a training set of
**[7:42]** these individual losses on different triplets.
**[7:48]** If you have a training set of say,
**[7:51]** 10,000 pictures with 1,000 different persons,
**[7:55]** what you'd have to do is take your
**[7:57]** 10,000 pictures and use it to generate,
**[8:00]** to select triplets like this,
**[8:02]** and then train your learning algorithm using
**[8:05]** gradient descent on this type of cost function,
**[8:08]** which is really defined on triplets
**[8:09]** of images drawn from your training set.
**[8:13]** Notice that in order to define this dataset of triplets,
**[8:19]** you do need some pairs of A and P,
**[8:22]** pairs of pictures of the same person.
**[8:25]** For the purpose of training your system,
**[8:27]** you do need a dataset where you
**[8:29]** have multiple pictures of the same person.
**[8:32]** That's why in this example I said if you have
**[8:34]** 10,000 pictures of 1,000 different persons,
**[8:38]** so maybe you have ten pictures,
**[8:40]** on average of each of your
**[8:41]** 1,000 persons to make up your entire dataset.
**[8:44]** If you had just one picture of each person,
**[8:47]** then you can't actually train this system.
**[8:49]** But of course, after having trained a system,
**[8:56]** you can then apply it to
**[8:58]** your one-shot learning problem
**[8:59]** where for your face recognition system,
**[9:02]** maybe you have only a single picture
**[9:04]** of someone you might be trying to recognize.
**[9:06]** But for your training set,
**[9:08]** you do need to make sure you have
**[9:09]** multiple images of the same person,
**[9:12]** at least for some people in your training set,
**[9:14]** so that you can have pairs of anchor and positive images.
**[9:18]** Now, how do you actually
**[9:21]** choose these triplets to form your training set?
**[9:24]** One of the problems is if you choose A,
**[9:28]** P, and N randomly from your training set,
**[9:31]** subject to A and P being
**[9:33]** the same person and A and N being different persons,
**[9:36]** one of the problems is that if
**[9:38]** you choose them so that they're random,
**[9:40]** then this constraint is very easy to satisfy.
**[9:44]** Because given two randomly chosen pictures of people,
**[9:48]** chances are A and N are much different than A and P.
**[9:53]** I hope you still recognize this notation.
**[9:55]** Does d (A, P) will be high
**[9:59]** written on the last few slides of these encoding.
**[10:02]** This is equal to
**[10:05]** this squared norm distance between
**[10:08]** the encodings that we had on the previous line.
**[10:10]** But if A and N are two randomly chosen different persons,
**[10:14]** then there's a very high chance that
**[10:16]** this will be much bigger,
**[10:18]** more than the margin helper,
**[10:20]** than that term on the left and
**[10:21]** the Neural Network won't learn much from it.
**[10:24]** To construct your training set,
**[10:26]** what you want to do is to choose triplets, A,
**[10:28]** P, and N, they're the ''hard'' to train on.
**[10:31]** In particular, what you want is for all triplets
**[10:34]** that this constraint be satisfied.
**[10:38]** A triplet that is ''hard'' would be if you
**[10:42]** choose values for A, P,
**[10:44]** and N so that may be d (A,
**[10:47]** P) is actually quite close to d (A, N).
**[10:52]** In that case, the learning algorithm has
**[10:55]** to try extra hard to take this thing on the right
**[10:58]** and try to push it up or take
**[11:00]** this thing on the left and try to push it down
**[11:02]** so that there is at least a margin of
**[11:05]** alpha between the left side and the right side.
**[11:08]** The effect of choosing these triplets is that it
**[11:11]** increases the computational efficiency
**[11:14]** of your learning algorithm.
**[11:16]** If you choose the triplets randomly,
**[11:18]** then too many triplets would be
**[11:20]** really easy and gradient descent
**[11:22]** won't do anything because you're Neural Network would
**[11:24]** get them right pretty much all the time.
**[11:27]** It's only by choosing ''hard'' to triplets
**[11:29]** that the gradient descent procedure
**[11:32]** has to do some work to try to push
**[11:34]** these quantities further away from those quantities.
**[11:38]** If you're interested, the details are
**[11:41]** presented in this paper by Florian Schroff,
**[11:45]** Dmitry Kalenichenko, and James Philbin,
**[11:48]** where they have a system called FaceNet,
**[11:51]** which is where a lot of the ideas I'm
**[11:53]** presenting in this video had come from.
**[11:55]** By the way, this is also a fun fact about
**[11:58]** how algorithms are often
**[12:00]** named in the Deep Learning World,
**[12:02]** which is if you work in a certain domain,
**[12:04]** then we call that Blank.
**[12:05]** You often have a system called Blank Net or Deep Blank.
**[12:10]** We've been talking about Face recognition.
**[12:13]** This paper is called FaceNet,
**[12:15]** and in the last video,
**[12:17]** you just saw Deep Face.
**[12:19]** But this idea of Blank Net or Deep Blank is
**[12:23]** a very popular way of
**[12:25]** naming algorithms in the Deep Learning World.
**[12:28]** You should feel free to take a look at
**[12:30]** that paper if you want to learn some of
**[12:32]** these other details for speeding up
**[12:34]** your algorithm by choosing
**[12:36]** the most useful triplets to train on;
**[12:38]** it is a nice paper.
**[12:40]** Just to wrap up, to train on triplet loss,
**[12:43]** you need to take your training set
**[12:45]** and map it to a lot of triples.
**[12:47]** Here is a triple with an Anchor and a Positive,
**[12:50]** both of the same person and
**[12:52]** a Negative of a different person.
**[12:54]** Here's another one where
**[12:56]** the Anchor and Positive are of the same person,
**[12:59]** but the Anchor and Negative are
**[13:01]** of different persons and so on.
**[13:03]** What you do, having to find
**[13:05]** this training set of Anchor, Positive,
**[13:08]** and Negative triples is use gradient descent to try to
**[13:11]** minimize the cost function
**[13:14]** J we defined on an earlier slide.
**[13:16]** That will have the effect of
**[13:18]** backpropagating to all the parameters
**[13:20]** of the Neural Network in
**[13:22]** order to learn an encoding so that
**[13:26]** d of two images will be small when
**[13:31]** these two images are of the same person and they'll
**[13:34]** be large when these are two images of different persons.
**[13:40]** That's it for the triplet loss
**[13:42]** and how you can use it to train
**[13:43]** a Neural Network to output
**[13:45]** a good encoding for face recognition.
**[13:48]** Now, it turns out that today's Face recognition systems,
**[13:52]** especially the large-scale
**[13:53]** commercial face recognition systems
**[13:55]** are trained on very large datasets.
**[13:57]** Datasets north of a million images are not uncommon.
**[14:00]** Some companies are using north of
**[14:02]** 10 million images and some companies
**[14:04]** have north of a100 million images
**[14:06]** with which they try to train these systems.
**[14:08]** These are very large datasets,
**[14:10]** even by modern standards,
**[14:12]** these dataset assets are not easy to acquire.
**[14:15]** Fortunately, some of these companies have trained
**[14:18]** these large networks and posted parameters online.
**[14:22]** Rather than trying to train one
**[14:23]** of these networks from scratch,
**[14:25]** this is one domain where because of
**[14:27]** the sheer data volumes sizes,
**[14:30]** it might be useful for you to download
**[14:33]** someone else's pre-trained model
**[14:35]** rather than do everything from scratch yourself.
**[14:38]** But even if you do download
**[14:39]** someone else's pre-trained model,
**[14:40]** I think it's still useful to know
**[14:42]** how these algorithms were trained in
**[14:45]** case you need to apply these ideas from
**[14:47]** scratch yourself for some application.
**[14:49]** That's it for the triplet loss.
**[14:51]** In the next video, I want to show you also
**[14:54]** some other variations on
**[14:56]** Siamese networks and how to train these systems.
**[14:58]** Let's go on to the next video.
