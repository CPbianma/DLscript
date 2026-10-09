---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 1
section: Setting up your Machine Learning Application
item_title: Train / Dev / Test sets
duration: 12 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/cxG1s/train-dev-test-sets
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Train / Dev / Test sets — Transcript

**[0:00]** Welcome to this course on the practical aspects of deep learning.
**[0:04]** Perhaps now you've learned how to implement a neural network.
**[0:07]** In this week, you'll learn the practical aspects of how to make
**[0:10]** your neural network work well.
**[0:12]** Ranging from things like hyperparameter tuning to how to set up your data,
**[0:16]** to how to make sure your optimization algorithm runs quickly so
**[0:20]** that you get your learning algorithm to learn in a reasonable amount of time.
**[0:24]** In this first week, we'll first talk about how the cellular machine learning problem,
**[0:27]** then we'll talk about randomization,
**[0:29]** then we'll talk about some tricks for
**[0:30]** making sure your neural network implementation is correct.
**[0:34]** With that, let's get started.
**[0:36]** Making good choices in how you set up your training, development, and
**[0:39]** test sets can make a huge difference in helping you quickly
**[0:43]** find a good high-performance neural network.
**[0:46]** When training a neural network, you have to make a lot of decisions,
**[0:49]** such as how many layers will your neural network have?
**[0:52]** And, how many hidden units do you want each layer to have?
**[0:55]** And, what's the learning rate?
**[0:57]** And, what are the activation functions you want to use for the different layers?
**[1:01]** When you're starting on a new application,
**[1:03]** it's almost impossible to correctly guess the right values for
**[1:07]** all of these, and for other hyperparameter choices, on your first attempt.
**[1:12]** So, in practice, applied machine learning is a highly iterative process,
**[1:16]** in which you often start with an idea,
**[1:18]** such as you want to build a neural network of a certain number of layers,
**[1:21]** a certain number of hidden units, maybe on certain data sets, and so on.
**[1:25]** And then you just have to code it up and try it, by running your code.
**[1:29]** You run an experiment and you get back a result that tells you
**[1:33]** how well this particular network, or this particular configuration works.
**[1:37]** And based on the outcome,
**[1:39]** you might then refine your ideas and change your choices and
**[1:44]** maybe keep iterating, in order to try to find a better and a better, neural network.
**[1:50]** Today, deep learning has found great success in a lot of areas
**[1:54]** ranging from natural language processing, to computer vision, to
**[1:59]** speech recognition, to a lot of applications on also structured data.
**[2:04]** And structured data includes everything from advertisements to web search,
**[2:10]** which isn't just Internet search engines. It's also, for example, shopping websites.
**[2:16]** Already any website that wants to
**[2:19]** deliver great search results when you enter terms into a search bar.
**[2:23]** To computer security, to logistics, such as figuring out where
**[2:29]** to send drivers to pick up and drop off things...to many more.
**[2:34]** So what I'm seeing is that sometimes a researcher with a lot of experience
**[2:39]** in NLP might enter...you know, might try to do something in computer vision.
**[2:43]** Or maybe a researcher with a lot of experience in speech recognition might, you know,
**[2:48]** jump in and try to do something on advertising.
**[2:50]** Or someone from security might want to jump in and do something on logistics.
**[2:54]** And what I've seen is that intuitions from one domain or
**[2:57]** from one application area often do not transfer to other application areas.
**[3:02]** And the best choices may depend on the amount of data you have,
**[3:06]** the number of input features you have through your computer configuration and
**[3:10]** whether you're training on GPUs or CPUs.
**[3:13]** And if so, exactly what configuration of GPUs and CPUs...and many other things.
**[3:18]** So, for a lot of applications, I think it's almost impossible.
**[3:21]** Even very experienced deep learning people find it almost impossible to correctly
**[3:26]** guess the best choice of hyperparameters the very first time.
**[3:30]** And so today, applied deep learning is a very iterative
**[3:34]** process where you just have to go around this cycle many times
**[3:39]** to hopefully find a good choice of network for your application.
**[3:43]** So one of the things that determine how quickly you can make progress is
**[3:48]** how efficiently you can go around this cycle.
**[3:51]** And setting up your data sets well, in terms of your train, development and
**[3:55]** test sets can make you much more efficient at that.
**[3:59]** So if this is your training data, let's draw that as a big box.
**[4:06]** Then traditionally, you might take all the data you have and
**[4:11]** carve off some portion of it to be your training set,
**[4:15]** some portion of it to be your hold-out cross validation set,
**[4:23]** and this is sometimes also called the development set.
**[4:30]** And for brevity, I'm just going to call this the dev set, but
**[4:33]** all of these terms mean roughly the same thing.
**[4:36]** And then you might carve out some final portion of it to be your test set.
**[4:41]** And so the workflow is that you keep on training algorithms on your training set.
**[4:46]** And use your dev set or your hold-out cross validation set to see which
**[4:51]** of many different models performs best on your dev set.
**[4:54]** And then after having done this long enough,
**[4:56]** when you have a final model that you want to evaluate,
**[5:00]** you can take the best model you have found and evaluate it on your test set
**[5:03]** in order to get an unbiased estimate of how well your algorithm is doing.
**[5:08]** So in the previous era of machine learning, it was common practice
**[5:13]** to take all your data and split it according to maybe a 70/30% in
**[5:18]** terms of a...people often talk about the 70/30 train test splits.
**[5:23]** If you don't have an explicit dev set or maybe a 60/20/20%
**[5:28]** split, in terms of 60% train, 20% dev and 20% test.
**[5:33]** And several years ago, this was widely considered best practice
**[5:37]** in machine learning.
**[5:38]** If you have here maybe 100 examples in total,
**[5:41]** maybe 1000 examples in total, maybe after 10,000 examples,
**[5:46]** these sorts of ratios were perfectly reasonable rules of thumb.
**[5:50]** But in the modern big data era, where, for example,
**[5:55]** you might have a million examples in total, then the trend is that your dev and
**[6:03]** test sets have been becoming a much smaller percentage of the total.
**[6:09]** Because remember, the goal of the dev set or the development set is that you're
**[6:13]** going to test different algorithms on it and see which algorithm works better.
**[6:17]** So the dev set just needs to be big enough for
**[6:20]** you to evaluate, say, two different algorithm choices or
**[6:23]** ten different algorithm choices and quickly decide which one is doing better.
**[6:27]** And you might not need a whole 20% of your data for that.
**[6:30]** So, for example, if you have a million training examples, you might decide that
**[6:34]** just having 10,000 examples in your dev set is more than enough
**[6:39]** to evaluate, you know, which one or two algorithms does better.
**[6:43]** And in a similar vein, the main goal of your test set is, given your final
**[6:47]** classifier, to give you a pretty confident estimate of how well it's doing.
**[6:51]** And again, if you have a million examples, maybe you might decide that 10,000
**[6:56]** examples is more than enough in order to evaluate a single classifier and
**[7:00]** give you a good estimate of how well it's doing.
**[7:03]** So, in this example, where you have a million examples,
**[7:07]** if you need just 10,000 for your dev and 10,000 for your test,
**[7:11]** your ratio will be more like...this 10,000 is 1% of 1 million, so
**[7:17]** you'll have 98% train, 1% dev, 1% test.
**[7:23]** And I've also seen applications where,
**[7:25]** if you have even more than a million examples, you might end up with,
**[7:29]** you know, 99.5% train and 0.25% dev, 0.25% test.
**[7:35]** Or maybe a 0.4% dev, 0.1% test.
**[7:42]** So just to recap, when setting up your machine learning problem,
**[7:45]** I'll often set it up into a train, dev and test sets, and
**[7:50]** if you have a relatively small dataset, these traditional ratios might be okay.
**[7:55]** But if you have a much larger data set, it's also fine to set your dev and
**[7:59]** test sets to be much smaller than your 20% or even 10% of your data.
**[8:05]** We'll give more specific guidelines on the sizes of dev and
**[8:08]** test sets later in this specialization.
**[8:11]** One other trend we're seeing in the era of modern deep learning is that more and
**[8:16]** more people train on mismatched train and test distributions.
**[8:20]** Let's say you're building an app that lets users upload a lot of pictures and
**[8:25]** your goal is to find pictures of cats in order to show your users.
**[8:29]** Maybe all your users are cat lovers.
**[8:31]** Maybe your training set comes from cat pictures downloaded off the Internet, but
**[8:37]** your dev and test sets might comprise cat pictures from users using your app.
**[8:42]** So maybe your training set has a lot of pictures crawled off the Internet but
**[8:46]** the dev and test sets are pictures uploaded by users.
**[8:49]** Turns out a lot of webpages have very high resolution, very professional,
**[8:53]** very nicely framed pictures of cats.
**[8:55]** But maybe your users are uploading, you know, blurrier,
**[8:58]** lower res images just taken with a cell phone camera in a more casual condition.
**[9:03]** And so these two distributions of data may be different.
**[9:07]** The rule of thumb I'd encourage you to follow, in this case, is to
**[9:13]** make sure that the dev and test sets come from the same distribution.
**[9:23]** We'll say more about this particular guideline as well, but
**[9:26]** because you will be using the dev set to evaluate a lot of different models and
**[9:30]** trying really hard to improve performance on the dev set,
**[9:33]** it's nice if your dev set comes from the same distribution as your test set.
**[9:38]** But because deep learning algorithms have such a huge hunger for training data,
**[9:43]** one trend I'm seeing is that you might use all sorts of creative tactics,
**[9:47]** such as crawling webpages,
**[9:49]** in order to acquire a much bigger training set than you would otherwise have.
**[9:53]** Even if part of the cost of that is then that your training set
**[9:57]** data might not come from the same distribution as your dev and test sets.
**[10:00]** But you find that so long as you follow this rule of thumb,
**[10:03]** that progress in your machine learning algorithm will be faster.
**[10:08]** And I'll give a more detailed explanation for
**[10:10]** this particular rule of thumb later in the specialization as well.
**[10:13]** Finally, it might be okay to not have a test set.
**[10:18]** Remember, the goal of the test set is to give you a ... unbiased estimate
**[10:22]** of the performance of your final network, of the network that you selected.
**[10:26]** But if you don't need that unbiased estimate,
**[10:29]** then it might be okay to not have a test set.
**[10:32]** So what you do, if you have only a dev set but not a test set,
**[10:35]** is you train on the training set and then you try different model architectures.
**[10:40]** Evaluate them on the dev set, and then use that to iterate and
**[10:44]** try to get to a good model.
**[10:46]** Because you've fit your data to the dev set,
**[10:48]** this no longer gives you an unbiased estimate of performance.
**[10:50]** But if you don't need one, that might be perfectly fine.
**[10:53]** In the machine learning world, when you have just a train and
**[10:55]** a dev set but no separate test set,
**[10:58]** most people will call this a training set and
**[11:01]** they will call the dev set the test set.
**[11:04]** But what they actually end up doing is using the test set as a hold-out
**[11:08]** cross validation set.
**[11:09]** Which maybe isn't completely a great use of terminology,
**[11:13]** because they're then overfitting to the test set.
**[11:17]** So when the team tells you that they have only a train and a test set,
**[11:21]** I would just be cautious and think, do they really have a train dev set?
**[11:26]** Because they're overfitting to the test set.
**[11:28]** Culturally, it might be difficult to change some of these team's terminology
**[11:33]** and get them to call it a trained dev set rather than a trained test set,
**[11:38]** even though I think calling it a train and
**[11:40]** development set would be more correct terminology.
**[11:43]** And this is actually okay practice if you don't need a completely
**[11:45]** unbiased estimate of the performance of your algorithm.
**[11:48]** So having set up a train dev and test set will allow you to integrate more quickly.
**[11:53]** It will also allow you to more efficiently measure the bias and variance of your
**[11:57]** algorithm so you can more efficiently select ways to improve your algorithm.
**[12:02]** Let's start to talk about that in the next video.
