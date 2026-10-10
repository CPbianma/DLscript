---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 4
section: Tree ensembles
item_title: Random forest algorithm
duration: 6 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/7MtSD/random-forest-algorithm
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# Random forest algorithm — Transcript

**[0:02]** Now that we have a way to use sampling with replacement
**[0:05]** to create new training sets that are a bit similar to but
**[0:08]** also quite different from the original training set.
**[0:11]** We're ready to build our first tree ensemble algorithm.
**[0:14]** In particular in this video,
**[0:16]** we'll talk about the random forest algorithm which is one powerful tree
**[0:21]** ensamble algorithm that works much better than using a single decision tree.
**[0:26]** Here's how we can generate an ensemble of trees.
**[0:29]** If you are given a training set of size M, then for
**[0:34]** B equals 1 to capital b so we do this capital B times.
**[0:40]** You can use something with replacement to create a new training set of size M.
**[0:45]** So if you have 10 training examples, you will put the 10 training examples in
**[0:50]** that virtual bag and sample of replacement 10 times to generate a new training set
**[0:55]** with also 10 examples, and then you would train a decision tree on this data set.
**[1:01]** So here's the data set I've generated using something with replacement.
**[1:05]** If you look carefully,
**[1:07]** you may notice that some of the training examples are repeated and that's okay.
**[1:11]** And if you train the decision on this data said you end up with this decision tree.
**[1:17]** And having done this once, we would then go and repeat this a second time.
**[1:22]** Use something with replacement to generate another training set of M or
**[1:27]** 10 training examples.
**[1:29]** This again looks a bit like the original training set but
**[1:32]** it's also a little bit different.
**[1:34]** You then train the decision tree on this new data set and
**[1:37]** you end up with a somewhat different decision tree.
**[1:41]** And so on.
**[1:41]** And you may do this a total of capital B times.
**[1:45]** Typical choice of capital B the number of such trees you built might be
**[1:51]** around a 100 people recommend any value from Say 64, 128.
**[1:56]** And having built an ensemble of say 100 different trees,
**[2:00]** you would then when you're trying to make a prediction,
**[2:04]** get these trees all votes on the correct final prediction.
**[2:08]** It turns out that setting capital B to be larger, never hurts performance,
**[2:13]** but beyond a certain point, you end up with diminishing returns and
**[2:17]** it doesn't actually get that much better when B is much larger than say 100 or so.
**[2:24]** And that's why I never use say 1000 trees that just slows down the computation
**[2:28]** significantly without meaningfully increasing the performance of
**[2:32]** the overall algorithm.
**[2:35]** Just to give this particular algorithm a name.
**[2:38]** This specific instance creation of tree ensemble is sometimes also called a bagged
**[2:43]** decision tree.
**[2:45]** And that refers to putting your training examples in that virtual bag.
**[2:50]** And that's why also we use the let us lower case B an uppercase B
**[2:53]** here because that stands for bag.
**[2:56]** There's one modification to this album that will actually make it work even much
**[3:00]** better and that changes this algorithm the bagged decision tree into the random forest
**[3:05]** algorithm.
**[3:07]** The key idea is that even with this sampling with replacement procedure
**[3:12]** sometimes you end up with always using the same split at the root node and
**[3:17]** very similar splits near the root note.
**[3:20]** That didn't happen in this particular example where a small change the trainings
**[3:24]** that resulted in a different split at the root note.
**[3:28]** But for other training sets it's not uncommon that for many or
**[3:32]** even all capital B training sets, you end up with the same choice of
**[3:37]** feature at the root node and at a few of the nodes near the root node.
**[3:41]** So there's one modification to the algorithm to further try to randomize
**[3:46]** the feature choice at each node that can cause the set of trees and
**[3:51]** you learn to become more different from each other.
**[3:55]** So when you vote them, you end up with an even more accurate prediction.
**[3:59]** The way this is typically done is at every note when choosing
**[4:04]** a feature to use to split if end features are available.
**[4:08]** So in our example we had three features available rather than picking from all end
**[4:15]** features, we will instead pick a random subset of K less than N features.
**[4:21]** And allow the algorithm to choose only from that subset of K features.
**[4:27]** So in other words, you would pick K features as the allowed features and
**[4:32]** then out of those K features choose the one with the highest
**[4:36]** information gain as the choice of feature to use the split.
**[4:40]** When N is large, say n is Dozens or 10's or even hundreds.
**[4:44]** A typical choice for the value of K would be to choose it to be square root of N,
**[4:49]** In our example we have only three features and this technique tends to
**[4:54]** be used more for larger problems with a larger number of features.
**[4:58]** And will just further change the algorithm you end up with the random Forest
**[5:03]** algorithm which will work typically much better and
**[5:07]** becomes much more robust than just a single decision tree.
**[5:11]** One way to think about why this is more robust to than a single decision tree is
**[5:16]** the sampling with replacement procedure causes the algorithm to explore a lot of
**[5:21]** small changes to the data already and it's training different decision trees and
**[5:26]** is averaging over all of those changes to the data that the sampling
**[5:30]** with replacement procedure causes.
**[5:32]** And so this means that any little change further to the training set makes it less
**[5:37]** likely to have a huge impact on the overall output of the overall random
**[5:42]** forest algorithm.
**[5:43]** Because it's already explored and
**[5:45]** it's averaging over a lot of small changes to the training set.
**[5:49]** Before wrapping up this video there's just one more thought I want to share with you
**[5:55]** Which is, where does a machine learning engineer go camping?
**[5:58]** In a random forest.
**[6:00]** All right.
**[6:00]** Go and tell that joke to your friends.
**[6:02]** I hope you enjoy it.
**[6:04]** The random forest is an effective algorithm and I hope you better use it in your work.
**[6:08]** Beyond the random forest It turns out there's one other algorithm that works
**[6:13]** even better.
**[6:14]** Which is a boosted decision tree.
**[6:16]** In the next video,
**[6:17]** let's talk about a boosted decision tree algorithm called X G boost.
