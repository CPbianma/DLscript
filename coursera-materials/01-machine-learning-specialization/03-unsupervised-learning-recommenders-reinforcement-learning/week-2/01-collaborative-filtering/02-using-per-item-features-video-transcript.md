---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 2
section: Collaborative filtering
item_title: Using per-item features
duration: 11 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/D3lIC/using-per-item-features
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Using per-item features — Transcript

**[0:01]** So let's take a look at how we can develop a recommender system if we had
**[0:06]** features of each item, or features of each movie.
**[0:10]** So here's the same data set that we had previously with the four users
**[0:15]** having rated some but not all of the five movies.
**[0:18]** What if we additionally have features of the movies?
**[0:22]** So here I've added two features X1 and X2, that tell us how much
**[0:27]** each of these is a romance movie, and how much each of these is an action movie.
**[0:33]** So for example Love at Last is a very romantic movie, so
**[0:37]** this feature takes on 0.9, but it's not at all an action movie.
**[0:42]** So this feature takes on 0.
**[0:45]** But it turns out Nonstop Car chases has just a little bit of romance in it.
**[0:50]** So it's 0.1, but it has a ton of action.
**[0:54]** So that feature takes on the value of 1.0.
**[0:57]** So you recall that I had used the notation nu to denote the number of users,
**[1:04]** which is 4 and m to denote the number of movies which is 5.
**[1:09]** I'm going to also introduce n to denote the number of features we have here.
**[1:14]** And so n=2, because we have two features X1 and X2 for each movie.
**[1:19]** With these features we have for example that the features for
**[1:25]** movie one, that is the movie Love at Last, would be 0.90.
**[1:31]** And the features for the third movie
**[1:35]** Cute Puppies of Love would be 0.99 and 0.
**[1:40]** And let's start by taking a look at how we might make predictions for
**[1:46]** Alice's movie ratings.
**[1:48]** So for user one, that is Alice,
**[1:52]** let's say we predict the rating for
**[1:57]** movie i as w.X(i)+b.
**[2:01]** So this is just a lot like linear regression.
**[2:05]** For example if we end up choosing the parameter w(1)=[5,0] and
**[2:12]** say b(1)=0, then the prediction for
**[2:16]** movie three where the features are 0.99 and 0,
**[2:22]** which is just copied from here, first feature 0.99, second feature 0.
**[2:28]** Our prediction would be w.X(3)+b=0.99
**[2:35]** times 5 plus 0 times zero,
**[2:38]** which turns out to be equal to 4.95.
**[2:44]** And this rating seems pretty plausible.
**[2:46]** It looks like Alice has given high ratings to Love at Last and Romance Forever,
**[2:51]** to two highly romantic movies, but given low ratings to the action movies,
**[2:57]** Nonstop Car Chases and Swords vs Karate.
**[2:59]** So if we look at Cute Puppies of Love,
**[3:02]** well predicting that she might rate that 4.95 seems quite plausible.
**[3:08]** And so these parameters w and b for
**[3:10]** Alice seems like a reasonable model for predicting her movie ratings.
**[3:16]** Just add a little the notation because we have not just one user but
**[3:21]** multiple users, or really nu equals 4 users.
**[3:24]** I'm going to add a superscript 1 here to denote that this is the parameter w(1) for
**[3:31]** user 1 and add a superscript 1 there as well.
**[3:35]** And similarly here and here as well, so that we would actually have
**[3:41]** different parameters for each of the 4 users on data set.
**[3:46]** And more generally in this model we can for user j,
**[3:51]** not just user 1 now, we can predict user j's rating for
**[3:58]** movie i as w(j).X(i)+b(j).
**[4:02]** So here the parameters w(j) and
**[4:05]** b(j) are the parameters used to predict user j's rating for
**[4:10]** movie i which is a function of X(i), which is the features of movie i.
**[4:16]** And this is a lot like linear regression, except that we're fitting a different
**[4:21]** linear regression model for each of the 4 users in the dataset.
**[4:25]** So let's take a look at how we can formulate the cost function for
**[4:30]** this algorithm.
**[4:31]** As a reminder, our notation is that r(i.,j)=1
**[4:37]** if user j has rated movie i or 0 otherwise.
**[4:41]** And y(i,j)=rating given by user j on movie i.
**[4:46]** And on the previous side we defined w(j), b(j) as the parameters for user j.
**[4:51]** And X(i) as the feature vector for movie i.
**[4:56]** So the model we have is for user j and
**[5:00]** movie i predict the rating to be w(j).X(i)+b(j).
**[5:06]** I'm going to introduce just one new piece of notation,
**[5:10]** which is I'm going to use m(j) to denote the number of movies rated by user j.
**[5:16]** So if the user has rated 4 movies, then m(j) would be equal to 4.
**[5:21]** And if the user has rated 3 movies then m(j) would be equal to 3.
**[5:25]** So what we'd like to do is to learn the parameters w(j) and
**[5:31]** b(j), given the data that we have.
**[5:35]** That is given the ratings a user has given of a set of movies.
**[5:40]** So the algorithm we're going to use is very similar to linear regression.
**[5:46]** So let's write out the cost function for learning the parameters w(j) and
**[5:51]** b(j) for a given user j.
**[5:52]** And let's just focus on one user on user j for now.
**[5:56]** I'm going to use the mean squared error criteria.
**[6:01]** So the cost will be the prediction, which is w(j).X(i)+b(j)
**[6:08]** minus the actual rating that the user had given.
**[6:13]** So minus y(i,j) squared.
**[6:17]** And we're trying to choose parameters w and
**[6:21]** b to minimize the squared error between the predicted rating and
**[6:26]** the actual rating that was observed.
**[6:30]** But the user hasn't rated all the movies, so
**[6:35]** if we're going to sum over this, we're going to
**[6:40]** sum over only over the values of i where r(i,j)=1.
**[6:46]** So we're going to sum only over the movies i that user j has actually rated.
**[6:53]** So that's what this denotes, sum of all values of i where r(i,j)=1.
**[6:59]** Meaning that user j has rated that movie i.
**[7:03]** And then finally we can take the usual normalization 1 over m(j).
**[7:11]** And this is very much like the cost function we have for
**[7:15]** linear regression with m or really m(j) training examples.
**[7:19]** Where you're summing over the m(j) movies for which you have a rating taking
**[7:24]** a squared error and the normalizing by this 1 over 2m(j).
**[7:28]** And this is going to be a cost
**[7:32]** function J of w(j), b(j).
**[7:38]** And if we minimize this as a function of w(j) and b(j),
**[7:42]** then you should come up with a pretty good choice of parameters w(i) and b(j).
**[7:48]** For making predictions for user j's ratings.
**[7:51]** Let me have just one more term to this cost function,
**[7:54]** which is the regularization term to prevent overfitting.
**[7:57]** And so here's our usual regularization parameter,
**[8:03]** lambda divided by 2m(j) and
**[8:06]** then times as sum of the squared values of the parameters w.
**[8:12]** And so n is a number of numbers in X(i) and
**[8:16]** that's the same as a number of numbers in w(j).
**[8:20]** If you were to minimize this cost function J as a function of w and
**[8:25]** b, you should get a pretty good set of parameters for
**[8:29]** predicting user j's ratings for other movies.
**[8:33]** Now, before moving on, it turns out that for recommender systems it would
**[8:39]** be convenient to actually eliminate this division by m(j) term,
**[8:44]** m(j) is just a constant in this expression.
**[8:48]** And so, even if you take it out,
**[8:50]** you should end up with the same value of w and b.
**[8:53]** Now let me take this cost function down here to the bottom and
**[8:58]** copy it to the next slide.
**[9:00]** So we have that to learn the parameters w(j), b(j) for user j.
**[9:04]** We would minimize this cost function as a function of w(j) and b(j).
**[9:11]** But instead of focusing on a single user,
**[9:14]** let's look at how we learn the parameters for all of the users.
**[9:19]** To learn the parameters w(1), b(1), w(2),
**[9:21]** b(2),...,w(nu), b(nu),
**[9:23]** we would take this cost function on top and sum it over all the nu users.
**[9:30]** So we would have sum from j=1 one to nu of the same
**[9:37]** cost function that we had written up above.
**[9:44]** And this becomes the cost for
**[9:47]** learning all the parameters for all of the users.
**[9:53]** And if we use gradient descent or
**[9:55]** any other optimization algorithm to minimize this as a function of w(1),
**[10:00]** b(1) all the way through w(nu), b(nu), then you have a pretty
**[10:05]** good set of parameters for predicting movie ratings for all the users.
**[10:10]** And you may notice that this algorithm is a lot like linear regression,
**[10:16]** where that plays a role similar to the output f(x) of linear regression.
**[10:22]** Only now we're training a different linear regression model for each of the nu users.
**[10:30]** So that's how you can learn parameters and predict movie ratings,
**[10:35]** if you had access to these features X1 and X2.
**[10:39]** That tell you how much is each of the movies, a romance movie, and
**[10:43]** how much is each of the movies an action movie?
**[10:46]** But where do these features come from?
**[10:48]** And what if you don't have access to such features that give you enough detail
**[10:53]** about the movies with which to make these predictions?
**[10:56]** In the next video, we'll look at the modification of this algorithm.
**[11:00]** They'll let you make predictions that you make recommendations.
**[11:04]** Even if you don't have, in advance, features that describe the items of
**[11:09]** the movies in sufficient detail to run the algorithm that we just saw.
**[11:13]** Let's go on and take a look at that in the next video
