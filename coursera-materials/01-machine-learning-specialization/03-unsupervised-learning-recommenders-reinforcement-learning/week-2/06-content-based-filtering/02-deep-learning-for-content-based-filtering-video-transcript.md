---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 2
section: Content-based filtering
item_title: Deep learning for content-based filtering
duration: 10 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/WIBGp/deep-learning-for-content-based-filtering
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Deep learning for content-based filtering — Transcript

**[0:00]** A good way to develop
**[0:02]** a content-based filtering algorithm
**[0:04]** is to use deep learning.
**[0:06]** The approach you see in this video is the way that
**[0:09]** many important commercial
**[0:12]** state-of-the-art content-based filtering algorithms
**[0:14]** are built today. Let's take a look.
**[0:16]** Recall that in our approach,
**[0:20]** given a feature vector describing a user,
**[0:24]** such as age and gender, and country,
**[0:26]** and so on, we have to compute
**[0:29]** the vector v_u, and similarly,
**[0:32]** given a vector describing
**[0:34]** a movie such as year of release,
**[0:37]** the stars in the movie, and so on,
**[0:39]** we have to compute a vector v_m.
**[0:42]** In order to do the former,
**[0:45]** we're going to use a neural network.
**[0:47]** The first neural network will
**[0:50]** be what we'll call the user network.
**[0:53]** Here's an example of user network,
**[0:56]** that takes as input the list
**[0:58]** of features of the user, x_u,
**[1:01]** so the age, the gender,
**[1:02]** the country of the user, and so on.
**[1:05]** Then using a few layers,
**[1:08]** say dense neural network layers,
**[1:10]** it will output this vector v_u that describes the user.
**[1:17]** Notice that in this neural network,
**[1:20]** the output layer has 32 units,
**[1:24]** and so v_u is actually a list of 32 numbers.
**[1:28]** Unlike most of the neural networks
**[1:30]** that we were using earlier,
**[1:31]** the final layer is not a layer with one unit,
**[1:36]** it's a layer with 32 units.
**[1:38]** Similarly, to compute v_m for a movie,
**[1:44]** we can have a movie network as follows,
**[1:47]** that takes as input features of the movie and
**[1:51]** through a few layers of
**[1:53]** a neural network is outputting v_m,
**[1:56]** that vector that describes the movie.
**[1:59]** Finally, we'll predict the rating of this user on
**[2:05]** that movie as v_ u dot product with v_m.
**[2:10]** Notice that the user network and the movie network can
**[2:14]** hypothetically have different numbers of
**[2:16]** hidden layers and different numbers
**[2:18]** of units per hidden layer.
**[2:20]** All the output layer needs to
**[2:22]** have the same size of the same dimension.
**[2:24]** In the description you've seen so far,
**[2:27]** we were predicting the 1-5 or 0-5 star movie rating.
**[2:33]** If we had binary labels,
**[2:35]** if y was to the user like or favor an item,
**[2:39]** then you can also modify this algorithm to output.
**[2:43]** Instead of v_u.v_m,
**[2:46]** you can apply the sigmoid function
**[2:49]** to that and use this to
**[2:51]** predict the probability that's y^i,j is 1.
**[2:56]** To flesh out this notation,
**[2:58]** we can also add superscripts i and
**[3:00]** j here if we want to emphasize that
**[3:03]** this is the prediction by user j on movie
**[3:06]** i. I've drawn here the user network
**[3:10]** and the movie network as two separate neural networks.
**[3:13]** But it turns out that we can actually
**[3:14]** draw them together in
**[3:16]** a single diagram as if it was a single neural network.
**[3:20]** This is what it looks like.
**[3:22]** On the upper portion of this diagram,
**[3:25]** we have the user network which
**[3:28]** inputs x_u and ends up computing v_u.
**[3:31]** On the lower portion of this diagram,
**[3:34]** we have what was the movie network,
**[3:36]** the input is x_m and ends up computing v_m,
**[3:40]** and these two vectors are then dot-product together.
**[3:45]** This dot here represents dot product,
**[3:47]** and this gives us our prediction.
**[3:51]** Now, this model has a lot of parameters.
**[3:56]** Each of these layers of a neural network has
**[3:58]** a usual set of parameters of the neural network.
**[4:01]** How do you train all the parameters of
**[4:04]** both the user network and the movie network?
**[4:08]** What we're going to do is construct a cost function J,
**[4:13]** which is going to be very similar to
**[4:15]** the cost function that you
**[4:16]** saw in collaborative filtering,
**[4:18]** which is assuming that you do have
**[4:20]** some data of some users having rated some movies,
**[4:24]** we're going to sum over all pairs i and
**[4:27]** j of where you have labels,
**[4:30]** where i,j equals 1
**[4:32]** of the difference between the prediction.
**[4:36]** That would be v_u^j dot product with
**[4:40]** v_m^i minus y^ij squared.
**[4:46]** The way we would train this model
**[4:49]** is depending on the parameters of the neural network,
**[4:53]** you end up with different vectors
**[4:55]** here for the users and for the movies.
**[4:58]** What we'd like to do is train the parameters
**[5:02]** of the neural network so that you end up with
**[5:04]** vectors for the users and for the movies that results in
**[5:08]** small squared error into predictions you get out here.
**[5:12]** To be clear, there's
**[5:15]** no separate training procedure
**[5:17]** for the user and movie networks.
**[5:20]** This expression down here,
**[5:22]** this is the cost function used to train
**[5:25]** all the parameters of the user and the movie networks.
**[5:29]** We're going to judge the two networks according to how
**[5:32]** well v_u and v_m predict y^ij,
**[5:36]** and with this cost function,
**[5:38]** we're going to use gradient descent or
**[5:40]** some other optimization algorithm to tune
**[5:43]** the parameters of the neural network to cause
**[5:45]** the cost function J to be as small as possible.
**[5:48]** If you want to regularize this model,
**[5:51]** we can also add the usual neural
**[5:53]** network regularization term to
**[5:56]** encourage the neural networks to keep
**[5:58]** the values of their parameters small.
**[6:01]** It turns out, after you've trained this model,
**[6:04]** you can also use this to find similar items.
**[6:07]** This is akin to what we have seen
**[6:09]** with collaborative filtering features,
**[6:12]** helping you find similar items
**[6:13]** as well. Let's take a look.
**[6:16]** V_u^j is a vector of length 32 that describes
**[6:21]** a user j that have features x_ u^j.
**[6:25]** Similarly, v^i_m is a vector
**[6:29]** of length 32 that describes
**[6:31]** a movie with these features over here.
**[6:34]** Given a specific movie,
**[6:37]** what if you want to find other movies similar to it?
**[6:41]** Well, this vector v^i_m describes the movie i.
**[6:48]** If you want to find other movies similar to it,
**[6:51]** you can then look for other movies k so that the distance
**[6:56]** between the vector describing
**[6:59]** movie k and the vector describing movie i,
**[7:02]** that the squared distance is small.
**[7:05]** This expression plays a role similar to what
**[7:09]** we had previously with collaborative filtering,
**[7:12]** where we talked about finding a movie with features
**[7:16]** x^k that was similar to the features x^i.
**[7:21]** Thus, with this approach,
**[7:22]** you can also find items similar to a given item.
**[7:26]** One final note, this can be pre-computed ahead of time.
**[7:31]** By that I mean,
**[7:32]** you can run a compute server overnight to
**[7:36]** go through the list of
**[7:37]** all your movies and for every movie,
**[7:40]** find similar movies to it, so that tomorrow,
**[7:44]** if a user comes to the website and
**[7:46]** they're browsing a specific movie,
**[7:48]** you can already have pre-computed to
**[7:50]** 10 or 20 most similar movies
**[7:52]** to show to the user at that time.
**[7:54]** The fact that you can pre-compute ahead of
**[7:57]** time what's similar to a given movie,
**[7:59]** will turn out to be important
**[8:01]** later when we talk about scaling
**[8:03]** up this approach to a very large catalog of movies.
**[8:07]** That's how you can use deep learning to build
**[8:10]** a content-based filtering algorithm.
**[8:13]** You might remember when we
**[8:15]** were talking about decision trees
**[8:17]** and the pros and cons of
**[8:18]** decision trees versus neural networks.
**[8:21]** I mentioned that one of the benefits of
**[8:23]** neural networks is that it's easier to take
**[8:26]** multiple neural networks and
**[8:27]** put them together to make them
**[8:28]** work in concert to build a larger system.
**[8:32]** What you just saw was actually an example of that,
**[8:35]** where we could take a user network and
**[8:37]** the movie network and put them together,
**[8:40]** and then take the inner product of the outputs.
**[8:42]** This ability to put
**[8:44]** two neural networks together this how we've
**[8:47]** managed to come up with
**[8:49]** a more complex architecture
**[8:50]** that turns out to be quite powerful.
**[8:53]** One notes, if you're
**[8:55]** implementing these algorithms in practice,
**[8:56]** I find that developers often
**[8:58]** end up spending a lot of time carefully
**[9:01]** designing the features needed to feed
**[9:03]** into these content-based filtering algorithms.
**[9:06]** If we end up building one of these systems commercially,
**[9:08]** it may be worth spending some time
**[9:11]** engineering good features for this application as well.
**[9:15]** In terms of these applications,
**[9:19]** one limitation that the algorithm
**[9:20]** as we've described it is it can be
**[9:22]** computationally very expensive to run if you have
**[9:25]** a large catalog of a lot of
**[9:27]** different movies you may want to recommend.
**[9:29]** In the next video, let's take a look at some of
**[9:32]** the practical issues and how you can modify
**[9:34]** this algorithm to make it scale that are working
**[9:37]** on even very large item catalogs.
**[9:40]** Let's go see that in the next video.
