---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 1
section: Clustering
item_title: Initializing K-means
duration: 9 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/lw9LD/initializing-k-means
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Initializing K-means — Transcript

**[0:01]** The very first step of the K means clustering algorithm, was to choose random
**[0:06]** locations as the initial guesses for the cluster centroids mu one through mu K.
**[0:12]** But how do you actually take that random guess.
**[0:15]** Let's take a look at that in this video, as well as how you can take multiple
**[0:20]** attempts at the initial guesses with mu one through mu K.
**[0:23]** That will result in your finding a better set of clusters.
**[0:27]** Let's take a look, here again is the K means algorithm and
**[0:31]** in this video let's take a look at how you can implement this first step.
**[0:37]** When running K means you should pretty much always choose the number of
**[0:41]** cluster centroids K to be lessened to training examples m.
**[0:46]** It doesn't really make sense to have K greater than m because then there
**[0:50]** won't even be enough training examples to have at least one training
**[0:55]** example per cluster centroids.
**[0:58]** So in our earlier example we had K equals two and m equals 30.
**[1:04]** In order to choose the cluster centroids,
**[1:09]** the most common way is to randomly pick K training examples.
**[1:16]** So here is a training set where if I were to randomly pick two training examples,
**[1:23]** maybe I end up picking this one and this one.
**[1:27]** And then we would set new one through mu K equal to these K training examples.
**[1:35]** So I might initialize my red cluster centroid here,
**[1:40]** and initialize my blue cluster centroids over here,
**[1:45]** in the example where K was equal to two.
**[1:48]** And it turns out that if this was your random initialization and
**[1:55]** you were to run K means you pray end up with K means
**[1:59]** deciding that these are the two classes in the data set.
**[2:02]** Notes that this method of initializing the cost of central is a little bit different
**[2:07]** than what I had used in the illustration in the earlier videos.
**[2:10]** Where I was initializing the cluster centroids mu one and mu two to be just
**[2:14]** random points rather than sitting on top of specific training examples.
**[2:20]** I've done that to make the illustrations clearer in the earlier videos.
**[2:24]** But what I'm showing in this slide is actually a much more commonly used way of
**[2:29]** initializing the clusters centroids.
**[2:33]** Now with this method there is a chance that you end up with an initialization of
**[2:39]** the cluster centroids where the red cross is here and maybe the blue cross is here.
**[2:46]** And depending on how you choose the random initial central centroids
**[2:52]** K-means will end up picking a difference set of causes for your data set.
**[2:56]** Let's look at a slightly more complex example, where we're going to look
**[3:01]** at this data set and try to find three clusters so k equals three in this data.
**[3:07]** If you were to run K means with one random initialization of the cluster centroid,
**[3:14]** you may get this result up here and this looks like a pretty good choice.
**[3:19]** Pretty good clustering of the data into three different clusters.
**[3:24]** But with a different initialization, say you had happened to initialize
**[3:28]** two of the cluster centroids within this group of points.
**[3:32]** And one within this group of points, after running k means you might
**[3:37]** end up with this clustering, which doesn't look as good.
**[3:41]** And this turns out to be a local optima, in which K-means is trying
**[3:47]** to minimize the distortion cost function, that cost function J of
**[3:52]** C one through CM and mu one through mu K that you saw in the last video.
**[3:58]** But with this less fortunate choice of random initialization,
**[4:03]** it had just happened to get stuck in a local minimum.
**[4:09]** And here's another example of a local minimum,
**[4:12]** where a different random initialization course came in to find this
**[4:17]** clustering of the data into three clusters,
**[4:20]** which again doesn't seem as good as the one that you saw up here on top.
**[4:27]** So if you want to give k means multiple shots at finding the best local optimum.
**[4:34]** If you want to try multiple random initialization, so
**[4:38]** give it a better chance of finding this good clustering up on top.
**[4:43]** One other thing you could do with the K-means algorithm
**[4:46]** is to run it multiple times and then to try to find the best local optima.
**[4:51]** And it turns out that if you were to run k means three times say, and
**[4:56]** end up with these three distinct clusterings.
**[5:00]** Then one way to choose between these three solutions,
**[5:04]** is to compute the cost function J for all three of these solutions,
**[5:09]** all three of these choices of clusters found by k means.
**[5:13]** And then to pick one of these three according to which one
**[5:17]** of them gives you the lowest value for the cost function J.
**[5:23]** And in fact, if you look at this grouping of clusters up here,
**[5:28]** this green cross has relatively small square distances, all the green dots.
**[5:33]** The red cross is relatively small distance and red dots and similarly the blue cross.
**[5:38]** And so the cost function J will be relatively small for this example on top.
**[5:44]** But here, the blue cross has larger distances to all of the blue dots.
**[5:51]** And here the red cross has larger distances to all of the red dots,
**[5:55]** which is why the cost function J, for these examples down below would be larger.
**[6:01]** Which is why if you pick from these three options,
**[6:05]** the one with the smallest distortion of the smallest cost function J.
**[6:10]** You end up selecting this choice of the cluster centroids.
**[6:15]** So let me write this out more formally into an algorithm, and wish you would
**[6:20]** run K-means multiple times using different random initialization.
**[6:26]** Here's the algorithm, if you want to use 100 random initialization for
**[6:32]** K-means, then you would run 100 times randomly initialized
**[6:38]** K-means using the method that you saw earlier in this video.
**[6:44]** Pick K training examples and let the cluster centroids
**[6:48]** initially be the locations of those K training examples.
**[6:53]** Using that random initialization, run the K-means algorithm to convergence.
**[6:58]** And that will give you a choice of cluster assignments and cluster centroids.
**[7:04]** And then finally,
**[7:06]** you would compute the distortion compute the cost function as follows.
**[7:12]** After doing this, say 100 times,
**[7:15]** you would finally pick the set of clusters, that gave the lowest cost.
**[7:20]** And it turns out that if you do this will often give you a much
**[7:25]** better set of clusters, with a much lower distortion
**[7:29]** function than if you were to run K means only a single time.
**[7:34]** I plugged in the number up here as 100.
**[7:38]** When I'm using this method,
**[7:40]** doing this somewhere between say 50 to 1000 times would be pretty common.
**[7:45]** Where, if you run this procedure a lot more than 1000 times,
**[7:49]** it tends to get computational expensive.
**[7:52]** And you tend to have diminishing returns when you run it a lot of times.
**[7:58]** Whereas trying at least maybe 50 or
**[8:00]** 100 random initializations, will often give you a much better
**[8:04]** result than if you only had one shot at picking a good random initialization.
**[8:10]** But with this technique you are much more likely to end up with this good choice
**[8:15]** of clusters on top.
**[8:16]** And these less superior local minima down at the bottom.
**[8:20]** So that's it, when I'm using the K means algorithm myself,
**[8:23]** I will almost always use more than one random initialization.
**[8:27]** Because it just causes K means to do a much better job minimizing the distortion
**[8:31]** cost function and finding a much better choice for the cluster centroids.
**[8:37]** Before we wrap up our discussion of K means,
**[8:40]** there's just one more video in which I hope to discuss with you.
**[8:43]** The question of how do you choose the number of clusters centroids?
**[8:47]** How do you choose the value of K?
**[8:50]** Let's go on to the next video to take a look at that.
