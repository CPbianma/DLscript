---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 2
section: Optimization Algorithms
item_title: Understanding Mini-batch Gradient Descent
duration: 11 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/lBXu8/understanding-mini-batch-gradient-descent
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Understanding Mini-batch Gradient Descent — Transcript

**[0:00]** In the previous video, you saw how you can use mini-batch gradient descent
**[0:04]** to start making progress and start taking gradient descent steps, even when you're
**[0:08]** just partway through processing your training set even for the first time.
**[0:11]** In this video, you learn more details of how to implement gradient descent and
**[0:16]** gain a better understanding of what it's doing and why it works.
**[0:19]** With batch gradient descent on every iteration you go through the entire
**[0:24]** training set and you'd expect the cost to go down on every single iteration.
**[0:30]** So if we've had the cost function j as
**[0:33]** a function of different iterations it should decrease on every single iteration.
**[0:37]** And if it ever goes up even on iteration then something is wrong.
**[0:40]** Maybe you're running ways to big.
**[0:43]** On mini batch gradient descent though, if you plot progress on your cost function,
**[0:48]** then it may not decrease on every iteration.
**[0:51]** In particular, on every iteration you're
**[0:56]** processing some X{t}, Y{t} and so
**[1:01]** if you plot the cost function J{t},
**[1:05]** which is computer using just X{t}, Y{t}.
**[1:11]** Then it's as if on every iteration you're training on a different training set or
**[1:17]** really training on a different mini batch.
**[1:19]** So you plot the cross function J,
**[1:20]** you're more likely to see something that looks like this.
**[1:23]** It should trend downwards, but it's also going to be a little bit noisier.
**[1:30]** So if you plot J{t}, as you're training mini batch in descent it may
**[1:35]** be over multiple epochs, you might expect to see a curve like this.
**[1:40]** So it's okay if it doesn't go down on every derivation.
**[1:44]** But it should trend downwards, and
**[1:46]** the reason it'll be a little bit noisy is that, maybe X{1},
**[1:51]** Y{1} is just the rows of easy mini batch so your cost might be a bit lower,
**[1:56]** but then maybe just by chance, X{2}, Y{2} is just a harder mini batch.
**[2:02]** Maybe you needed some mislabeled examples in it,
**[2:04]** in which case the cost will be a bit higher and so on.
**[2:06]** So that's why you get these oscillations as you
**[2:09]** plot the cost when you're running mini batch gradient descent.
**[2:13]** Now one of the parameters you need to choose is the size of your mini batch.
**[2:18]** So m was the training set size on one extreme, if the mini-batch size,
**[2:26]** = m, then you just end up with batch gradient descent.
**[2:36]** Alright, so in this extreme you would just have one mini-batch X{1},
**[2:41]** Y{1}, and this mini-batch is equal to your entire training set.
**[2:45]** So setting a mini-batch size m just gives you batch gradient descent.
**[2:49]** The other extreme would be if your mini-batch size, Were = 1.
**[2:59]** This gives you an algorithm called stochastic gradient descent.
**[3:07]** And here every example is its own mini-batch.
**[3:18]** So what you do in this case is you look at the first mini-batch, so X{1}, Y{1},
**[3:24]** but when your mini-batch size is one, this just has your first training example,
**[3:29]** and you take derivative to sense that your first training example.
**[3:34]** And then you next take a look at your second mini-batch, which is just your
**[3:39]** second training example, and take your gradient descent step with that, and
**[3:43]** then you do it with the third training example and so
**[3:45]** on looking at just one single training sample at the time.
**[3:50]** So let's look at what these two extremes will do on optimizing this cost function.
**[3:55]** If these are the contours of the cost function you're trying to minimize so
**[3:59]** your minimum is there.
**[4:01]** Then batch gradient descent might start somewhere and
**[4:05]** be able to take relatively low noise, relatively large steps.
**[4:12]** And you could just keep matching to the minimum.
**[4:15]** In contrast with stochastic gradient descent
**[4:19]** If you start somewhere let's pick a different starting point.
**[4:22]** Then on every iteration you're taking gradient descent with just a single strain
**[4:26]** example so most of the time you hit two at the global minimum.
**[4:30]** But sometimes you hit in the wrong direction if that one example
**[4:33]** happens to point you in a bad direction.
**[4:36]** So stochastic gradient descent can be extremely noisy.
**[4:40]** And on average, it'll take you in a good direction, but
**[4:45]** sometimes it'll head in the wrong direction as well.
**[4:47]** As stochastic gradient descent won't ever converge,
**[4:50]** it'll always just kind of oscillate and wander around the region of the minimum.
**[4:54]** But it won't ever just head to the minimum and stay there.
**[4:58]** In practice, the mini-batch size you use will be somewhere in between.
**[5:07]** Somewhere between in 1 and m and 1 and m are respectively too small and too large.
**[5:15]** And here's why.
**[5:16]** If you use batch gradient descent, So
**[5:23]** this is your mini batch size equals m.
**[5:30]** Then you're processing a huge training set on every iteration.
**[5:35]** So the main disadvantage of this is that it takes too much time too long
**[5:40]** per iteration assuming you have a very long training set.
**[5:43]** If you have a small training set then batch gradient descent is fine.
**[5:46]** If you go to the opposite, if you use stochastic gradient descent,
**[5:54]** Then it's nice that you get to make progress after processing just tone
**[5:58]** example that's actually not a problem.
**[6:02]** And the noisiness can be ameliorated or
**[6:04]** can be reduced by just using a smaller learning rate.
**[6:07]** But a huge disadvantage to stochastic gradient descent is
**[6:12]** that you lose almost all your speed up from vectorization.
**[6:18]** Because, here you're processing a single training example at a time.
**[6:22]** The way you process each example is going to be very inefficient.
**[6:26]** So what works best in practice is something in between where you have some,
**[6:36]** Mini-batch size not to big or too small.
**[6:44]** And this gives you in practice the fastest learning.
**[6:51]** And you notice that this has two good things going for it.
**[6:54]** One is that you do get a lot of vectorization.
**[6:58]** So in the example we used on the previous video, if your mini batch size was
**[7:02]** 1000 examples then, you might be able to vectorize across 1000 examples
**[7:07]** which is going to be much faster than processing the examples one at a time.
**[7:13]** And second, you can also make progress,
**[7:22]** Without needing to wait til you process the entire training set.
**[7:32]** So again using the numbers we have from the previous video, each epoch each part
**[7:36]** your training set allows you to see 5,000 gradient descent steps.
**[7:41]** So in practice they'll be some in-between mini-batch size that works best.
**[7:46]** And so with mini-batch gradient descent we'll start here,
**[7:49]** maybe one iteration does this, two iterations, three, four.
**[7:53]** And It's not guaranteed to always head toward the minimum but it tends to head
**[7:58]** more consistently in direction of the minimum than the consequent descent.
**[8:03]** And then it doesn't always exactly convert or oscillate in a very small region.
**[8:08]** If that's an issue you can always reduce the learning rate slowly.
**[8:11]** We'll talk more about learning rate decay or
**[8:13]** how to reduce the learning rate in a later video.
**[8:15]** So if the mini-batch size should not be m and should not be 1 but
**[8:20]** should be something in between, how do you go about choosing it?
**[8:23]** Well, here are some guidelines.
**[8:24]** First, if you have a small training set, Just use batch gradient descent.
**[8:36]** If you have a small training set then no point using mini-batch gradient descent
**[8:41]** you can process a whole training set quite fast.
**[8:43]** So you might as well use batch gradient descent.
**[8:45]** What a small training set means, I would say if it's less than maybe 2000
**[8:50]** it'd be perfectly fine to just use batch gradient descent.
**[8:54]** Otherwise, if you have a bigger training set, typical mini batch sizes would be,
**[9:03]** Anything from 64 up to maybe 512 are quite typical.
**[9:09]** And because of the way computer memory is layed out and accessed,
**[9:14]** sometimes your code runs faster if your mini-batch size is a power of 2.
**[9:19]** All right, so 64 is 2 to the 6th, is 2 to the 7th, 2 to the 8,
**[9:24]** 2 to the 9, so often I'll implement my mini-batch size to be a power of 2.
**[9:30]** I know that in a previous video I used a mini-batch size of 1000,
**[9:33]** if you really wanted to do that I would recommend you just use your 1024,
**[9:37]** which is 2 to the power of 10.
**[9:39]** And you do see mini batch sizes of size 1024, it is a bit more rare.
**[9:46]** This range of mini batch sizes, a little bit more common.
**[9:50]** One last tip is to make sure that your mini batch,
**[9:57]** All of your X{t}, Y{t} that that fits in CPU/GPU memory.
**[10:08]** And this really depends on your application and
**[10:10]** how large a single training sample is.
**[10:12]** But if you ever process a mini-batch that doesn't actually fit in CPU,
**[10:17]** GPU memory, whether you're using the process, the data.
**[10:20]** Then you find that the performance suddenly falls of a cliff and
**[10:24]** is suddenly much worse.
**[10:25]** So I hope this gives you a sense of the typical range of mini batch sizes that
**[10:30]** people use.
**[10:31]** In practice of course the mini batch size is another hyper parameter
**[10:35]** that you might do a quick search over to try to figure out which one
**[10:40]** is most sufficient of reducing the cost function j.
**[10:43]** So what i would do is just try several different values.
**[10:47]** Try a few different powers of two and then see if you can pick one that makes your
**[10:51]** gradient descent optimization algorithm as efficient as possible.
**[10:56]** But hopefully this gives you a set of guidelines for
**[10:59]** how to get started with that hyper parameter search.
**[11:03]** You now know how to implement mini-batch gradient descent and make your algorithm
**[11:07]** run much faster, especially when you're training on a large training set.
**[11:10]** But it turns out there're even more efficient algorithms
**[11:12]** than gradient descent or mini-batch gradient descent.
**[11:15]** Let's start talking about them in the next few videos.
