---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 4
section: Tree ensembles
item_title: XGBoost
duration: 7 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/op26P/xgboost
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# XGBoost — Transcript

**[0:01]** Over the years, machine learning researchers have come up with a lot of
**[0:06]** different ways to build decision trees and decision tree ensembles.
**[0:10]** Today by far the most commonly used way or implementation of decision tree ensembles
**[0:15]** or decision trees there's an algorithm called XGBoost.
**[0:18]** It runs quickly, the open source implementations are easily used,
**[0:22]** has also been used very successfully to win many machine learning competitions as
**[0:26]** well as in many commercial applications.
**[0:29]** Let's take a look at how XGBoost works.
**[0:32]** There's a modification to the back decision tree algorithm that we saw in
**[0:36]** the last video that can make it work much better.
**[0:39]** Here again, is the algorithm that we had written down previously.
**[0:43]** Given the training set to size m, you repeat B times,
**[0:46]** use sampling with replacement to create a new training set of size M and
**[0:50]** then train the decision tree on the new data set.
**[0:54]** And so the first time through this loop,
**[0:56]** we may create a training set like that and train a decision tree like that.
**[1:02]** But here's where we're going to change the algorithm, which is every time through
**[1:06]** this loop, other than the first time, that is the second time, third time and so on.
**[1:11]** When sampling, instead of picking from all
**[1:14]** m examples of equal probability with one over m probability,
**[1:18]** let's make it more likely that we'll pick misclassified examples that the
**[1:23]** previously trained trees do poorly on.
**[1:26]** In training and education, there's an idea called deliberate practice.
**[1:31]** For example, if you're learning to play the piano and
**[1:34]** you're trying to master a piece on the piano rather than practicing the entire
**[1:39]** say five minute piece over and over, which is quite time consuming.
**[1:43]** If you instead play the piece and
**[1:45]** then focus your attention on just the parts of the piece that you aren't yet
**[1:49]** playing that well in practice those smaller parts over and over.
**[1:52]** Then that turns out to be a more efficient way for
**[1:54]** you to learn to play the piano well.
**[1:57]** And so this idea of boosting is similar.
**[2:00]** We're going to look at the decision trees, we've trained so far and
**[2:03]** look at what we're still not yet doing well on.
**[2:06]** And then when building the next decision tree,
**[2:08]** we're going to focus more attention on the examples that we're not yet doing well.
**[2:12]** So rather than looking at all the training examples, we focus more attention
**[2:16]** on the subset of examples is not yet doing well on and get the new decision tree,
**[2:21]** the next decision tree reporting ensemble to try to do well on them.
**[2:25]** And this is the idea behind boosting and
**[2:28]** it turns out to help the learning algorithm learn to do better more quickly.
**[2:32]** So in detail, we will look at this tree that we have just built and
**[2:38]** go back to the original training set.
**[2:41]** Notice that this is the original training set,
**[2:44]** not one generated through sampling with replacement.
**[2:47]** And we'll go through all ten examples and
**[2:50]** look at what this learned decision tree predicts on all ten examples.
**[2:54]** So this fourth most column are their predictions and
**[2:58]** put a checkmark across next to each example,
**[3:02]** depending on whether the trees classification was correct or incorrect.
**[3:09]** So what we'll do in the second time through this loop is we will sort of use
**[3:14]** sampling with replacement to generate another training set of ten examples.
**[3:20]** But every time we pick an example from these ten will give a higher chance of
**[3:25]** picking from one of these three examples that were still misclassifying.
**[3:30]** And so this focuses the second decision trees attention via a process
**[3:35]** like deliberate practice on the examples that the album is still not yet
**[3:40]** doing that well.
**[3:42]** And the boosting procedure will do this for
**[3:44]** a total of B times where on each iteration,
**[3:50]** you look at what the ensemble of trees for trees 1,
**[3:55]** 2 up through (b- 1), are not yet doing that well on.
**[4:01]** And when you're building tree number b,
**[4:04]** you will then have a higher probability of picking examples that
**[4:08]** the ensemble of the previously sample trees is still not yet doing well on.
**[4:13]** The mathematical details of exactly how much to increase the probability
**[4:18]** of picking this versus that example are quite complex, but
**[4:23]** you don't have to worry about them in order to use boosted tree implementations.
**[4:28]** And of different ways of implementing boosting the most widely used one today is
**[4:34]** XGBoost, which stands for extreme gradient boosting, which is an open
**[4:39]** source implementation of boosted trees that is very fast and efficient.
**[4:44]** XGBoost also has a good choice of the default splitting criteria and
**[4:48]** criteria for when to stop splitting.
**[4:50]** And one of the innovations in XGBoost is that it also has built in
**[4:54]** regularization to prevent overfitting, and in machine learning
**[4:58]** competitions such as does a widely used competition site called Kaggle.
**[5:03]** XGBoost is often a highly competitive algorithm.
**[5:07]** In fact, XGBoost and deep learning algorithms seem to be the two types of
**[5:11]** algorithms that win a lot of these competitions.
**[5:15]** And one technical note, rather than doing sampling with replacement XGBoost
**[5:19]** actually assigns different weights to different training examples.
**[5:23]** So it doesn't actually need to generate a lot of randomly chosen training sets and
**[5:28]** this makes it even a little bit more efficient than using a sampling with
**[5:32]** replacement procedure.
**[5:34]** But the intuition that you saw on the previous slide is still correct
**[5:39]** in terms of how XGBoost is choosing examples to focus on.
**[5:43]** The details of XGBoost are quite complex to implement, which is why many
**[5:48]** practitioners will use the open source libraries that implement XGBoost.
**[5:54]** This is all you need to do in order to use XGBoost,
**[6:00]** you will import the XGBoost library as follows and
**[6:04]** initialize a model as an XGBoost classifier.
**[6:08]** Further model and then finally, this allows you to make
**[6:12]** predictions using this boosted decision trees algorithm.
**[6:15]** I hope that you find this algorithm useful for
**[6:18]** many applications that you may build in the future.
**[6:21]** Or alternatively, if you want to use XGBoost for regression rather than for
**[6:26]** classification, then this line here just becomes XGBRegressor and
**[6:32]** the rest of the code works similarly.
**[6:35]** So that's it for the XGBoost algorithm.
**[6:38]** We have just one last video for this week and for
**[6:41]** this course where we'll wrap up and also talk about when should you use a decision
**[6:45]** tree versus maybe use the neural network.
**[6:48]** Let's go on to the last and final video of this week.
