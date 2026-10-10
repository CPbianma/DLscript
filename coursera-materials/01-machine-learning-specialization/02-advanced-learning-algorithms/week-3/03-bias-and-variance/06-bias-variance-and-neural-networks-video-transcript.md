---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 3
section: Bias and variance
item_title: Bias/variance and neural networks
duration: 11 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/d1EGK/bias-variance-and-neural-networks
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# Bias/variance and neural networks — Transcript

**[0:01]** Was seen that high bias or high variance are both
**[0:04]** bad in the sense that they hurt the performance of your algorithm.
**[0:08]** One of the reasons that neural networks have been so successful is because your
**[0:12]** networks, together with the idea of big data or hopefully having large data sets.
**[0:17]** It's given us a new way of new ways to address both high bias and high variance.
**[0:23]** Let's take a look.
**[0:24]** You saw that if you're fitting different order polynomial is to a data set,
**[0:30]** then if you were to fit a linear model like this on the left.
**[0:34]** You have a pretty simple model that can have high bias whereas you were
**[0:39]** to fit a complex model, then you might suffer from high variance.
**[0:44]** And there's this tradeoff between bias and variance, and in our example
**[0:50]** it was choosing a second order polynomial that helps you make a tradeoff and
**[0:56]** pick a model with lowest possible cross validation error.
**[1:01]** And so before the days of neural networks,
**[1:04]** machine learning engineers talked a lot about this bias variance tradeoff in
**[1:10]** which you have to balance the complexity that is the degree of polynomial.
**[1:16]** Or the regularization parameter longer to make bias and
**[1:20]** variance both not be too high.
**[1:22]** And if you hear machine learning engineers talk about the bias variance tradeoff.
**[1:27]** This is what they're referring to where if you have too simple a model,
**[1:31]** you have high bias, too complex a model high variance.
**[1:34]** And you have to find a tradeoff between these two bad things to find probably
**[1:39]** the best possible outcome.
**[1:41]** But it turns out that neural networks offer us a way out of this dilemma
**[1:46]** of having to tradeoff bias and variance with some caveats.
**[1:50]** And it turns out that large neural networks when trained on
**[1:55]** small term moderate sized datasets are low bias machines.
**[2:01]** And what I mean by that is, if you make your neural network large enough,
**[2:06]** you can almost always fit your training set well.
**[2:10]** So long as your training set is not enormous.
**[2:13]** And what this means is this gives us a new recipe to try to reduce bias or reduce
**[2:18]** variance as needed without needing to really trade off between the two of them.
**[2:23]** So let me share with you a simple recipe that isn't always applicable.
**[2:28]** But if it applies can be very powerful for getting an accurate model
**[2:33]** using a neural network which is first train your algorithm on your
**[2:38]** training set and then asked does it do well on the training set.
**[2:43]** So measure Jtrain and see if it is high and by high, I mean for
**[2:48]** example, relative to human level performance or
**[2:52]** some baseline level of performance and if it is not doing
**[2:57]** well then you have a high bias problem, high trains error.
**[3:02]** And one way to reduce bias is to just use a bigger neural network and
**[3:07]** by bigger neural network,
**[3:09]** I mean either more hidden layers or more hidden units per layer.
**[3:14]** And you can then keep on going through this loop and
**[3:17]** make your neural network bigger and bigger until it does well on the training set.
**[3:22]** Meaning that achieves the level of error in your training set that is roughly
**[3:26]** comparable to the target level of error you hope to get to,
**[3:29]** which could be human level performance.
**[3:33]** After it does well on the training set, so the answer to that question is yes.
**[3:38]** You then ask does it do well on the cross validation set?
**[3:41]** In other words, does it have high variance and if the answer is no,
**[3:46]** then you can conclude that the algorithm has high variance because it
**[3:50]** doesn't want to train set does not do on the cross validation set.
**[3:54]** So that big gap in Jcv and Jtrain indicates you probably have a high
**[3:59]** variance problem, and if you have a high variance problem,
**[4:03]** then one way to try to fix it is to get more data.
**[4:06]** To get more data and go back and retrain the model and just double-check,
**[4:11]** do you just want the training set?
**[4:13]** If not, have a bigger network, or
**[4:15]** it does see if it does when the cross validation set and if not get more data.
**[4:20]** And if you can keep on going around and around and
**[4:23]** around this loop until eventually it does well in the cross validation set.
**[4:27]** Then you're probably done because now you have a model that does well on the cross
**[4:33]** validation set and hopefully will also generalize to new examples as well.
**[4:38]** Now, of course there are limitations of the application of this recipe training
**[4:43]** bigger neural network doesn't reduce bias but
**[4:45]** at some point it does get computationally expensive.
**[4:49]** That's why the rise of neural networks has been really assisted by the rise of
**[4:54]** very fast computers, including especially GPUs or graphics processing units.
**[5:00]** Hardware traditionally used to speed up computer graphics, but
**[5:04]** it turns out has been very useful for speeding on neural networks as well.
**[5:08]** But even with hardware accelerators beyond a certain point,
**[5:11]** the neural networks are so large, it takes so long to train, it becomes infeasible.
**[5:16]** And then of course the other limitation is more data.
**[5:20]** Sometimes you can only get so much data, and
**[5:23]** beyond a certain point it's hard to get much more data.
**[5:26]** But I think this recipe explains a lot of the rise of deep learning in the last
**[5:31]** several years, which is for applications where you do have access to a lot of data.
**[5:37]** Then being able to train large neural networks allows you to
**[5:41]** eventually get pretty good performance on a lot of applications.
**[5:46]** One thing that was implicit in this slide that may not have been obvious is that as
**[5:51]** you're developing a learning algorithm, sometimes you find that you have high
**[5:55]** bias, in which case you do things like increase your neural network.
**[6:00]** But then after you increase your neural network you may find that you have high
**[6:04]** variance, in which case you might do other things like collect more data.
**[6:09]** And during the hours or days or weeks, you're developing a machine learning
**[6:13]** algorithm at different points, you may have high bias or high variance.
**[6:17]** And it can change but it's depending on whether your algorithm has high bias or
**[6:22]** high variance at that time.
**[6:24]** Then that can help give guidance for what you should be trying next.
**[6:28]** When you train your neural network, one thing that people have asked me
**[6:33]** before is, hey Andrew, what if my neural network is too big?
**[6:37]** Will that create a high variance problem?
**[6:40]** It turns out that a large neural network with well-chosen regularization,
**[6:46]** well usually do as well or better than a smaller one.
**[6:51]** And so for example, if you have a small neural network like this,
**[6:56]** and you were to switch to a much larger neural network like this,
**[7:00]** you would think that the risk of overfitting goes up significantly.
**[7:06]** But it turns out that if you were to regularize this larger neural network
**[7:10]** appropriately, then this larger neural network usually will do at least
**[7:15]** as well or better than the smaller one.
**[7:18]** So long as the regularization has chosen appropriately.
**[7:22]** So another way of saying this is that it almost never hurts to go to a larger
**[7:26]** neural network so long as you regularized appropriately with one caveat,
**[7:31]** which is that when you train the larger neural network,
**[7:34]** it does become more computational e expensive.
**[7:37]** So the main way it hurts, it will slow down your training and
**[7:41]** your inference process and very briefly to regularize a neural network.
**[7:46]** This is what you do if the cost function for
**[7:50]** your neural network is the average loss and
**[7:54]** so the loss here could be squared error or logistic loss.
**[7:59]** Then the regularization term for a neural network looks like pretty much what
**[8:04]** you'd expect is lambda over two m times the sum of w squared where this is
**[8:08]** a sum over all weights W in the neural network and similar to regularization for
**[8:13]** linear regression and logistic regression,
**[8:16]** we usually don't regularize the parameters be in the neural network although
**[8:21]** in practice it makes very little difference whether you do so or not.
**[8:26]** And the way you would implement regularization in tensorflow is
**[8:30]** recall that this was the code for
**[8:33]** implementing an unregulated Rised handwritten digit classification model.
**[8:38]** We create three layers like so with a number of fitting units activation And
**[8:43]** then create a sequential model with the three layers.
**[8:47]** If you want to add regularization then you would just add this
**[8:52]** extra term colonel regularize A equals l.
**[8:55]** two and then 0.01 where that's the value of longer in terms of though actually
**[9:00]** lets you choose different values of lambda for different layers although for
**[9:05]** simplicity you can choose the same value of lambda for all the weights and
**[9:10]** all of the different layers as follows.
**[9:12]** And then this will allow you to implement regularization in your neural network.
**[9:18]** So to summarize two Takeaways, I hope you have from this video are one.
**[9:23]** It hardly ever hurts to have a larger neural network so
**[9:26]** long as you regularize appropriately.
**[9:29]** one caveat being that having a larger neural network can slow down your algorithm.
**[9:34]** So maybe that's the one way it hurts, but it shouldn't hurt your algorithm's performance
**[9:38]** for the most part and in fact it could even help it significantly.
**[9:42]** And second so long as your training set isn't too large.
**[9:47]** Then a neural network,
**[9:48]** especially large neural network is often a low bias machine.
**[9:52]** It just fits very complicated functions very well, which is why when I'm training
**[9:56]** neural networks, I find that I'm often fighting variance problems rather than bias
**[10:01]** problems, at least if the neural network is large enough.
**[10:05]** So the rise of deep learning has really changed the way that machine learning
**[10:09]** practitioners think about bias and variance.
**[10:12]** Having said that even when you're training a neural network measuring bias and
**[10:16]** variance and
**[10:17]** using that to guide what you do next is often a very helpful thing to do.
**[10:23]** So that's it for bias and variance.
**[10:25]** Let's go on to the next video.
**[10:27]** We will take all the ideas we've learned and
**[10:30]** see how they fit in to the development process of machine learning systems.
**[10:34]** And I hope that we'll tie a lot of these pieces together to give you practical
**[10:38]** advice for how to quickly move forward in the development of your machine
**[10:42]** learning systems
