---
type: video-transcript
specialization: Deep Learning Specialization
course: Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization
week: 1
section: Setting up your Machine Learning Application
item_title: Basic Recipe for Machine Learning 
duration: 6 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/ZBkx4/basic-recipe-for-machine-learning
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Basic Recipe for Machine Learning  — Transcript

**[0:00]** In the previous video,
**[0:01]** you saw how looking at training error and depth error can help you
**[0:04]** diagnose whether your algorithm has a bias or a variance problem, or maybe both.
**[0:09]** It turns out that this information that lets you much more
**[0:11]** systematically, using what they call a basic
**[0:15]** recipe for machine learning and lets you much more systematically
**[0:18]** go about improving your algorithms' performance. Let's take a look.
**[0:21]** When training a neural network,
**[0:22]** here's a basic recipe I will use.
**[0:24]** After having trained in an initial model,
**[0:26]** I will first ask,
**[0:28]** does your algorithm have high bias?
**[0:30]** And so, to try and evaluate if there is high bias,
**[0:33]** you should look at, really,
**[0:35]** the training set or the training data performance.
**[0:40]** Right. And so, if it does have high bias,
**[0:43]** does not even fitting in the training set that well,
**[0:45]** some things you could try would be to try pick a network,
**[0:49]** such as more hidden layers or more hidden units,
**[0:52]** or you could train it longer, you know,
**[0:54]** maybe run trains longer or try some more advanced optimization algorithms,
**[0:58]** which we'll talk about later in this course.
**[1:00]** Or, you can also try,
**[1:03]** this is kind of a, maybe it work, maybe it won't.
**[1:06]** But we'll see later that there are a lot of different neural network architectures
**[1:10]** and maybe you can find a new network architecture that's better suited for this problem.
**[1:15]** Putting this in parentheses because one of those things that,
**[1:17]** you know, you just have to try,
**[1:19]** maybe you can make it work, maybe not.
**[1:20]** Whereas, getting a bigger network almost always helps,
**[1:24]** and training longer, well, doesn't always help,
**[1:26]** but it certainly never hurts.
**[1:28]** But,so when training a learning algorithm,
**[1:29]** I would try these things until I can at least get rid of the bias problems,
**[1:34]** as I go back after I've tried this until, and keep doing that until I can fit,
**[1:39]** at least, fit the training set pretty well.
**[1:42]** And usually, if you have a big enough network,
**[1:44]** you should usually be able to fit the training data well, so long
**[1:49]** as it's a problem that is possible for someone to do, alright?
**[1:54]** If the image is very blurry,
**[1:55]** it may be impossible to fit it,
**[1:57]** but if at least a human can do well on the task,
**[1:59]** if you think Bayes error is not too high,
**[2:01]** then by training a big enough network you should be able to,
**[2:04]** hopefully, do well, at least on the training set,
**[2:07]** to at least fit or overfit the training set.
**[2:09]** Once you've reduce bias to acceptable amounts, I will then ask,
**[2:14]** do you have a variance problem?
**[2:17]** And so to evaluate that I would look at dev set performance.
**[2:21]** Are you able to generalize, from a pretty good training
**[2:24]** set performance, to having a pretty good dev set performance?
**[2:28]** And if you have high variance, well,
**[2:30]** best way to solve a high variance problem is to get more data,
**[2:34]** if you can get it, this,
**[2:35]** you know, can only help.
**[2:36]** But sometimes you can't get more data.
**[2:40]** Or, you could try regularization,
**[2:43]** which we'll talk about in the next video,
**[2:45]** to try to reduce overfitting.
**[2:46]** And then also, again, sometimes you just have to try it.
**[2:50]** But if you can find a more appropriate neural network architecture,
**[2:54]** sometimes that can reduce your variance problem as well,
**[2:57]** as well as reduce your bias problem. But how to do that?
**[3:00]** It's harder to be totally systematic how you do that.
**[3:04]** But, so I try these things and I kind of keep going back,
**[3:06]** until, hopefully, you find something with both low bias and low variance,
**[3:11]** whereupon you would be done.
**[3:14]** So a couple of points to notice.
**[3:16]** First, is that depending on whether you have high bias or high variance,
**[3:19]** the set of things you should try could be quite different.
**[3:24]** So I'll usually use the training dev set to try to
**[3:26]** diagnose if you have a bias or variance problem,
**[3:29]** and then use that to select the appropriate subset of things to try.
**[3:33]** So, for example, if you actually have a high bias problem,
**[3:37]** getting more training data is actually not going to help.
**[3:40]** Or, at least it's not the most efficient thing to do, alright?
**[3:44]** So being clear on how much of a bias problem or variance problem or
**[3:47]** both, can help you focus on selecting the most useful things to try.
**[3:52]** Second, in the earlier era of machine learning,
**[3:56]** there used to be a lot of discussion on what is called the bias variance tradeoff.
**[4:02]** And the reason for that was that,
**[4:04]** for a lot of the things you could try,
**[4:06]** you could increase bias and reduce variance,
**[4:09]** or reduce bias and increase variance.
**[4:11]** But, back in the pre-deep learning era,
**[4:15]** we didn't have many tools,
**[4:17]** we didn't have as many tools that just reduce
**[4:19]** bias, or that just reduce variance without hurting the other one.
**[4:24]** But in the modern deep learning, big data era,
**[4:28]** so long as you can keep training a bigger network,
**[4:31]** and so long as you can keep getting more data,
**[4:34]** which isn't always the case for either of these,
**[4:36]** but if that's the case,
**[4:37]** then getting a bigger network almost always just
**[4:40]** reduces your bias, without necessarily hurting your variance,
**[4:43]** so long as you regularize appropriately.
**[4:46]** And getting more data, pretty much always
**[4:48]** reduces your variance and doesn't hurt your bias much.
**[4:52]** So what's really happened is that,
**[4:54]** with these two steps,
**[4:55]** the ability to train, pick a network,
**[4:57]** or get more data,
**[4:58]** we now have tools to drive down bias and just drive down bias,
**[5:03]** or drive down variance and just drive down variance,
**[5:05]** without really hurting the other thing that much.
**[5:09]** And I think this has been one of the big reasons
**[5:12]** that deep learning has been so useful for supervised learning,
**[5:16]** that there's much less of this tradeoff where you
**[5:18]** have to carefully balance bias and variance,
**[5:21]** but sometimes, you just have more options for reducing bias
**[5:25]** or reducing variance, without necessarily increasing the other one.
**[5:30]** And, in fact, so last, you have a well-regularized network.
**[5:33]** We'll talk about regularization starting from the next video.
**[5:36]** Training a bigger network almost never hurts.
**[5:40]** And the main cost of training a neural network that's too big is just computational time,
**[5:44]** so long as you're regularizing.
**[5:46]** So I hope this gives you a sense of the basic structure of how to
**[5:49]** organize your machine learning problem to diagnose bias and variance,
**[5:53]** and then try to select the right operation for you to make progress on your problem.
**[5:57]** One of the things I mentioned several times in the video is regularization,
**[6:01]** is a very useful technique for reducing variance.
**[6:03]** There is a little bit of a bias variance tradeoff when you use regularization.
**[6:07]** It might increase the bias a little bit,
**[6:09]** although often not too much if you have a huge enough network.
**[6:13]** But, let's dive into more details in the next video so you can
**[6:16]** better understand how to apply regularization to your neural network.
