---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 2
section: Collaborative filtering
item_title: Collaborative filtering algorithm
duration: 14 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/ppY77/collaborative-filtering-algorithm
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Collaborative filtering algorithm — Transcript

**[0:01]** In the last video, you saw how
**[0:04]** if you have features for each movie,
**[0:06]** such as features x_1 and x_2 that tell you how much is
**[0:09]** this a romance movie and how
**[0:11]** much is this an action movie.
**[0:13]** Then you can use basically linear regression
**[0:16]** to learn to predict movie ratings.
**[0:18]** But what if you don't have those features, x_1 and x_2?
**[0:21]** Let's take a look at how you can learn or come up
**[0:24]** with those features x_1 and x_2 from the data.
**[0:28]** Here's the data that we had before.
**[0:31]** But what if instead of
**[0:33]** having these numbers for x_1 and x_2,
**[0:36]** we didn't know in advance what
**[0:38]** the values of the features x_1 and x_2 were?
**[0:40]** I'm going to replace them with question marks over here.
**[0:44]** Now, just for the purposes of illustration,
**[0:48]** let's say we had somehow already
**[0:50]** learned parameters for the four users.
**[0:53]** Let's say that we learned parameters w^1
**[0:56]** equals 5 and 0 and b^1 equals 0, for user one.
**[1:01]** W^2 is also 5, 0 b^2, 0.
**[1:06]** W^3 is 0,
**[1:10]** 5 b^3 is 0,
**[1:11]** and for user four W^4 is also 0,
**[1:15]** 5 and b^4 0, 0.
**[1:18]** We'll worry later about how we might have
**[1:20]** come up with these parameters, w and b.
**[1:23]** But let's say we have them already.
**[1:26]** As a reminder, to predict user j's rating on movie i,
**[1:32]** we're going to use w^j dot product,
**[1:36]** the features of x_i plus b^j.
**[1:41]** To simplify this example,
**[1:43]** all the values of b are actually equal to 0.
**[1:46]** Just to reduce a little bit of writing,
**[1:48]** I'm going to ignore b for the rest of this example.
**[1:51]** Let's take a look at how we can try to guess
**[1:54]** what might be reasonable features for movie one.
**[1:58]** If these are the parameters you have on the left,
**[2:01]** then given that Alice rated movie one, 5,
**[2:05]** we should have that w^1.x^1 should be about equal to
**[2:11]** 5 and w^2.x^2 should
**[2:15]** also be about equal to 5 because Bob rated it 5.
**[2:20]** W^3.x^1 should be close to 0
**[2:24]** and w^4.x^1 should be close to 0 as well.
**[2:28]** The question is, given
**[2:30]** these values for w that we have up here,
**[2:34]** what choice for x_1 will cause these values to be right?
**[2:44]** Well, one possible choice would be if
**[2:46]** the features for that first movie,
**[2:48]** were 1, 0 in which case,
**[2:52]** w^1.x^1 will be equal to 5,
**[2:56]** w^2.x^1 will be equal to 5 and similarly,
**[3:01]** w^3 or w^4 dot product with
**[3:04]** this feature vector x_1 would be equal to 0.
**[3:07]** What we have is that if you
**[3:09]** have the parameters for all four users here,
**[3:12]** and if you have four ratings
**[3:15]** in this example that you want to try to match,
**[3:17]** you can take a reasonable guess at what lists a feature
**[3:21]** vector x_1 for movie one that
**[3:25]** would make good predictions
**[3:27]** for these four ratings up on top.
**[3:29]** Similarly, if you have these parameter vectors,
**[3:34]** you can also try to come up with
**[3:36]** a feature vector x_2 for the second movie,
**[3:40]** feature vector x_3 for the third movie,
**[3:43]** and so on to try to make the algorithm's predictions on
**[3:49]** these additional movies close
**[3:53]** to what was actually the ratings given by the users.
**[3:56]** Let's come up with a cost function for actually
**[4:00]** learning the values of x_1 and x_2.
**[4:04]** By the way, notice that this works only
**[4:08]** because we have parameters for four users.
**[4:11]** That's what allows us to try
**[4:13]** to guess appropriate features, x_1.
**[4:16]** This is why in a typical linear regression application
**[4:19]** if you had just a single user,
**[4:21]** you don't actually have
**[4:22]** enough information to figure
**[4:24]** out what would be the features,
**[4:25]** x_1 and x_2, which is why in
**[4:28]** the linear regression contexts that you saw in course 1,
**[4:31]** you can't come up with features x_1 and x_2 from scratch.
**[4:36]** But in collaborative filtering,
**[4:38]** is because you have ratings from
**[4:40]** multiple users of the same item with the same movie.
**[4:44]** That's what makes it possible to try to
**[4:46]** guess what are possible values for these features.
**[4:49]** Given w^1, b^1, w^2, b^2,
**[4:52]** and so on through w^n_u and b^n_u,
**[4:56]** for the n subscript u users.
**[4:59]** If you want to learn
**[5:01]** the features x^i for a specific movie,
**[5:03]** i is a cost function we could use which is that.
**[5:08]** I'm going to want to minimize squared error as usual.
**[5:14]** If the predicted rating by
**[5:17]** user j on movie i is given by this,
**[5:21]** let's take the squared difference
**[5:25]** from the actual movie rating y,i,j.
**[5:28]** As before, let's sum over all the users j.
**[5:35]** But this will be a sum over
**[5:36]** all values of j, where r, i,
**[5:38]** j is equal to I. I'll add a 1.5 there as usual.
**[5:44]** As I defined this as a cost function for x^i.
**[5:49]** Then if we minimize this as a function of x^i
**[5:53]** you be choosing the features for movie i.
**[5:58]** So therefore all the users J that have rated movie i,
**[6:02]** we will try to minimize the squared difference between
**[6:07]** what your choice of features x^i results in terms of
**[6:11]** the predicted movie rating minus
**[6:13]** the actual movie rating that the user had given it.
**[6:16]** Then finally, if we want to add a regularization term,
**[6:20]** we add the usual plus Lambda over 2,
**[6:23]** K equals 1 through n,
**[6:25]** where n as usual is the number of
**[6:26]** features of x^i squared.
**[6:30]** Lastly, to learn all the features
**[6:34]** x1 through x^n_m because we have n_m movies,
**[6:39]** we can take this cost function on
**[6:41]** top and sum it over all the movies.
**[6:44]** Sum from i equals 1 through
**[6:47]** the number of movies and then just take
**[6:50]** this term from above and this becomes
**[6:55]** a cost function for learning
**[6:57]** the features for all of the movies in the dataset.
**[7:02]** So if you have parameters w and b, all the users,
**[7:07]** then minimizing this cost function as a function
**[7:11]** of x1 through x^n_m
**[7:14]** using gradient descent or some other algorithm,
**[7:16]** this will actually allow you to take a pretty good guess
**[7:19]** at learning good features for the movies.
**[7:22]** This is pretty remarkable
**[7:24]** for most machine learning applications
**[7:27]** the features had to be
**[7:28]** externally given but in this algorithm,
**[7:32]** we can actually learn the features for a given movie.
**[7:35]** But what we've done so far in this video,
**[7:38]** we assumed you had
**[7:39]** those parameters w and b for the different users.
**[7:42]** Where do you get those parameters from?
**[7:44]** Well, let's put together the algorithm from
**[7:46]** the last video for learning w and b and what we
**[7:49]** just talked about in this video for learning x and
**[7:53]** that will give us our collaborative filtering algorithm.
**[7:57]** Here's the cost function for learning the features.
**[8:01]** This is what we had derived on the last slide.
**[8:04]** Now, it turns out that if we put these two together,
**[8:09]** this term here is exactly the same as this term here.
**[8:14]** Notice that sum over j of all values
**[8:17]** of i is that r,i,j equals 1 is the
**[8:20]** same as summing over all values of
**[8:23]** i with all j where r,i,j is equal to 1.
**[8:27]** This summation is just summing over
**[8:30]** all user movie pairs where there is a rating.
**[8:34]** What I'm going to do is put
**[8:36]** these two cost functions together and have
**[8:40]** this where I'm just writing out the summation more
**[8:44]** explicitly as summing over all pairs i and j,
**[8:49]** where we do have a rating
**[8:52]** of the usual squared cost function and then let
**[8:55]** me take the regularization term
**[8:57]** from learning the parameters w and b,
**[9:02]** and put that here and take
**[9:04]** the regularization term from
**[9:06]** learning the features x and put them
**[9:09]** here and this ends up being
**[9:11]** our overall cost function for learning w, b, and x.
**[9:18]** It turns out that if you minimize
**[9:20]** this cost function as a function of w and b as well as x,
**[9:25]** then this algorithm actually works.
**[9:27]** Here's what I mean. If we had three users and
**[9:32]** two movies and if you have ratings for these four movies,
**[9:37]** but not those two, over here does,
**[9:40]** is it sums over all the users.
**[9:42]** For user 1 has determined the cost function for this,
**[9:46]** for user 2 has determined the cost function for this,
**[9:48]** for user 3 has determined the cost function for this.
**[9:51]** We're summing over users first and
**[9:55]** then having one term for
**[9:57]** each movie where there is a rating.
**[10:00]** But an alternative way to carry out the summation
**[10:02]** is to first look at movie 1,
**[10:05]** that's what this summation here does,
**[10:07]** and then to include all the users that rated movie 1,
**[10:11]** and then look at movie 2 and have a term
**[10:15]** for all the users that had rated movie 2.
**[10:19]** You see that in both cases we're just summing over
**[10:22]** these four areas where
**[10:25]** the user had rated the corresponding movie.
**[10:28]** That's why this summation
**[10:30]** on top and this summation here are
**[10:32]** the two ways of summing over
**[10:34]** all of the pairs where the user had rated that movie.
**[10:38]** How do you minimize this cost function
**[10:40]** as a function of w, b, and x?
**[10:43]** One thing you could do is to use gradient descent.
**[10:48]** In course 1 when we learned about linear regression,
**[10:52]** this is the gradient descent algorithm you had seen,
**[10:56]** where we had the cost function J,
**[10:57]** which is a function of the parameters w and b,
**[11:00]** and we'd apply gradient descent as follows.
**[11:02]** With collaborative filtering, the cost function is in
**[11:06]** a function of just w and b is now a function of w,
**[11:11]** b, and x. I'm using
**[11:14]** w and b here to denote the parameters for all
**[11:16]** of the users and x here just
**[11:18]** informally to denote the features of all of the movies.
**[11:21]** But if you're able to take
**[11:23]** partial derivatives with respect
**[11:25]** to the different parameters,
**[11:27]** you can then continue to update
**[11:29]** the parameters as follows.
**[11:31]** But now we need to optimize
**[11:33]** this with respect to x as well.
**[11:35]** We also will want to update each of
**[11:38]** these parameters x using gradient descent as follows.
**[11:44]** It turns out that if you do this,
**[11:48]** then you actually find pretty good values
**[11:51]** of w and b as well as x.
**[11:54]** In this formulation of the problem,
**[11:56]** the parameters of w and b,
**[12:00]** and x is also a parameter.
**[12:04]** Then finally, to learn the values of x,
**[12:06]** we also will update x as x
**[12:11]** minus the partial derivative respect to x of the cost w,
**[12:18]** b, x. I'm using the notation here a little bit
**[12:21]** informally and not keeping
**[12:23]** very careful track of the superscripts and subscripts,
**[12:25]** but the key takeaway I hope you have from this is
**[12:29]** that the parameters to this model are w and b,
**[12:33]** and x now is also a parameter,
**[12:36]** which is why we minimize the cost function as
**[12:39]** a function of all three of these sets of parameters,
**[12:42]** w and b, as well as x.
**[12:45]** The algorithm we derived is
**[12:47]** called collaborative filtering,
**[12:49]** and the name collaborative filtering
**[12:52]** refers to the sense that
**[12:54]** because multiple users have
**[12:56]** rated the same movie collaboratively,
**[12:58]** given you a sense of what this movie maybe like,
**[13:02]** that allows you to guess what
**[13:04]** are appropriate features for that movie,
**[13:06]** and this in turn allows you to
**[13:08]** predict how other users that
**[13:10]** haven't yet rated that same movie
**[13:13]** may decide to rate it in the future.
**[13:15]** This collaborative filtering is
**[13:18]** this gathering of data from multiple users.
**[13:22]** This collaboration between users to help you predict
**[13:24]** ratings for even other users in the future.
**[13:28]** So far, our problem formulation has used
**[13:32]** movie ratings from 1- 5 stars or from 0- 5 stars.
**[13:36]** A very common use case of recommender systems is when you
**[13:40]** have binary labels such as that the user favors,
**[13:44]** or like, or interact with an item.
**[13:46]** In the next video, let's take a look at a generalization
**[13:50]** of the model that you've seen so far to binary labels.
**[13:53]** Let's go see that in the next video.
