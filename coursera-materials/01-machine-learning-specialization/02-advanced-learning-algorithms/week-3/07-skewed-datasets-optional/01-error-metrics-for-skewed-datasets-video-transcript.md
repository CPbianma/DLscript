---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 3
section: Skewed datasets (optional)
item_title: Error metrics for skewed datasets
duration: 12 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/pjuBJ/error-metrics-for-skewed-datasets
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Error metrics for skewed datasets — Transcript

**[0:00]** If you're working on a machine learning application
**[0:04]** where the ratio of positive
**[0:06]** to negative examples is very skewed,
**[0:08]** very far from 50-50,
**[0:10]** then it turns out that
**[0:11]** the usual error metrics like
**[0:13]** accuracy don't work that well.
**[0:15]** Let's start with an example.
**[0:17]** Let's say you're training
**[0:19]** a binary classifier to detect a rare disease in
**[0:23]** patients based on lab tests or
**[0:26]** based on other data from the patients.
**[0:29]** Y is equal to 1 if the disease is
**[0:32]** present and y is equal to 0 otherwise.
**[0:37]** Suppose you find that you've
**[0:40]** achieved one percent error on the test set,
**[0:43]** so you have a 99 percent correct diagnosis.
**[0:45]** This seems like a great outcome.
**[0:47]** But it turns out that if this is a rare disease,
**[0:51]** so y is equal to 1, very rarely,
**[0:54]** then this may not be as impressive as it sounds.
**[0:58]** Specifically, if it is a rare disease and if only
**[1:01]** 0.5 percent of the patients
**[1:04]** in your population have the disease,
**[1:06]** then if instead you wrote the program,
**[1:09]** that just said, print y equals 0.
**[1:12]** It predicts y equals 0 all the time.
**[1:14]** This very simple even non-learning algorithm,
**[1:18]** because it just says y equals 0 all the time,
**[1:20]** this will actually have 99.5 percent
**[1:23]** accuracy or 0.5 percent error.
**[1:28]** This really dumb algorithm
**[1:30]** outperforms your learning algorithm
**[1:32]** which had one percent error,
**[1:34]** much worse than 0.5 percent error.
**[1:37]** But I think a piece
**[1:39]** of software that just prints y equals 0,
**[1:41]** is not a very useful diagnostic tool.
**[1:44]** What this really means is that you can't tell
**[1:47]** if getting one percent error is
**[1:49]** actually a good result or a bad result.
**[1:52]** In particular, if you have
**[1:55]** one algorithm that achieves 99.5 percent accuracy,
**[1:59]** different one that achieves 99.2 percent accuracy,
**[2:03]** different one that achieves 99.6 percent accuracy.
**[2:07]** It's difficult to know which of
**[2:09]** these is actually the best algorithm.
**[2:12]** Because if you have an algorithm
**[2:15]** that achieve 0.5 percent error and
**[2:18]** a different one that achieves one percent error and
**[2:21]** a different one that achieves 1.2 percent error,
**[2:24]** it's difficult to know
**[2:26]** which of these is the best algorithm.
**[2:28]** Because the one with the lowest error may
**[2:30]** be is not particularly useful prediction
**[2:33]** like this that always predicts y equals 0 and
**[2:36]** never ever diagnose any patient as having this disease.
**[2:40]** Quite possibly an algorithm that has one percent error,
**[2:43]** but that at least diagnosis some patients as having
**[2:46]** the disease could be more useful than just
**[2:49]** printing y equals 0 all the time.
**[2:52]** When working on problems with skewed data sets,
**[2:56]** we usually use a different error metric rather than just
**[3:00]** classification error to figure
**[3:02]** out how well your learning algorithm is doing.
**[3:04]** In particular, a common pair
**[3:07]** of error metrics are precision and recall,
**[3:11]** which we'll define on the slide.
**[3:12]** In this example, y equals one will be the rare class,
**[3:17]** such as the rare disease that we may want to detect.
**[3:20]** In particular, to evaluate
**[3:23]** a learning algorithm's performance with
**[3:26]** one rare class it's useful to
**[3:28]** construct what's called a confusion matrix,
**[3:32]** which is a two-by-two matrix
**[3:34]** or a two-by-two table that looks like this.
**[3:37]** On the axis on top,
**[3:38]** I'm going to write the actual class,
**[3:40]** which could be one or zero.
**[3:43]** On the vertical axis,
**[3:44]** I'm going to write the predicted class,
**[3:47]** which is what did your learning algorithm predicts
**[3:49]** on a given example, one or zero?
**[3:53]** To evaluate your algorithm's performance on
**[3:55]** the cross-validation set or the test set say,
**[3:58]** we will then count up how many examples?
**[4:02]** Was the actual class, 1,
**[4:04]** and the predicted class 1?
**[4:05]** Maybe you have 100 cross-validation examples
**[4:08]** and on 15 of them,
**[4:11]** the learning algorithm had predicted one
**[4:13]** and the actual label was also one.
**[4:17]** Over here you would count up the number of
**[4:20]** examples in C or cross-validation
**[4:22]** set where the actual class
**[4:24]** was zero and your algorithm predicted one.
**[4:27]** Maybe you've five examples there and
**[4:30]** here predicted Class 0, actual Class 1.
**[4:33]** You have 10 examples and let's say
**[4:35]** 70 examples with predicted Class 0 and actual Class 0.
**[4:40]** In this example, the skew isn't
**[4:43]** as extreme as what I had on the previous slide.
**[4:47]** Because in these 100 examples
**[4:50]** in your cross-validation set,
**[4:52]** we have a total of
**[4:54]** 25 examples where the actual class was one
**[4:58]** and 75 where the actual class was
**[5:02]** zero by adding up these numbers vertically.
**[5:06]** You'll notice also that I'm using different colors to
**[5:08]** indicate these four cells in the table.
**[5:12]** I'm actually going to give names to these four cells.
**[5:15]** When the actual class is
**[5:17]** one and the predicted class is one,
**[5:19]** we're going to call that a true positive
**[5:22]** because you predicted positive
**[5:24]** and it was true there's a positive example.
**[5:26]** In this cell on the lower right,
**[5:29]** where the actual class is
**[5:30]** zero and the predicted class is zero,
**[5:32]** we will call that a true negative
**[5:34]** because you predicted negative and it was true.
**[5:37]** It really was a negative example.
**[5:39]** This cell on the upper right is called a
**[5:43]** false positive because the algorithm
**[5:48]** predicted positive, but it was false.
**[5:50]** It's not actually positive,
**[5:52]** so this is called a false positive.
**[5:54]** This cell is called the number of
**[5:57]** false negatives because the algorithm
**[6:00]** predicted zero, but it was false.
**[6:01]** It wasn't actually negative.
**[6:03]** The actual class was one.
**[6:06]** Having divided the classifications
**[6:10]** into these four cells,
**[6:12]** two common metrics you might compute are
**[6:14]** then the precision and recall.
**[6:17]** Here's what they mean.
**[6:19]** The precision of the learning algorithm computes
**[6:22]** of all the patients where we predicted y is equal to 1,
**[6:26]** what fraction actually has the rare disease.
**[6:29]** In other words, precision is defined as the number of
**[6:34]** true positives divided by
**[6:36]** the number classified as positive.
**[6:41]** In other words, of all the examples
**[6:43]** you predicted as positive,
**[6:45]** what fraction did we actually get right.
**[6:48]** Another way to write this formula would be
**[6:51]** true positives divided by true positives
**[6:57]** plus false positives because it is by summing
**[7:04]** this cell and this cell
**[7:07]** that you end up with the total number
**[7:10]** that was predicted as positive.
**[7:12]** In this example, the numerator, true positives,
**[7:16]** would be 15 and divided by 15 plus 5,
**[7:22]** and so that's 15 over 20 or three-quarters, 0.75.
**[7:27]** So we say that this algorithm has a precision of
**[7:30]** 75 percent because of
**[7:32]** all the things it predicted as positive,
**[7:35]** of all the patients that it
**[7:36]** thought has this rare disease,
**[7:38]** it was right 75 percent of the time.
**[7:40]** The second metric that is useful to compute is recall.
**[7:45]** And recall asks:
**[7:47]** Of all the patients that actually have the rare disease,
**[7:49]** what fraction did we correctly detect as having it?
**[7:53]** Recall is defined as the number of true positives divided
**[7:57]** by the number of actual positives.
**[8:02]** Alternatively, we can write that as number of
**[8:06]** true positives divided by the number of actual positives.
**[8:11]** Well, it's this cell plus this cell.
**[8:13]** So it's actually the number of true positives plus
**[8:17]** the number of false negatives because
**[8:20]** it's by summing up this upper-left cell
**[8:22]** and this lower-left cell
**[8:23]** that you get the number of actual positive examples.
**[8:27]** In our example, this would be 15 divided by 15 plus 10,
**[8:32]** which is 15 over 25,
**[8:36]** which is 0.6 or 60 percent.
**[8:40]** This learning algorithm would have
**[8:42]** 0.75 precision and 0.60 recall.
**[8:46]** You notice that this will help you detect if
**[8:50]** the learning algorithm is just
**[8:53]** printing y equals 0 all the time.
**[8:56]** Because if it predicts zero all the time,
**[9:00]** then the numerator of both
**[9:02]** of these quantities would be zero.
**[9:04]** It has no true positives.
**[9:08]** The recall metric in particular helps you detect if
**[9:12]** the learning algorithm is predicting zero all the time.
**[9:16]** Because if your learning algorithm just
**[9:19]** prints y equals 0,
**[9:22]** then the number of
**[9:25]** true positives will be
**[9:26]** zero because it never predicts positive,
**[9:29]** and so the recall will be equal to
**[9:32]** zero divided by the number of actual positives,
**[9:35]** which is equal to zero.
**[9:37]** In general, a learning algorithm with
**[9:39]** either zero precision or
**[9:41]** zero recall is not a useful algorithm.
**[9:44]** But just as a side note,
**[9:46]** if an algorithm actually predicts zero all the time,
**[9:49]** precision actually becomes undefined
**[9:51]** because it's actually zero over.
**[9:53]** zero. But in practice,
**[9:55]** if an algorithm doesn't predict even a single positive,
**[9:58]** we just say that precision is also equal to zero.
**[10:01]** But we'll find that
**[10:10]** computing both precision and
**[10:11]** recall makes it easier to spot
**[10:13]** if an algorithm is both reasonably accurate,
**[10:16]** in that, when it says a patient has a disease,
**[10:20]** there's a good chance the patient has a disease,
**[10:22]** such as 0.75 chance in this example,
**[10:24]** and also making sure that
**[10:26]** of all the patients that have the disease,
**[10:28]** it's helping to diagnose a reasonable fraction of them,
**[10:31]** such as here it's finding 60 percent of them.
**[10:34]** When you have a rare class,
**[10:37]** looking at precision and recall and making sure that
**[10:40]** both numbers are decently high,
**[10:43]** that hopefully helps reassure you that
**[10:45]** your learning algorithm is actually useful.
**[10:48]** The term recall was motivated by this observation
**[10:53]** that if you have
**[10:54]** a group of patients or population of patients,
**[10:57]** then recall measures,
**[10:59]** of all the patients that have the disease,
**[11:02]** how many would you have
**[11:03]** accurately diagnosed as having it.
**[11:06]** So when you have skewed classes
**[11:08]** or a rare class that you want to detect,
**[11:11]** precision and recall helps you tell if
**[11:14]** your learning algorithm is making
**[11:16]** good predictions or useful predictions.
**[11:19]** Now that we have these metrics for
**[11:21]** telling how well your learning algorithm is doing,
**[11:23]** in the next video,
**[11:24]** let's take a look at how to trade-off between precision
**[11:28]** and recall to try to optimize
**[11:30]** the performance of your learning algorithm.
