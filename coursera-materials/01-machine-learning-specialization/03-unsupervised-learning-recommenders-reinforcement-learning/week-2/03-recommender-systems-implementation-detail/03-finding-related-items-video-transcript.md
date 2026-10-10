---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 2
section: Recommender systems implementation detail
item_title: Finding related items
duration: 7 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/pcdvC/finding-related-items
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Finding related items — Transcript

**[0:01]** If you come to an online shopping website
**[0:05]** and you're looking at a specific item,
**[0:07]** say maybe a specific book,
**[0:09]** the website may show you things like,
**[0:11]** "Here are some other books similar to this
**[0:13]** one" or if you're browsing a specific movie,
**[0:16]** it may say, "Here are
**[0:17]** some other movies similar to this one."
**[0:19]** How do the websites do that?,
**[0:21]** so that when you're looking at one item,
**[0:23]** it gives you other similar or related items to consider.
**[0:26]** It turns out the collaborative
**[0:28]** filtering algorithm that we've been talking
**[0:30]** about gives you a nice way to
**[0:32]** find related items. Let's take a look.
**[0:35]** As part of the collaborative filtering we've discussed,
**[0:39]** you learned features x^(i) for every item i,
**[0:42]** for every movie i or other type of
**[0:44]** item they're recommending to users.
**[0:47]** Whereas early this week,
**[0:48]** I had used a hypothetical example of the features
**[0:52]** representing how much a movie
**[0:54]** is a romance movie versus an action movie.
**[0:57]** In practice, when you use this algorithm to
**[0:59]** learn the features x^(i) automatically,
**[1:02]** looking at the individual features x_1,
**[1:05]** x_2, x_3,
**[1:07]** you find them to be quite hard to interpret.
**[1:10]** Is quite hard to learn features and say,
**[1:13]** x_1 is an action movie
**[1:15]** and x_2 is as a foreign film and so on.
**[1:19]** But nonetheless, these learned features,
**[1:22]** collectively x_1, x_2, x_3,
**[1:26]** other many features,
**[1:28]** and you have collectively these features
**[1:31]** do convey something about what that movie is like.
**[1:36]** It turns out that given features x^(i) of item i,
**[1:41]** if you want to find other items,
**[1:43]** say other movies related to movie i,
**[1:47]** then what you can do is try to find the item k with
**[1:51]** features x^(k) that is similar to x^(i).
**[1:58]** In particular, given a feature vector x^(k),
**[2:03]** the way we determine what are known as
**[2:05]** similar to the feature x^(i) is
**[2:07]** as follows: is the sum from l equals 1 through n with
**[2:11]** n features of x^(k)_l minus x^(i)_l square.
**[2:16]** This turns out to be the squared distance between
**[2:19]** x^(k) and x^(i) and in math,
**[2:23]** this squared distance between these two vectors,
**[2:28]** x^(k) and x^(i),
**[2:29]** is sometimes written as follows as well.
**[2:32]** If you find not just the one movie with
**[2:36]** the smallest distance between
**[2:38]** x^(k) and x^(i) but find say,
**[2:40]** the five or 10 items with
**[2:43]** the most similar feature vectors,
**[2:45]** then you end up finding
**[2:47]** five or 10 related items to the item x^(i).
**[2:51]** If you're building a website and want to help users find
**[2:54]** related products to
**[2:56]** a specific product they are looking at,
**[2:57]** this would be a nice way to do so because
**[3:01]** the features x^(i) give a sense of what item i is about,
**[3:07]** other items x^(k) with
**[3:08]** similar features will turn out to be similar to item i.
**[3:12]** It turns out later this week,
**[3:15]** this idea of finding
**[3:16]** related items will be a small building blocks that we'll
**[3:19]** use to get to
**[3:20]** an even more powerful recommended system as well.
**[3:24]** Before wrapping up this section,
**[3:26]** I want to mention
**[3:28]** a few limitations of collaborative filtering.
**[3:31]** In collaborative filtering, you
**[3:33]** have a set of items and so
**[3:35]** the users and the users have rated some subset of items.
**[3:39]** One of this weaknesses is that is
**[3:41]** not very good at the cold start problem.
**[3:44]** For example, if there's a new item in your catalog,
**[3:48]** say someone's just published a new movie
**[3:50]** and hardly anyone has rated that movie yet,
**[3:53]** how do you rank the new item
**[3:55]** if very few users have rated it before?
**[3:58]** Similarly, for new users
**[4:01]** that have rated only a few items,
**[4:04]** how can we make sure we show them something reasonable?
**[4:07]** We could see in an earlier video,
**[4:10]** how mean normalization can help
**[4:12]** with this and it does help a lot.
**[4:15]** But perhaps even better ways to
**[4:17]** show users that rated very few items,
**[4:20]** things that are likely to interest them.
**[4:22]** This is called the cold start problem,
**[4:26]** because when you have a new item,
**[4:28]** there are few users have rated,
**[4:30]** or we have a new user that's rated very few items,
**[4:35]** the results of collaborative filtering for that item
**[4:38]** or for that user may not be very accurate.
**[4:40]** The second limitation of
**[4:42]** collaborative filtering is it doesn't give you
**[4:44]** a natural way to use side information
**[4:47]** or additional information about items or users.
**[4:50]** For example, for a given movie in your catalog,
**[4:53]** you might know what is the genre of the movie,
**[4:56]** who had a movie stars,
**[4:57]** whether it is a studio,
**[4:59]** what is the budget, and so on.
**[5:01]** You may have a lot of features about a given movie.
**[5:04]** For a single user,
**[5:06]** you may know something about their demographics,
**[5:09]** such as their age, gender, location.
**[5:12]** They express preferences, such as if they tell
**[5:15]** you they like certain movies genres
**[5:17]** but not other movies genres,
**[5:19]** or it turns out if you know the user's IP address,
**[5:22]** that can tell you a lot about a user's location,
**[5:26]** and knowing the user's location might also help
**[5:29]** you guess what might the user be interested in,
**[5:32]** or if you know whether the user is accessing
**[5:35]** your site on a mobile or on a desktop,
**[5:39]** or if you know what web browser they're using.
**[5:41]** It turns out all of these are little cues you can get.
**[5:44]** They can be surprisingly
**[5:45]** correlated with the preferences of a user.
**[5:48]** It turns out by the way, that it is known that users,
**[5:51]** that use the Chrome versus Firefox versus
**[5:53]** Safari versus the Microsoft Edge browser,
**[5:56]** they actually behave in very different ways.
**[5:58]** Even knowing the user web browser can give you
**[6:01]** a hint when you have collected
**[6:03]** enough data of what this particular user may like.
**[6:06]** Even though collaborative filtering,
**[6:08]** we have multiple users give
**[6:10]** you ratings of multiple items,
**[6:12]** is a very powerful set of algorithms,
**[6:14]** it also has some limitations.
**[6:16]** In the next video,
**[6:18]** let's go on to
**[6:19]** develop content-based filtering algorithms,
**[6:21]** which can address a lot of these limitations.
**[6:24]** Content-based filtering algorithms are
**[6:26]** a state of the art technique used in
**[6:28]** many commercial applications today.
**[6:30]** Let's go take a look at how they work.
