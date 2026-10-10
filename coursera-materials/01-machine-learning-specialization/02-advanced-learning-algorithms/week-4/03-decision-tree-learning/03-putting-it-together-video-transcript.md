---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 4
section: Decision tree learning
item_title: Putting it together
duration: 9 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/a51O3/putting-it-together
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# Putting it together — Transcript

**[0:01]** The information gain criteria lets you decide
**[0:04]** how to choose one feature to split a one-node.
**[0:07]** Let's take that and use that in multiple places through
**[0:10]** a decision tree in order to figure out how to
**[0:13]** build a large decision tree with multiple nodes.
**[0:16]** Here is the overall process of building a decision tree.
**[0:19]** Starts with all training examples
**[0:22]** at the root node of the tree
**[0:24]** and calculate the information gain for
**[0:27]** all possible features and pick the feature to split on,
**[0:30]** that gives the highest information gain.
**[0:33]** Having chosen this feature,
**[0:35]** you would then split the dataset into
**[0:37]** two subsets according to the selected feature,
**[0:40]** and create left and right branches of the tree and
**[0:44]** send the training examples
**[0:46]** to either the left or the right branch,
**[0:49]** depending on the value of that feature for that example.
**[0:53]** This allows you to have made a split at the root node.
**[0:57]** After that, you will then keep on repeating
**[1:01]** the splitting process on the left branch of the tree,
**[1:04]** on the right branch of the tree and so on.
**[1:07]** Keep on doing that until the stopping criteria is met.
**[1:11]** Where the stopping criteria can be,
**[1:14]** when a node is 100 percent a single clause,
**[1:17]** someone has reached entropy of zero,
**[1:21]** or when further splitting a node will cause
**[1:23]** the tree to exceed the maximum depth that you had set,
**[1:27]** or if the information gain from
**[1:29]** an additional splits is less than the threshold,
**[1:32]** or if the number of
**[1:34]** examples in a nodes is below a threshold.
**[1:38]** You will keep on repeating the splitting process until
**[1:42]** the stopping criteria that you've chosen,
**[1:46]** which could be one or more of these criteria is met.
**[1:49]** Let's look at an illustration
**[1:51]** of how this process will work.
**[1:53]** We started all of the examples at
**[1:57]** the root nodes and based on
**[1:59]** computing information gain for all three features,
**[2:02]** decide that ear-shaped is the best feature to split on.
**[2:07]** Based on that, we create a left
**[2:09]** and right sub-branches and send
**[2:11]** the subsets of the data with pointy versus
**[2:13]** floppy ear to left and right sub-branches.
**[2:17]** Let me cover the root node and
**[2:19]** the right sub-branch and just focus on
**[2:21]** the left sub-branch where we have these five examples.
**[2:26]** Let's see off splitting criteria is to keep splitting
**[2:29]** until everything in the node belongs to a single class,
**[2:32]** so either all cancel all nodes.
**[2:34]** We will look at this node and
**[2:36]** see if it meets the splitting criteria,
**[2:38]** and it does not because there is
**[2:40]** a mix of cats and dogs here.
**[2:41]** The next step is to then pick a feature to split on.
**[2:47]** We then go through the features one at a time and compute
**[2:50]** the information gain of each of
**[2:52]** those features as if this node,
**[2:56]** were the new root node of a decision tree that was
**[3:00]** trained using just five training examples shown here.
**[3:05]** We would compute the information gain for
**[3:08]** splitting on the whiskers feature,
**[3:10]** the information gain on splitting on the face shape feature.
**[3:14]** It turns out that the information gain
**[3:16]** for splitting on ear shape will be
**[3:17]** zero because all of these have the same point ear shape.
**[3:22]** Between whiskers and face shape,
**[3:26]** face shape turns out to have a highest information gain.
**[3:29]** We're going to split on face shape and that
**[3:32]** allows us to build
**[3:33]** left and right sub branches as follows.
**[3:36]** For the left sub-branch, we
**[3:38]** check for the criteria for whether or
**[3:40]** not we should stop splitting and we have all cats here.
**[3:44]** The stopping criteria is met and we create
**[3:47]** a leaf node that makes a prediction of cat.
**[3:50]** For the right sub-branch,
**[3:51]** we find that it is all dogs.
**[3:54]** We will also stop splitting since we've met
**[3:57]** the splitting criteria and put a leaf node there,
**[4:00]** that predicts not cat.
**[4:03]** Having built out this left subtree,
**[4:06]** we can now turn our attention to
**[4:08]** building the right subtree.
**[4:10]** Let me now again cover up
**[4:12]** the root node and the entire left subtree.
**[4:15]** To build out the right subtree,
**[4:17]** we have these five examples here.
**[4:19]** Again, the first thing we do is check if
**[4:22]** the criteria to stop splitting has been met,
**[4:25]** their criteria being met or not.
**[4:27]** All the examples are a single class,
**[4:29]** we've not met that criteria.
**[4:31]** We'll decide to keep
**[4:34]** splitting in this right sub-branch as well.
**[4:37]** In fact, the procedure for building
**[4:39]** the right sub-branch will be a lot
**[4:41]** as if you were training
**[4:43]** a decision tree learning algorithm from scratch,
**[4:45]** where the dataset you have
**[4:47]** comprises just these five training examples.
**[4:52]** Again, computing information gain
**[4:55]** for all of the possible features to split on,
**[4:58]** you find that the whiskers feature
**[5:01]** use the highest information gain.
**[5:03]** Split this set of five examples
**[5:04]** according to whether whiskers are present or absent.
**[5:07]** Check if the criteria to stop splitting are met
**[5:11]** in the left and right
**[5:13]** sub-branches here and decide that they are.
**[5:15]** You end up with leaf nodes that predict cat and dog cat.
**[5:19]** This is the overall process
**[5:22]** for building the decision tree.
**[5:25]** Notice that there's
**[5:27]** interesting aspects of what we've done,
**[5:29]** which is after we decided what to
**[5:32]** split on at the root node,
**[5:34]** the way we built the left subtree was by
**[5:38]** building a decision tree on a subset of five examples.
**[5:43]** The way we built the right subtree was by, again,
**[5:47]** building a decision tree on a subset of five examples.
**[5:51]** In computer science, this is an example
**[5:54]** of a recursive algorithm.
**[5:57]** All that means is the way you build
**[5:59]** a decision tree at the root is by
**[6:02]** building other smaller decision trees
**[6:04]** in the left and the right sub-branches.
**[6:08]** Recursion in computer science
**[6:11]** refers to writing code that calls itself.
**[6:13]** The way this comes up in building a decision tree is you
**[6:18]** build the overall decision tree by building
**[6:21]** smaller sub-decision trees and
**[6:23]** then putting them all together.
**[6:25]** That's why if you look at
**[6:27]** software implementations of decision trees,
**[6:30]** you'll see sometimes references to a recursive algorithm.
**[6:34]** But if you don't feel like you've fully understood
**[6:37]** this concept of recursive algorithms,
**[6:39]** don't worry about it.
**[6:40]** You still be able to fully
**[6:42]** complete this week's assignments,
**[6:44]** as well as use libraries to get
**[6:46]** decision trees to work for yourself.
**[6:48]** But if you're implementing
**[6:50]** a decision tree algorithm from scratch,
**[6:52]** then a recursive algorithm turns
**[6:55]** out to be one of the steps you'd have to implement.
**[6:59]** By the way, you may be wondering how to
**[7:01]** choose the maximum depth parameter.
**[7:03]** There are many different possible choices,
**[7:07]** but some of the open-source libraries will
**[7:09]** have good default choices that you can use.
**[7:12]** One intuition is, the larger the maximum depth,
**[7:16]** the bigger the decision tree you're willing to build.
**[7:19]** This is a bit like fitting
**[7:21]** a higher degree polynomial
**[7:23]** or training a larger neural network.
**[7:25]** It lets the decision tree learn a more complex model,
**[7:28]** but it also increases the risk of overfitting
**[7:31]** if this fitting a very complex function to your data.
**[7:35]** In theory, you could use
**[7:37]** cross-validation to pick parameters
**[7:39]** like the maximum depth,
**[7:41]** where you try out different values
**[7:42]** of the maximum depth and
**[7:43]** pick what works best on the cross-validation set.
**[7:46]** Although in practice, the open-source libraries have
**[7:49]** even somewhat better ways
**[7:51]** to choose this parameter for you.
**[7:52]** Or another criteria that
**[7:55]** you can use to decide when to stop splitting is
**[7:57]** if the information gained
**[7:59]** from an additional split is less than a certain threshold.
**[8:03]** If any feature is splint on,
**[8:06]** achieves only a small reduction in entropy
**[8:08]** or a very small information gain,
**[8:11]** then you might also decide to not bother.
**[8:13]** Finally, you can also decide to stop splitting
**[8:17]** when the number of examples in
**[8:18]** the node is below a certain threshold.
**[8:21]** That's the process of building a decision tree.
**[8:24]** Now that you've learned the decision tree,
**[8:26]** if you want to make a prediction,
**[8:28]** you can then follow the procedure that you
**[8:30]** saw in the very first video of this week,
**[8:32]** where you take a new example,
**[8:34]** say a test example,
**[8:35]** and started a route and keep on
**[8:37]** following the decisions down until you get to the leaf node,
**[8:41]** which then makes the prediction.
**[8:43]** Now that you know the basic
**[8:45]** decision tree learning algorithm,
**[8:47]** in the next few videos,
**[8:48]** I'd like to go into
**[8:49]** some further refinements of this algorithm.
**[8:52]** So far we've only used features
**[8:54]** to take on two possible values.
**[8:56]** But sometimes you have
**[8:58]** a feature that takes on categorical or discrete values,
**[9:01]** but maybe more than two values.
**[9:03]** Let's take a look in the next video at
**[9:05]** how to handle that case.
