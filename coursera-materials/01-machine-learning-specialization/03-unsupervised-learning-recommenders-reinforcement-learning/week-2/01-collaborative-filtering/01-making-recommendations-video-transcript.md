---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 2
section: Collaborative filtering
item_title: Making recommendations
duration: 6 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/cOHyS/making-recommendations
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Making recommendations — Transcript

**[0:02]** Welcome to this second to last week of the machine learning specialization.
**[0:06]** I'm really happy that together, almost all the way to the finish line.
**[0:11]** What we'll do this week is discuss recommended systems.
**[0:14]** This is one of the topics that has received quite a bit of attention
**[0:18]** in academia.
**[0:19]** But the commercial impact and
**[0:21]** the actual number of practical use cases of recommended systems seems to me to be
**[0:26]** even vastly greater than the amount of attention it has received in academia.
**[0:32]** Every time you go to an online shopping website like Amazon or
**[0:36]** a movie streaming sites like Netflix or go to one of the apps or
**[0:41]** sites that do food delivery.
**[0:43]** Many of these sites will recommend things to you that they think you may want to buy
**[0:48]** or movies they think you may want to watch or
**[0:50]** restaurants that they think you may want to try out.
**[0:53]** And for many companies,
**[0:54]** a large fraction of sales is driven by their recommended systems.
**[0:59]** So today for many companies, the economics or the value driven by recommended systems
**[1:05]** is very large and so what we're doing this week is take a look at how they work.
**[1:10]** So with that let's dive in and take a look at what is a recommended system.
**[1:14]** I'm going to use as a running example, the application of predicting movie ratings.
**[1:20]** So say you run a large movie streaming website and
**[1:24]** your users have rated movies using one to five stars.
**[1:29]** And so in a typical recommended system you have a set of users,
**[1:33]** here we have four users Alice, Bob Carol and Dave.
**[1:36]** Which have numbered users 1,2,3,4.
**[1:39]** As well as a set of movies Love at last, Romance forever,
**[1:43]** Cute puppies of love and then Nonstop car chases and Sword versus karate.
**[1:48]** And what the users have done is rated these movies one to five stars.
**[1:53]** Or in fact to make some of these examples a little bit easier.
**[1:57]** I'm not going to let them rate the movies from zero to five stars.
**[2:01]** So say Alice has rated Love and last five stars, Romance forever five stars.
**[2:06]** Maybe she has not yet watched cute puppies of love so
**[2:08]** you don't have a rating for that.
**[2:10]** And I'm going to denote that via a question mark and
**[2:13]** she thinks nonstop car chases and sword versus karate deserve zero stars bob.
**[2:20]** Race at five stars has not watched that, so
**[2:23]** you don't have a rating race at four stars, 0,0.
**[2:27]** Carol on the other hand, thinks that deserve zero stars has not
**[2:31]** watched that zero stars and she loves nonstop car chases and
**[2:35]** swords versus karate and Dave rates the movies as follows.
**[2:40]** In the typical recommended system,
**[2:44]** you have some number of users as well as some number of items.
**[2:49]** In this case the items are movies that you want to recommend to the users.
**[2:55]** And even though I'm using movies in this example, the same logic or the same thing
**[3:00]** works for recommending anything from products or websites to my self, to restaurants,
**[3:04]** to even which media articles, the social media articles to show,
**[3:08]** to the user that may be more interesting for them.
**[3:11]** The notation I'm going to use is I'm going to use nu to denote the number of users.
**[3:18]** So in this example nu is equal to four because you have four users and
**[3:23]** nm to denote the number of movies or really the number of items.
**[3:28]** So in this example nm is equal to five because we have five movies.
**[3:33]** I'm going to set r(i,j)=1,
**[3:38]** if user j has rated movie i.
**[3:42]** So for example, use a one Dallas Alice has rated movie one but
**[3:48]** has not rated movie three and so r(1,1) =1,
**[3:53]** because she has rated movie one, but
**[3:57]** r( 3,1)=0 because she has not rated movie number three.
**[4:04]** Then finally I'm going to use y(i,j).
**[4:05]** J to denote the rating given by user j to movie i.
**[4:10]** So for example,
**[4:11]** this rating here would be that movie three was rated by user 2 to be equal to four.
**[4:19]** Notice that not every user rates every movie and it's important for
**[4:23]** the system to know which users have rated which movies.
**[4:26]** That's why we're going to define r(i,j)=1 if user j has rated movie i and
**[4:33]** will be equal to zero if user j has not rated movie i.
**[4:37]** So with this framework for recommended systems one possible way to approach
**[4:42]** the problem is to look at the movies that users have not rated.
**[4:46]** And to try to predict how users would rate those movies because then we can try
**[4:52]** to recommend to users things that they are more likely to rate as five stars.
**[4:57]** And in the next video we'll start to develop an algorithm for
**[5:01]** doing exactly that.
**[5:02]** But making one very special assumption.
**[5:04]** Which is we're going to assume temporarily that we have access to features or
**[5:09]** extra information about the movies such as which movies are romance movies,
**[5:14]** which movies are action movies.
**[5:16]** And using that will start to develop an algorithm.
**[5:20]** But later this week will actually come back and ask what if we don't have these
**[5:24]** features, how can you still get the algorithm to work then?
**[5:28]** But let's go on to the next video to start building up this algorithm.
