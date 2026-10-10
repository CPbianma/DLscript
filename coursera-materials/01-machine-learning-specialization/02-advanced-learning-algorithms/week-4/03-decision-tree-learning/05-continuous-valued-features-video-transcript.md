---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 4
section: Decision tree learning
item_title: Continuous valued features
duration: 7 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/a4v1O/continuous-valued-features
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# Continuous valued features — Transcript

**[0:01]** Let's look at how you can modify decision tree to work with
**[0:04]** features that aren't just discrete values but continuous values.
**[0:07]** That is features that can be any number.
**[0:10]** Let's start with an example, I have modified the cat adoption center
**[0:15]** of data set to add one more feature which is the weight of the animal.
**[0:20]** In pounds on average between cats and dogs, cats are a little bit lighter
**[0:25]** than dogs, although there are some cats are heavier than some dogs.
**[0:31]** But so the weight of an animal is a useful feature for
**[0:34]** deciding if it is a cat or not.
**[0:38]** So how do you get a decision tree to use a feature like this?
**[0:42]** The decision tree learning algorithm will proceed similarly as before except that
**[0:47]** rather than constraint splitting just on ear shape, face shape and whiskers.
**[0:51]** You have to consist splitting on ear shape, face shape whisker or weight.
**[0:56]** And if splitting on the weight feature gives better information
**[1:00]** gain than the other options.
**[1:01]** Then you will split on the weight feature.
**[1:04]** But how do you decide how to split on the weight feature?
**[1:09]** Let's take a look.
**[1:10]** Here's a plot of the data at the root.
**[1:13]** Not a plotted on the horizontal axis.
**[1:16]** The way to the animal and the vertical axis is cat on top and not cat below.
**[1:23]** So the vertical axis indicates the label, y being 1 or 0.
**[1:28]** The way we were split on the weight feature would be if we were to split
**[1:32]** the data based on whether or not the weight is less than or
**[1:36]** equal to some value.
**[1:37]** Let's say 8 or some of the number.
**[1:40]** That will be the job of the learning algorithm to choose.
**[1:43]** And what we should do when constraints splitting on the weight
**[1:48]** feature is to consider many different values of this threshold and
**[1:53]** then to pick the one that is the best.
**[1:56]** And by the best I mean the one that results in the best information gain.
**[2:03]** So in particular, if you were considering splitting the examples
**[2:08]** based on whether the weight is less than or equal to 8,
**[2:12]** then you will be splitting this data set into two subsets.
**[2:16]** Where the subset on the left has two cats and
**[2:19]** the subset on the right has three cats and five dogs.
**[2:24]** So if you were to calculate our usual information gain calculation,
**[2:31]** you'll be computing the entropy at the root node N C p
**[2:36]** f 0.5 minus now 2/10 times entropy of the left split has two other two cats.
**[2:44]** So it should be 2/2 plus the right split has
**[2:48]** eight out of 10 examples and an entropy F.
**[2:53]** That's of the eight examples on the right three cats.
**[2:57]** To entry of 3/8 and this turns out to be 0.24.
**[3:02]** So this would be information gain if you were to split on whether the weight is
**[3:07]** less than equal to 8 but we should try other values as well.
**[3:12]** So what if you were to split on whether or not the weight is less than equal to 9 and
**[3:19]** that corresponds to this new line over here.
**[3:23]** And the information gain calculation becomes H (0.5) minus.
**[3:29]** So now we have four examples and left split all cats.
**[3:33]** So that's 4/10 times entropy of 4/4 plus six
**[3:38]** examples on the right of which you have one cat.
**[3:42]** So that's 6/10 times each of 1/6, which is equal to turns out 0.61.
**[3:49]** So the information gain here looks much better is 0.61
**[3:54]** information gain which is much higher than 0.24.
**[3:58]** Or we could try another value say 13.
**[4:01]** And the calculation turns out to look like this, which is 0.40.
**[4:09]** In the more general case, we'll actually try not just three values,
**[4:14]** but multiple values along the X axis.
**[4:16]** And one convention would be to sort all of the examples according to the weight or
**[4:22]** according to the value of this feature and
**[4:25]** take all the values that are mid points between the sorted list of training.
**[4:30]** Examples as the values for consideration for this threshold over here.
**[4:36]** This way, if you have 10 training examples,
**[4:39]** you will test nine different possible values for this threshold and
**[4:43]** then try to pick the one that gives you the highest information gain.
**[4:47]** And finally, if the information gained from splitting on a given value of this
**[4:53]** threshold is better than the information gain from splitting on any other feature,
**[4:58]** then you will decide to split that node at that feature.
**[5:03]** And in this example an information gain of 0.61 turns out to be
**[5:07]** higher than that of any other feature.
**[5:10]** It turns out they're actually two thresholds.
**[5:13]** And so assuming the algorithm chooses this feature to split on,
**[5:18]** you will end up splitting the data set according to whether or
**[5:23]** not the weight of the animal is less than equal to £9.
**[5:28]** And so you end up with two subsets of the data like this and
**[5:32]** you can then build recursively, additional decision trees using
**[5:36]** these two subsets of the data to build out the rest of the tree.
**[5:41]** So to summarize to get the decision tree to work
**[5:44]** on continuous value features at every note.
**[5:47]** When consuming splits, you would just consider different values to split on,
**[5:51]** carry out the usual information gain calculation and decide to split on that
**[5:56]** continuous value feature if it gives the highest possible information gain.
**[6:01]** So that's how you get the decision tree to work with continuous value features.
**[6:06]** Try different thresholds, do the usual information gain calculation and
**[6:11]** split on the continuous value feature with the selected threshold if it gives you
**[6:16]** the best possible information gain out of all possible features to split on.
**[6:21]** And that's it for the required videos on the core decision tree algorithm
**[6:26]** After there's there is an optional video you can watch or
**[6:29]** not that generalizes the decision tree learning algorithm to regression trees.
**[6:35]** So far, we've only talked about using decision trees to make predictions that
**[6:39]** are classifications predicting a discrete category, such as cat or not cat.
**[6:44]** But what if you have a regression problem where you want to
**[6:47]** predict a number in the next video.
**[6:49]** I'll talk about a generalization of decision trees to handle that.
