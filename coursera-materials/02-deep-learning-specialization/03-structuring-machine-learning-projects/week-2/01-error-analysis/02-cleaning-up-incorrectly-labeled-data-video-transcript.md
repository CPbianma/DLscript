---
type: video-transcript
specialization: Deep Learning Specialization
course: Structuring Machine Learning Projects
week: 2
section: Error Analysis
item_title: Cleaning Up Incorrectly Labeled Data
duration: 13 min
source_url: https://www.coursera.org/learn/machine-learning-projects/lecture/IGRRb/cleaning-up-incorrectly-labeled-data
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Cleaning Up Incorrectly Labeled Data — Transcript

**[0:00]** The data for your supervised learning problem comprises input X and output labels Y.
**[0:06]** What if you going through your data and you find that some of
**[0:09]** these output labels Y are incorrect,
**[0:12]** you have data which is incorrectly labeled?
**[0:14]** Is it worth your while to go in to fix up some of these labels? Let's take a look.
**[0:19]** In the cat classification problem,
**[0:21]** Y equals one for cats and zero for non cats.
**[0:25]** So, let's say you're looking through some data and that's a cat,
**[0:28]** that's not a cat, that's a cat,
**[0:30]** that's a cat, that's not a cat, that's at a cat.
**[0:33]** No, wait. That's actually not a cat.
**[0:35]** So this is an example with an incorrect label.
**[0:41]** So I've used the term, mislabeled examples,
**[0:43]** to refer to if your learning algorithm outputs the wrong value of Y.
**[0:48]** But I'm going to say, incorrectly labeled examples,
**[0:50]** to refer to if in the data
**[0:53]** set you have in the training set or the dev set or the test set,
**[0:56]** the label for Y, whatever a human label
**[0:59]** assigned to this piece of data, is actually incorrect.
**[1:02]** And that's actually a dog so that Y really should have been zero.
**[1:06]** But maybe the labeler got that one wrong.
**[1:10]** So if you find that your data has some incorrectly labeled examples,
**[1:14]** what should you do?
**[1:16]** Well, first, let's consider the training set.
**[1:21]** It turns out that deep learning algorithms
**[1:24]** are quite robust to random errors in the training set.
**[1:27]** So long as your errors or your incorrectly labeled examples,
**[1:32]** so long as those errors are not too far from random,
**[1:35]** maybe sometimes the labeler just wasn't paying attention or they accidentally,
**[1:41]** randomly hit the wrong key on the keyboard.
**[1:44]** If the errors are reasonably random,
**[1:46]** then it's probably okay to just leave
**[1:49]** the errors as they are and not spend too much time fixing them.
**[1:53]** There's certainly no harm to going into
**[1:55]** your training set and re-examining the labels and fixing them.
**[1:57]** Sometimes that is worth doing but your effort might be okay even if you don't.
**[2:02]** So long as the total data set size is big
**[2:05]** enough and the actual percentage of errors is maybe not too high.
**[2:10]** So I see a lot of machine learning algorithms that trained even when we know that
**[2:15]** there are few X mistakes in the training set labels and usually works okay.
**[2:21]** There is one caveat to this which is
**[2:24]** that deep learning algorithms are robust to random errors.
**[2:28]** They are less robust to systematic errors.
**[2:34]** So for example, if your labeler consistently labels white dogs as cats,
**[2:40]** then that is a problem because your classifier will
**[2:43]** learn to classify all white colored dogs as cats.
**[2:46]** But random errors or near random errors are
**[2:50]** usually not too bad for most deep learning algorithms.
**[2:54]** Now, this discussion has focused on what to do
**[2:57]** about incorrectly labeled examples in your training set.
**[3:00]** How about incorrectly labeled examples in your dev set or test set?
**[3:04]** If you're worried about the impact of
**[3:07]** incorrectly labeled examples on your dev set or test set,
**[3:10]** what I recommend you do is during error analysis to add
**[3:14]** one extra column so that you can also count up
**[3:17]** the number of examples where the label Y was incorrect.
**[3:22]** So for example, maybe when you count up the impact on a 100 mislabeled dev set examples,
**[3:29]** so you're going to find a 100 examples where
**[3:31]** your classifier's output disagrees with the label in your dev set.
**[3:35]** And sometimes for a few of those examples,
**[3:38]** your classifier disagrees with the label because the label was wrong,
**[3:42]** rather than because your classifier was wrong.
**[3:44]** So maybe in this example,
**[3:46]** you find that the labeler missed a cat in the background.
**[3:49]** So put the check mark there to signify that example 98 had an incorrect label.
**[3:55]** And maybe for this one,
**[3:57]** the picture is actually a picture of a drawing of a cat rather than a real cat.
**[4:01]** Maybe you want the labeler to have labeled that Y equals zero rather than Y equals one.
**[4:06]** And so put another check mark there.
**[4:09]** And just as you count up the percent of
**[4:12]** errors due to other categories like we saw in the previous video,
**[4:15]** you'd also count up the fraction of percentage of errors due to incorrect labels.
**[4:20]** Where the Y value in your dev set was wrong,
**[4:23]** and that accounted for why your learning algorithm
**[4:25]** made a prediction that differed from what the label on your data says.
**[4:32]** So the question now is,
**[4:33]** is it worthwhile going in to try to fix up this 6% of incorrectly labeled examples.
**[4:41]** My advice is, if it makes
**[4:43]** a significant difference to your ability to evaluate algorithms on your dev set,
**[4:47]** then go ahead and spend the time to fix incorrect labels.
**[4:50]** But if it doesn't make a significant difference to
**[4:52]** your ability to use the dev set to evaluate classifiers,
**[4:56]** then it might not be the best use of your time.
**[4:58]** Let me show you an example that illustrates what I mean by this.
**[5:02]** So, three numbers I recommend you look at to try to decide if
**[5:05]** it's worth going in and reducing the number of mislabeled examples are the following.
**[5:09]** I recommend you look at the overall dev set error.
**[5:12]** And so in the example we had from the previous video,
**[5:16]** we said that maybe our system has 90% overall accuracy.
**[5:20]** So 10% error.
**[5:22]** Then you should look at the number of errors or
**[5:26]** the percentage of errors that are due to incorrect labels.
**[5:30]** So it looks like in this case,
**[5:32]** 6% of the errors are due to incorrect labels.
**[5:35]** So 6% of 10% is 0.6%.
**[5:40]** And then you should look at errors due to all other causes.
**[5:45]** So if you made 10% error on your dev set
**[5:48]** and 0.6% of those are because the label was wrong,
**[5:51]** then the remainder, 9.4% of them,
**[5:54]** are due to other causes such as misrecognizing dogs being cats,
**[5:58]** great cats and blurry images.
**[6:01]** So in this case, I would say there's 9.4% worth of error that you could focus on fixing,
**[6:08]** whereas the errors due to incorrect labels is
**[6:12]** a relatively small fraction of the overall set of errors.
**[6:16]** So by all means,
**[6:17]** go in and fix these incorrect labels if you want
**[6:20]** but it's maybe not the most important thing to do right now.
**[6:24]** Now, let's take another example.
**[6:26]** Suppose you've made a lot more progress on your learning problem.
**[6:30]** So instead of 10% error,
**[6:31]** let's say you brought the errors down to 2%,
**[6:35]** but still 0.6% of your overall errors are due to incorrect labels.
**[6:43]** So now, if you want to examine a set of mislabeled dev set images,
**[6:47]** set that comes from just 2% of dev set data you're mislabeling,
**[6:52]** then a very large fraction of them,
**[6:56]** 0.6 divided by 2%,
**[6:59]** so that is actually 30% rather than 6% of your labels.
**[7:05]** Your incorrect examples are actually due to incorrectly label examples.
**[7:09]** And so errors due to other causes are now 1.4%.
**[7:12]** When such a high fraction of
**[7:16]** your mistakes as measured on your dev set due to incorrect labels,
**[7:23]** then it maybe seems much more worthwhile to fix up the incorrect labels in your dev set.
**[7:30]** And if you remember the goal of the dev set,
**[7:32]** the main purpose of the dev set is,
**[7:34]** you want to really use it to help you select between two classifiers A and B.
**[7:39]** So if you're trying out two classifiers A and B,
**[7:42]** and one has 2.1% error and the other has 1.9% error on your dev set.
**[7:49]** But you don't trust your dev set anymore to be
**[7:52]** correctly telling you whether this classifier is
**[7:55]** actually better than this because your
**[7:57]** 0.6% of these mistakes are due to incorrect labels.
**[8:02]** Then there's a good reason to go in and fix the incorrect labels in your dev set.
**[8:06]** Because in this example on the right is just having a very large impact
**[8:10]** on the overall assessment of the errors of the algorithm,
**[8:13]** whereas in the example on the left, the percentage impact is
**[8:17]** having on your algorithm is still smaller.
**[8:21]** Now, if you decide to go into your dev set and
**[8:24]** manually re-examine the labels and try to fix up some of the labels,
**[8:28]** here are a few additional guidelines or principles to consider.
**[8:33]** First, I would encourage you to apply
**[8:36]** whatever process you apply to both your dev and test sets at the same time.
**[8:41]** We've talk previously about why you want
**[8:44]** your dev and test sets to come from the same distribution.
**[8:47]** The dev set is telling you where to aim to target and when you hit it,
**[8:50]** you want that to generalize to the test set.
**[8:53]** So your team really works more
**[8:55]** efficiently to dev and test sets come from the same distribution.
**[8:59]** So if you're going in to fix something on the dev set,
**[9:01]** I would apply the same process to the test set to make sure
**[9:04]** that they continue to come from the same distribution.
**[9:07]** So we hire someone to examine the labels more carefully.
**[9:10]** Do that for both your dev and test sets.
**[9:13]** Second, I would urge you to consider examining
**[9:16]** examples your algorithm got right as well as ones it got wrong.
**[9:20]** It is easy to look at the examples your algorithm
**[9:23]** got wrong and just see if any of those need to be fixed.
**[9:26]** But it's possible that there are some examples that you haven't got right,
**[9:30]** that should also be fixed.
**[9:32]** And if you only fix ones that your algorithms got wrong,
**[9:34]** you end up with more bias estimates of the error of your algorithm.
**[9:38]** It gives your algorithm a little bit of an unfair advantage.
**[9:42]** If you just try to double check what it got wrong but you don't also
**[9:46]** double check what it got right because it might have gotten something right,
**[9:50]** that it was just lucky on fixing the label would
**[9:54]** cause it to go from being right to being wrong, on that example.
**[9:59]** The second bullet isn't always easy to do,
**[10:01]** so it's not always done.
**[10:03]** The reason it's not always done is because if you classifier's very accurate,
**[10:08]** then it's getting fewer things wrong than right.
**[10:11]** So if your classifier has 98% accuracy,
**[10:15]** then it's getting 2% of things wrong and 98% of things right.
**[10:19]** So it's much easier to examine and validate the labels on 2% of
**[10:24]** the data and it takes much longer to validate labels on 98% of the data,
**[10:30]** so this isn't always done.
**[10:31]** That's just something to consider.
**[10:34]** Finally, if you go into a dev and test data to correct some of the labels there,
**[10:41]** you may or may not decide to go and apply the same process for the training set.
**[10:46]** Remember we said that at the start of this video that it's actually
**[10:48]** less important to correct the labels in your training set.
**[10:51]** And it's quite possible you decide to just correct the labels in your dev and
**[10:54]** test set which are also often smaller
**[10:58]** than a training set and you might not invest all that extra effort
**[11:01]** needed to correct the labels in a much larger training set.
**[11:06]** This is actually okay.
**[11:07]** We'll talk later this week about some processes
**[11:11]** for handling when your training data is
**[11:14]** different in distribution than you dev and test data.
**[11:17]** Learning algorithms are quite robust to that.
**[11:20]** It's super important that your dev and test sets come from the same distribution.
**[11:25]** But if your training set comes from a slightly different distribution,
**[11:28]** often that's a pretty reasonable thing to do.
**[11:31]** I will talk more about how to handle this later this week.
**[11:34]** So I'd like to wrap up with just a couple of pieces of advice.
**[11:37]** First, deep learning researchers sometimes like to say things like,
**[11:41]** "I just fed the data to the algorithm.
**[11:42]** I trained in and it worked."
**[11:44]** There is a lot of truth to that in the deep learning era.
**[11:48]** There is more of feeding data to an algorithm and just training
**[11:51]** it and doing less hand engineering and using less human insight.
**[11:54]** But I think that in building practical systems,
**[11:57]** often there's also more manual error analysis and more human insight
**[12:01]** that goes into the systems than sometimes deep learning researchers like to acknowledge.
**[12:07]** Second is that somehow I've seen some engineers and
**[12:10]** researchers be reluctant to manually look at the examples.
**[12:14]** Maybe it's not the most interesting thing to do,
**[12:16]** to sit down and look at
**[12:17]** a 100 or a couple hundred examples to counter the number of errors.
**[12:21]** But this is something that I so do myself.
**[12:23]** When I'm leading a machine learning team and I
**[12:25]** want to understand what mistakes it is making,
**[12:27]** I would actually go in and look at the data myself and
**[12:29]** try to counter the fraction of errors.
**[12:31]** And I think that because these minutes or maybe a small number of
**[12:35]** hours of counting data can really help you prioritize where to go next.
**[12:40]** I find this a very good use of your time and I urge
**[12:42]** you to consider doing it if you've built a machine learning
**[12:45]** system and you're trying to decide
**[12:47]** what ideas or what directions to prioritize things.
**[12:51]** So that's it for the error analysis process.
**[12:55]** In the next video, I want to share a view of some thoughts on how error analysis
**[13:00]** fits in to how you might go about starting out on a new machine learning project.
