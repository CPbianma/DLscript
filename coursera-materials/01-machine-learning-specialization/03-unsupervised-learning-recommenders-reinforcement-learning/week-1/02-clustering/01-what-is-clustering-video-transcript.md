---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 1
section: Clustering
item_title: What is clustering?
duration: 4 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/zoCuG/what-is-clustering
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# What is clustering? — Transcript

**[0:00]** What is clustering?
**[0:03]** A clustering algorithm looks at
**[0:05]** a number of data points and
**[0:07]** automatically finds data points that are
**[0:09]** related or similar to each other.
**[0:12]** Let's take a look at what that means.
**[0:14]** Let me contrast clustering,
**[0:17]** which is an unsupervised learning algorithm,
**[0:19]** with what you had previously seen with
**[0:22]** supervised learning for binary classification.
**[0:25]** Given a dataset like this with features x_1 and x_2.
**[0:32]** With supervised learning, we had a training set with both
**[0:36]** the input features x as well as the labels y.
**[0:41]** We could plot a dataset like this and fit, say,
**[0:44]** a logistic regression algorithm or
**[0:46]** a neural network to learn a decision boundary like that.
**[0:50]** In supervised learning, the dataset included
**[0:53]** both the inputs x as well as the target outputs y.
**[0:57]** In contrast, in unsupervised learning,
**[1:01]** you are given a dataset like this with just x,
**[1:05]** but not the labels or the target labels y.
**[1:08]** That's why when I plot a dataset,
**[1:11]** it looks like this,
**[1:12]** with just dots rather than two classes
**[1:15]** denoted by the x's and the o's.
**[1:19]** Because we don't have target labels y,
**[1:21]** we're not able to tell
**[1:23]** the algorithm what is the "right answer,
**[1:27]** y" that we wanted to predict.
**[1:29]** Instead, we're going to ask the algorithm to
**[1:32]** find something interesting about the data,
**[1:35]** that is to find some interesting
**[1:36]** structure about this data.
**[1:38]** But the first unsupervised learning algorithm
**[1:42]** that you learn about is called a clustering algorithm,
**[1:46]** which looks for one particular type
**[1:48]** of structure in the data.
**[1:50]** Namely, look at the dataset like this and try to
**[1:53]** see if it can be grouped into clusters,
**[1:57]** meaning groups of points that are similar to each other.
**[2:01]** A clustering algorithm, in this case,
**[2:04]** might find that this dataset
**[2:06]** comprises of data from two clusters shown here.
**[2:09]** Here are some applications of clustering.
**[2:12]** In the first week of the first course,
**[2:15]** you heard me talk about
**[2:17]** grouping similar news articles together,
**[2:20]** like the story about Pandas or market segmentation,
**[2:24]** where at deeplearning.ai,
**[2:26]** we discovered that there are many learners that come
**[2:30]** here because you may want to grow your skills,
**[2:33]** or develop your careers,
**[2:36]** or stay updated with
**[2:38]** AI and understand how it affects your field of work.
**[2:41]** We want to help everyone with any of
**[2:44]** these skills to learn about machine learning,
**[2:49]** or if you don't fall into one of these clusters,
**[2:51]** that's totally fine too.
**[2:53]** I hope deeplearning.ai and
**[2:56]** Stanford Online's materials will
**[2:57]** be useful to you as well.
**[2:59]** Clustering has also been used to analyze DNA data,
**[3:03]** where you will look at the genetic expression data from
**[3:08]** different individuals and try to group them
**[3:10]** into people that exhibit similar traits.
**[3:15]** I find astronomy and space exploration fascinating.
**[3:21]** One application that I thought was very
**[3:24]** exciting was astronomers using
**[3:27]** clustering for astronomical data analysis to
**[3:30]** group bodies in space together for
**[3:33]** their own analysis of what's going on in space.
**[3:37]** One of the applications I found
**[3:40]** fascinating was astronomers using
**[3:43]** clustering to group bodies together to figure out which
**[3:48]** ones form one galaxy or
**[3:51]** which one form coherent structures in space.
**[3:55]** Clustering today is used for all of
**[3:58]** these applications and many more.
**[4:02]** In the next video,
**[4:03]** let's take a look at
**[4:04]** the most commonly used clustering algorithm
**[4:07]** called the k-means algorithm,
**[4:09]** and let's take a look at how it works.
