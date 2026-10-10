---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 4
section: Decision trees
item_title: Decision tree model
duration: 7 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/HFvPH/decision-tree-model
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# Decision tree model — Transcript

**[0:01]** Welcome to the final week of
**[0:03]** this course on Advanced Learning Algorithms.
**[0:06]** One of the learning algorithms that is very
**[0:08]** powerful, widely used in many applications,
**[0:11]** also used by many to win
**[0:13]** machine learning competitions is
**[0:15]** decision trees and tree ensembles.
**[0:17]** Despite all the successes of decision trees,
**[0:21]** they somehow haven't received
**[0:22]** that much attention in academia,
**[0:24]** and so you may not hear about
**[0:26]** decision trees nearly that much,
**[0:28]** but it is a tool well worth having in your toolbox.
**[0:31]** In this week, we'll learn
**[0:32]** about decision trees and you'll see
**[0:34]** how to get them to work for yourself. Let's dive in.
**[0:37]** To explain how decision trees work,
**[0:39]** I'm going to use as a running example this week
**[0:41]** a cat classification example.
**[0:43]** You are running a cat adoption center
**[0:46]** and given a few features,
**[0:48]** you want to train a classifier to
**[0:50]** quickly tell you if an animal is a cat or not.
**[0:54]** I have here 10 training examples.
**[0:58]** Associated with each of these 10 examples,
**[1:01]** we're going to have features
**[1:03]** regarding the animal's ear shape,
**[1:06]** face shape, whether it has whiskers,
**[1:08]** and then the ground truth label that you want to
**[1:10]** predict this animal cat.
**[1:13]** The first example has pointy ears,
**[1:16]** round face, whiskers are present, and it is a cat.
**[1:19]** The second example has floppy ears,
**[1:22]** the face shape is not round,
**[1:23]** whiskers are present, and yes,
**[1:25]** that is a cat, and so on for the rest of the examples.
**[1:29]** This dataset has five cats and five dogs in it.
**[1:34]** The input features X are these three columns,
**[1:39]** and the target output that you want to predict,
**[1:43]** Y, is this final column of,
**[1:45]** is this a cat or not?
**[1:47]** In this example, the features X
**[1:49]** take on categorical values.
**[1:51]** In other words, the features take on
**[1:54]** just a few discrete values.
**[1:57]** Your shapes are either pointy or floppy.
**[2:00]** The face shape is either round or not round and
**[2:03]** whiskers are either present or absent.
**[2:06]** This is a binary classification task
**[2:09]** because the labels are also one or zero.
**[2:13]** For now, each of the features X_1,
**[2:17]** X_2, and X_3 take on only two possible values.
**[2:22]** We'll talk about features that can
**[2:24]** take on more than two possible values,
**[2:27]** as well as continuous-valued features later in this week.
**[2:32]** What is a decision tree?
**[2:34]** Here's an example of a model that you might get after
**[2:39]** training a decision tree learning
**[2:41]** algorithm on the data set that you just saw.
**[2:45]** The model that is output by
**[2:47]** the learning algorithm looks like a tree,
**[2:50]** and a picture like this is what
**[2:52]** computer scientists call a tree.
**[2:54]** If it looks nothing like
**[2:56]** the biological trees that you see out there to you,
**[2:59]** it's okay, don't worry about it.
**[3:01]** We'll go through an example to make sure that
**[3:03]** this computer science definition of
**[3:05]** a tree makes sense to you as well.
**[3:07]** Every one of these ovals or
**[3:11]** rectangles is called a node in the tree.
**[3:14]** The way this model works is
**[3:17]** if you have a new test example,
**[3:20]** she has a cat where the ear-shaped has pointy,
**[3:23]** face shape is round, and whiskers are present.
**[3:25]** The way this model will look at
**[3:27]** this example and make a classification decision
**[3:31]** is will start with
**[3:33]** this example at this topmost node of the tree,
**[3:37]** this is called the root node of the tree,
**[3:41]** and we will look at
**[3:44]** the feature written inside, which is ear shape.
**[3:47]** Based on the value of the ear shape of this example
**[3:50]** we'll either go left or go right.
**[3:54]** The value of the ear-shape with this example is pointy,
**[3:58]** and so we'll go down the left branch of the tree,
**[4:03]** like so, and end up at this oval node over here.
**[4:09]** We then look at the face shape of this example,
**[4:12]** which turns out to be round,
**[4:14]** and so we will follow this arrow down over here.
**[4:18]** The algorithm will make
**[4:20]** a inference that it thinks this is a cat.
**[4:24]** You get to this node and the algorithm will
**[4:27]** make a prediction that this is a cat.
**[4:30]** What I've shown on this slide is
**[4:32]** one specific decision tree model.
**[4:35]** To introduce a bit more terminology,
**[4:38]** this top-most node in the tree is called the root node.
**[4:45]** All of these nodes,
**[4:47]** that is, all of these oval shapes,
**[4:49]** but excluding the boxes at the bottom,
**[4:52]** all of these are called decision nodes.
**[4:55]** They're decision nodes because they look at
**[4:58]** a particular feature and
**[5:00]** then based on the value of the feature,
**[5:02]** cause you to decide whether to
**[5:04]** go left or right down the tree.
**[5:06]** Finally, these nodes at the bottom,
**[5:10]** these rectangular boxes are called leaf nodes.
**[5:14]** They make a prediction.
**[5:16]** If you haven't seen
**[5:18]** computer scientists' definitions of trees before,
**[5:21]** it may seem non-intuitive that the roots of the tree
**[5:25]** is at the top and the leaves of
**[5:27]** the tree are down at the bottom.
**[5:30]** Maybe one way to think about this is
**[5:33]** this is more akin to an indoor hanging plant,
**[5:35]** which is why the roots are up top,
**[5:37]** and then the leaves tend to
**[5:39]** fall down to the bottom of the tree.
**[5:41]** In this slide, I've shown
**[5:43]** just one example of a decision tree.
**[5:46]** Here are a few others.
**[5:47]** This is a different decision tree for trying to
**[5:50]** classify cat versus not cat.
**[5:53]** In this tree, to make a classification decision,
**[5:57]** you would again start at this topmost root node.
**[6:00]** Depending on their ear shape of an example,
**[6:02]** you'd go either left or right.
**[6:04]** If the ear shape is pointy,
**[6:06]** then you look at the whiskers feature,
**[6:08]** and depending on whether whiskers are present or absent,
**[6:10]** you go left or right to gain and
**[6:12]** classify cat versus not cat.
**[6:15]** Just for fun, here's
**[6:16]** a second example of a decision tree,
**[6:18]** here's a third one,
**[6:20]** and here's a fourth one.
**[6:22]** Among these different decision trees,
**[6:24]** some will do better and some will do worse on
**[6:27]** the training sets or on
**[6:28]** the cross-validation and test sets.
**[6:31]** The job of the decision tree learning algorithm is,
**[6:33]** out of all possible decision trees,
**[6:36]** to try to pick one that
**[6:38]** hopefully does well on the training set,
**[6:40]** and then also ideally generalizes
**[6:43]** well to new data such as
**[6:45]** your cross-validation and test sets as well.
**[6:48]** Seems like there are lots of
**[6:50]** different decision trees one
**[6:51]** could build for a given application.
**[6:53]** How do you get an algorithm to learn
**[6:55]** a specific decision tree based on a training set?
**[6:58]** Let's take a look at that in the next video.
