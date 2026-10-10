---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 2
section: Content-based filtering
item_title: Collaborative filtering vs Content-based filtering
duration: 10 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/8weTz/collaborative-filtering-vs-content-based-filtering
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Collaborative filtering vs Content-based filtering — Transcript

**[0:01]** In this video, we'll start to develop a second type of
**[0:05]** recommender system called
**[0:06]** a content-based filtering algorithm.
**[0:09]** To get started, let's compare and contrast
**[0:11]** the collaborative filtering approach that we'll be
**[0:13]** looking at so far with
**[0:15]** this new content-based filtering approach.
**[0:17]** Let's take a look.
**[0:18]** With collaborative filtering,
**[0:21]** the general approach is that we would recommend items to
**[0:25]** you based on ratings of
**[0:27]** users who gave similar ratings as you.
**[0:30]** We have some number of users
**[0:32]** give some ratings for some items,
**[0:35]** and the algorithm figures out how to use
**[0:37]** that to recommend new items to you.
**[0:40]** In contrast, content-based filtering takes
**[0:44]** a different approach to
**[0:46]** deciding what to recommend to you.
**[0:48]** A content-based filtering algorithm
**[0:51]** will recommend items to you based on
**[0:53]** the features of users and
**[0:55]** features of the items to find a good match.
**[0:58]** In other words, it
**[0:59]** requires having some features of each user,
**[1:03]** as well as some features of
**[1:05]** each item and it uses those features to try to
**[1:08]** decide which items and
**[1:10]** users might be a good match for each other.
**[1:13]** With a content-based filtering algorithm,
**[1:15]** you still have data where users have rated some items.
**[1:20]** Well, content-based filtering
**[1:22]** will continue to use r, i,
**[1:24]** j to denote whether or not user j has
**[1:28]** rated item i and will continue to use y i,
**[1:33]** j to denote the rating
**[1:35]** that user j is given item i if it's defined.
**[1:39]** But the key to
**[1:41]** content-based filtering is that
**[1:43]** we will be able to make good use of
**[1:45]** features of the user and of the items to
**[1:50]** find better matches than
**[1:52]** potentially a pure collaborative
**[1:53]** filtering approach might be able to.
**[1:55]** Let's take a look at how this works.
**[1:57]** In the case of movie recommendations,
**[1:59]** here are some examples of features.
**[2:01]** You may know the age of the user,
**[2:04]** or you may have the gender of the user.
**[2:08]** This could be a one-hot feature
**[2:11]** similar to what you saw when we were talking
**[2:14]** about decision trees where you
**[2:16]** could have a one-hot feature with
**[2:18]** the values based on whether
**[2:20]** the user's self-identified gender
**[2:22]** is male or female or unknown,
**[2:25]** and you may know the country of the user.
**[2:29]** If there are about 200 countries
**[2:31]** in the world then also be
**[2:33]** a one-hot feature with about 200 possible values.
**[2:37]** You can also look at past behaviors of
**[2:39]** the user to construct this feature vector.
**[2:43]** For example, if you look at
**[2:45]** the top thousand movies in your catalog,
**[2:47]** you might construct a thousand features that tells you of
**[2:51]** the thousand most popular movies in
**[2:53]** the world which of these has the user watch.
**[2:56]** In fact, you can also take ratings the user might
**[3:00]** have already given in order to construct new features.
**[3:04]** It turns out that if you have a set of movies
**[3:07]** and if you know what genre each movie is in,
**[3:11]** then the average rating
**[3:13]** per genre that the user has given.
**[3:16]** Of all the romance movies that the user has rated,
**[3:21]** what was the average rating?
**[3:22]** Of all the action movies that the user has rated,
**[3:25]** what was the average rating?
**[3:27]** And so on for all the other genres.
**[3:29]** This too can be a powerful feature to describe the user.
**[3:34]** One interesting thing about this feature is that it
**[3:38]** actually depends on the ratings that the user had given.
**[3:42]** But there's nothing wrong with that.
**[3:44]** Constructing a feature vector that
**[3:46]** depends on the user's ratings is
**[3:48]** a completely fine way to
**[3:50]** develop a feature vector to describe that user.
**[3:53]** With features like these you can then come up
**[3:57]** with a feature vector x subscript u,
**[4:01]** use as a user superscript j for user j.
**[4:04]** Similarly, you can also come up with a set of
**[4:06]** features for each movie of each item,
**[4:09]** such as what was the year of the movie?
**[4:12]** What's the genre or genres of the movie of known?
**[4:16]** If there are critic reviews of the movie,
**[4:19]** you can construct one or multiple features to
**[4:22]** capture something about what
**[4:24]** the critics are saying about the movie.
**[4:26]** Or once again, you can actually take
**[4:29]** user ratings of the movie to construct a feature of,
**[4:32]** say, the average rating of this movie.
**[4:35]** This feature again depends on the ratings
**[4:38]** that users are given but again,
**[4:42]** does nothing wrong with that.
**[4:43]** You can construct a feature for
**[4:45]** a given movie that
**[4:47]** depends on the ratings that movie had received,
**[4:50]** such as the average rating of the movie.
**[4:51]** Or if you wish, you can also have
**[4:54]** average rating per country or
**[4:56]** average rating per user demographic as they
**[4:59]** want to construct other types of
**[5:01]** features of the movies as well.
**[5:03]** With this, for each movie,
**[5:05]** you can then construct a feature vector,
**[5:07]** which I'm going to denote x subscript m,
**[5:10]** m stands for movie,
**[5:12]** and superscript i for movie i.
**[5:14]** Given features like this,
**[5:16]** the task is to try to figure out whether
**[5:20]** a given movie i is going to be good match for user j.
**[5:26]** Notice that the user features and
**[5:29]** movie features can be very different in size.
**[5:33]** For example, maybe the user features could be
**[5:37]** 1500 numbers and the movie features
**[5:41]** could be just 50 numbers.
**[5:43]** That's okay too. In content-based filtering,
**[5:46]** we're going to develop an algorithm that learns to
**[5:48]** match users and movies.
**[5:51]** Previously, we were predicting
**[5:53]** the rating of user j on movie
**[5:56]** i as wj dot products of xi plus bj.
**[6:02]** In order to develop content-based filtering,
**[6:06]** I'm going to get rid of bj.
**[6:08]** It turns out this won't hurt
**[6:10]** the performance of the content-based filtering at all.
**[6:12]** Instead of writing wj for a user j and xi for a movie i,
**[6:20]** I'm instead going to just
**[6:21]** replace this notation with vj_u.
**[6:25]** This v here stands for a vector.
**[6:28]** There'll be a list of numbers computed for
**[6:31]** user j and the u subscript here stands for user.
**[6:36]** Instead of xi,
**[6:38]** I'm going to compute a separate vector subscript m,
**[6:42]** to stand for the movie and
**[6:44]** for movie is what a superscript stands for.
**[6:48]** Vj_u as a vector as a list of numbers
**[6:52]** computed from the features of user j
**[6:58]** and vi_m is a list of numbers computed from
**[7:03]** the features like the ones you saw on
**[7:05]** the previous slide of movie i.
**[7:08]** If we're able to come up with
**[7:11]** an appropriate choice of these vectors,
**[7:14]** vj_u and vi_m,
**[7:16]** then hopefully the dot product
**[7:19]** between these two vectors will be
**[7:20]** a good prediction of
**[7:22]** the rating that user j gives movie i.
**[7:25]** Just illustrate what a learning algorithm
**[7:28]** could come up with.
**[7:30]** If v, u, that is a user vector,
**[7:34]** turns out to capture the user's preferences,
**[7:38]** say is 4.9,
**[7:40]** 0.1, and so on.
**[7:42]** Lists of numbers like that.
**[7:43]** The first number captures
**[7:46]** how much do they like romance movies.
**[7:49]** Then the second number captures how much do they
**[7:51]** like action movies and so on.
**[7:54]** Then v_m, the movie vector is 4.5, 0.2,
**[8:01]** and so on and so forth of these numbers
**[8:04]** capturing how much is this a romance movie,
**[8:07]** how much is this an action movie, and so on.
**[8:10]** Then the dot product,
**[8:12]** which multiplies these lists of
**[8:14]** numbers element-wise and then takes a sum,
**[8:17]** hopefully, will give a sense of how much
**[8:19]** this particular user will like this particular movie.
**[8:23]** The challenges given features of a user, say xj_u,
**[8:28]** how can we compute this vector vj_u that
**[8:32]** represents succinctly or
**[8:34]** compactly the user's preferences?
**[8:37]** Similarly given features of a movie,
**[8:39]** how can we compute vi_m?
**[8:42]** Notice that whereas x_u
**[8:45]** and x_m could be different in size,
**[8:48]** one could be very long lists of numbers,
**[8:50]** one could be much shorter list,
**[8:52]** v here have to be the same size.
**[8:56]** Because if you want to take
**[8:58]** a dot product between v_u and v_m,
**[9:00]** then both of them have to
**[9:02]** have the same dimensions such as
**[9:04]** maybe both of these are say 32 numbers.
**[9:08]** To summarize, in collaborative filtering,
**[9:12]** we had number of users give ratings of different items.
**[9:16]** In contrast, in content-based filtering,
**[9:19]** we have features of users and features of items and we
**[9:23]** want to find a way to find
**[9:25]** good matches between the users and the items.
**[9:28]** The way we're going to do so is to compute these vectors,
**[9:32]** v_u for the users and v_m for the items over the movies,
**[9:36]** and then take dot products between
**[9:37]** them to try to find good matches.
**[9:39]** How do we compute the v_u and v_m?
**[9:42]** Let's take a look at that in the next video.
