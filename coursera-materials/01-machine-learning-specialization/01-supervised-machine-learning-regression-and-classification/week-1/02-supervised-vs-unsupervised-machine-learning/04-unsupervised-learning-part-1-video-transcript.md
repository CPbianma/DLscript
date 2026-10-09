---
type: video-transcript
specialization: Machine Learning Specialization
course: Supervised Machine Learning: Regression and Classification
week: 1
section: Supervised vs. Unsupervised Machine Learning
item_title: Unsupervised learning part 1
duration: 9 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/TxO6F/unsupervised-learning-part-1
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Unsupervised learning part 1 — Transcript

**[0:02]** After supervised learning,
**[0:03]** the most widely used form of machine learning is unsupervised learning.
**[0:08]** Let's take a look at what that means, we've talked about supervised learning and
**[0:13]** this video is about unsupervised learning.
**[0:16]** But don't let the name uncivilized for you,
**[0:19]** unsupervised learning is I think just as super as supervised learning.
**[0:24]** When we're looking at supervised learning in the last video recalled,
**[0:28]** it looks something like this in the case of a classification problem.
**[0:32]** Each example, was associated with an output label y such as benign or
**[0:37]** malignant, designated by the poles and crosses in unsupervised learning.
**[0:43]** Were given data that isn't associated with any output labels y,
**[0:48]** say you're given data on patients and their tumor size and the patient's age.
**[0:55]** But not whether the tumor was benign or malignant, so
**[0:59]** the dataset looks like this on the right.
**[1:03]** We're not asked to diagnose whether the tumor is benign or
**[1:07]** malignant, because we're not given any labels.
**[1:11]** Why in the dataset, instead, our job is to find some structure or
**[1:16]** some pattern or just find something interesting in the data.
**[1:20]** This is unsupervised learning,
**[1:22]** we call it unsupervised because we're not trying to supervise the algorithm.
**[1:27]** To give some quote right answer for every input, instead,
**[1:32]** we asked the our room to figure out all by yourself what's interesting.
**[1:37]** Or what patterns or structures that might be in this data,
**[1:41]** with this particular data set.
**[1:43]** An unsupervised learning algorithm, might decide that
**[1:47]** the data can be assigned to two different groups or two different clusters.
**[1:51]** And so it might decide, that there's one cluster what group over here,
**[1:58]** and there's another cluster or group over here.
**[2:03]** This is a particular type of unsupervised learning, called a clustering algorithm.
**[2:08]** Because it places the unlabeled data, into different clusters and
**[2:13]** this turns out to be used in many applications.
**[2:17]** For example, clustering is used in google news,
**[2:21]** what google news does is every day it goes.
**[2:25]** And looks at hundreds of thousands of news articles on the internet, and
**[2:29]** groups related stories together.
**[2:31]** For example, here is a sample from Google News, where the headline of the top
**[2:36]** article, is giant panda gives birth to rear twin cubs at Japan's oldest zoo.
**[2:41]** This article has actually caught my eye, because my daughter loves pandas and so
**[2:46]** there are a lot of stuff panda toys.
**[2:48]** And watching panda videos in my house, and looking at this,
**[2:54]** you might notice that below this are other related articles.
**[2:59]** Maybe from the headlines alone,
**[3:01]** you can start to guess what clustering might be doing.
**[3:05]** Notice that the word panda appears here here,
**[3:11]** here, here and here and notice that the word
**[3:16]** twin also appears in all five articles.
**[3:21]** And the word Zoo also appears in all of these articles, so
**[3:25]** the clustering algorithm is finding articles.
**[3:29]** All of all the hundreds of thousands of news articles on the internet that day,
**[3:34]** finding the articles that mention similar words and grouping them into clusters.
**[3:39]** Now, what's cool is that this clustering algorithm figures out on his own which
**[3:43]** words suggest, that certain articles are in the same group.
**[3:47]** What I mean is there isn't an employee at google news who's telling the algorithm to
**[3:52]** find articles that the word panda.
**[3:54]** And twins and zoo to put them into the same cluster,
**[3:57]** the news topics change every day.
**[3:59]** And there are so many news stories, it just isn't feasible to people
**[4:04]** doing this every single day for all the topics that use covers.
**[4:08]** Instead the algorithm has to figure out on his own without supervision,
**[4:14]** what are the clusters of news articles today.
**[4:17]** So that's why this clustering algorithm,
**[4:20]** is a type of unsupervised learning algorithm.
**[4:23]** Let's look at the second example of unsupervised learning
**[4:28]** applied to clustering genetic or DNA data.
**[4:31]** This image shows a picture of DNA micro array data,
**[4:35]** these look like tiny grids of a spreadsheet.
**[4:38]** And each tiny column represents the genetic or DNA activity of one person,
**[4:44]** So for example, this entire Column here is from one person's DNA.
**[4:50]** And this other column is of another person,
**[4:54]** each row represents a particular gene.
**[4:57]** So just as an example, perhaps this role here might represent a gene that
**[5:03]** affects eye color, or this role here is a gene that affects how tall someone is.
**[5:09]** Researchers have even found a genetic link to whether someone dislikes certain
**[5:14]** vegetables, such as broccoli, or brussels sprouts, or asparagus.
**[5:19]** So next time someone asks you why didn't you finish your salad,
**[5:23]** you can tell them, maybe it's genetic for DNA micro race.
**[5:28]** The idea is to measure how much certain genes, are expressed for
**[5:32]** each individual person.
**[5:33]** So these colors red, green, gray, and so on, show the degree to
**[5:38]** which different individuals do, or do not have a specific gene active.
**[5:44]** And what you can do is then run a clustering algorithm to group
**[5:48]** individuals into different categories.
**[5:51]** Or different types of people like maybe these individuals that group together,
**[5:57]** and let's just call this type one.
**[6:00]** And these people are grouped into type two,
**[6:04]** and these people are groups as type three.
**[6:08]** This is unsupervised learning, because we're not telling the algorithm in
**[6:12]** advance, that there is a type one person with certain characteristics.
**[6:16]** Or a type two person with certain characteristics,
**[6:18]** instead what we're saying is here's a bunch of data.
**[6:21]** I don't know what the different types of people are but
**[6:25]** can you automatically find structure into data.
**[6:28]** And automatically figure out whether the major types of individuals,
**[6:32]** since we're not giving the algorithm the right answer for the examples in advance.
**[6:36]** This is unsupervised learning, here's the third example,
**[6:41]** many companies have huge databases of customer information given this data.
**[6:47]** Can you automatically group your customers,
**[6:50]** into different market segments so that you can more efficiently serve your customers.
**[6:56]** Concretely the deep learning dot AI team did some research to better understand
**[7:00]** the deep learning dot AI community.
**[7:02]** And why different individuals take these classes,
**[7:06]** subscribed to the batch weekly newsletter, or attend our AI events.
**[7:11]** Let's visualize the deep learning dot AI community,
**[7:15]** as this collection of people running clustering.
**[7:18]** That is market segmentation found a few distinct groups of individuals,
**[7:24]** one group's primary motivation is seeking knowledge to grow their skills.
**[7:30]** Perhaps this is you, and so that's great,
**[7:32]** a second group's primary motivation is looking for a way to develop their career.
**[7:38]** Maybe you want to get a promotion or a new job, or
**[7:40]** make some career progression if this describes you, that's great too.
**[7:45]** And yet another group wants to stay updated on how AI impacts their
**[7:49]** field of work, perhaps this is you, that's great too.
**[7:54]** This is a clustering that our team used to try to better serve our community
**[7:59]** as we're trying to figure out.
**[8:01]** Whether the major categories of learners in the deeper and community, So
**[8:05]** if any of these is your top motivation for learning, that's great.
**[8:10]** And I hope I'll be able to help you on your journey, or in case this is you, and
**[8:15]** you want something totally different than the other three categories.
**[8:19]** That's fine too, and I want you to know, I love you all the same, so
**[8:24]** to summarize a clustering algorithm.
**[8:26]** Which is a type of unsupervised learning algorithm,
**[8:30]** takes data without labels and tries to automatically group them into clusters.
**[8:35]** And so maybe the next time you see or think of a panda,
**[8:39]** maybe you think of clustering as well.
**[8:42]** And besides clustering, there are other types of unsupervised learning as well.
**[8:47]** Let's go on to the next video,
**[8:48]** to take a look at some other types of unsupervised learning algorithms.
