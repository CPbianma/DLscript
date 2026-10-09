---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 4
section: Decision tree learning
item_title: Using one-hot encoding of categorical features
duration: 5 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/RQVdw/using-one-hot-encoding-of-categorical-features
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Using one-hot encoding of categorical features — Transcript

**[0:02]** In the example we've seen so
**[0:04]** far each of the features could take on only one of two possible values.
**[0:09]** The ear shape was either pointy or floppy, the face shape was either round or
**[0:13]** not round and whiskers were either present or absent.
**[0:17]** But whether if you have features that can take on more than two discrete values,
**[0:21]** in this video we'll look at how you can use one-hot encoding
**[0:25]** to address features like that.
**[0:28]** Here's a new training set for our pet adoption center application
**[0:32]** where all the data is the same except for the ear shaped feature.
**[0:37]** Rather than ear shape only being pointy and floppy,
**[0:42]** it can now also take on an oval shape.
**[0:46]** And so the initial feature is still a categorical value feature but
**[0:51]** it can take on three possible values instead of just two possible values.
**[0:57]** And this means that when you split on this feature you end up creating
**[1:02]** three subsets of the data and end up building three sub branches for this tree.
**[1:10]** But in this video I'd like to describe a different way of addressing features
**[1:15]** that can take on more than two values, which is to use the one-hot encoding.
**[1:21]** In particular rather than using an ear shaped feature,
**[1:25]** they can take on any of three possible values.
**[1:28]** We're instead going to create three new features where one feature is,
**[1:34]** does this animal have pointy ears, a second is does their floppy ears and
**[1:40]** the third is does it have oval ears.
**[1:43]** And so for the first example whereas we previously had ear shape as pointy,
**[1:49]** we are now instead say that this animal has a value for
**[1:54]** the pointy ear feature of 1 and 0 for floppy and oval.
**[1:59]** Whereas previously for the second example,
**[2:02]** we previously said it had oval ears now we'll say that it has a value of 0 for
**[2:08]** pointy ears because it doesn't have pointy ears.
**[2:11]** It also doesn't have floppy ears but it does have oval ears which is why this
**[2:16]** value here is 1 and so on for the rest of the examples in the data set.
**[2:21]** And so instead of one feature taking on three possible values,
**[2:26]** we've now constructed three new features each of which can take
**[2:31]** on only one of two possible values, either 0 or 1.
**[2:35]** In a little bit more detail, if a categorical feature can take on k
**[2:40]** possible values, k was three in our example, then we will replace
**[2:45]** it by creating k binary features that can only take on the values 0 or 1.
**[2:52]** And you notice that among all of these three features,
**[2:56]** if you look at any role here, exactly 1 of the values is equal to 1.
**[3:02]** And that's what gives this method of future construction the name one-hot
**[3:07]** encoding.
**[3:08]** And because one of these features will always take on the value 1 that's
**[3:12]** the hot feature and hence the name one-hot encoding.
**[3:17]** And with this choice of features we're now back to the original setting of where
**[3:21]** each feature only takes on one of two possible values, and so
**[3:25]** the decision tree learning algorithm that we've seen previously will apply to
**[3:30]** this data with no further modifications.
**[3:33]** Just an aside, even though this week's material has been focused on
**[3:38]** training decision tree models the idea of using one-hot encodings to
**[3:42]** encode categorical features also works for training neural networks.
**[3:48]** In particular if you were to take the face shape feature and
**[3:53]** replace round and not round with 1 and
**[3:56]** 0 where round gets matter 1, not round gets matter 0 and so on.
**[4:01]** And for whiskers similarly replace presence with 1 and absence with 0.
**[4:08]** They noticed that we have taken all the categorical features we had
**[4:13]** where we had three possible values for ear shape, two for face shape and
**[4:18]** one for whiskers and encoded as a list of these five features.
**[4:22]** Three from the one-hot encoding of ear shape, one from face shape and
**[4:27]** from whiskers and now this list of five features can also be fed to a new
**[4:32]** network or to logistic regression to try to train a cat classifier.
**[4:37]** So one-hot encoding is a technique that works not just for decision tree learning
**[4:42]** but also lets you encode categorical features using ones and zeros, so that it
**[4:48]** can be fed as inputs to a neural network as well which expects numbers as inputs.
**[4:54]** So that's it, with a one-hot encoding you can get your decision tree to work on
**[4:59]** features that can take on more than two discrete values and you can also apply
**[5:04]** this to neural networks or linear regression or logistic regression training.
**[5:09]** But how about features that are numbers that can take on any value,
**[5:14]** not just a small number of discrete values.
**[5:17]** In the next video let's look at how you can get the decision tree to handle
**[5:21]** continuous value features that can be any number.
