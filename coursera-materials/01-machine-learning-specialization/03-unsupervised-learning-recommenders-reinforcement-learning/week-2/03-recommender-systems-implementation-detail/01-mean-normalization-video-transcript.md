---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 2
section: Recommender systems implementation detail
item_title: Mean normalization
duration: 9 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/hTjvz/mean-normalization
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Mean normalization — Transcript

**[0:01]** Back in the first course, you have seen how for linear regression,
**[0:05]** future normalization can help the algorithm run faster.
**[0:09]** In the case of building a recommended system
**[0:12]** with numbers wide such as movie ratings from one to five or
**[0:15]** zero to five stars, it turns out your algorithm will run more efficiently.
**[0:20]** And also perform a bit better if you first carry out mean normalization.
**[0:25]** That is if you normalize the movie ratings to have a consistent average value,
**[0:30]** let's take a look at what that means.
**[0:33]** So here's the data set that we've been using.
**[0:36]** And down below is the cost function you used to learn the parameters for
**[0:41]** the model.
**[0:42]** In order to explain mean normalization,
**[0:46]** I'm ctually going to add fifth user Eve who has not yet rated any movies.
**[0:53]** And you see in a little bit that adding mean normalization will
**[0:58]** help the algorithm make better predictions on the user Eve.
**[1:02]** In fact, if you were to train a collaborative filtering algorithm
**[1:07]** on this data, then because we are trying to make the parameters w
**[1:12]** small because of this regularization term.
**[1:15]** If you were to run the algorithm on this dataset,
**[1:20]** you actually end up with the parameters w for the fifth user,
**[1:26]** for the user Eve to be equal to [0 0] as well as quite likely b(5) = 0.
**[1:33]** Because Eve hasn't rated any movies yet, the parameters w and
**[1:38]** b don't affect this first term in the cost function because none of
**[1:43]** Eve's movie's rating play a role in this squared error cost function.
**[1:48]** And so minimizing this means making the parameters w as small as possible.
**[1:55]** We didn't really regularize b.
**[1:57]** But if you initialize b to 0 as the default, you end up with b(5) = 0 as well.
**[2:03]** But if these are the parameters for user 5 that is for
**[2:09]** Eve, then what the average will end up doing is predict
**[2:15]** that all of Eve's movies ratings would be w(5) dot x for movie i + b(5).
**[2:23]** And this is equal to 0 if w and b above equals 0.
**[2:27]** And so this algorithm will predict that if you have a new user that has not yet
**[2:31]** rated anything, we think they'll rate all movies with zero stars and
**[2:35]** that's not particularly helpful.
**[2:37]** So in this video, we'll see that mean normalization will help this
**[2:42]** algorithm come up with better predictions of the movie ratings for
**[2:47]** a new user that has not yet rated any movies.
**[2:50]** In order to describe mean normalization,
**[2:53]** let me take all of the values here including all the question marks for
**[2:58]** Eve and put them in a two dimensional matrix like this.
**[3:02]** Just to write out all the ratings including the question marks in a more
**[3:07]** sustained and more compact way.
**[3:09]** To carry out mean normalization,
**[3:12]** what we're going to do is take all of these ratings and for
**[3:16]** each movie, compute the average rating that was given.
**[3:21]** So movie one had two 5s and two 0s and so the average rating is 2.5.
**[3:26]** Movie two had a 5 and a 0, so that averages out to 2.5.
**[3:31]** Movie three 4 and 0 averages out to 2.
**[3:34]** Movie four averages out to 2.25 rating.
**[3:38]** And movie five not that popular, has an average 1.25 rating.
**[3:45]** So I'm going to take all of these five numbers and
**[3:47]** gather them into a vector which I'm going to call μ because this is the vector
**[3:52]** of the average ratings that each of the movies had.
**[3:55]** Averaging over just the users that did read that particular movie.
**[3:59]** Instead of using these original 0 to 5 star ratings over here, I'm
**[4:04]** going to take this and subtract from every rating the mean rating that it was given.
**[4:10]** So for example this movie rating was 5.
**[4:15]** I'm going to subtract 2.5 giving me 2.5 over here.
**[4:20]** This movie had a 0 star rating.
**[4:23]** I'm going to subtract 2.25 giving me a -2.25 rating and so on for all
**[4:29]** of the now five users including the new user Eve as well as for all five movies.
**[4:35]** Then these new values on the right become your new values of Y(i,j).
**[4:39]** We're going to pretend that user 1 had given a 2.5 rating to movie one and
**[4:45]** the -2.25 rating to movie four.
**[4:48]** And using this, you can then learn w(j),
**[4:53]** b(j) and x(i) same as before for user j on movie i,
**[4:59]** you would predict w(j).x(i) + b(j).
**[5:04]** But because we had subtracted off µi for movie i during this mean
**[5:09]** normalization step, in order to predict not a negative star
**[5:14]** rating which is impossible for user rates from 0 to 5 stars.
**[5:19]** We have to add back this µi which is just the value we have subtracted out.
**[5:26]** So as a concrete example, if we look at what happens with user
**[5:31]** 5 with the new user Eve because she had not yet rated any movies,
**[5:36]** the average might learn parameters w(5) = [0 0] and say b(5) = 0.
**[5:42]** And so if we look at the predicted rating for
**[5:48]** movie one, we will predict that Eve will
**[5:53]** rate it w(5).x1 + b(5) but this is 0 and
**[6:00]** then + µ1 which is equal to 2.5.
**[6:05]** So this seems more reasonable to think Eve is likely to rate this movie
**[6:09]** 2.5 rather than think Eve will rate all movie zero stars just because she
**[6:14]** hasn't rated any movies yet.
**[6:16]** And in fact the effect of this algorithm is it will cause
**[6:21]** the initial guesses for the new user Eve to be just equal to
**[6:26]** the mean of whatever other users have rated these five movies.
**[6:31]** And that seems more reasonable to take the average rating of the movies
**[6:35]** rather than to guess that all the ratings by Eve will be zero.
**[6:40]** It turns out that by normalizing the mean of the different movies ratings
**[6:44]** to be zero, the optimization algorithm for
**[6:47]** the recommender system will also run just a little bit faster.
**[6:52]** But it does make the algorithm behave much better for
**[6:55]** users who have rated no movies or very small numbers of movies.
**[7:00]** And the predictions will become more reasonable.
**[7:04]** In this example,
**[7:05]** what we did was normalize each of the rows of this matrix to have zero mean and
**[7:09]** we saw this helps when there's a new user that hasn't rated a lot of movies yet.
**[7:14]** There's one other alternative that you could use which is to instead
**[7:19]** normalize the columns of this matrix to have zero mean.
**[7:23]** And that would be a reasonable thing to do too.
**[7:26]** But I think in this application, normalizing the rows so
**[7:30]** that you can give reasonable ratings for
**[7:33]** a new user seems more important than normalizing the columns.
**[7:39]** Normalizing the columns would hope if there was a brand new movie that no one
**[7:43]** has rated yet.
**[7:44]** But if there's a brand new movie that no one has rated yet,
**[7:48]** you probably shouldn't show that movie to too many users initially because you
**[7:52]** don't know that much about that movie.
**[7:55]** So normalizing columns the hope with the case of a movie with no ratings
**[8:00]** seems less important to me than normalizing the rules
**[8:04]** to hope with the case of a new user that's hardly rated any movies yet.
**[8:09]** And when you are building your own recommended system in this week's
**[8:13]** practice lab, normalizing just the roles should work fine.
**[8:17]** So that's mean normalization.
**[8:19]** It makes the algorithm run a little bit faster.
**[8:22]** But even more important, it makes the algorithm give much better, much
**[8:26]** more reasonable predictions when there are users that rated very few movies or
**[8:31]** even no movies at all.
**[8:32]** This implementation detail of mean normalization will make your recommended
**[8:37]** system work much better.
**[8:39]** Next, let's go into the next video to talk about how you can implement this for
**[8:43]** yourself in TensorFlow.
