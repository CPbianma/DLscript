---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 4
section: Decision trees
item_title: Learning Process
duration: 11 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/5ysdd/learning-process
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# Learning Process — Transcript

**[0:00]** The process of building
**[0:03]** a decision tree given a training set has a few steps.
**[0:06]** In this video, let's take a look at
**[0:08]** the overall process of
**[0:10]** what you need to do to build a decision tree.
**[0:12]** Given a training set of 10 examples
**[0:15]** of cats and dogs like you saw in the last video.
**[0:19]** The first step of decision tree learning is,
**[0:23]** we have to decide what feature to use at the root node.
**[0:28]** That is the first node at
**[0:30]** the very top of the decision tree.
**[0:32]** Via an algorithm that we'll
**[0:34]** talk about in the next few videos.
**[0:35]** Let's say that we decided to
**[0:37]** pick as the feature and the root node,
**[0:40]** the ear shape feature.
**[0:42]** What that means is we will decide
**[0:44]** to look at all of our training examples,
**[0:47]** all ten examples shown here,
**[0:49]** I split them according to
**[0:51]** the value of the ear shape feature.
**[0:54]** In particular, let's pick out the five examples with
**[0:58]** pointy ears and move them over down to the left.
**[1:03]** Let's pick the five examples with
**[1:06]** floppy ears and move them down to the right.
**[1:09]** The second step is focusing just on
**[1:11]** the left part or sometimes called the left branch
**[1:14]** of the decision tree to
**[1:16]** decide what nodes to put over there.
**[1:20]** In particular, what feature that we want
**[1:24]** to split on or what feature do we want to use next.
**[1:28]** Via an algorithm that again,
**[1:30]** we'll talk about later this week.
**[1:32]** Let's say you decide to use the face shape feature there.
**[1:36]** What we'll do now is take these five examples and split
**[1:40]** these five examples into
**[1:41]** two subsets based on their value of the face shape.
**[1:45]** We'll take the four examples out of these
**[1:49]** five with a round face shape
**[1:51]** and move them down to the left.
**[1:53]** The one example with
**[1:55]** a not round face shape and move it down to the right.
**[1:59]** Finally, we notice that
**[2:01]** these four examples are all cats four of them are cats.
**[2:06]** Rather than splitting further,
**[2:09]** were created a leaf node that makes
**[2:11]** a prediction that things that
**[2:12]** get down to that node of cats.
**[2:15]** Over here we notice that none of
**[2:17]** the examples zero of the one examples are
**[2:20]** cats or alternative 100 percent
**[2:23]** of the examples here are dogs.
**[2:25]** We can create a leaf node here that
**[2:28]** makes a prediction of not cat.
**[2:30]** Having done this on the left part to
**[2:33]** the left branch of this decision tree,
**[2:35]** we now repeat a similar process on
**[2:37]** the right part or the right branch of this decision tree.
**[2:40]** Focus attention on just these five examples,
**[2:43]** which contains one cat and four dogs.
**[2:46]** We would have to pick some feature over
**[2:49]** here to use the split these five examples further,
**[2:53]** if we end up choosing the whiskers feature,
**[2:56]** we would then split these five examples based on
**[3:00]** where the whiskers are present or absent, like so.
**[3:05]** You notice that one out of one examples on the left for
**[3:09]** cats and zeros out of four are cats.
**[3:13]** Each of these nodes is completely pure,
**[3:17]** meaning that is, all cats or
**[3:20]** not cats and there's no longer a mix of cats and dogs.
**[3:23]** We can create these leaf nodes,
**[3:26]** making a cat prediction on the left
**[3:28]** and a nightcap prediction here on the right.
**[3:31]** This is a process of building a decision tree.
**[3:35]** Through this process,
**[3:37]** there were a couple of key decisions that we
**[3:39]** had to make at various steps during the algorithm.
**[3:42]** Let's talk through what
**[3:44]** those key decisions were and we'll keep on
**[3:46]** session of the details of how to make
**[3:48]** these decisions in the next few videos.
**[3:50]** The first key decision was,
**[3:53]** how do you choose
**[3:55]** what features to use to split on at each node?
**[3:58]** At the root node,
**[4:00]** as well as on
**[4:01]** the left branch and
**[4:03]** the right branch of the decision tree,
**[4:04]** we had to decide if there were
**[4:07]** a few examples at
**[4:09]** that node comprising a mix of cats and dogs.
**[4:11]** Do you want to split on
**[4:13]** the ear-shaped feature or
**[4:15]** the facial feature or the whiskers feature?
**[4:17]** We'll see in the next video,
**[4:19]** that decision trees will choose what feature to split
**[4:22]** on in order to try to maximize purity.
**[4:25]** By purity, I mean,
**[4:27]** you want to get to what subsets,
**[4:29]** which are as close as possible to all cats or all dogs.
**[4:33]** For example, if we had a feature that said,
**[4:36]** does this animal have cat DNA,
**[4:39]** we don't actually have this feature.
**[4:41]** But if we did, we could have
**[4:42]** split on this feature at the root node,
**[4:44]** which would have resulted in five out of
**[4:47]** five cats in the left branch
**[4:49]** and zero of the five cats in the right branch.
**[4:51]** Both these left and
**[4:52]** right subsets of the data are completely pure,
**[4:56]** meaning that there's only one class,
**[4:59]** either cats only or not cats
**[5:01]** only in both of these left and right sub-branches,
**[5:05]** which is why the cat DNA feature if we had this feature,
**[5:09]** would have been a great feature to use.
**[5:11]** But with the features that we actually have,
**[5:14]** we had to decide,
**[5:16]** what is the split on year shape,
**[5:18]** which result in four out of
**[5:19]** five examples on the left being cats,
**[5:22]** and one of the five examples on
**[5:24]** the right being cats or face
**[5:26]** shape where it resulted in the four of the
**[5:28]** seven on the left and one of the three on the right,
**[5:31]** or whiskers, which resulted in three out four examples
**[5:35]** being cast on the left and two out of
**[5:36]** six being not cats on the right.
**[5:39]** The decision tree learning algorithm has
**[5:43]** to choose between ear-shaped,
**[5:45]** face shape, and whiskers.
**[5:47]** Which of these features results in
**[5:51]** the greatest purity of
**[5:53]** the labels on the left and right sub branches?
**[5:57]** Because it is if you can get to
**[6:00]** a highly pure subsets of examples,
**[6:04]** then you can either predict
**[6:06]** cat or predict not cat and get it mostly right.
**[6:10]** The next video on entropy,
**[6:13]** we'll talk about how to estimate
**[6:15]** impurity and how to minimize impurity.
**[6:19]** The first decision we have to make when
**[6:21]** learning a decision tree is how to choose which feature
**[6:24]** to split on on each node.
**[6:27]** The second key decision you need to make when building
**[6:30]** a decision tree is to decide when do you stop splitting.
**[6:35]** The criteria that we use just now
**[6:37]** was until I know there's either 100 percent,
**[6:40]** all cats or a 100 percent of dogs and not cats.
**[6:44]** Because at that point is seems natural to build
**[6:47]** a leaf node that just makes a classification prediction.
**[6:51]** Alternatively, you might also
**[6:53]** decide to stop splitting when
**[6:56]** splitting and no further results in
**[6:58]** the tree exceeding the maximum depth.
**[7:01]** Where the maximum depth
**[7:03]** that you allow the tree to go to,
**[7:04]** is a parameter that you could just say.
**[7:07]** In decision tree,
**[7:09]** the depth of a node is defined as the number of hops
**[7:14]** that it takes to get from the root node that
**[7:16]** is denoted the very top to that particular node.
**[7:19]** So the root node takes zero hops,
**[7:22]** to get to itself and is at Depth 0.
**[7:25]** The notes below it are at depth one
**[7:28]** and in those below it would be at Depth 2.
**[7:32]** If you had decided that
**[7:35]** the maximum depth of the decision tree is say two,
**[7:38]** then you would decide not to split any nodes below
**[7:44]** this level so that the tree never gets to Depth 3.
**[7:50]** One reason you might want to
**[7:53]** limit the depth of the decision tree
**[7:55]** is to make sure for us to tree doesn't
**[7:58]** get too big and unwieldy and second,
**[8:01]** by keeping the tree small,
**[8:02]** it makes it less prone to overfitting.
**[8:05]** Another criteria you might use to decide to stop
**[8:08]** splitting might be if
**[8:10]** the improvements in the purity score,
**[8:12]** which you see in
**[8:13]** a later video of below a certain threshold.
**[8:16]** If splitting a node results in minimum improvements to
**[8:20]** purity or you see later is
**[8:22]** actually decreases in impurity.
**[8:26]** But if the gains are too small,
**[8:28]** they might not bother.
**[8:30]** Again, both to keep the trees smaller
**[8:32]** and to reduce the risk of overfitting.
**[8:35]** Finally, if the number of
**[8:38]** examples that a node is below a certain threshold,
**[8:42]** then you might also decide to stop splitting.
**[8:45]** For example, if at the root node
**[8:48]** we have split on the face shape feature,
**[8:51]** then the right branch will have had
**[8:54]** just three training examples with
**[8:56]** one cat and two dogs and rather
**[8:59]** than splitting this into even smaller subsets,
**[9:02]** if you decided not to split
**[9:04]** further set of examples
**[9:06]** with just three of your examples,
**[9:09]** then you will just create a decision node and
**[9:12]** because there are mainly dogs, 2 out  three adults here,
**[9:17]** this would be a node and this makes
**[9:18]** a prediction of not cat.
**[9:20]** Again, one reason you might decide this is not worth
**[9:24]** splitting on is to keep the tree
**[9:26]** smaller and to avoid overfitting.
**[9:28]** When I look at decision tree learning
**[9:30]** algorithms myself, sometimes I feel like,
**[9:32]** boy, there's a lot of different pieces and
**[9:34]** lots of different things going on in this algorithm.
**[9:37]** Part of the reason it might feel
**[9:39]** is in the evolution of decision trees.
**[9:42]** There was one researcher that proposed a basic version
**[9:45]** of decision trees and then a different researcher said,
**[9:48]** oh, we can modify this thing this way,
**[9:51]** such as his new criteria for splitting.
**[9:53]** Then a different researcher
**[9:55]** comes up with a different thing like, oh,
**[9:56]** maybe we should stop splitting
**[9:58]** when it reaches a certain maximum depth.
**[9:59]** Over the years, different researchers came up
**[10:02]** with different refinements to the algorithm.
**[10:04]** As a result of that,
**[10:06]** it does work really well but we look
**[10:08]** at all the details of how to implement a decision
**[10:10]** tree. It feels a lot of different pieces such as
**[10:14]** why there's so many different ways to
**[10:15]** decide when to stop splitting.
**[10:17]** If it feels like a somewhat complicated,
**[10:20]** messy algorithm to you, it does to me too.
**[10:23]** But these different pieces,
**[10:25]** they do fit together into
**[10:26]** a very effective learning algorithm and what you
**[10:29]** learn in this course is the key,
**[10:31]** most important ideas for how to make it work well,
**[10:34]** and then at the end of this week,
**[10:36]** I'll also share with you some guidance,
**[10:38]** some suggestions for how to use
**[10:40]** open source packages so that you
**[10:43]** don't have to have too complicated
**[10:44]** the procedure for making all these decisions.
**[10:47]** Like how do I decide to stop splitting?
**[10:49]** You really get these algorithms to work well for yourself.
**[10:52]** But I want to reassure you that if
**[10:54]** this algorithm seems complicated and messy,
**[10:56]** it frankly does to me too,
**[10:57]** but it does work well.
**[10:59]** Now, the next key decision that I want to dive
**[11:04]** more deeply into is how do you
**[11:06]** decide how to split a node.
**[11:08]** In the next video, let's take a look
**[11:10]** at this definition of entropy,
**[11:12]** which would be a way for us to measure purity,
**[11:15]** or more precisely, impurity in a node.
**[11:18]** Let's go on to the next video.
