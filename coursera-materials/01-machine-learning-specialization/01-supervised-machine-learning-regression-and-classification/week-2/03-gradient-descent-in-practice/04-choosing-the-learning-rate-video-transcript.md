---
type: video-transcript
specialization: Machine Learning Specialization
course: Supervised Machine Learning: Regression and Classification
week: 2
section: Gradient descent in practice
item_title: Choosing the learning rate
duration: 6 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/10ZVv/choosing-the-learning-rate
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Choosing the learning rate — Transcript

**[0:01]** Your learning algorithm will run much
**[0:04]** better with an appropriate choice of learning rate.
**[0:06]** If it's too small,
**[0:08]** it will run very slowly and if it is too large,
**[0:10]** it may not even converge.
**[0:12]** Let's take a look at how you can
**[0:13]** choose a good learning rate for your model.
**[0:16]** Concretely, if you
**[0:18]** plot the cost for a number of iterations
**[0:21]** and notice that the costs sometimes
**[0:23]** goes up and sometimes goes down,
**[0:26]** you should take that as a clear sign that
**[0:28]** gradient descent is not working properly.
**[0:31]** This could mean that there's a bug in the code.
**[0:33]** Or sometimes it could mean that
**[0:35]** your learning rate is too large.
**[0:37]** So here's an illustration of what might be happening.
**[0:41]** Here the vertical axis is a cost function J,
**[0:46]** and the horizontal axis represents a parameter like
**[0:50]** maybe w_1 and if the learning rate is too big,
**[0:55]** then if you start off here,
**[0:57]** your update step may overshoot
**[0:59]** the minimum and end up here,
**[1:01]** and in the next update step here,
**[1:03]** your gain overshooting so you end up here and so on.
**[1:08]** That's why the cost can sometimes go
**[1:10]** up instead of decreasing.
**[1:12]** To fix this, you can use a smaller learning rate.
**[1:15]** Then your updates may start
**[1:17]** here and go down a little bit and down a bit,
**[1:20]** and we'll hopefully consistently
**[1:22]** decrease until it reaches the global minimum.
**[1:25]** Sometimes you may see that the cost
**[1:28]** consistently increases after each iteration,
**[1:31]** like this curve here.
**[1:33]** This is also likely due to
**[1:35]** a learning rate that is too large,
**[1:37]** and it could be addressed by
**[1:38]** choosing a smaller learning rate.
**[1:41]** But learning rates like this could
**[1:43]** also be a sign of a possible broken code.
**[1:46]** For example, if I wrote my code so that w_1 gets
**[1:51]** updated as w_1 plus Alpha times this derivative term,
**[1:56]** this could result in the cost consistently
**[1:58]** increasing at each iteration.
**[2:01]** This is because having the derivative term moves
**[2:05]** your cost J further from
**[2:07]** the global minimum instead of closer.
**[2:09]** So remember, you want to use in minus sign,
**[2:12]** so the code should be updated w_1 updated
**[2:16]** by w_1 minus Alpha times the derivative term.
**[2:21]** One debugging tip for a correct implementation of
**[2:24]** gradient descent is that
**[2:26]** with a small enough learning rate,
**[2:28]** the cost function should
**[2:29]** decrease on every single iteration.
**[2:32]** So if gradient descent isn't working,
**[2:36]** one thing I often do
**[2:37]** and I hope you find this tip useful too,
**[2:39]** one thing I'll often do is just set Alpha to be
**[2:43]** a very small number and see if that
**[2:46]** causes the cost to decrease on every iteration.
**[2:50]** If even with Alpha set to a very small number,
**[2:55]** J doesn't decrease on every single iteration,
**[2:58]** but instead sometimes increases,
**[3:00]** then that usually means
**[3:01]** there's a bug somewhere in the code.
**[3:02]** Note that setting Alpha
**[3:06]** to be really small is meant here as
**[3:08]** a debugging step and a very small value of Alpha
**[3:12]** is not going to be the most efficient choice
**[3:14]** for actually training your learning algorithm.
**[3:17]** One important trade-off is
**[3:18]** that if your learning rate is too small,
**[3:21]** then gradient descents can take
**[3:23]** a lot of iterations to converge.
**[3:25]** So when I am running gradient descent,
**[3:28]** I will usually try a range of
**[3:30]** values for the learning rate Alpha.
**[3:32]** I may start by trying a learning rate of
**[3:35]** 0.001 and I may also try
**[3:38]** learning rate as 10 times as large say
**[3:40]** 0.01 and 0.1 and so on.
**[3:44]** For each choice of Alpha,
**[3:46]** you might run gradient descent just for
**[3:49]** a handful of iterations and plot the cost function
**[3:52]** J as a function of the number of
**[3:55]** iterations and after trying a few different values,
**[3:59]** you might then pick the value of Alpha that seems to
**[4:02]** decrease the learning rate
**[4:04]** rapidly, but also consistently.
**[4:07]** In fact, what I actually do
**[4:09]** is try a range of values like this.
**[4:12]** After trying 0.001, I'll
**[4:15]** then increase the learning rate threefold to 0.003.
**[4:19]** After that, I'll try 0.01,
**[4:23]** which is again about three times as large as 0.003.
**[4:27]** So these are roughly trying out
**[4:29]** gradient descents with each value of
**[4:31]** Alpha being roughly three times
**[4:33]** bigger than the previous value.
**[4:36]** What I'll do is try a range of
**[4:38]** values until I found the value of that's too
**[4:41]** small and then also make
**[4:43]** sure I've found a value that's too large.
**[4:45]** I'll slowly try to
**[4:47]** pick the largest possible learning rate,
**[4:50]** or just something slightly smaller than
**[4:52]** the largest reasonable value that I found.
**[4:55]** When I do that, it usually gives
**[4:57]** me a good learning rate for my model.
**[5:00]** I hope this technique too
**[5:02]** will be useful for you to choose
**[5:04]** a good learning rate for
**[5:05]** your implementation of gradient descent.
**[5:08]** In the upcoming optional lab you can
**[5:12]** also take a look at how feature scaling is done in
**[5:15]** code and also see how different choices of
**[5:18]** the learning rate Alpha can lead to
**[5:20]** either better or worse training of your model.
**[5:23]** I hope you have fun playing with the value of Alpha
**[5:26]** and seeing the outcomes of different choices of Alpha.
**[5:30]** Please take a look and run the code in
**[5:32]** the optional lab to gain
**[5:34]** a deeper intuition about feature scaling,
**[5:36]** as well as the learning rate Alpha.
**[5:39]** Choosing learning rates is an important part of
**[5:41]** training many learning algorithms and I hope that
**[5:44]** this video gives you intuition about
**[5:46]** different choices and how to pick a good value for Alpha.
**[5:50]** Now, there are couple more ideas that you can use to
**[5:53]** make multiple linear regression much more powerful.
**[5:56]** That is choosing custom features,
**[5:59]** which will also allow you to fit curves,
**[6:01]** not just a straight line to your data.
**[6:03]** Let's take a look at that in the next video.
