---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 4
section: Tree ensembles
item_title: When to use decision trees
duration: 6 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/vh1V7/when-to-use-decision-trees
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# When to use decision trees — Transcript

**[0:01]** Both decision trees, including
**[0:04]** tree ensembles as well as
**[0:05]** neural networks are very powerful,
**[0:07]** very effective learning algorithms.
**[0:09]** When should you pick one or the other?
**[0:12]** Let's look at some of the pros and cons of each.
**[0:14]** Decision trees and tree ensembles will
**[0:17]** often work well on tabular data,
**[0:19]** also called structured data.
**[0:21]** What that means is if your dataset looks like
**[0:25]** a giant spreadsheet then
**[0:27]** decision trees would be worth considering.
**[0:30]** For example, in
**[0:31]** the housing price prediction application we had
**[0:34]** a dataset with features
**[0:36]** corresponding to the size of the house,
**[0:39]** the number of bedrooms, the number of floors,
**[0:40]** and the age at home.
**[0:42]** That type of data stored in a spreadsheet with
**[0:45]** either categorical or continuous
**[0:48]** valued features and both for
**[0:50]** classification or for
**[0:52]** regression task where you're trying to
**[0:53]** predict a discrete category or predict a number.
**[0:56]** All of these problems are ones
**[0:59]** that decision trees can do well on.
**[1:02]** In contrast, I will not recommend using
**[1:05]** decision trees and tree ensembles on unstructured data.
**[1:09]** That's data such as images, video, audio,
**[1:12]** and texts that you're less likely to
**[1:14]** store in a spreadsheet format.
**[1:17]** Neural networks as we'll see in a second will tend to
**[1:19]** work better for unstructured data task.
**[1:22]** One huge advantage of decision trees and tree ensembles
**[1:25]** is that they can be very fast to train.
**[1:29]** You might remember this diagram from the previous week
**[1:33]** in which we talked about
**[1:35]** the iterative loop of machine learning development.
**[1:38]** If your model takes many hours to train then
**[1:42]** that limits how quickly you can go through
**[1:44]** this loop and improve the performance of your algorithm.
**[1:46]** But because decision trees,
**[1:49]** including tree ensembles tend
**[1:51]** to be pretty fast to train,
**[1:53]** that allows you to go to this loop more quickly and
**[1:56]** maybe more efficiently improve
**[1:58]** the performance of your learning algorithm.
**[2:00]** Finally, small decision trees maybe human interpretable.
**[2:05]** If you are training just a single decision tree
**[2:08]** and that decision tree has only say
**[2:11]** a few dozen nodes you may be able to print out
**[2:14]** a decision tree to
**[2:15]** understand exactly how it's making decisions.
**[2:18]** I think that the interpretability of
**[2:21]** decision trees is sometimes a bit overstated
**[2:24]** because when you build an ensemble of
**[2:26]** 100 trees and if each of
**[2:27]** those trees has hundreds of nodes,
**[2:30]** then looking at that ensemble to figure out what it's
**[2:33]** doing does become difficult and
**[2:35]** may need some separate visualization techniques.
**[2:37]** But if you have a small decision tree you can
**[2:40]** actually look at it and see, oh,
**[2:42]** it's classifying whether something is a cat
**[2:45]** by looking at certain features in certain ways.
**[2:48]** If you've decided to use
**[2:50]** a decision tree or tree ensemble,
**[2:52]** I would probably use
**[2:55]** XGBoost for most of the applications I will work on.
**[2:59]** One slight downside of a tree ensemble is that it
**[3:02]** is a bit more expensive than a single decision tree.
**[3:05]** If you had a very constrained computational budget
**[3:09]** you might use a single decision tree
**[3:12]** but other than that setting I would almost always
**[3:15]** use a tree ensemble and use XGBoost in particular.
**[3:18]** How about neural networks?
**[3:20]** In contrast to decision trees and tree ensembles,
**[3:24]** it works well on all types of data,
**[3:26]** including tabular or structured
**[3:28]** data as well as unstructured data.
**[3:30]** As well as mixed data that includes
**[3:32]** both structured and unstructured components.
**[3:35]** Whereas on tabular structured data,
**[3:39]** neural networks and decision trees are often both
**[3:42]** competitive on unstructured data, such as images,
**[3:45]** video, audio, and text,
**[3:47]** a neural network will really be
**[3:49]** the preferred algorithm and
**[3:50]** not the decision tree or a tree ensemble.
**[3:53]** On the downside though,
**[3:55]** neural networks may be slower than a decision tree.
**[4:00]** A large neural network can
**[4:01]** just take a long time to train.
**[4:04]** Other benefits of neural networks includes that it
**[4:07]** works with transfer learning and this
**[4:10]** is really important because for many applications we
**[4:13]** have only a small dataset being able to
**[4:16]** use transfer learning and carry out pre-training on
**[4:20]** a much larger dataset that is
**[4:22]** critical to getting competitive performance.
**[4:26]** Finally, if you're building a system of
**[4:28]** multiple machine learning models working together,
**[4:31]** it might be easier to string together and
**[4:34]** train multiple neural networks
**[4:35]** than multiple decision trees.
**[4:37]** The reasons for this are quite technical and you
**[4:40]** don't need to worry about
**[4:41]** it for the purpose of this course.
**[4:43]** But it relates to that even when
**[4:45]** you string together multiple neural networks
**[4:47]** you can train them all together using gradient descent.
**[4:51]** Whereas for decision trees you can only train
**[4:54]** one decision tree at a time. That's it.
**[4:58]** You've reached the end of the videos for
**[5:00]** this course on Advanced Learning Algorithms.
**[5:03]** Thank you for sticking with me all this way
**[5:04]** and congratulations on getting to
**[5:06]** the end of the videos on advanced learning algorithms.
**[5:09]** You've now learned how to
**[5:11]** build and use both neural networks
**[5:13]** and decision trees and also
**[5:15]** heard about a variety of tips,
**[5:17]** practical advice on how to get
**[5:19]** these algorithms to work well for you.
**[5:22]** But even if all that you've seen on supervised learning,
**[5:25]** that's just part of what learning algorithms can do.
**[5:29]** Supervised learnings need labeled datasets
**[5:32]** with the labels Y on your training set.
**[5:35]** There's another set of very powerful algorithms
**[5:37]** called unsupervised learning algorithms
**[5:39]** where you don't even need
**[5:40]** labels Y for the algorithm to figure out
**[5:43]** very interesting patterns and
**[5:45]** to do things with the data that you have.
**[5:47]** I look forward to seeing you also in
**[5:50]** the third and final course of
**[5:52]** this specialization which should
**[5:53]** be on unsupervised learning.
**[5:56]** Now, before you finish up this course
**[5:58]** I hope you also enjoy practicing
**[6:00]** the ideas of decision trees in
**[6:03]** their practice quizzes and in their practice labs.
**[6:05]** I'd like to wish you the best of luck in
**[6:08]** the practice labs or for
**[6:10]** those of you that may be Star Wars fans,
**[6:12]** let me say, may the forest be with you.
