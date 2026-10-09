---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 2
section: Content-based filtering
item_title: TensorFlow implementation of content-based filtering
duration: 5 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/72pRa/tensorflow-implementation-of-content-based-filtering
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# TensorFlow implementation of content-based filtering — Transcript

**[0:00]** In the practice lab, you see how to implement
**[0:04]** content-based filtering in TensorFlow.
**[0:06]** What I'd like to do in this video
**[0:08]** is just set through of you a few of
**[0:10]** the key concepts in the code
**[0:12]** that you get to play with. Let's take a look.
**[0:15]** Recall that our code has started with
**[0:17]** a user network as well as a movie that's work.
**[0:22]** The way you can implement this in TensorFlow is,
**[0:26]** it's very similar to how we have previously
**[0:29]** implemented a neural network with a set of dense layers.
**[0:34]** We're going to use a sequential model.
**[0:36]** We then in this example have
**[0:38]** two dense layers with
**[0:39]** the number of hidden units specified here,
**[0:41]** and the final layer has 32 units and output's 32 numbers.
**[0:46]** Then for the movie network,
**[0:49]** I'm going to call it the item network,
**[0:51]** because the movies are the items here,
**[0:53]** this is what the code looks like.
**[0:55]** Once again, we have coupled dense hidden layers,
**[0:59]** followed by this layer,
**[1:01]** which outputs 32 numbers.
**[1:04]** For the hidden layers, we'll use
**[1:06]** our default choice of activation function,
**[1:08]** which is the relu activation function.
**[1:12]** Next, we need to tell
**[1:15]** TensorFlow Keras how to
**[1:17]** feed the user features or the item features,
**[1:20]** that is the movie features to the two neural networks.
**[1:23]** This is the syntax for doing so.
**[1:26]** That extracts out the input features for
**[1:30]** the user and then feeds it to the user
**[1:33]** and that we had defined up here to compute vu,
**[1:36]** the vector for the user.
**[1:39]** Then one additional step that turns out to make
**[1:41]** this algorithm work a bit better is at this line here,
**[1:45]** which normalizes the vector vu to have length one.
**[1:49]** This normalizes the length,
**[1:51]** also called the l2 norm,
**[1:53]** but basically the length of
**[1:54]** the vector vu to be equal to one.
**[1:57]** Then we do the same thing for the item network,
**[2:00]** for the movie network.
**[2:02]** This extract out the item features and feeds it to
**[2:06]** the item neural network that we defined up there
**[2:10]** This computes the movie vector vm.
**[2:15]** Then finally, the step also
**[2:18]** normalizes that vector to have length one.
**[2:21]** After having computed vu and vm,
**[2:25]** we then have to take
**[2:27]** the dot product between these two vectors.
**[2:30]** This is the syntax for doing so.
**[2:32]** Keras has a special layer type,
**[2:36]** notice we had here tf keras layers dense,
**[2:40]** here this is tf keras layers dot.
**[2:43]** It turns out that there's a special Keras layer,
**[2:46]** they just takes a dot product between two numbers.
**[2:49]** We're going to use that to take
**[2:50]** the dot product between the vectors vu and vm.
**[2:56]** This gives the output of the neural network.
**[2:59]** This gives the final prediction.
**[3:02]** Finally, to tell keras
**[3:05]** what are the inputs and outputs of the model,
**[3:07]** this line tells it that
**[3:09]** the overall model is a model with inputs
**[3:12]** being the user features and
**[3:15]** the movie or the item features and the output,
**[3:17]** this is output that we just defined up above.
**[3:21]** The cost function that we'll use to train this model
**[3:24]** is going to be the mean squared error cost function.
**[3:28]** These are the key code snippets for
**[3:31]** implementing content-based filtering as a neural network.
**[3:35]** You see the rest of the code in
**[3:38]** the practice lab but
**[3:40]** hopefully you'll be able to play with
**[3:42]** that and see how all these code snippets fit together
**[3:46]** into working TensorFlow implementation
**[3:48]** of a content-based filtering algorithm.
**[3:51]** It turns out that there's
**[3:52]** one other step that I didn't talk about previously,
**[3:54]** but if you do this,
**[3:55]** which is normalize the length of the vector vu,
**[3:59]** that makes the algorithm work a bit better.
**[4:02]** TensorFlows has this l2 normalized motion
**[4:06]** that normalizes the vector,
**[4:08]** is also called normalizing the l2 norm of the vector,
**[4:12]** hence the name of the function.
**[4:13]** That's it. Thanks for sticking with me through
**[4:16]** all this material on recommender systems,
**[4:19]** it is an exciting technology.
**[4:21]** I hope you enjoy playing with
**[4:23]** these ideas and codes in the practice labs for this week.
**[4:27]** That takes us to the lots of
**[4:29]** these videos on recommender systems and to
**[4:32]** the end of the next to
**[4:34]** final week for this specialization.
**[4:37]** I look forward to seeing you next week as well.
**[4:39]** We'll talk about the exciting technology
**[4:41]** of reinforcement learning.
**[4:43]** Hope you have fun with the quizzes and with
**[4:45]** the practice labs and I
**[4:46]** look forward to seeing you next week.
