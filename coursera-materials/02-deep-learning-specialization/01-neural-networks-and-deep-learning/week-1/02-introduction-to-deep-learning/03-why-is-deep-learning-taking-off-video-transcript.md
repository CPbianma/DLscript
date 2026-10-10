---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 1
section: Introduction to Deep Learning
item_title: Why is Deep Learning taking off?
duration: 10 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/praGm/why-is-deep-learning-taking-off
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Why is Deep Learning taking off? — Transcript

**[0:00]** If the basic technical ideas behind
**[0:03]** deep learning behind your networks have
**[0:05]** been around for decades why are they
**[0:07]** only just now taking off in this video
**[0:09]** let's go over some of the main drivers
**[0:12]** behind the rise of deep learning because
**[0:14]** I think this will help you to spot
**[0:16]** the best opportunities within your own
**[0:18]** organization to apply these to over the
**[0:20]** last few years a lot of people have
**[0:22]** asked me "Andrew why is deep learning
**[0:24]** suddenly working so well?" and when I
**[0:26]** am asked that question this is usually the
**[0:28]** picture I draw for them. Let's say we
**[0:31]** plot a figure where on the horizontal
**[0:33]** axis we plot the amount of data we have
**[0:36]** for a task and let's say on the vertical
**[0:39]** axis we plot the performance on involved
**[0:42]** learning algorithms such as the accuracy
**[0:44]** of our spam classifier or our ad click
**[0:48]** predictor or the accuracy of our neural
**[0:51]** net for figuring out the position of
**[0:53]** other cars for our self-driving car. It
**[0:56]** turns out if you plot the performance of
**[0:58]** a traditional learning algorithm like
**[1:00]** support vector machine or logistic
**[1:02]** regression as a function of the amount
**[1:04]** of data you have you might get a curve
**[1:07]** that looks like this where the
**[1:09]** performance improves for a while as you
**[1:11]** add more data but after a while the
**[1:14]** performance you know pretty much
**[1:16]** plateaus right suppose your horizontal
**[1:18]** lines enjoy that very well you know was
**[1:21]** it they didn't know what to do with huge
**[1:25]** amounts of data and what happened in our
**[1:28]** society over the last 10 years maybe is
**[1:30]** that for a lot of problems we went from
**[1:32]** having a relatively small amount of data
**[1:34]** to having you know often a fairly large
**[1:38]** amount of data and all of this was
**[1:40]** thanks to the digitization of a society
**[1:43]** where so much human activity is now in
**[1:46]** the digital realm we spend so much time
**[1:48]** on the computers on websites on mobile
**[1:51]** apps and activities on digital devices
**[1:54]** creates data and thanks to the rise of
**[1:57]** inexpensive cameras built into our cell
**[2:00]** phones, accelerometers, all sorts of
**[2:02]** sensors in the Internet of Things. We
**[2:05]** also just have been collecting one more
**[2:07]** and more data. So over the last 20 years
**[2:11]** for a lot of applications we just
**[2:12]** accumulate
**[2:13]** a lot more data more than traditional
**[2:16]** learning algorithms were able to
**[2:17]** effectively take advantage of and what
**[2:20]** new network lead turns out that if you
**[2:22]** train a small neural net then this
**[2:26]** performance maybe looks like that.
**[2:28]** If you train a somewhat larger Internet
**[2:31]** that's called as a medium-sized internet.
**[2:34]** To fall in something a little bit between
**[2:36]** and if you train a very large neural net
**[2:39]** then it's the form and often just keeps
**[2:42]** getting better and better. So, a couple
**[2:44]** observations. One is if you want to hit
**[2:46]** this very high level of performance then
**[2:49]** you need two things first: often you need
**[2:52]** to be able to train a big enough neural
**[2:54]** network in order to take advantage of
**[2:57]** the huge amount of data and second you
**[2:59]** need to be out here, on the x axis you do
**[3:02]** need a lot of data so we often say that
**[3:05]** scale has been driving deep learning
**[3:07]** progress and by scale I mean both the
**[3:10]** size of the neural network, meaning just
**[3:12]** a new network, a lot of hidden units, a
**[3:15]** lot of parameters, a lot of connections,
**[3:17]** as well as the scale of the data. In fact,
**[3:21]** today one of the most reliable ways to
**[3:23]** get better performance in a neural
**[3:25]** network is often to either train a
**[3:27]** bigger network or throw more data at it
**[3:29]** and that only works up to a point
**[3:31]** because eventually you run out of data
**[3:33]** or eventually then your network is so
**[3:35]** big that it takes too long to train. But,
**[3:37]** just improving scale has actually taken
**[3:40]** us a long way in the world of learning
**[3:42]** in order to make this diagram a bit more
**[3:45]** technically precise and just add a few
**[3:48]** more things I wrote the amount of data
**[3:49]** on the x-axis. Technically, this is amount
**[3:53]** of labeled data where by label data
**[3:57]** I mean training examples we have both
**[4:00]** the input X and the label Y I went to
**[4:03]** introduce a little bit of notation that
**[4:05]** we'll use later in this course. We're
**[4:07]** going to use lowercase alphabet m to
**[4:10]** denote the size of my training sets or
**[4:12]** the number of training examples
**[4:13]** this lowercase M so that's the
**[4:15]** horizontal axis. A couple other details, to
**[4:18]** this figure,
**[4:20]** in this regime of smaller training sets
**[4:23]** the relative ordering of the algorithms
**[4:26]** is actually not very well defined so if
**[4:29]** you don't have a lot of training data it is
**[4:31]** often up to your skill at hand
**[4:34]** engineering features that determines the
**[4:36]** foreman so it's quite possible that if
**[4:39]** someone training an SVM is more
**[4:41]** motivated to hand engineer features and
**[4:44]** someone training even larger neural nets,
**[4:46]** that may be in this small training set
**[4:48]** regime, the SEM could do better
**[4:50]** so you know in this region to the left
**[4:53]** of the figure the relative ordering
**[4:55]** between gene algorithms is not that well
**[4:57]** defined and performance depends much
**[4:59]** more on your skill at engine features
**[5:01]** and other mobile details of the
**[5:03]** algorithms and there's only in this some
**[5:05]** big data regime. Very large training sets,
**[5:08]** very large M regime in the right that we
**[5:12]** more consistently see large neural nets
**[5:14]** dominating the other approaches. And so
**[5:17]** if any of your friends ask you why are
**[5:19]** neural nets taking off I would
**[5:21]** encourage you to draw this picture for
**[5:23]** them as well. So I will say that in the
**[5:26]** early days in their modern rise of deep
**[5:28]** learning,
**[5:29]** it was scaled data and scale of
**[5:32]** computation just our ability to train
**[5:34]** very large neural networks
**[5:36]** either on a CPU or GPU that enabled us
**[5:39]** to make a lot of progress. But
**[5:41]** increasingly, especially in the last
**[5:43]** several years, we've seen tremendous
**[5:45]** algorithmic innovation as well so I also
**[5:48]** don't want to understate that.
**[5:50]** Interestingly, many of the algorithmic
**[5:53]** innovations have been about trying to
**[5:56]** make neural networks run much faster so
**[6:01]** as a concrete example one of the huge
**[6:03]** breakthroughs in neural networks has been
**[6:05]** switching from a sigmoid function, which
**[6:08]** looks like this, to a railer function,
**[6:12]** which we talked about briefly in an
**[6:14]** early video, that looks like this. If you
**[6:18]** don't understand the details of one
**[6:20]** about the state don't worry about it but
**[6:22]** it turns out that one of the problems of
**[6:24]** using sigmoid functions and machine
**[6:26]** learning is that there are these regions
**[6:27]** here where the slope of the function
**[6:29]** where the
**[6:30]** gradient is nearly zero and so learning
**[6:32]** becomes really slow, because when you
**[6:35]** implement gradient descent and gradient
**[6:37]** is zero the parameters just change very
**[6:39]** slowly. And so, learning is very slow
**[6:41]** whereas by changing the what's called
**[6:44]** the activation function the neural
**[6:46]** network to use this function called the
**[6:48]** value function of the rectified linear
**[6:52]** unit, or RELU, the gradient is equal to
**[6:54]** 1 for all positive values of input.
**[6:57]** right. And so, the gradient is much less
**[7:00]** likely to gradually shrink to 0 and
**[7:03]** the gradient here. the slope of this line
**[7:04]** is 0 on the left but it turns out
**[7:07]** that just by switching to the sigmoid
**[7:09]** function to the RELU function has
**[7:12]** made an algorithm called gradient
**[7:14]** descent work much faster and so this is
**[7:16]** an example of maybe relatively simple
**[7:19]** algorithmic innovation. But ultimately, the
**[7:22]** impact of this algorithmic innovation
**[7:23]** was it really helped computation. so there
**[7:27]** are actually quite a lot of examples like
**[7:29]** this of where we change the algorithm
**[7:31]** because it allows that code to run much
**[7:33]** faster and this allows us to train
**[7:35]** bigger neural networks, or to do so the
**[7:37]** reason will decline even when we have
**[7:39]** a large network roam all the data. The
**[7:42]** other reason that fast computation is
**[7:45]** important is that it turns out the
**[7:48]** process of training your network is
**[7:51]** very intuitive. Often, you have an idea
**[7:53]** for a neural network architecture and so
**[7:56]** you implement your idea and code.
**[7:58]** Implementing your idea then lets you run
**[8:01]** an experiment which tells you how well
**[8:02]** your neural network does and then by
**[8:05]** looking at it you go back to change the
**[8:07]** details of your new network and then you
**[8:10]** go around this circle over and over and
**[8:12]** when your new network takes a long time
**[8:15]** to train it just takes a long time to go
**[8:18]** around this cycle and there's a huge
**[8:21]** difference in your productivity. Building
**[8:24]** effective neural networks when you can
**[8:26]** have an idea and try it and see the work
**[8:29]** in ten minutes, or maybe at most a day,
**[8:34]** versus if you've to train your neural
**[8:36]** network for a month, which sometimes does
**[8:39]** happen,
**[8:40]** because you get a result back you know
**[8:42]** in ten minutes or maybe in a day you
**[8:44]** should just try a lot more ideas and be
**[8:47]** much more likely to discover in your
**[8:49]** network. And it works well for your
**[8:50]** application and so faster computation
**[8:53]** has really helped in terms of speeding
**[8:57]** up the rate at which you can get an
**[8:59]** experimental result back and this has
**[9:02]** really helped both practitioners of
**[9:05]** neural networks as well as researchers
**[9:07]** working and deep learning iterate much
**[9:10]** faster and improve your ideas much
**[9:13]** faster. So, all this has also been a
**[9:16]** huge boon to the entire deep learning
**[9:18]** research community which has been
**[9:21]** incredible with just inventing
**[9:23]** new algorithms and making nonstop
**[9:25]** progress on that front. So these are some
**[9:28]** of the forces powering the rise of deep
**[9:30]** learning but the good news is that these
**[9:33]** forces are still working powerfully to
**[9:36]** make deep learning even better. Take data...
**[9:38]** society is still throwing out more
**[9:41]** digital data. Or take computation, with
**[9:43]** the rise of specialized hardware like
**[9:45]** GPUs and faster networking many types of
**[9:48]** hardware, I'm actually quite confident
**[9:50]** that our ability to do very large neural
**[9:53]** networks from a computation point
**[9:55]** of view will keep on getting better and
**[9:57]** take algorithms relative to learning
**[10:00]** research communities are continuously
**[10:02]** phenomenal at elevating on the
**[10:05]** algorithms front. So because of this, I
**[10:07]** think that we can be optimistic answer
**[10:09]** is that deep learning will
**[10:11]** keep on getting better for many years to
**[10:13]** come.
**[10:14]** So with that, let's go on to the last video of
**[10:17]** the section where we'll talk a little
**[10:18]** bit more about what you learn from this
**[10:20]** course.
