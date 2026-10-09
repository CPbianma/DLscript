---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 2
section: Collaborative filtering
item_title: "Binary labels: favs, likes and clicks"
duration: 8 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/e6AxK/binary-labels-favs-likes-and-clicks
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Binary labels: favs, likes and clicks — Transcript

**[0:02]** Many important applications of recommender systems or
**[0:06]** collective filtering algorithms involved binary labels where instead of
**[0:11]** a user giving you a one to five star or zero to five star rating, they just
**[0:15]** somehow give you a sense of they like this item or they did not like this item.
**[0:20]** Let's take a look at how to generalize the algorithm you've seen to this setting.
**[0:25]** The process we'll use to generalize the algorithm will be very much reminiscent
**[0:30]** to how we have gone from linear regression to logistic regression, to predicting
**[0:35]** numbers to predicting a binary label back in course one, let's take a look.
**[0:39]** Here's an example of a collaborative filtering data set with binary labels.
**[0:45]** A one the notes that the user liked or engaged with a particular movie.
**[0:51]** So label one could mean that Alice watched the movie Love at last all the way to
**[0:56]** the end and watch romance forever all the way to the end.
**[1:00]** But after playing a few minutes of nonstop car chases decided to stop the video and
**[1:05]** move on.
**[1:06]** Or it could mean that she explicitly hit like or
**[1:09]** favorite on an app to indicate that she liked these movies.
**[1:14]** But after checking out nonstop car chasers and
**[1:16]** swords versus karate did not hit like.
**[1:18]** And the question mark usually means the user has not yet seen the item and so
**[1:23]** they weren't in a position to decide whether or not to hit like or
**[1:27]** favorite on that particular item.
**[1:29]** So the question is how can we take the collaborative filtering algorithm that you
**[1:34]** saw in the last video and get it to work on this dataset.
**[1:37]** And by predicting how likely Alice, Bob carol and
**[1:41]** Dave are to like the items that they have not yet rated,
**[1:45]** we can then decide how much we should recommend these items to them.
**[1:51]** There are many ways of defining what is the label one and what is the label zero,
**[1:56]** and what is the label question mark in collaborative filtering with binary
**[2:00]** labels.
**[2:01]** Let's take a look at a few examples.
**[2:03]** In an online shopping website, the label could denote whether or
**[2:08]** not user j chose to purchase an item after they were exposed to it,
**[2:13]** after they were shown the item.
**[2:16]** So one would denote that they purchase it zero would denote that they did
**[2:19]** not purchase it.
**[2:20]** And the question mark would denote that they were not even shown were not even
**[2:24]** exposed to the item.
**[2:25]** Or in a social media setting, the labels one or
**[2:28]** zero could denote did the user favorite or like an item after they were shown it.
**[2:34]** And question mark would be if they have not yet been shown the item or
**[2:39]** many sites instead of asking for explicit user rating will use
**[2:44]** the user behavior to try to guess if the user like the item.
**[2:48]** So for example, you can measure if a user spends at least 30 seconds of an item.
**[2:54]** And if they did, then assign that a label one because the user found the item
**[2:59]** engaging or if a user was shown an item but
**[3:02]** did not spend at least 30 seconds with it, then assign that a label zero.
**[3:07]** Or if the user was not shown the item yet, then assign it a question mark.
**[3:12]** Another way to generate a rating implicitly as a function
**[3:16]** of the user behavior will be to see that the user click on an item.
**[3:21]** This is often done in online advertising where if the user has been shown an ad,
**[3:25]** if they clicked on it assign it the label one,
**[3:28]** if they did not click assign it the label zero and the question mark were
**[3:33]** referred to if the user has not even been shown that ad in the first place.
**[3:37]** So often these binary labels will have a rough meaning as follows.
**[3:42]** A labor of one means that the user engaged after being shown an item And
**[3:47]** engaged could mean that they clicked or spend 30 seconds or
**[3:50]** explicitly favorite or like to purchase the item.
**[3:54]** A zero will reflect the user not engaging after being shown the item,
**[3:58]** the question mark will reflect the item not yet having been shown to the user.
**[4:03]** So given these binary labels,
**[4:05]** let's look at how we can generalize our algorithm which is a lot like linear
**[4:10]** regression from the previous couple videos to predicting these binary outputs.
**[4:16]** Previously we were predicting label yij as wj.xi+b.
**[4:22]** So this was a lot like a linear regression model.
**[4:25]** For binary labels, we're going to predict
**[4:31]** that the probability of yijb=1 is given by not wj.xi+b.
**[4:38]** But it said by g of this formula,
**[4:43]** where now g(z) 1/1 +e to the -z.
**[4:48]** So this is the logistic function just like we saw in logistic regression.
**[4:52]** And what we would do is take what was a lot like a linear regression model and
**[4:58]** turn it into something that would be a lot like a logistic regression
**[5:04]** model where will now predict the probability of yij being
**[5:09]** 1 that is of the user having engaged with or like the item using this model.
**[5:16]** In order to build this algorithm,
**[5:18]** we'll also have to modify the cost function from the squared error
**[5:24]** cost function to the cost function that is more appropriate for
**[5:29]** binary labels for a logistic regression like model.
**[5:34]** So previously, this was the cost function that we had where this term
**[5:38]** play their role similar to f(x), the prediction of the algorithm.
**[5:43]** When you now have binary labels,
**[5:47]** yij when the labels are one or zero or
**[5:51]** question mark, then the prediction f(x)
**[5:56]** becomes instead of wj.xi+b j it becomes g
**[6:01]** of this where g is the logistic function.
**[6:06]** And similar to when we had derived logistic regression,
**[6:10]** we had written out the following loss function for
**[6:14]** a single example which was at the loss if the algorithm predicts f(x) and
**[6:19]** the true label was y, the loss was this.
**[6:22]** It was -y log
**[6:26]** f-y log 1-f.
**[6:31]** This is also sometimes called the binary cross entropy cost function.
**[6:36]** But this is a standard cost function that we used for logistic regression as was for
**[6:40]** the binary classification problems when we're training neural networks.
**[6:45]** And so to adapt this to the collaborative filtering setting,
**[6:50]** let me write out the cost function which is now a function of all
**[6:55]** the parameters w and b as well as all the parameters x
**[6:59]** which are the features of the individual movies or items of.
**[7:04]** We now need to sum over all the pairs ij where riij=1 notice
**[7:11]** this is just similar to the summation up on top.
**[7:16]** And now instead of this squared error cost function,
**[7:20]** we're going to use that loss function.
**[7:22]** There's a function of f(x), yij.
**[7:28]** Where f(x) here?
**[7:30]** That's my abbreviation.
**[7:32]** My shorthand for g(w) j.x1+ej.
**[7:38]** As we plug this into here, then this gives you the cost function
**[7:43]** they could use for collaborative filtering on binary labels.
**[7:48]** So that's it.
**[7:49]** That's how you can take the linear regression,
**[7:52]** like collaborative filtering algorithm and generalize it to work with binary labels.
**[7:57]** And this actually very significantly opens up the set of applications you can address
**[8:02]** with this algorithm.
**[8:04]** Now, even though you've seen the key structure and
**[8:07]** cost function of the algorithm, there are also some implementation,
**[8:12]** all tips that will make your algorithm work much better.
**[8:15]** Let's go on to the next video to take a look at some details of how you implement
**[8:20]** it and some little modifications that make the algorithm run much faster.
**[8:25]** Let's go on to the next video.
