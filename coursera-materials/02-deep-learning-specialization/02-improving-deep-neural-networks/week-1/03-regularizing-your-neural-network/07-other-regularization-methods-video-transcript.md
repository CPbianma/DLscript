---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 1
section: Regularizing your Neural Network
item_title: Other Regularization Methods
duration: 8 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/Pa53F/other-regularization-methods
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Other Regularization Methods — Transcript

**[0:00]** In addition to L2 regularization and drop out regularization there
**[0:04]** are few other techniques to reducing over fitting in your neural network.
**[0:08]** Let's take a look.
**[0:09]** Let's say you fitting a CAD crossfire.
**[0:10]** If you are over fitting getting more training data can help, but getting more
**[0:15]** training data can be expensive and sometimes you just can't get more data.
**[0:20]** But what you can do is augment your training set by taking image like this.
**[0:24]** And for example, flipping it horizontally and
**[0:27]** adding that also with your training set.
**[0:29]** So now instead of just this one example in your training set,
**[0:32]** you can add this to your training example.
**[0:35]** So by flipping the images horizontally,
**[0:38]** you could double the size of your training set.
**[0:40]** Because you're training set is now a bit redundant this isn't as good as if you had
**[0:44]** collected an additional set of brand new independent examples.
**[0:50]** But you could do this Without needing to pay the expense of going out to take
**[0:55]** more pictures of cats.
**[0:57]** And then other than flipping horizontally,
**[0:59]** you can also take random crops of the image.
**[1:02]** So here we're rotated and sort of randomly zoom into the image and
**[1:06]** this still looks like a cat.
**[1:07]** So by taking random distortions and translations of the image you could
**[1:11]** augment your data set and make additional fake training examples.
**[1:16]** Again, these extra fake training examples they don't add as much information as they
**[1:20]** were to call they get a brand new independent example of a cat.
**[1:25]** But because you can do this, almost for free, other than for
**[1:28]** some computational costs.
**[1:30]** This can be an inexpensive way to give your algorithm more data and
**[1:37]** therefore sort of regularize it and reduce over fitting.
**[1:42]** And by synthesizing examples like this what you're really telling your algorithm
**[1:47]** is that If something is a cat then flipping it horizontally is still a cat.
**[1:51]** Notice I didn't flip it vertically,
**[1:53]** because maybe we don't want upside down cats, right?
**[1:55]** And then also maybe randomly zooming in to part of the image it's probably
**[1:58]** still a cat.
**[2:00]** For optical character recognition you can also bring your data set by taking digits
**[2:04]** and imposing random rotations and distortions to it.
**[2:08]** So If you add these things to your training set,
**[2:11]** these are also still digit force.
**[2:14]** For illustration I applied a very strong distortion.
**[2:18]** So this look very wavy for, in practice you don't need to distort the four quite
**[2:23]** as aggressively, but just a more subtle distortion than what I'm showing here,
**[2:27]** to make this example clearer for you, right?
**[2:29]** But a more subtle distortion is usually used in practice,
**[2:32]** because this looks like really warped fours.
**[2:35]** So data augmentation can be used as a regularization technique,
**[2:40]** in fact similar to regularization.
**[2:43]** There's one other technique that is often used called early stopping.
**[2:46]** So what you're going to do is as you run gradient descent you're going to plot
**[2:52]** your, either the training error,
**[2:54]** you'll use 01 classification error on the training set.
**[2:57]** Or just plot the cost function J optimizing, and
**[3:00]** that should decrease monotonically, like so, all right?
**[3:04]** Because as you trade, hopefully,
**[3:05]** you're trading around your cost function J should decrease.
**[3:09]** So with early stopping, what you do is you plot this, and
**[3:11]** you also plot your dev set error.
**[3:17]** And again, this could be a classification error in a development sense, or something
**[3:20]** like the cost function, like the logistic loss or the log loss of the dev set.
**[3:25]** Now what you find is that your dev set error will usually go down for
**[3:29]** a while, and then it will increase from there.
**[3:32]** So what early stopping does is, you will say well,
**[3:35]** it looks like your neural network was doing best around that iteration, so
**[3:40]** we just want to stop trading on your neural network halfway and
**[3:43]** take whatever value achieved this dev set error.
**[3:47]** So why does this work?
**[3:48]** Well when you've haven't run many iterations for
**[3:51]** your neural network yet your parameters w will be close to zero.
**[3:55]** Because with random initialization you probably initialize w to small random
**[3:59]** values so before you train for a long time, w is still quite small.
**[4:04]** And as you iterate, as you train, w will get bigger and bigger and bigger until
**[4:08]** here maybe you have a much larger value of the parameters w for your neural network.
**[4:14]** So what early stopping does is by stopping halfway you have only
**[4:18]** a mid-size rate w.
**[4:23]** And so similar to L2 regularization by picking a neural network with smaller
**[4:28]** norm for your parameters w, hopefully your neural network is over fitting less.
**[4:34]** And the term early stopping refers to the fact that you're just
**[4:37]** stopping the training of your neural network earlier.
**[4:40]** I sometimes use early stopping when training a neural network.
**[4:43]** But it does have one downside, let me explain.
**[4:46]** I think of the machine learning process as comprising several different steps.
**[4:50]** One, is that you want an algorithm to optimize the cost function j and
**[4:55]** we have various tools to do that, such as grade intersect.
**[4:59]** And then we'll talk later about other algorithms, like momentum and
**[5:04]** RMS prop and Atom and so on.
**[5:08]** But after optimizing the cost function j, you also wanted to not over-fit.
**[5:15]** And we have some tools to do that such as your regularization,
**[5:19]** getting more data and so on.
**[5:22]** Now in machine learning, we already have so many hyper-parameters it surge over.
**[5:26]** It's already very complicated to choose among the space of possible algorithms.
**[5:31]** And so I find machine learning easier to think about
**[5:34]** when you have one set of tools for optimizing the cost function J,
**[5:37]** and when you're focusing on authorizing the cost function J.
**[5:41]** All you care about is finding w and b, so that J(w,b) is as small as possible.
**[5:46]** You just don't think about anything else other than reducing this.
**[5:50]** And then it's completely separate task to not over fit,
**[5:55]** in other words, to reduce variance.
**[5:57]** And when you're doing that, you have a separate set of tools for doing it.
**[6:01]** And this principle is sometimes called orthogonalization.
**[6:06]** And there's this idea, that you want to be able to think about one task at a time.
**[6:10]** I'll say more about orthorganization in a later video, so
**[6:14]** if you don't fully get the concept yet, don't worry about it.
**[6:17]** But, to me the main downside of early stopping is that
**[6:21]** this couples these two tasks.
**[6:23]** So you no longer can work on these two problems independently,
**[6:28]** because by stopping gradient decent early,
**[6:30]** you're sort of breaking whatever you're doing to optimize cost function J,
**[6:34]** because now you're not doing a great job reducing the cost function J.
**[6:37]** You've sort of not done that that well.
**[6:39]** And then you also simultaneously trying to not over fit.
**[6:43]** So instead of using different tools to solve the two problems,
**[6:46]** you're using one that kind of mixes the two.
**[6:48]** And this just makes the set of
**[6:52]** things you could try are more complicated to think about.
**[6:56]** Rather than using early stopping, one alternative is just use L2 regularization
**[7:01]** then you can just train the neural network as long as possible.
**[7:05]** I find that this makes the search space of hyper parameters easier to decompose,
**[7:09]** and easier to search over.
**[7:10]** But the downside of this though is that you might have to try a lot of values of
**[7:14]** the regularization parameter lambda.
**[7:16]** And so this makes searching over many values of lambda more computationally
**[7:21]** expensive.
**[7:22]** And the advantage of early stopping is that running the gradient descent process
**[7:26]** just once, you get to try out values of small w, mid-size w, and
**[7:30]** large w, without needing to try a lot of values of the L2 regularization
**[7:35]** hyperparameter lambda.
**[7:40]** If this concept doesn't completely make sense to you yet, don't worry about it.
**[7:43]** We're going to talk about orthogonalization in greater
**[7:46]** detail in a later video, I think this will make a bit more sense.
**[7:49]** Despite it's disadvantages, many people do use it.
**[7:52]** I personally prefer to just use L2 regularization and
**[7:55]** try different values of lambda.
**[7:57]** That's assuming you can afford the computation to do so.
**[8:00]** But early stopping does let you get a similar effect without
**[8:03]** needing to explicitly try lots of different values of lambda.
**[8:06]** So you've now seen how to use data augmentation as well as if you wish early
**[8:12]** stopping in order to reduce variance or prevent over fitting your neural network.
**[8:17]** Next let's talk about some techniques for
**[8:19]** setting up your optimization problem to make your training go quickly.
