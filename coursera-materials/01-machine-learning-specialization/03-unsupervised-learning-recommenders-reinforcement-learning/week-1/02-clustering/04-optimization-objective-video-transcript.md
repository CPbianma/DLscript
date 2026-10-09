---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 1
section: Clustering
item_title: Optimization objective
duration: 11 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/f5G5k/optimization-objective
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Optimization objective — Transcript

**[0:01]** In the earlier courses, courses one and two of the specialization, you saw a lot of
**[0:07]** supervised learning algorithms as taking training set posing a cost function.
**[0:13]** And then using grading descent or
**[0:14]** some other algorithms to optimize that cost function.
**[0:18]** It turns out that the K-means algorithm that
**[0:21]** you saw in the last video is also optimizing a specific cost function.
**[0:26]** Although the optimization algorithm that it uses to optimize that is not gradient
**[0:31]** descent is actually the algorithm that you already saw in the last video.
**[0:35]** Let's take a look at what all this means.
**[0:38]** Let's take a look at what is the cost function for K-means,
**[0:42]** to get started as a reminder this is a notation we've been
**[0:46]** using whereas CI is the index of the cluster.
**[0:50]** So CI is some number from one Su K of the index of the cluster
**[0:55]** to which training example XI is currently assigned and
**[1:01]** new K is the location of cluster centroid k.
**[1:05]** Let me introduce one more piece of notation,
**[1:10]** which is when lower case K equals CI.
**[1:15]** So mu subscript CI is the cluster centroid of
**[1:19]** the cluster to which example XI has been assigned.
**[1:24]** So for example, if I were to look at some training example C train example 10 and
**[1:30]** I were to ask What's the location of the clustering centroids to which
**[1:34]** the 10th training example has been assigned?
**[1:39]** Well, I would then look up C10.
**[1:41]** This will give me a number from one to K.
**[1:43]** That tells me was example 10 assigned to the red or the blue or
**[1:48]** some other cluster centroid, and then mu subscript C- 10 is
**[1:54]** the location of the cluster centroid to which extent has been assigned.
**[2:00]** So armed with this notation, let me now write out
**[2:05]** the cost function that K means turns out to be minimizing.
**[2:12]** The cost function J, which is a function of C1 through CM.
**[2:18]** These are all the assignments of points to clusters Androids as
**[2:23]** well as new one through mu capsule K.
**[2:26]** These are the locations of all the clusters centroid is defined as
**[2:31]** this expression on the right.
**[2:34]** It is the average, so one over M some from i
**[2:40]** equals to m of the squared distance between every training example XI
**[2:46]** as I goes from one through M it is a square distance between X I.
**[2:53]** And Nu subscript C high.
**[2:55]** So this quantity up here, in other words, the cost function good for
**[3:00]** K is the average squared distance between every training example XI.
**[3:07]** And the location of the cluster centroid to which the training example exile has
**[3:11]** been assigned.
**[3:12]** So for this example up here we've been measuring the distance
**[3:17]** between X10 and mu subscript C10.
**[3:20]** The cluster centroid to which extent has been assigned and taking the square of
**[3:26]** that distance and that would be one of the terms over here that we're averaging over.
**[3:32]** And it turns out that what the K means algorithm is doing is trying to find
**[3:36]** assignments of points of clusters centroid as well as find locations of
**[3:41]** clusters centroid that minimizes the squared distance.
**[3:45]** Visually, here's what you saw part way into the run
**[3:50]** of K means in the earlier video.
**[3:53]** And at this step the cost function.
**[3:55]** If you were to computer it would be to look at everyone at the blue points and
**[4:00]** measure these distances and computer square.
**[4:03]** And then also similarly look at every one of the red points and
**[4:07]** compute these distances and compute the square.
**[4:11]** And then the average of the squares of all of these differences for
**[4:17]** the red and the blue points is the value of the cost function J,
**[4:23]** at this particular configuration of the parameters for K-means.
**[4:30]** And what they will do on every step is try to update the cluster
**[4:34]** assignments C1 through C30 in this example.
**[4:37]** Or update the positions of the cluster centralism, U1 and U2.
**[4:41]** In order to keep on reducing this cost function J.
**[4:45]** By the way, this cost function J also has a name in
**[4:49]** the literature is called the distortion function.
**[4:54]** I don't know that this is a great name.
**[4:56]** But if you hear someone talk about the key news algorithm and the distortion or
**[5:00]** the distortion cost function, that's just what this formula J is computing.
**[5:06]** Let's now take a deeper look at the algorithm and
**[5:09]** why the algorithm is trying to minimize this cost function J.
**[5:13]** Or why is trying to minimize the distortion here on top of copied over
**[5:17]** the cost function from the previous slide.
**[5:21]** It turns out that the first part of K means where you assign points to cluster
**[5:26]** centroid.
**[5:27]** That turns out to be trying to update C1 through CM.
**[5:32]** To try to minimize the cost function J as much as possible
**[5:36]** while holding mu one through mu K fix.
**[5:40]** And the second step, in contrast where you move the custom centroid,
**[5:45]** it turns out that is trying to leave C1 through CM fix.
**[5:49]** But to update new one through mu K to try to minimize the cost function or
**[5:55]** the distortion as much as possible.
**[5:58]** Let's take a look at why this is the case.
**[6:00]** During the first step, if you want to choose the values of C1 through CM or
**[6:05]** save a particular value of Ci to try to minimize this.
**[6:10]** Well, what would make Xi minus
**[6:15]** mu CI as small as possible?
**[6:19]** This is the distance or the square distance between a training example XI.
**[6:25]** And the location of the class is central to which has been assigned.
**[6:31]** So if you want to minimize this distance or the square distance,
**[6:36]** what you should do is assign XI to the closest cluster centroid.
**[6:42]** So to take a simplified example, if you have two clusters centroid say
**[6:47]** close to central is one and two and just a single training example, XI.
**[6:53]** If you were to sign it to cluster centroid one,
**[6:57]** this square distance here would be this large distance, well squared.
**[7:04]** And if you were to assign it to cluster centroid 2 then this square distance would
**[7:08]** be the square of this much smaller distance.
**[7:11]** So if you want to minimize this term, you will take X I and
**[7:15]** assign it to the closer centroid, which is exactly what the algorithm is doing up here.
**[7:21]** So that's why the step where you assign points to a cluster centroid is choosing
**[7:26]** the values for CI to try to minimize J.
**[7:29]** Without changing, we went through the mu K for now, but just choosing
**[7:33]** the values of C1 through CM to try to make these terms as small as possible.
**[7:40]** How about the second step of the K-means algorithm that is to
**[7:45]** move to clusters centroids?
**[7:47]** It turns out that choosing mu K to be average and the mean of the points
**[7:53]** assigned is the choice of these terms mu that will minimize this expression.
**[8:00]** To take a simplified example,
**[8:03]** say you have a cluster with just two points assigned to it shown as follows.
**[8:08]** And so with the cluster centroid here,
**[8:12]** the average of the square distances would be a distance of
**[8:17]** one here squared plus this distance here, which is 9 squared.
**[8:23]** And then you take the average of these two numbers.
**[8:26]** And so that turns out to be one half of 1 plus 81,
**[8:32]** which turns out to be 41.
**[8:35]** But if you were to take the average of these two points, so
**[8:40]** 1+ 11/2, that's equal to 6.
**[8:43]** And if you were to move the cluster centroid over here to
**[8:48]** middle than the average of these two square distances,
**[8:53]** turns out to be a distance of five and five here.
**[8:57]** So you end up with one half of 5 squared plus 5 squared, which is equal to 25.
**[9:04]** And this is a much smaller average squared distance than 41.
**[9:09]** And in fact, you can play around with the location of this cluster centroid and
**[9:13]** maybe convince yourself that taking this mean location.
**[9:17]** This average location in the middle of these two training examples,
**[9:20]** that is really the value that minimizes the square distance.
**[9:25]** So the fact that the K-means algorithm is optimizing a cost function J
**[9:30]** means that it is guaranteed to converge, that is on every single iteration.
**[9:35]** The distortion cost function should go down or stay the same, but if it ever
**[9:41]** fails to go down or stay the same, in the worst case, if it ever goes up.
**[9:46]** That means there's a bug in the code, it should never go up because
**[9:51]** every single step of K means is setting the value CI and
**[9:55]** mu K to try to reduce the cost function.
**[9:58]** Also, if the cost function ever stops going down,
**[10:02]** that also gives you one way to test if K means has converged.
**[10:05]** Once there's a single iteration where it stays the same.
**[10:09]** That usually means K means has converged and you should just stop running the algorithm
**[10:14]** even further or in some rare cases you will run K means for a long time.
**[10:19]** And the cost function of the distortion is just going down very, very slowly, and
**[10:24]** that's a bit like gradient descent where maybe running even longer might
**[10:28]** help a bit.
**[10:29]** But if the rate at which the cost function is going down has become very, very slow.
**[10:34]** You might also just say this is good enough.
**[10:36]** I'm just going to say it's close enough to convergence and
**[10:39]** not spend even more compute cycles running the algorithm for even longer.
**[10:44]** So these are some of the ways that computing the cost function is helpful
**[10:48]** helps you figure out if the algorithm has converged.
**[10:52]** It turns out that there's one other very useful way
**[10:55]** to take advantage of the cost function,
**[10:58]** which is to use multiple different random initialization of the cluster centroid.
**[11:04]** It turns out if you do this, you can often find much better clusters using K means,
**[11:09]** let's take a look at the next video of how to do that.
