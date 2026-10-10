---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 1
section: Clustering
item_title: K-means intuition
duration: 7 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/xS8nN/k-means-intuition
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# K-means intuition — Transcript

**[0:01]** Let's take a look at what the K-means clustering algorithm does.
**[0:05]** Let me start with an example.
**[0:08]** Here I've plotted a data set with 30 unlabeled training examples.
**[0:13]** So there are 30 points.
**[0:15]** And what we like to do is run K-means on this data set.
**[0:19]** The first thing that the K-means algorithm does is it will take a random guess
**[0:25]** at where might be the centers of the two clusters that you might ask it to find.
**[0:31]** In this example I'm going to ask it to try to find two clusters.
**[0:36]** Later in this week we'll talk about how
**[0:38]** you might decide how many clusters to find.
**[0:41]** But the very first step is it will randomly pick two points,
**[0:46]** which I've shown here as a red cross and the blue cross,
**[0:51]** at where might be the centers of two different clusters.
**[0:56]** This is just a random initial guess and they're not particularly good guesses.
**[1:00]** But it's a start.
**[1:02]** One thing I hope you take away from this video is that K-means will
**[1:07]** repeatedly do two different things.
**[1:09]** The first is assign points to cluster centroids and
**[1:13]** the second is move cluster centroids.
**[1:15]** Let's take a look at what this means.
**[1:18]** The first of the two steps is it will go through each of these points and
**[1:25]** look at whether it is closer to the red cross or to the blue cross.
**[1:31]** The very first thing that K-means does is it will take a random guess
**[1:36]** at where are the centers of the cluster?
**[1:39]** And the centers of the cluster are called cluster centroids.
**[1:45]** After it's made an initial guess at where the cluster centroid is,
**[1:50]** it will go through all of these examples, x(1) through x(30), my 30 data points.
**[1:57]** And for each of them it will check if it is closer to the red cluster centroid,
**[2:02]** shown by the red cross, or if it's closer to the blue cluster centroid,
**[2:06]** shown by the blue cross.
**[2:08]** And it will assign each of these points to whichever of the cluster
**[2:13]** centroids It is closer to.
**[2:15]** I'm going to illustrate that by painting each of these examples,
**[2:19]** each of these little round dots, either red or blue, depending on
**[2:24]** whether that example is closer to the red or to the blue cluster centroid.
**[2:30]** So this point up here is closer to the red centroid, which is why it's painted red.
**[2:34]** Whereas this point down there is closer to the blue cluster centroid,
**[2:39]** which is why I've now painted it blue.
**[2:41]** So that was the first of the two things that K-means does over and over.
**[2:47]** Which is a sign points to clusters centroids.
**[2:50]** And all that means is it will associate which I'm illustrating with the color,
**[2:55]** every point of one of the cluster centroids.
**[2:58]** The second of the two steps that K-means does is,
**[3:02]** it'll look at all of the red points and take an average of them.
**[3:08]** And it will move the red cross to whatever is the average
**[3:13]** location of the red dots, which turns out to be here.
**[3:18]** And so the red cross, that is the red cluster centroid will move here.
**[3:23]** And then we do the same thing for all the blue dots.
**[3:25]** Look at all the blue dots, and take an average of them, and
**[3:29]** move the blue cross over there.
**[3:31]** So you now have a new location for the blue cluster centroid as well.
**[3:37]** In the next video we'll look at the mathematical formulas for
**[3:41]** how to do both of these steps.
**[3:43]** But now that you have these new and hopefully slightly improved guesses for
**[3:48]** the locations of the to cluster centroids,
**[3:51]** we'll look through all of the 30 training examples again.
**[3:55]** And check for every one of them, whether it's closer to the red or
**[3:59]** the blue cluster centroid for the new locations.
**[4:03]** And then we will associate them which are indicated by the color again,
**[4:08]** every point to the closer cluster centroid.
**[4:11]** And if you do that, you see that the field points change color.
**[4:15]** So for example, this point is colored red,
**[4:18]** because it was closer to the red cluster centroid previously.
**[4:22]** But if we now look again, it's now actually closer to
**[4:25]** the blue cluster centroid, because the blue and red cluster centroids have moved.
**[4:30]** So if we go through and associate each point with the closer
**[4:35]** cluster centroids, you end up with this.
**[4:38]** And then we just repeat the second part of K-means again.
**[4:42]** Which is look at all of the red dots and compute the average.
**[4:48]** And also look at all of the blue dots and
**[4:51]** compute the average location of all of the blue dots.
**[4:54]** And it turns out that you end up moving the red cross over there and
**[5:00]** the blue cross over here.
**[5:02]** And we repeat.
**[5:03]** Let's look at all of the points again and we color them,
**[5:06]** either red or blue, depending on which cluster centroid that is closer to.
**[5:11]** So you end up with this.
**[5:13]** And then again, look at all of the red dots and take their average location,
**[5:18]** and look at all the blue dots and take the average location, and
**[5:22]** move the clusters to the new locations.
**[5:24]** And it turns out that if you were to keep on repeating these two steps, that is
**[5:29]** look at each point and assign it to the nearest cluster centroid and then also
**[5:34]** move each cluster centroid to the mean of all the points with the same color.
**[5:39]** If you keep on doing those two steps, you find that there are no more changes to
**[5:43]** the colors of the points or to the locations of the clusters centroids.
**[5:48]** And so this means that at this point the K-means clustering algorithm has
**[5:52]** converged.
**[5:53]** Because applying those two steps over and over, results in no further
**[5:58]** changes to either the assignment to point to the centroids or
**[6:02]** the location of the cluster centroids.
**[6:05]** In this example, it looks like K-means has done a pretty good job.
**[6:09]** It has found that these points up here correspond to one cluster,
**[6:14]** and these points down here correspond to a second cluster.
**[6:19]** So now you've seen an illustration of how K-means works.
**[6:24]** The two key steps are, assign every point to the cluster centroid,
**[6:28]** depending on what cluster centroid is nearest to.
**[6:31]** And second move each cluster centroid to the average or
**[6:35]** the mean of all the points that were assigned to it.
**[6:39]** In the next video, we'll look at how to formalize this and
**[6:42]** write out the algorithm that does what you just saw in this video.
**[6:46]** Let's go on to the next video.
