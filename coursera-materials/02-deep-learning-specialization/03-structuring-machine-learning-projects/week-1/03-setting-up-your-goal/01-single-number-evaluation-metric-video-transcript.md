---
type: video-transcript
specialization: Deep Learning Specialization
course: Structuring Machine Learning Projects
week: 1
section: Setting Up your Goal
item_title: Single Number Evaluation Metric
duration: 7 min
source_url: https://www.coursera.org/learn/machine-learning-projects/lecture/wIKkC/single-number-evaluation-metric
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Single Number Evaluation Metric — Transcript

**[0:00]** Whether you're tuning hyperparameters, or trying out different ideas for
**[0:03]** learning algorithms, or just trying out different options for
**[0:06]** building your machine learning system.
**[0:07]** You'll find that your progress will be much faster if you have a single real
**[0:12]** number evaluation metric that lets you quickly tell if the new thing you
**[0:16]** just tried is working better or worse than your last idea.
**[0:20]** So when teams are starting on a machine learning project, I often recommend that
**[0:24]** you set up a single real number evaluation metric for your problem.
**[0:29]** Let's look at an example.
**[0:32]** You've heard me say before that applied machine learning is a very
**[0:35]** empirical process.
**[0:36]** We often have an idea, code it up, run the experiment to see how it did, and
**[0:40]** then use the outcome of the experiment to refine your ideas.
**[0:44]** And then keep going around this loop as you keep on improving your algorithm.
**[0:48]** So let's say for your cat classifier, you had previously built some classifier A.
**[0:54]** And by changing the hyperparameters and the training sets or
**[0:58]** some other thing, you've now trained a new classifier, B.
**[1:02]** So one reasonable way to evaluate the performance of your classifiers is to look
**[1:06]** at its precision and recall.
**[1:08]** The exact details of what's precision and recall don't matter too much for
**[1:12]** this example.
**[1:13]** But briefly, the definition of precision is,
**[1:16]** of the examples that your classifier recognizes as cats,
**[1:23]** What percentage actually are cats?
**[1:32]** So if classifier A has 95% precision, this means that when classifier A says
**[1:37]** something is a cat, there's a 95% chance it really is a cat.
**[1:41]** And recall is, of all the images that really are cats,
**[1:45]** what percentage were correctly recognized by your classifier?
**[1:50]** So what percentage of actual cats, Are correctly recognized?
**[2:04]** So if classifier A is 90% recall, this means that of all of the images in, say,
**[2:08]** your dev sets that really are cats,
**[2:11]** classifier A accurately pulled out 90% of them.
**[2:13]** So don't worry too much about the definitions of precision and recall.
**[2:19]** But it turns out that there's often a tradeoff between precision and recall,
**[2:23]** and you care about both.
**[2:26]** You want that, when the classifier says something is a cat,
**[2:29]** there's a high chance it really is a cat.
**[2:31]** But of all the images that are cats,
**[2:33]** you also want it to pull a large fraction of them as cats.
**[2:37]** So it might be reasonable to try to evaluate
**[2:40]** the classifiers in terms of its precision and its recall.
**[2:44]** The problem with using precision recall as your evaluation metric is that if
**[2:49]** classifier A does better on recall, which it does here, the classifier B does
**[2:54]** better on precision, then you're not sure which classifier is better.
**[3:03]** And if you're trying out a lot of different ideas, a lot of different
**[3:06]** hyperparameters, you want to rather quickly try out not just two classifiers,
**[3:11]** but maybe a dozen classifiers and quickly pick out the, quote, "best ones",
**[3:14]** so you can keep on iterating from there.
**[3:19]** And with two evaluation metrics, it is difficult to know
**[3:23]** how to quickly pick one of the two or quickly pick one of the ten.
**[3:29]** So what I recommend is rather than using two numbers, precision and
**[3:33]** recall, to pick a classifier,
**[3:35]** you just have to find a new evaluation metric that combines precision and recall.
**[3:41]** In the machine learning literature, the standard way to combine precision and recall
**[3:45]** is something called an F1 score.
**[3:47]** And the details of F1 score aren't too important, but informally,
**[3:52]** you can think of this as the average of precision, P, and recall, R.
**[3:58]** Formally, the F1 score is defined by this formula,
**[4:04]** it's 2/ 1/P + 1/R.
**[4:07]** And in mathematics, this function is called the harmonic
**[4:12]** mean of precision P and recall R.
**[4:16]** But less formally,
**[4:17]** you can think of this as some way that averages precision and recall.
**[4:22]** Only instead of taking the arithmetic mean,
**[4:25]** you take the harmonic mean, which is defined by this formula.
**[4:28]** And it has some advantages in terms of trading off precision and recall.
**[4:33]** But in this example,
**[4:34]** you can then see right away that classifier A has a better F1 score.
**[4:39]** And assuming F1 score is a reasonable way to combine precision and recall,
**[4:43]** you can then quickly select classifier A over classifier B.
**[4:48]** So what I found for
**[4:48]** a lot of machine learning teams is that having a well-defined dev set,
**[4:52]** which is how you're measuring precision and recall, plus a single number
**[4:57]** evaluation metric, sometimes I'll call it single row number.
**[5:04]** Evaluation metric allows you to quickly tell if classifier A or
**[5:09]** classifier B is better, and therefore having a dev set plus single
**[5:13]** number evaluation metric distance to speed up iterating.
**[5:21]** It speeds up this iterative process of improving your machine learning algorithm.
**[5:26]** Let's look at another example.
**[5:29]** Let's say you're building a cat app for cat lovers in four major geographies,
**[5:35]** the US, China, India, and other, the rest of the world.
**[5:40]** And let's say that your two classifiers achieve different errors
**[5:45]** in data from these four different geographies.
**[5:48]** So algorithm A achieves 3% error on pictures submitted by US users and so on.
**[5:56]** So it might be reasonable to keep track of how well
**[5:59]** your classifiers do in these different markets or these different geographies.
**[6:03]** But by tracking four numbers, it's very difficult to look at these numbers and
**[6:06]** quickly decide if algorithm A or algorithm B is superior.
**[6:10]** And if you're testing a lot of different classifiers,
**[6:13]** then it's just difficult to look at all these numbers and quickly pick one.
**[6:17]** So what I recommend in this example is, in addition to tracking your
**[6:22]** performance in the four different geographies, to also compute the average.
**[6:26]** And assuming that average performance is a reasonable single real number
**[6:30]** evaluation metric, by computing the average,
**[6:33]** you can quickly tell that it looks like algorithm C has a lowest average error.
**[6:38]** And you might then go ahead with that one.
**[6:40]** If you have to pick an algorithm to keep on iterating from.
**[6:44]** So your work load machine learning is often, you have an idea,
**[6:47]** you implement it and try it out, and you want to know whether your idea helped.
**[6:51]** So what we've seen in this video is that having a single number evaluation metric
**[6:56]** can really improve your efficiency or
**[6:58]** the efficiency of your team in making those decisions.
**[7:02]** Now we're not yet
**[7:03]** done with the discussion on how to effectively set up evaluation metrics.
**[7:07]** In the next video,
**[7:08]** I'm going to share with you how to set up optimizing, as well as satisfying metrics.
**[7:13]** So let's take a look at the next video.
