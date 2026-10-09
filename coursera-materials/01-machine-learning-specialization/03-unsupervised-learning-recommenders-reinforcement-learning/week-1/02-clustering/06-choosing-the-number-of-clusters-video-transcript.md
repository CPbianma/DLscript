---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 1
section: Clustering
item_title: Choosing the number of clusters
duration: 7 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/LK4Zn/choosing-the-number-of-clusters
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Choosing the number of clusters — Transcript

**[0:01]** The k-means algorithm requires as one of its inputs, k,
**[0:06]** the number of clusters you want it to find,
**[0:08]** but how do you decide how many clusters to used.
**[0:11]** Do you want two clusters or three clusters of
**[0:13]** five clusters or 10 clusters? Let's take a look.
**[0:16]** For a lot of clustering problems,
**[0:18]** the right value of K is truly ambiguous.
**[0:23]** If I were to show
**[0:25]** different people the same data set and ask,
**[0:28]** how many clusters do you see?
**[0:30]** There will definitely be people that will say,
**[0:33]** it looks like there are two distinct clusters
**[0:36]** and they will be right.
**[0:38]** There would also be others that will see
**[0:42]** actually four distinct clusters.
**[0:47]** They would also be right.
**[0:49]** Because clustering is
**[0:51]** unsupervised learning algorithm you're not given
**[0:55]** the quote right answers in the form
**[0:58]** of specific labels to try to replicate.
**[1:01]** There are lots of applications where the data itself
**[1:05]** does not give a clear indicator
**[1:08]** for how many clusters there are in it.
**[1:10]** I think it truly is ambiguous if
**[1:12]** this data has two or four,
**[1:15]** or maybe three clusters.
**[1:18]** If you take say, the red one
**[1:20]** here and the two blue ones here say.
**[1:22]** If you look at the academic literature on K-means,
**[1:25]** there are a few techniques to try to automatically
**[1:29]** choose the number of
**[1:31]** clusters to use for a certain application.
**[1:34]** I'll briefly mention one here
**[1:36]** that you may see others refer to,
**[1:38]** although I had to say,
**[1:40]** I personally do not use this method myself.
**[1:44]** But one way to try to choose the value of K
**[1:48]** is called the elbow method and
**[1:52]** what that does is you would run
**[1:54]** K-means with a variety of values of
**[1:58]** K and plot the cost function or
**[2:01]** the distortion function J
**[2:03]** as a function of the number of clusters.
**[2:06]** What you find is that when you have
**[2:08]** very few clusters, say one cluster,
**[2:11]** the distortion function or the cost function J will be
**[2:14]** high and as you increase the number of clusters,
**[2:17]** it will go down, maybe as follows.
**[2:22]** and if the curve looks like this,
**[2:24]** you say, well, it looks
**[2:26]** like the cost function is decreasing
**[2:28]** rapidly until we get to three clusters
**[2:30]** but the decrease is more slowly after that.
**[2:33]** Let's choose K equals
**[2:35]** 3 and this is called an elbow, by the way,
**[2:38]** because think of it as analogous
**[2:41]** to that's your hand and that's your elbow over here.
**[2:47]** Plotting the cost function as
**[2:50]** a function of K could help,
**[2:51]** it could help you gain some insight.
**[2:53]** I personally hardly ever
**[2:56]** use the the elbow method myself to
**[2:58]** choose the right number of clusters
**[3:00]** because I think for a lot of applications,
**[3:02]** the right number of clusters is truly
**[3:04]** ambiguous and you find that a lot of
**[3:07]** cost functions look like this with
**[3:10]** just decreases smoothly and it
**[3:13]** doesn't have a clear elbow by wish you
**[3:16]** could use to pick the value of K. By the way,
**[3:19]** one technique that does not work is to choose
**[3:22]** K so as to minimize the cost function
**[3:25]** J because doing so
**[3:27]** would cause you to almost always just choose
**[3:30]** the largest possible value of K because having
**[3:33]** more clusters will pretty much
**[3:35]** always reduce the cost function J.
**[3:38]** Choosing K to minimize
**[3:40]** the cost function J is not a good technique.
**[3:43]** How do you choose the value of K and practice?
**[3:47]** Often you're running K-means in order to get clusters
**[3:51]** to use for some later or some downstream purpose.
**[3:54]** That is, you're going to take the clusters and do
**[3:57]** something with those clusters.
**[3:59]** What I usually do and what I recommend you
**[4:02]** do is to evaluate K-means
**[4:05]** based on how well it performs
**[4:07]** for that later downstream purpose.
**[4:11]** Let me illustrate to the example of t-shirt sizing.
**[4:15]** One thing you could do is run K-means
**[4:18]** on this data set to find the clusters,
**[4:20]** in which case you may find clusters
**[4:23]** like that and this would be how you size your small,
**[4:27]** medium, and large t-shirts,
**[4:29]** but how many t-shirt sizes should there be?
**[4:32]** Well, it's ambiguous.
**[4:34]** If you were to also run K-means with five clusters,
**[4:38]** you might get clusters that look like this.
**[4:43]** This will let shoe size
**[4:45]** t-shirts according to extra small,
**[4:47]** small, medium, large, and extra large.
**[4:51]** Both of these are completely valid
**[4:53]** and completely fine groupings
**[4:56]** of the data into clusters,
**[4:58]** but whether you want to use
**[5:00]** three clusters or five clusters can
**[5:03]** now be decided based on what makes
**[5:05]** sense for your t-shirt business.
**[5:08]** Does a trade-off between how well the t-shirts will fit,
**[5:11]** depending on whether you have three sizes or five sizes,
**[5:15]** but there will be extra costs as well associated with
**[5:19]** manufacturing and shipping five types of
**[5:22]** t-shirts instead of three different types of t-shirts.
**[5:25]** What I would do in this case is to run
**[5:27]** K-means with K equals 3 and K equals 5
**[5:31]** and then look at these two solutions to
**[5:35]** see based on the trade-off
**[5:37]** between fits of t-shirts with more sizes,
**[5:40]** results in better fit versus
**[5:42]** the extra cost of making more t-shirts where making
**[5:46]** fewer t-shirts is simpler and less expensive to
**[5:49]** try to decide what makes sense for the t-shirt business.
**[5:52]** When you get to the programming exercise,
**[5:55]** you also see there an application
**[5:58]** of K-means to image compression.
**[6:01]** This is actually one of the most fun visual examples
**[6:04]** of K-means and there
**[6:05]** you see that there'll be a trade-off
**[6:07]** between the quality of the compressed image,
**[6:11]** that is, how good the image looks
**[6:13]** versus how much you can compress the image
**[6:16]** to save the space.
**[6:18]** In that program exercise,
**[6:20]** you see that you can use
**[6:21]** that trade-off to maybe manually decide what's
**[6:25]** the best value of K
**[6:26]** based on how good do you want the image to
**[6:28]** look versus how large
**[6:31]** you want the compress image size to be.
**[6:33]** That's it for the K-means clustering algorithm.
**[6:37]** Congrats on learning
**[6:39]** your first unsupervised learning algorithm.
**[6:41]** You now know not just how to do supervised learning,
**[6:44]** but also unsupervised learning.
**[6:46]** I hope you also have fun with the practice lab,
**[6:50]** is actually one of the most fun exercises
**[6:52]** I know of the K-means.
**[6:54]** With that, we're ready to move on to
**[6:57]** our second unsupervised learning algorithm,
**[7:00]** which is anomaly detection.
**[7:03]** How do you look at the data set and find
**[7:05]** unusual or anomalous things in it.
**[7:08]** This turns out to be another,
**[7:10]** one of the most commercially important applications
**[7:12]** of unsupervised learning.
**[7:14]** I've used this myself many
**[7:15]** times in many different applications.
**[7:17]** Let's go on to the next video to
**[7:19]** talk about anomaly detection.
