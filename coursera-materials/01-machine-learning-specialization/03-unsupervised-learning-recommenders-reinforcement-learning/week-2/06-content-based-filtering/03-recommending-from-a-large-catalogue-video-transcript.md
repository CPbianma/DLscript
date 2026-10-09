---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 2
section: Content-based filtering
item_title: Recommending from a large catalogue
duration: 8 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/FOMGX/recommending-from-a-large-catalogue
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Recommending from a large catalogue — Transcript

**[0:00]** Today's recommender systems will sometimes need to pick a handful of items to
**[0:05]** recommend.
**[0:06]** From a catalog of thousands or millions or 10s of millions or even more items.
**[0:11]** How do you do this efficiently computationally, let's take a look.
**[0:15]** Here's in your network we've been
**[0:18]** using to make predictions about how a user might rate an item.
**[0:22]** Today a large movie streaming site may have thousands of movies or
**[0:29]** a system that is trying to decide what ad to show.
**[0:34]** May have a catalog of millions of ads to choose from.
**[0:38]** Or a music streaming sites may have 10s of millions of songs to choose from.
**[0:45]** And large online shopping sites can have millions or
**[0:49]** even 10s of millions of products to choose from.
**[0:52]** When a user shows up on your website, they have some feature Xu.
**[0:58]** But if you need to take thousands of millions of items to feed
**[1:02]** through this neural network in order to compute in the product.
**[1:07]** To figure out which products you should recommend,
**[1:10]** then having to run neural network inference.
**[1:12]** Thousands of millions of times every time a user shows up on your website
**[1:17]** becomes computationally infeasible.
**[1:20]** Many law scale recommender systems are implemented as two
**[1:24]** steps which are called the retrieval and ranking steps.
**[1:28]** The idea is during the retrieval step will generate
**[1:33]** a large list of plausible item candidates.
**[1:37]** That tries to cover a lot of possible things you might recommend to the user and
**[1:42]** it's okay during the retrieval step.
**[1:44]** If you include a lot of items that the user is not likely to like and
**[1:49]** then during the ranking step will fine tune and
**[1:53]** pick the best items to recommend to the user.
**[1:56]** So here's an example, during the retrieval step we might do something like.
**[2:02]** For each of the last 10 movies that the user has
**[2:06]** watched find the 10 most similar movies.
**[2:10]** So this means for example if a user has watched
**[2:14]** the movie I with vector VIM you can find the movies
**[2:20]** hey with vector VKM that is similar to that.
**[2:24]** And as you saw in the last video finding the similar movies,
**[2:29]** the given movie can be pre computed.
**[2:31]** So having pre computed the most similar movies to give a movie,
**[2:35]** you can just pull up the results using a look up table.
**[2:38]** This would give you an initial set of maybe somewhat plausible movies to
**[2:42]** recommend to user that just showed up on your website.
**[2:45]** Additionally you might decide to add to it for
**[2:49]** whatever are the most viewed three genres of the user.
**[2:53]** Say that the user has watched a lot of romance movies and
**[2:57]** a lot of comedy movies and a lot of historical dramas.
**[3:01]** Then we would add to the list of possible item candidates the top 10
**[3:06]** movies in each of these three genres.
**[3:09]** And then maybe we will also add to this list the top
**[3:13]** 20 movies in the country of the user.
**[3:16]** So this retrieval step can be done very quickly and
**[3:19]** you may end up with a list of 100 or maybe 100s of plausible movies.
**[3:25]** To recommend to the user and
**[3:27]** hopefully this list will recommend some good options.
**[3:31]** But it's also okay if it includes some options that the user won't like at all.
**[3:36]** The goal of the retrieval step is to ensure broad coverage to
**[3:41]** have enough movies at least have many good ones in there.
**[3:46]** Finally, we would then take all the items we retrieve during the retrieval step and
**[3:51]** combine them into a list.
**[3:53]** Removing duplicates and removing items that the user has already watched or
**[3:57]** that the user has already purchased and
**[4:00]** that you may not want to recommend to them again.
**[4:02]** The second step of this is then the ranking step.
**[4:05]** During the ranking step you will take the list retrieved during the retrieval step.
**[4:11]** So this may be just hundreds of possible movies and
**[4:15]** rank them using the learned model.
**[4:18]** And what that means is you will feed the user feature vector and
**[4:23]** the movie feature actor into this neural network.
**[4:27]** And for each of the user movie pairs compute the predicted rating.
**[4:33]** And based on this, you now have all of the say 100 plus movies,
**[4:37]** the ones that the user is most likely to give a high rating to.
**[4:42]** And then you can just display the rank list of items to the user depending on
**[4:47]** what you think the user will give.
**[4:49]** The highest rating to one additional optimization is that
**[4:53]** if you have computed VM.
**[4:56]** For all the movies in advance, then all you need to do is to do inference
**[5:01]** on this part of the neural network a single time to compute VU.
**[5:06]** And then take that VU they just computed for the user on your website right now.
**[5:11]** And take the inner product between VU and VM.
**[5:14]** For the movies that you have retrieved during the retrieval step.
**[5:18]** So this computation can be done relatively quickly.
**[5:21]** If the retrieval step just brings up say 100s of movies,
**[5:25]** one of the decisions you need to make for
**[5:28]** this algorithm is how many items do you want to retrieve during the retrieval step?
**[5:34]** To feed into the more accurate ranking step.
**[5:38]** During the retrieval step,
**[5:40]** retrieving more items will tend to result in better performance.
**[5:44]** But the algorithm will end up being slower to analyze or
**[5:49]** to optimize the trade off between how many items to retrieve
**[5:54]** to retrieve 100 or 500 or 1000 items.
**[5:58]** I would recommend carrying out offline experiments to see how much retrieving
**[6:03]** additional items results in more relevant recommendations.
**[6:06]** And in particular, if the estimated probability that YIJ.
**[6:12]** Is equal to one according to your neural network model.
**[6:16]** Or if the estimated rating of Y being high of the retrieve items
**[6:20]** according to your model's prediction ends up being much higher.
**[6:26]** If only you were to retrieve say 500 items instead of only 100 items,
**[6:31]** then that would argue for maybe retrieving more items.
**[6:36]** Even if it slows down the algorithm a bit.
**[6:38]** But with the separate retrieval step and the ranking step, this allows
**[6:43]** many recommender systems today to give both fast as well as accurate results.
**[6:49]** Because the retrieval step tries to prune out a lot of items that are just
**[6:54]** not worth doing the more detailed influence and inner product on.
**[6:59]** And then the ranking step makes a more careful prediction for
**[7:03]** what are the items that the user is actually likely to enjoy so that's it.
**[7:08]** This is how you make your recommender system work efficiently
**[7:13]** even on very large catalogs of movies or products or what have you.
**[7:18]** Now, it turns out that as commercially important as our recommender systems,
**[7:24]** there are some significant ethical issues associated with them as well.
**[7:29]** And unfortunately there have been recommender systems that have
**[7:33]** created harm.
**[7:34]** So as you build your own recommender system,
**[7:37]** I hope you take an ethical approach and use it to serve your users.
**[7:42]** And society as large as well as yourself and
**[7:44]** the company that you might be working for.
**[7:47]** Let's take a look at the ethical issues associated with recommender systems in
**[7:51]** the next video
