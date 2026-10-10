---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 4
section: Tree ensembles
item_title: Using multiple decision trees
duration: 4 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/3Epc2/using-multiple-decision-trees
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# Using multiple decision trees — Transcript

**[0:00]** One of the weaknesses of using
**[0:03]** a single decision tree is that
**[0:05]** that decision tree can be highly
**[0:07]** sensitive to small changes in the data.
**[0:10]** One solution to make the algorithm less sensitive or
**[0:14]** more robust is to build not one decision tree,
**[0:17]** but to build a lot of decision trees,
**[0:19]** and we call that a tree ensemble.
**[0:21]** Let's take a look. With the example
**[0:24]** that we've been using,
**[0:26]** the best feature to split on at the root node
**[0:28]** turned out to be the ear shape resulting in
**[0:31]** these two subsets of the data and then
**[0:33]** building further sub trees on
**[0:35]** these two subsets of the data.
**[0:37]** But it turns out that if you were to
**[0:39]** take just one of the ten examples and
**[0:41]** change it to a different cat
**[0:43]** so that instead of having pointy ears,
**[0:45]** round face, whiskers absent,
**[0:47]** this new cat has floppy ears,
**[0:49]** round face, whiskers present,
**[0:51]** with just changing a single training example,
**[0:56]** the highest information gain feature to split on
**[0:59]** becomes the whiskers feature
**[1:01]** instead of the ear shape feature.
**[1:03]** As a result of that,
**[1:06]** the subsets of data you get in
**[1:08]** the left and right sub-trees become totally
**[1:10]** different and as you continue to
**[1:13]** run the decision tree learning algorithm recursively,
**[1:16]** you build out totally different sub trees
**[1:19]** on the left and right.
**[1:20]** The fact that changing just one training example causes
**[1:25]** the algorithm to come up with
**[1:27]** a different split at the root and
**[1:28]** therefore a totally different tree,
**[1:31]** that makes this algorithm just not that robust.
**[1:35]** That's why when you're using decision trees,
**[1:38]** you often get a much better result, that is,
**[1:40]** you get more accurate predictions if you train not
**[1:43]** just a single decision tree
**[1:45]** but a whole bunch of different decision trees.
**[1:48]** This is what we call a tree ensemble,
**[1:51]** which just means a collection of multiple trees.
**[1:54]** We'll see, in the next few videos,
**[1:56]** how to construct this ensemble of trees.
**[1:59]** But if you had this ensemble three trees,
**[2:03]** each one of these is maybe
**[2:05]** a plausible way to classify cat versus not cat.
**[2:08]** If you had a new test example
**[2:11]** that you wanted to classify,
**[2:13]** then what you would do is run all three of these trees on
**[2:17]** your new example and get them to
**[2:19]** vote on whether it's the final prediction.
**[2:22]** This test example has pointy ears,
**[2:25]** a not round face shape and whiskers are present and so
**[2:29]** the first tree would carry out inferences
**[2:31]** like this and predict that it is a cat.
**[2:34]** The second tree's inference would follow this path
**[2:38]** through the tree and therefore predict that is not cat.
**[2:43]** The third tree would follow this path and
**[2:46]** therefore predict that it is a cat.
**[2:50]** These three trees have made
**[2:52]** different predictions and so
**[2:54]** what we'll do is actually get them to vote.
**[2:56]** The majority votes of the predictions
**[2:58]** among these three trees is, cat.
**[3:00]** The final prediction of this ensemble of trees is
**[3:03]** that this is a cat
**[3:05]** which happens to be the correct prediction.
**[3:07]** The reason we use an ensemble of trees
**[3:11]** is by having lots
**[3:12]** of decision trees and having them vote,
**[3:14]** it makes your overall algorithm less sensitive to what
**[3:18]** any single tree may be doing because it
**[3:21]** gets only one vote out of three or one vote out of many,
**[3:25]** many different votes and it makes
**[3:26]** your overall algorithm more robust.
**[3:28]** But how do you come up with all of
**[3:31]** these different plausible but
**[3:33]** maybe slightly different decision trees
**[3:35]** in order to get them to vote?
**[3:37]** In the next video,
**[3:38]** we'll talk about a technique from
**[3:40]** statistics called sampling with
**[3:42]** replacement and this will
**[3:44]** turn out to be a key technique that we'll
**[3:46]** use in the video after that in
**[3:48]** order to build this ensemble of trees.
**[3:51]** Let's go on to the next video to talk
**[3:53]** about sampling with replacement.
