---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 4
section: Decision tree learning
item_title: "Choosing a split: Information Gain"
duration: 12 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/ZSbs2/choosing-a-split-information-gain
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Choosing a split: Information Gain — Transcript

**[0:00]** When building a decision tree,
**[0:03]** the way we'll decide
**[0:04]** what feature to split on at a node will be
**[0:07]** based on what choice of feature reduces entropy the most.
**[0:11]** Reduces entropy or reduces impurity, or maximizes purity.
**[0:16]** In decision tree learning,
**[0:18]** the reduction of entropy is called information gain.
**[0:22]** Let's take a look, in this video,
**[0:24]** at how to compute information gain and therefore
**[0:27]** choose what features to use to
**[0:29]** split on at each node in a decision tree.
**[0:31]** Let's use the example of deciding
**[0:34]** what feature to use at the root node
**[0:37]** of the decision tree we were building just now
**[0:39]** for recognizing cats versus not cats.
**[0:42]** If we had split using
**[0:45]** their ear shape feature at the root node,
**[0:48]** this is what we would have gotten,
**[0:50]** five examples on the left and five on the right.
**[0:54]** On the left, we would have four out of five cats,
**[0:58]** so P1 would be equal to 4/5 or 0.8.
**[1:04]** On the right, one out of five are cats,
**[1:06]** so P1 is equal to 1/5 or 0.2.
**[1:09]** If you apply the entropy formula from the last video
**[1:13]** to this left subset
**[1:16]** of data and this right subset of data,
**[1:18]** we find that the degree of
**[1:20]** impurity on the left is entropy of 0.8,
**[1:24]** which is about 0.72,
**[1:26]** and on the right,
**[1:28]** the entropy of 0.2 turns out also to be 0.72.
**[1:34]** This would be the entropy at the left and
**[1:38]** right subbranches if we
**[1:41]** were to split on the ear shape feature.
**[1:43]** One other option would be to
**[1:45]** split on the face shape feature.
**[1:48]** If we'd done so then on the left,
**[1:51]** four of the seven examples would be cats,
**[1:54]** so P1 is 4/7 and on the right,
**[1:58]** 1/3 are cats, so P1 on the right is 1/3.
**[2:02]** The entropy of 4/7 and the entropy
**[2:06]** of 1/3 are 0.99 and 0.92.
**[2:10]** So the degree of impurity in the left
**[2:12]** and right nodes seems much higher,
**[2:15]** 0.99 and 0.92 compared to 0.72 and 0.72.
**[2:20]** Finally, the third possible choice of
**[2:22]** feature to use at the root node would be
**[2:24]** the whiskers feature in which case
**[2:26]** you split based on whether
**[2:27]** whiskers are present or absent.
**[2:29]** In this case, P1 on the left is 3/4,
**[2:33]** P1 on the right is 2/6,
**[2:35]** and the entropy values are as follows.
**[2:39]** The key question we need to answer is,
**[2:42]** given these three options
**[2:43]** of a feature to use at the root node,
**[2:46]** which one do we think works best?
**[2:49]** It turns out that rather than looking at
**[2:54]** these entropy numbers and comparing them,
**[2:58]** it would be useful to take
**[3:00]** a weighted average of them, and here's what I mean.
**[3:04]** If there's a node with a lot of
**[3:07]** examples in it with high entropy
**[3:09]** that seems worse than if there was a node
**[3:12]** with just a few examples in it with high entropy.
**[3:15]** Because entropy, as a measure of impurity,
**[3:18]** is worse if you have
**[3:19]** a very large and impure dataset compared to
**[3:23]** just a few examples
**[3:24]** and a branch of the tree that is very impure.
**[3:28]** The key decision is,
**[3:29]** of these three possible choices
**[3:31]** of features to use at the root node,
**[3:34]** which one do we want to use?
**[3:36]** Associated with each of these splits is two numbers,
**[3:40]** the entropy on the left sub-branch
**[3:42]** and the entropy on the right sub-branch.
**[3:45]** In order to pick from these,
**[3:47]** we like to actually combine
**[3:48]** these two numbers into a single number.
**[3:50]** So you can just pick
**[3:52]** of these three choices, which one does best?
**[3:55]** The way we're going to combine
**[3:56]** these two numbers is by taking a weighted average.
**[4:00]** Because how important it
**[4:03]** is to have low entropy in, say,
**[4:05]** the left or right sub-branch also depends on
**[4:08]** how many examples went into the left or right sub-branch.
**[4:12]** Because if there are lots of examples in, say,
**[4:14]** the left sub-branch then it seems more
**[4:17]** important to make sure that that
**[4:19]** left sub-branch's entropy value is low.
**[4:22]** In this example we have,
**[4:25]** five of the 10 examples went to the left sub-branch,
**[4:29]** so we can compute the weighted average
**[4:31]** as 5/10 times the entropy of 0.8,
**[4:34]** and then add to that 5/10 examples
**[4:38]** also went to the right sub-branch,
**[4:40]** plus 5/10 times the entropy of 0.2.
**[4:45]** Now, for this example in the middle,
**[4:48]** the left sub-branch had
**[4:51]** received seven out of 10 examples.
**[4:54]** and so we're going to compute
**[4:56]** 7/10 times the entropy of 0.57 plus,
**[5:03]** the right sub-branch had three out of 10 examples,
**[5:05]** so plus 3/10 times entropy of 0.3 of 1/3.
**[5:11]** Finally, on the right,
**[5:14]** we'll compute 4/10 times entropy of
**[5:18]** 0.75 plus 6/10 times entropy of 0.33.
**[5:24]** The way we will choose a split is by
**[5:27]** computing these three numbers and picking whichever one
**[5:31]** is lowest because that gives us the left and
**[5:35]** right sub-branches with
**[5:36]** the lowest average weighted entropy.
**[5:40]** In the way that decision trees are built,
**[5:42]** we're actually going to make one more change to
**[5:45]** these formulas to stick to
**[5:47]** the convention in decision tree building,
**[5:49]** but it won't actually change the outcome.
**[5:51]** Which is rather than computing
**[5:53]** this weighted average entropy,
**[5:56]** we're going to compute the reduction in
**[5:58]** entropy compared to if we hadn't split at all.
**[6:02]** If we go to the root node,
**[6:04]** remember that the root node we have started off with
**[6:07]** all 10 examples in the root node
**[6:09]** with five cats and dogs,
**[6:11]** and so at the root node,
**[6:13]** we had p_1 equals 5/10 or 0.5.
**[6:18]** The entropy of the root nodes,
**[6:22]** entropy of 0.5 was actually equal to 1.
**[6:25]** This was maximum impurity
**[6:27]** because it was five cats and five dogs.
**[6:29]** The formula that we're actually going to
**[6:31]** use for choosing a split is
**[6:33]** not this weighted entropy at
**[6:36]** the left and right sub-branches,
**[6:38]** instead is going to be the entropy at the root node,
**[6:41]** which is entropy of 0.5,
**[6:43]** then minus this formula.
**[6:48]** In this example, if you work out the math,
**[6:50]** it turns out to be 0.28.
**[6:53]** For the face shape example,
**[6:55]** we can compute entropy of the root node,
**[6:57]** entropy of 0.5 minus this,
**[7:00]** which turns out to be 0.03, and for whiskers,
**[7:04]** compute that, which turns out to be 0.12.
**[7:09]** These numbers that we just calculated,
**[7:12]** 0.28, 0.03, and 0.12,
**[7:14]** these are called the information gain,
**[7:17]** and what it measures is the reduction in
**[7:20]** entropy that you get in
**[7:21]** your tree resulting from making a split.
**[7:24]** Because the entropy was originally
**[7:27]** one at the root node and by making the split,
**[7:32]** you end up with a lower value of entropy and
**[7:35]** the difference between those two values
**[7:37]** is a reduction in entropy,
**[7:39]** and that's 0.28 in
**[7:41]** the case of splitting on the ear shape.
**[7:43]** Why do we bother to compute reduction in
**[7:47]** entropy rather than just
**[7:49]** entropy at the left and right sub-branches?
**[7:52]** It turns out that one of
**[7:53]** the stopping criteria for deciding when to not
**[7:56]** bother to split any further is
**[7:58]** if the reduction in entropy is too small.
**[8:00]** In which case you could decide,
**[8:02]** you're just increasing the size of the tree
**[8:04]** unnecessarily and risking overfitting by
**[8:06]** splitting and just decide to not bother if
**[8:09]** the reduction in entropy
**[8:11]** is too small or below a threshold.
**[8:13]** In this other example,
**[8:15]** spitting on ear shape results
**[8:17]** in the biggest reduction in entropy,
**[8:19]** 0.28 is bigger than 0.03 or 0.12
**[8:23]** and so we would choose to split onto
**[8:25]** ear shape feature at the root node.
**[8:28]** On the next slide, let's give
**[8:31]** a more formal definition of information gain.
**[8:34]** By the way, one additional piece
**[8:36]** of notation that we'll introduce
**[8:38]** also in the next slide is these numbers, 5/10 and 5/10.
**[8:42]** I'm going to call this w^left because
**[8:45]** that's the fraction of
**[8:46]** examples that went to the left branch,
**[8:48]** and I'm going to call this w^right
**[8:50]** because that's the fraction of
**[8:52]** examples that went to the right branch.
**[8:54]** Whereas for this another example,
**[8:57]** w^left would be 7/10,
**[8:58]** and w^right will be 3/10.
**[9:01]** Let's now write down
**[9:02]** the general formula for how to compute information gain.
**[9:07]** Using the example of splitting on the ear shape feature,
**[9:11]** let me define p_1^left to be equal to
**[9:16]** the fraction of examples in
**[9:18]** the left subtree that have
**[9:20]** a positive label, that are cats.
**[9:22]** In this example, p_1^left will be equal to 4/5.
**[9:27]** Also, let me define w^left to be the fraction of
**[9:31]** examples of all of the examples of
**[9:33]** the root node that went to the left sub-branch,
**[9:37]** and so in this example, w^left would be 5/10.
**[9:40]** Similarly, let's define
**[9:43]** p_1^right to be of all the examples in the right branch.
**[9:48]** The fraction that are positive examples and
**[9:51]** so one of the five of these examples being cats,
**[9:53]** there'll be 1/5, and similarly,
**[9:56]** w^right is 5/10 the fraction
**[9:59]** of examples that went to the right sub-branch.
**[10:02]** Let's also define p_1^root to
**[10:07]** be the fraction of examples that
**[10:09]** are positive in the root node.
**[10:12]** In this case, this would be 5/10 or 0.5.
**[10:17]** Information gain is then defined as
**[10:21]** the entropy of p_1^root,
**[10:24]** so what's the entropy at the root node,
**[10:27]** minus that weighted entropy calculation
**[10:31]** that we had on the previous slide,
**[10:32]** minus w^left those were 5/10 in the example,
**[10:35]** times the entropy applied to p_1^left,
**[10:38]** that's entropy on the left sub-branch,
**[10:41]** plus w^right the fraction
**[10:44]** of examples that went to the right branch,
**[10:46]** times entropy of p_1^right.
**[10:51]** With this definition of entropy,
**[10:54]** and you can calculate the information gain associated
**[10:57]** with choosing any particular feature
**[11:00]** to split on in the node.
**[11:02]** Then out of all the possible futures,
**[11:04]** you could choose to split on,
**[11:05]** you can then pick the one that gives you
**[11:07]** the highest information gain.
**[11:09]** That will result in, hopefully,
**[11:13]** increasing the purity of your subsets of
**[11:16]** data that you get on the left and right sub-branches
**[11:19]** of your decision tree and that
**[11:21]** will result in choosing a feature to split
**[11:24]** on that increases the purity of
**[11:27]** your subsets of data in
**[11:29]** both the left and right
**[11:30]** sub-branches of your decision tree.
**[11:33]** Now that you know how to calculate
**[11:35]** information gain or reduction in entropy,
**[11:37]** you know how to pick a feature to split on another node.
**[11:41]** Let's put all the things we've talked about together into
**[11:44]** the overall algorithm for
**[11:46]** building a decision tree given a training set.
**[11:49]** Let's go see that in the next video.
