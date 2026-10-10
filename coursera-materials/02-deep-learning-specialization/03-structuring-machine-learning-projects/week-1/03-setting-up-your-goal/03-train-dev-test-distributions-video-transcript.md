---
type: video-transcript
specialization: Deep Learning Specialization
course: Structuring Machine Learning Projects
week: 1
section: Setting Up your Goal
item_title: Train/Dev/Test Distributions
duration: 7 min
source_url: https://www.coursera.org/learn/machine-learning-projects/lecture/78P8f/train-dev-test-distributions
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Train/Dev/Test Distributions — Transcript

**[0:00]** The way you set up your training dev,
**[0:03]** or development sets and test sets,
**[0:04]** can have a huge impact on how rapidly you or
**[0:06]** your team can make progress on building machine learning application.
**[0:09]** The same teams, even teams in very large companies,
**[0:12]** set up these data sets in ways that really slows down,
**[0:15]** rather than speeds up, the progress of the team.
**[0:18]** Let's take a look at how you can set up
**[0:20]** these data sets to maximize your team's efficiency.
**[0:23]** In this video, I want to focus on how you set up your dev and test sets.
**[0:28]** So, the dev set is also called the development set,
**[0:33]** or sometimes called the hold out cross validation set.
**[0:36]** And, workflow in machine learning is that you try a lot of ideas,
**[0:42]** train up different models on the training set,
**[0:44]** and then use the dev set to evaluate the different ideas and pick one.
**[0:47]** And, keep innovating to improve dev set performance until, finally,
**[0:51]** you have one clause that you're happy with that you then evaluate on your test set.
**[0:56]** Now, let's say, by way of example,
**[0:59]** that you're building a cat crossfire,
**[1:01]** and you are operating in these regions: in the U.S,
**[1:05]** U.K, other European countries, South America,
**[1:07]** India, China, other Asian countries, and Australia.
**[1:10]** So, how do you set up your dev set and your test set?
**[1:14]** Well, one way you could do so is to pick four of these regions.
**[1:19]** I'm going to use these four but it could be four randomly chosen regions.
**[1:22]** And say, that data from these four regions will go into the dev set.
**[1:25]** And, the other four regions, I'm going to use these four,
**[1:28]** could be randomly chosen four as well,
**[1:30]** that those will go into the test set.
**[1:33]** It turns out, this is a very bad idea because in this example,
**[1:36]** your dev and test sets come from different distributions.
**[1:40]** I would, instead, recommend that you find a way to make your dev and
**[1:44]** test sets come from the same distribution. So, here's what I mean.
**[1:49]** One picture to keep in mind is that, I think,
**[1:51]** setting up your dev set, plus,
**[1:54]** your single role number evaluation metric,
**[1:57]** that's like placing a target and telling
**[1:59]** your team where you think is the bull's eye you want to aim at.
**[2:03]** Because, what happen once you've established that dev set and the metric is that,
**[2:07]** the team can innovate very quickly, try different ideas,
**[2:09]** run experiments and very quickly use the dev set and
**[2:13]** the metric to evaluate crossfires and try to pick the best one.
**[2:16]** So, machine learning teams are often very good at shooting different arrows into
**[2:21]** targets and innovating to get closer and closer to hitting the bullseye.
**[2:26]** So, doing well on your metric on your dev sets.
**[2:30]** And, the problem with how we've set up
**[2:32]** the dev and test sets in the example on the left is that,
**[2:34]** your team might spend months innovating to do well on the dev set only to realize that,
**[2:39]** when you finally go to test them on the test set,
**[2:41]** that data from these four countries or these four regions at the bottom,
**[2:45]** might be very different than the regions in your dev set.
**[2:49]** So, you might have a nasty surprise and realize that,
**[2:51]** all the months of work you spent optimizing to the dev set,
**[2:54]** is not giving you good performance on the test set.
**[2:58]** So, having dev and test sets from different distributions is like setting a target,
**[3:03]** having your team spend months trying to aim closer and closer to bull's eye,
**[3:06]** only to realize after months of work that,
**[3:08]** you'll say, "Oh wait, to test it,
**[3:10]** I'm going to move target over here."
**[3:12]** And, the team might say, "Well,
**[3:14]** why did you make us spend months optimizing for a different bull's eye when suddenly,
**[3:18]** you can move the bull's eye to a different location somewhere else?"
**[3:21]** So, to avoid this,
**[3:23]** what I recommend instead is that,
**[3:24]** you take all this randomly shuffled data into the dev and test set.
**[3:29]** So that, both the dev and test sets have data from all eight regions
**[3:33]** and that the dev and test sets really come from the same distribution,
**[3:38]** which is the distribution of all of your data mixed together.
**[3:41]** Here's another example. This is a,
**[3:43]** actually, true story but with some details changed.
**[3:46]** So, I know a machine learning team that actually spent
**[3:48]** several months optimizing on a dev set
**[3:50]** which was comprised of loan approvals for medium income zip codes.
**[3:55]** So, the specific machine learning problem was,
**[3:57]** "Given an input X about a loan application,
**[4:00]** can you predict y and which is,
**[4:02]** whether or not, they'll repay the loan?"
**[4:04]** So, this helps you decide whether or not to approve a loan.
**[4:07]** And so, the dev set came from loan applications.
**[4:11]** They came from medium income zip codes.
**[4:13]** Zip codes is what we call postal codes in the United States.
**[4:16]** But, after working on this for a few months, the team then,
**[4:18]** suddenly decided to test this on
**[4:21]** data from low income zip codes or low income postal codes.
**[4:24]** And, of course, the distributional data for
**[4:27]** medium income and low income zip codes is very different.
**[4:30]** And, the crossfire, that they spend so much time optimizing in the former case,
**[4:34]** just didn't work well at all on the latter case.
**[4:39]** And so, this particular team actually wasted about three months of
**[4:42]** time and had to go back and really re-do a lot of work.
**[4:47]** And, what happened here was,
**[4:48]** the team spent three months aiming for one target,
**[4:52]** and then, after three months,
**[4:54]** the manager asked, "Oh,
**[4:55]** how are you doing on hitting this other target?"
**[4:57]** This is a totally different location.
**[4:59]** And, it just was a very frustrating experience for the team.
**[5:02]** So, what I recommand for setting up a dev set and test set is,
**[5:05]** choose a dev set and test set to reflect data you expect to get in
**[5:08]** future and consider important to do well on.
**[5:11]** And, in particular, the dev set and the test set here,
**[5:14]** should come from the same distribution.
**[5:20]** So, whatever type of data you expect to get in the future,
**[5:23]** and want to do well on,
**[5:25]** try to get data that looks like that.
**[5:27]** And, whatever that data is,
**[5:29]** put it into both your dev set and your test set.
**[5:32]** Because that way, you're putting
**[5:33]** the target where you actually want to hit and you're having
**[5:36]** the team innovate very efficiently to hitting that same target,
**[5:40]** hopefully, the same target well.
**[5:41]** Since we haven't talked yet about how to set up a training set,
**[5:45]** we'll talk about the training set in a later video.
**[5:48]** But, the important take away from this video is that,
**[5:51]** setting up the dev set,
**[5:53]** as well as the valuation metric,
**[5:56]** is really defining what target you want to aim at.
**[5:59]** And hopefully, by setting the dev set and the test set to the same distribution,
**[6:04]** you're really aiming at whatever target you hope your machine learning team will hit.
**[6:08]** The way you choose your training set
**[6:10]** will affect how well you can actually hit that target.
**[6:14]** But, we can talk about that separately in a later video.
**[6:18]** So, I know some machine learning teams that could literally have saved
**[6:20]** themselves months of work could they follow the guidelines in this video.
**[6:23]** So, I hope these guidelines will help you, too.
**[6:26]** Next, it turns out, that the size of your dev and test sets,
**[6:29]** how to choose the size of them,
**[6:31]** is also changing the era of deep learning.
**[6:33]** Let's talk about that in the next video.
