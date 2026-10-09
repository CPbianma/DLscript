---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 3
section: Continuous state spaces
item_title: Algorithm refinement:  Mini-batch and soft updates (optional)
duration: 12 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/TsaXj/algorithm-refinement-mini-batch-and-soft-updates-optional
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Algorithm refinement:  Mini-batch and soft updates (optional) — Transcript

**[0:01]** In this video, we'll look at
**[0:03]** two further refinements to
**[0:05]** the reinforcement learning algorithm you've seen.
**[0:07]** The first idea is called using mini-batches,
**[0:11]** and this turns out to be an idea they can both speedup
**[0:14]** your reinforcement learning algorithm and it's
**[0:16]** also applicable to supervised learning.
**[0:19]** They can help you speed up
**[0:20]** your supervised learning algorithm as well,
**[0:22]** like training a neural network,
**[0:23]** or training a linear regression,
**[0:25]** or logistic regression model.
**[0:27]** The second idea we'll look at is soft updates,
**[0:31]** which it turns out will help
**[0:32]** your reinforcement learning algorithm
**[0:33]** do a better job to converge to a good solution.
**[0:36]** Let's take a look at mini-batches and soft updates.
**[0:40]** To understand mini-batches, let's
**[0:43]** just look at supervised learning to start.
**[0:47]** Here's the dataset of
**[0:49]** housing sizes and prices that you had seen
**[0:53]** way back in the first course of this specialization
**[0:56]** on using linear regression to predict housing prices.
**[0:59]** There we had come up with
**[1:02]** this cost function for the parameters w and b,
**[1:06]** it was 1 over 2m,
**[1:07]** sum of the prediction minus the actual value y^​2.
**[1:12]** The gradient descent algorithm was
**[1:15]** to repeatedly update w as w minus
**[1:18]** the learning rate alpha times the partial derivative respect
**[1:22]** to w of the cost J of wb,
**[1:26]** and similarly to update b as follows.
**[1:30]** Let me just take this definition of J of
**[1:33]** wb and substitute it in here.
**[1:38]** Now, when we looked at this example,
**[1:41]** way back when were starting to talk
**[1:43]** about linear regression and supervised learning,
**[1:46]** the training set size m was pretty small.
**[1:49]** I think we had 47 training examples.
**[1:51]** But what if you have a very large training set?
**[1:54]** Say m equals 100 million.
**[1:58]** There are many countries including
**[2:00]** the United States with over a 100 million housing units,
**[2:04]** and so a national census will give you
**[2:07]** a dataset that is this order of magnitude or size.
**[2:11]** The problem with this algorithm
**[2:13]** when your dataset is this big,
**[2:15]** is that every single step of gradient descent requires
**[2:19]** computing this average over 100 million examples,
**[2:25]** and this turns out to be very slow.
**[2:28]** Every step of gradient descent means you would compute
**[2:31]** this sum or this average over 100 million examples.
**[2:35]** Then you take one tiny gradient descent step
**[2:38]** and you go back and have to scan over
**[2:41]** your entire 100 million example
**[2:43]** dataset again to compute the derivative on the next step,
**[2:46]** they take another tiny gradient descent step
**[2:49]** and so on and so on.
**[2:51]** When the training set size is very large,
**[2:54]** this gradient descent algorithm
**[2:57]** turns out to be quite slow.
**[2:58]** The idea of mini-batch gradient descent is to not
**[3:03]** use all 100 million training examples
**[3:06]** on every single iteration through this loop.
**[3:08]** Instead, we may pick a smaller number,
**[3:10]** let me call it m prime equals say, 1,000.
**[3:15]** On every step, instead of using all 100 million examples,
**[3:21]** we would pick some subset of 1,000 or m prime examples.
**[3:27]** This inner term becomes 1 over 2m prime is
**[3:30]** sum over sum m prime examples.
**[3:34]** Now each iteration through gradient descent
**[3:38]** requires looking only at the
**[3:40]** 1,000 rather than 100 million examples,
**[3:43]** and every step takes
**[3:45]** much less time and just
**[3:46]** leads to a more efficient algorithm.
**[3:48]** What mini-batch gradient descent does
**[3:50]** is on the first iteration through the algorithm,
**[3:53]** may be it looks at that subset of the data.
**[3:57]** On the next iteration,
**[3:58]** maybe it looks at that subset of the data, and so on.
**[4:02]** For the third iteration and so on,
**[4:05]** so that every iteration is looking at
**[4:07]** just a subset of
**[4:09]** the data so each iteration runs much more quickly.
**[4:12]** To see why this might be a reasonable algorithm,
**[4:16]** here's the housing dataset.
**[4:19]** If on the first iteration we were
**[4:22]** to look at just say five examples,
**[4:25]** this is not the whole dataset but it's slightly
**[4:28]** representative of the string line
**[4:30]** you might want to fit in the end,
**[4:31]** and so taking one gradient descent step to
**[4:34]** make the algorithm better fit
**[4:35]** these five examples is okay.
**[4:37]** But then on the next iteration,
**[4:38]** you take a different five examples like that shown here.
**[4:42]** You take one gradient descent step
**[4:44]** using these five examples,
**[4:46]** and on the next iteration you use
**[4:48]** a different five examples and so on and so forth.
**[4:50]** You can scan through this list of
**[4:53]** examples from top to bottom.
**[4:55]** That would be one way.
**[4:57]** Another way would be if
**[4:59]** on every single iteration you just
**[5:01]** pick a totally different five examples to use.
**[5:05]** You might remember with batch gradient descent,
**[5:08]** if these are the contours of the cost function J.
**[5:12]** Then batch gradient descent would say,
**[5:14]** start here and take a step,
**[5:17]** take a step, take a step,
**[5:18]** take a step, take a step.
**[5:20]** Every step of gradient descent
**[5:22]** causes the parameters to reliably
**[5:25]** get closer to the global minimum
**[5:27]** of the cost function here in the middle.
**[5:29]** In contrast, mini-batch gradient descent or
**[5:32]** a mini-batch learning algorithm
**[5:34]** will do something like this.
**[5:36]** If you start here,
**[5:37]** then the first iteration uses just five examples.
**[5:40]** It'll hit in the right direction but
**[5:42]** maybe not the best gradient descent direction.
**[5:45]** Then the next iteration they may do that,
**[5:48]** the next iteration that,
**[5:49]** and that and sometimes just by chance,
**[5:53]** the five examples you chose may be an unlucky choice and
**[5:56]** even head in the wrong direction
**[5:58]** away from the global minimum,
**[6:00]** and so on and so forth.
**[6:02]** But on average,
**[6:03]** mini-batch gradient descent will
**[6:05]** tend toward the global minimum,
**[6:08]** not reliably and somewhat noisily,
**[6:10]** but every iteration is
**[6:12]** much more computationally inexpensive and
**[6:15]** so mini-batch learning or mini-batch gradient descent
**[6:19]** turns out to be a much faster algorithm
**[6:21]** when you have a very large training set.
**[6:24]** In fact, for supervised learning,
**[6:26]** where you have a very large training set,
**[6:28]** mini-batch learning or mini-batch gradient descent,
**[6:32]** or a mini-batch version
**[6:34]** with other optimization algorithms like Atom,
**[6:37]** is used more common than batch gradient descent.
**[6:40]** Going back to our reinforcement learning algorithm,
**[6:44]** this is the algorithm that we had seen previously.
**[6:49]** The mini-batch version of this would be,
**[6:52]** even if you have stored the 10,000 most
**[6:55]** recent tuples in the replay buffer,
**[7:00]** what you might choose to do is not use all
**[7:02]** 10,000 every time you train a model.
**[7:06]** Instead, what you might do is just take the subset.
**[7:09]** You might choose just 1,000 examples of these s,
**[7:14]** a, R of s,
**[7:15]** s prime tuples and use it to create
**[7:19]** just 1,000 training examples to train the neural network.
**[7:24]** It turns out that this will make
**[7:26]** each iteration of training a model a little bit more
**[7:29]** noisy but much faster and this will
**[7:32]** overall tend to speed
**[7:34]** up this reinforcement learning algorithm.
**[7:36]** That's how mini-batching can speed up
**[7:39]** both a supervised learning algorithm
**[7:41]** like linear regression
**[7:43]** as well as this reinforcement learning algorithm
**[7:46]** where you may use a mini-batch size of say,
**[7:50]** 1,000 examples, even if you store it away,
**[7:53]** 10,000 of these tuples in your replay buffer.
**[7:56]** Finally, there's one other refinement to
**[7:58]** the algorithm that can make it converge more reliably,
**[8:02]** which is, I've written out this step
**[8:04]** here of Set Q equals Q_new.
**[8:07]** But it turns out that this can
**[8:10]** make a very abrupt change to Q.
**[8:13]** If you train a new neural network to new,
**[8:16]** maybe just by chance is not a very good neural network.
**[8:19]** Maybe is even a little bit worse than the old one,
**[8:22]** then you just overwrote your Q function
**[8:25]** with a potentially worse noisy neural network.
**[8:30]** The soft update method helps to prevent
**[8:34]** Q_new through just one unlucky step getting worse.
**[8:39]** In particular, the neural network
**[8:42]** Q will have some parameters,
**[8:44]** W and B,
**[8:45]** all the parameters for all
**[8:46]** the layers in the neural network.
**[8:48]** When you train the new neural network,
**[8:51]** you get some parameters W_new and B_new.
**[8:57]** In the original algorithm S as described on that slide,
**[9:00]** you would set W to be equal to W_new and B equals B_new.
**[9:08]** That's what set Q equals Q_new means.
**[9:10]** With the soft update,
**[9:12]** what we do is instead Set W equals 0.01
**[9:17]** times W_new plus 0.99 times W. In other words,
**[9:24]** we're going to make W to be 99 percent the old version of
**[9:28]** W plus one percent of the new version W_new.
**[9:33]** This is called a soft update because
**[9:35]** whenever we train a new neural network W_new,
**[9:39]** we're only going to accept a little bit of the new value.
**[9:42]** As similarly, B equals 0.01 times
**[9:45]** B_new plus 0.99 times B.
**[9:49]** These numbers, 0.01 and 0.99,
**[9:52]** these are hyperparameters that you could set,
**[9:55]** but it controls how aggressively you move W
**[9:59]** to W_new and these two numbers
**[10:02]** are expected to add up to one.
**[10:04]** One extreme would be if you were to set W equals
**[10:07]** one times W_new plus 0 times W, in which case,
**[10:11]** you're back to the original algorithm
**[10:13]** up here where you're just copying W_new onto
**[10:16]** W. But a soft update allows you to make
**[10:19]** a more gradual change to Q or to
**[10:23]** the neural network parameters W and B that affect
**[10:26]** your current guess for the Q function Q of s, a.
**[10:31]** It turns out that using the soft update method
**[10:34]** causes the reinforcement learning algorithm
**[10:37]** to converge more reliably.
**[10:39]** It makes it less likely
**[10:40]** that the reinforcement learning algorithm will
**[10:42]** oscillate or divert or have other undesirable properties.
**[10:46]** With these two final refinements to the algorithm,
**[10:49]** mini-batching, which actually
**[10:51]** applies very well to supervise learning as well,
**[10:53]** not just reinforcement learning,
**[10:55]** as well as the idea of soft updates,
**[10:57]** you should be able to get your lunar algorithm to
**[10:59]** work really well on the Lunar Lander.
**[11:02]** The Lunar Lander is actually a decently complex,
**[11:05]** decently challenging application and so that
**[11:08]** you can get it to work and land safely on the moon.
**[11:11]** I think that's actually really cool and I hope you
**[11:14]** enjoy playing with the practice lab.
**[11:17]** Now, we've talked a lot about reinforcement learning.
**[11:20]** Before we wrap up, I'd like to share with you
**[11:23]** my thoughts on the state of reinforcement learning
**[11:25]** so that as you go out and build applications
**[11:28]** using different machine learning
**[11:29]** techniques via supervised,
**[11:31]** unsupervised, reinforcement learning
**[11:32]** techniques that you have a framework for
**[11:35]** understanding where reinforcement learning
**[11:37]** fits in to the world of machine learning today.
**[11:40]** Let's go take a look at that in the next video.
