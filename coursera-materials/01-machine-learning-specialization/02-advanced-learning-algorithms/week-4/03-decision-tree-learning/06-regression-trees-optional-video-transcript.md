---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 4
section: Decision tree learning
item_title: Regression Trees (optional)
duration: 10 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/XlM5n/regression-trees-optional
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Regression Trees (optional) — Transcript

**[0:01]** So far we've only been talking about decision trees as classification
**[0:06]** algorithms.
**[0:06]** In this optional video, we'll generalize decision trees to be regression
**[0:11]** algorithms so that we can predict a number.
**[0:14]** Let's take a look.
**[0:15]** The example I'm going to use for
**[0:17]** this video will be to use these three valued features that we had previously,
**[0:22]** that is, these features X, In order to predict the weight of the animal, Y.
**[0:28]** So just to be clear, the weight here,
**[0:30]** unlike the previous video is no longer an input feature.
**[0:34]** Instead, this is the target output, Y, that we want to predict rather
**[0:40]** than trying to predict whether or not an animal is or is not a cat.
**[0:45]** This is a regression problem because we want to predict a number, Y.
**[0:50]** Let's look at what a regression tree will look like.
**[0:54]** Here I've already constructed a tree for this regression problem
**[0:58]** where the root node splits on ear shape and then the left and
**[1:02]** right sub tree split on face shape and also face shape here on the right.
**[1:06]** And there's nothing wrong with a decision tree that chooses to split on
**[1:11]** the same feature in both the left and right side branches.
**[1:15]** It's perfectly fine if the splitting algorithm chooses to do that.
**[1:21]** If during training, you had decided on these splits,
**[1:25]** then this node down here would have these four animals with
**[1:30]** weights 7.2, 7.6 and 10.2.
**[1:33]** This node would have this one animal with weight 9.2 and
**[1:38]** so on for these remaining two nodes.
**[1:43]** So, the last thing we need to fill in for this decision tree is if there's
**[1:48]** a test example that comes down to this node, what is there weights that
**[1:54]** we should predict for an animal with pointy ears and a round face shape?
**[1:59]** The decision tree is going to make a prediction based on taking
**[2:03]** the average of the weights in the training examples down here.
**[2:08]** And by averaging these four numbers, it turns out you get 8.35.
**[2:14]** If on the other hand, an animal has pointy ears and
**[2:18]** a not round face shape, then it will predict 9.2 or
**[2:22]** 9.2 pounds because that's the weight of this one animal down here.
**[2:28]** And similarly, this will be 17.70 and 9.90.
**[2:34]** So, what this model will do is given a new test example, follow the decision
**[2:39]** nodes down as usual until it gets to a leaf node and then predict that value
**[2:44]** at the leaf node which I had just computed by taking an average of the weights
**[2:49]** of the animals that during training had gotten down to that same leaf node.
**[2:56]** So, if you were constructing a decision tree from scratch using this data
**[3:01]** set in order to predict the weight.
**[3:04]** The key decision as you've seen earlier this week will be,
**[3:08]** how do you choose which feature to split on?
**[3:11]** Let me illustrate how to make that decision with an example.
**[3:15]** At the root node, one thing you could do is split on the ear shape and
**[3:20]** if you do that, you end up with left and right branches of the tree
**[3:25]** with five animals on the left and right with the following weights.
**[3:32]** If you were to choose the split on the face shape, you end up with these animals on
**[3:36]** the left and right with the corresponding weights that are written below.
**[3:41]** And if you were to choose to split on whiskers being present or absent,
**[3:45]** you end up with this.
**[3:47]** So, the question is, given these three possible features to
**[3:52]** split on at the root node, which one do you want to pick
**[3:56]** that gives the best predictions for the weight of the animal?
**[4:01]** When building a regression tree, rather than trying to reduce entropy,
**[4:06]** which was that measure of impurity that we had for
**[4:10]** a classification problem, we instead try to reduce the variance
**[4:15]** of the weight of the values Y at each of these subsets of the data.
**[4:20]** So, if you've seen the notion of variants in other contexts, that's great.
**[4:26]** This is the statistical mathematical notion of variants that we'll used in
**[4:30]** a minute.
**[4:31]** But if you've not seen how to compute the variance of a set of numbers before,
**[4:37]** don't worry about it.
**[4:38]** All you need to know for this slide is that variants informally
**[4:43]** computes how widely a set of numbers varies.
**[4:47]** So for this set of numbers 7.2, 9.2 and so on, up to 10.2,
**[4:52]** it turns out the variance is 1.47, so it doesn't vary that much.
**[4:58]** Whereas, here 8.8, 15, 11, 18 and 20,
**[5:02]** these numbers go all the way from 8.8 all the way up to 20.
**[5:06]** And so the variance is much larger, turns out to the variance of 21.87.
**[5:12]** And so the way we'll evaluate the quality of the split is,
**[5:16]** we'll compute same as before, W left and
**[5:19]** W right as the fraction of examples that went to the left and right branches.
**[5:26]** And the average variance after the split is going to be 5/10,
**[5:31]** which is W left times 1.47, which is the variance on the left and
**[5:36]** then plus 5/10 times the variance on the right, which is 21.87.
**[5:43]** So, this weighted average variance plays a very similar role to the weighted
**[5:48]** average entropy that we had used when deciding what split to use for
**[5:52]** a classification problem.
**[5:54]** And we can then repeat this calculation for
**[5:58]** the other possible choices of features to split on.
**[6:02]** Here in the tree in the middle,
**[6:04]** the variance of these numbers here turns out to be 27.80.
**[6:10]** The variance here is 1.37.
**[6:13]** And so with W left equals seven-tenths and W right as three-tenths,
**[6:18]** and so with these values, you can compute the weighted variance as follows.
**[6:25]** Finally, for the last example, if you were to split on the whiskers feature,
**[6:30]** this is the variance on the left and right, there's W left and W right.
**[6:34]** And so the weight of variance is this.
**[6:36]** A good way to choose a split would be to just choose the value of
**[6:41]** the weighted variance that is lowest.
**[6:44]** Similar to when we're computing information gain,
**[6:47]** I'm going to make just one more modification to this equation.
**[6:51]** Just as for the classification problem, we didn't just measure the average weighted
**[6:56]** entropy, we measured the reduction in entropy and that was information gain.
**[7:01]** For a regression tree we'll also similarly measure the reduction in variance.
**[7:06]** Turns out, if you look at all of the examples in the training set,
**[7:11]** all ten examples and compute the variance of all of them,
**[7:15]** the variance of all the examples turns out to be 20.51.
**[7:19]** And that's the same value for the roots node in all of these,
**[7:23]** of course, because it's the same ten examples at the roots node.
**[7:28]** And so what we'll actually compute is the variance of the roots node,
**[7:33]** which is 20.51 minus this expression down here, which turns out to be equal to 8.84.
**[7:41]** And so at the roots node, the variance was 20.51 and after splitting on ear shape,
**[7:49]** the average weighted variance at these two nodes is 8.84 lower.
**[7:54]** So, the reduction in variance is 8.84.
**[7:57]** And similarly, if you compute the expression for reduction in variance for
**[8:02]** this example in the middle, it's 20.51 minus this expression that we had before,
**[8:09]** which turns out to be equal to 0.64.
**[8:11]** So, this is a very small reduction in variance.
**[8:14]** And for the whiskers feature you end up with this which is 6.22.
**[8:22]** So, between all three of these examples,
**[8:25]** 8.84 gives you the largest reduction in variance.
**[8:29]** So, just as previously we would choose the feature that gives you
**[8:33]** the largest information gain for a regression tree,
**[8:36]** you will choose the feature that gives you the largest reduction in variance,
**[8:41]** which is why you choose ear shape as the feature to split on.
**[8:46]** Having chosen the ear shape feature to split on, you now have two subsets
**[8:51]** of five examples in the left and right side branches and you would then,
**[8:57]** again, we say recursively, where you take these five examples and
**[9:02]** do a new decision tree focusing on just these five examples,
**[9:06]** again, evaluating different options of features to split on and
**[9:11]** picking the one that gives you the biggest variance reduction.
**[9:16]** And similarly on the right.
**[9:18]** And you keep on splitting until you meet the criteria for
**[9:22]** not splitting any further.
**[9:24]** And so that's it.
**[9:25]** With this technique, you can get your decision treat to not just carry
**[9:30]** out classification problems, but also regression problems.
**[9:34]** So far, we've talked about how to train a single decision tree.
**[9:38]** It turns out if you train a lot of decision trees,
**[9:41]** we call this an ensemble of decision trees, you can get a much better result.
**[9:46]** Let's take a look at why and how to do so in the next video.
