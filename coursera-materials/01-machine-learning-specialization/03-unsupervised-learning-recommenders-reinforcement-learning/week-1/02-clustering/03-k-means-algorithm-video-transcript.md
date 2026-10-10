---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 1
section: Clustering
item_title: K-means algorithm
duration: 10 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/GwgDo/k-means-algorithm
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# K-means algorithm — Transcript

**[0:00]** In the last video, you saw
**[0:03]** an illustration of the k-means algorithm running.
**[0:06]** Now let's write out the K-means algorithm in
**[0:09]** detail so that you'd
**[0:10]** be able to implement it for yourself.
**[0:12]** Here's the K-means algorithm.
**[0:14]** The first step is to
**[0:17]** randomly initialize K cluster centroids,
**[0:20]** Mu 1 Mu 2,
**[0:21]** through Mu k. In the example that we had,
**[0:25]** this corresponded to when we randomly
**[0:28]** chose a location for
**[0:30]** the red cross and for
**[0:33]** the blue cross corresponding
**[0:35]** to the two cluster centroids.
**[0:38]** In our example, K was equal to two.
**[0:41]** If the red cross was cluster
**[0:45]** centroid one and the blue cross was cluster centroid two.
**[0:48]** These are just two indices
**[0:51]** to denote the first and the second cluster.
**[0:53]** Then the red cross would be the location of Mu 1
**[0:58]** and the blue cross would be the location of Mu 2.
**[1:04]** Just to be clear, Mu 1 and Mu 2
**[1:08]** are vectors which have
**[1:10]** the same dimension as your training examples,
**[1:13]** X1 through say X30, in our example.
**[1:17]** All of these are lists of two numbers or they're
**[1:20]** two-dimensional vectors or whatever
**[1:23]** dimension the training data had.
**[1:26]** We had n equals two features for each of
**[1:30]** the training examples then Mu 1 and Mu
**[1:32]** 2 will also be two-dimensional vectors,
**[1:36]** meaning vectors with two numbers in them.
**[1:38]** Having randomly initialized the K cluster centroids,
**[1:43]** K-means will then repeatedly carry
**[1:45]** out the two steps that you saw in the last video.
**[1:48]** The first step is to assign points to clusters,
**[1:51]** centroids, meaning color, each of the points,
**[1:54]** either red or blue,
**[1:57]** corresponding to assigning them to cluster centroids one
**[2:00]** or two when K is equal to two.
**[2:05]** Rinse it out enough.
**[2:08]** That means that we're going to,
**[2:10]** for I equals one through m for all m training examples,
**[2:14]** we're going to set c^i to be equal to the index,
**[2:17]** which can be anything from one to K of
**[2:21]** the cluster centroid closest to the training example x^i.
**[2:25]** Mathematically you can write this out
**[2:27]** as computing the distance
**[2:29]** between x^i and Mu k. In math,
**[2:33]** the distance between two points
**[2:35]** is often written like this.
**[2:38]** It is also called the L2 norm.
**[2:41]** What you want to find is the value of
**[2:44]** k that minimizes this,
**[2:48]** because that corresponds to the cluster centroid Mu k
**[2:52]** that is closest to the training example x^i.
**[2:58]** Then the value of k that minimizes this
**[3:01]** is what gets set to c^i.
**[3:06]** When you implement this algorithm,
**[3:09]** you find that it's actually a little
**[3:11]** bit more convenient to minimize
**[3:13]** the squared distance because the cluster centroid with
**[3:17]** the smallest square distance should be the
**[3:20]** same as the cluster centroid with the smallest distance.
**[3:25]** When you look at
**[3:26]** this week's optional labs and practice labs,
**[3:30]** you see how to implement this in code for yourself.
**[3:33]** As a concrete example,
**[3:36]** this point up here is closer to
**[3:38]** the red or two cluster centroids 1.
**[3:41]** If this was training example x^1,
**[3:44]** we will set c^1 to be equal to 1.
**[3:49]** Whereas this point over here,
**[3:50]** if this was the 12th training example,
**[3:53]** this is closer to
**[3:54]** the second cluster centroids the blue one.
**[3:57]** We will set this,
**[3:59]** the corresponding cluster assignment
**[4:01]** variable to two because it's
**[4:03]** closer to cluster centroid 2.
**[4:06]** That's the first step of the K-means algorithm,
**[4:10]** assign points to cluster centroids.
**[4:12]** The second step is to move the cluster centroids.
**[4:17]** What that means is for lowercase k equals 1 to capital K,
**[4:22]** the number of clusters.
**[4:24]** We're going to set
**[4:26]** the cluster centroid location to be updated to
**[4:30]** be the average or the mean of the points
**[4:33]** assigned to that cluster k. Concretely,
**[4:36]** what that means is, we'll look at all
**[4:38]** of these red points, say,
**[4:39]** and look at their position on
**[4:41]** the horizontal axis and look at
**[4:43]** the value of the first feature x^1,
**[4:45]** and average that out.
**[4:47]** Compute the average value on the vertical axis as well.
**[4:52]** After computing those two averages,
**[4:54]** you find that the mean is here,
**[4:56]** which is why Mu 1,
**[4:59]** that is the location that the red cluster centroid
**[5:02]** gets updated as follows.
**[5:05]** Similarly, we will look at all of
**[5:08]** the points that were colored blue, that is,
**[5:10]** with c^i equals 2 and
**[5:15]** computes the average of the value on the horizontal axis,
**[5:19]** the average of their feature x1.
**[5:21]** Compute the average of the feature x2.
**[5:24]** Those two averages give you
**[5:26]** the new location of the blue cluster centroid,
**[5:29]** which therefore moves over here.
**[5:32]** Just to write those out in math.
**[5:35]** If the first cluster has assigned to
**[5:39]** it training examples 1,5,6,10.
**[5:46]** Just as an example.
**[5:48]** Then what that means is you will
**[5:50]** compute the average this way.
**[5:54]** Notice that x^1, x^5, x^6,
**[5:56]** and x^10 are training examples.
**[6:00]** Four training examples,
**[6:02]** so we divide by 4 and this gives
**[6:04]** you the new location of Mu1,
**[6:07]** the new cluster centroid for cluster 1.
**[6:11]** To be clear, each of these x values
**[6:14]** are vectors with two numbers in them,
**[6:17]** or n numbers in them if you have n features,
**[6:21]** and so Mu will also have two numbers in it or
**[6:24]** n numbers in it if you have n features instead of two.
**[6:29]** Now, there is one corner case of this algorithm,
**[6:32]** which is what happens if
**[6:34]** a cluster has zero training examples assigned to it.
**[6:38]** In that case, the second step, Mu k,
**[6:41]** would be trying to compute the average of zero points.
**[6:45]** That's not well-defined.
**[6:46]** If that ever happens,
**[6:48]** the most common thing to do is to
**[6:50]** just eliminate that cluster.
**[6:52]** You end up with K minus 1 clusters.
**[6:55]** Or if you really, really need
**[6:57]** K clusters an alternative would be to just
**[6:59]** randomly reinitialize that cluster centroid
**[7:03]** and hope that it gets assigned at
**[7:04]** least some points next time round.
**[7:06]** But it's actually more
**[7:08]** common when running K-means to just
**[7:10]** eliminate a cluster if no points are assigned to it.
**[7:14]** Even though I've mainly been describing
**[7:16]** K-means for clusters that are well separated.
**[7:19]** Clusters that may look like this.
**[7:21]** Where if you asked her to find three clusters,
**[7:25]** hopefully they will find these three distinct clusters.
**[7:29]** It turns out that K-means is also frequently applied to
**[7:32]** data sets where the clusters are not that well separated.
**[7:36]** For example, if you are
**[7:38]** a designer and manufacturer of cool t-shirts,
**[7:42]** and you want to decide,
**[7:44]** how do I size my small,
**[7:47]** medium, and large t-shirts.
**[7:49]** How small should a small be,
**[7:51]** how large should a large be,
**[7:52]** and what should a medium-size t-shirt really be?
**[7:55]** One thing you might do is collect
**[7:57]** data of people likely to
**[7:59]** buy your t-shirts based on their heights and weights.
**[8:03]** You find that the height and weight of people tend to
**[8:07]** vary continuously on the spectrum
**[8:09]** without some very clear clusters.
**[8:12]** Nonetheless, if you were to run K-means
**[8:15]** with say, three clusters centroids,
**[8:19]** you might find that K-means would
**[8:21]** group these points into one cluster,
**[8:23]** these points into a second cluster,
**[8:25]** and these points into a third cluster.
**[8:29]** If you're trying to decide
**[8:32]** exactly how to size your small,
**[8:34]** medium, and large t-shirts,
**[8:36]** you might then choose the dimensions of
**[8:40]** your small t-shirt to try to make it
**[8:42]** fit these individuals well.
**[8:44]** The medium-size t-shirt to
**[8:46]** try to fit these individuals well,
**[8:47]** and the large t-shirt to try to
**[8:49]** fit these individuals well with
**[8:52]** potentially the cluster centroids
**[8:55]** giving you a sense of what is
**[8:56]** the most representative height and weight that
**[8:59]** you will want your three t-shirt sizes to fit.
**[9:02]** This is an example of K-means
**[9:05]** working just fine and giving
**[9:07]** a useful results even if the data does
**[9:10]** not lie in well-separated groups or clusters.
**[9:14]** That was the K-means clustering algorithm.
**[9:18]** Assign cluster centroids randomly and then repeatedly
**[9:21]** assign points to cluster centroids
**[9:23]** and move the cluster centroids.
**[9:25]** But what this algorithm really doing and do we think
**[9:28]** this algorithm will converge or they just
**[9:30]** keep on running forever and never converge.
**[9:33]** To gain deeper intuition about the K-means algorithm and
**[9:36]** also see why we might hope this algorithm does converge,
**[9:40]** let's go on to the next video where you see that
**[9:43]** K-means is actually trying to
**[9:44]** optimize a specific cost function.
**[9:47]** Let's take a look at that in the next video.
