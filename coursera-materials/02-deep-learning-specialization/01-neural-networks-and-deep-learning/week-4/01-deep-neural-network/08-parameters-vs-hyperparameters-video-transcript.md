---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 4
section: Deep Neural Network
item_title: Parameters vs Hyperparameters
duration: 7 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/TBvb5/parameters-vs-hyperparameters
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Parameters vs Hyperparameters — Transcript

**[0:00]** Being effective in developing your deep
**[0:02]** Neural Nets requires that you not only
**[0:04]** organize your parameters well but also
**[0:06]** your hyper parameters. So what are hyper
**[0:09]** parameters? let's take a look! So the
**[0:11]** parameters your model are W and B and
**[0:15]** there are other things you need to tell
**[0:17]** your learning algorithm, such as the
**[0:21]** learning rate alpha, because we need
**[0:26]** to set alpha and that in turn will
**[0:28]** determine how your parameters evolve or
**[0:32]** maybe the number of iterations of
**[0:34]** gradient descent you carry out. Your
**[0:38]** learning algorithm has oth
**[0:40]** numbers that you need to set such as the
**[0:42]** number of hidden layers, so we call that
**[0:47]** capital L, or the number of hidden units,
**[0:50]** such as 0 and 1 and 2 and
**[0:56]** so on. Then you also have the choice
**[0:59]** of activation function. do you want to
**[1:03]** use a RELU, or tangent or a sigmoid
**[1:05]** function especially in the
**[1:06]** hidden layers. So all of these things
**[1:11]** are things that you need to tell your
**[1:13]** learning algorithm and so these are
**[1:15]** parameters that control the ultimate
**[1:19]** parameters W and B and so we call all of
**[1:22]** these things below hyper parameters.
**[1:25]** Because these things like alpha, the
**[1:29]** learning rate, the number of iterations,
**[1:30]** number of hidden layers, and so on, these
**[1:32]** are all parameters that control W and B.
**[1:36]** So we call these things hyper parameters,
**[1:39]** because it is the hyper parameters that
**[1:41]** somehow determine the final
**[1:44]** value of the parameters W and B that you
**[1:46]** end up with. In fact, deep learning has a
**[1:50]** lot of different hyper parameters.
**[1:53]** In the later course, we'll see other
**[1:55]** hyper parameters as well such as the
**[1:57]** momentum term, the mini batch size,
**[2:05]** various forms of regularization
**[2:07]** parameters, and so on. If none of
**[2:13]** these terms at the bottom make sense yet,
**[2:14]** don't worry about it! We'll talk about
**[2:16]** them in the second course. Because deep
**[2:18]** learning has so many hyper parameters in
**[2:21]** contrast to earlier errors of machine
**[2:24]** learning, I'm going to try to be very
**[2:26]** consistent in calling the learning rate
**[2:28]** alpha a hyper parameter rather than
**[2:31]** calling the parameter. I think in earlier
**[2:33]** eras of machine learning when we didn't
**[2:35]** have so many hyper parameters, most of us
**[2:37]** used to be a bit slow up here and just
**[2:39]** call alpha a parameter. Technically,
**[2:42]** alpha is a parameter, but is a parameter
**[2:44]** that determines the real parameters. I'll
**[2:47]** try to be consistent in calling these
**[2:50]** things like alpha, the number of
**[2:51]** iterations, and so on hyper parameters. So
**[2:54]** when you're training a deep net for your
**[2:55]** own application you find that there may
**[2:57]** be a lot of possible settings for the
**[2:59]** hyper parameters that you need to just
**[3:01]** try out. So applying deep learning today is
**[3:04]** a very intrictate process where often you
**[3:07]** might have an idea. For example, you might
**[3:09]** have an idea for the best value for the
**[3:12]** learning rate. You might say, well maybe
**[3:13]** alpha equals 0.01 I want to try that.
**[3:16]** Then you implement, try it out, and then
**[3:20]** see how that works. Based on
**[3:22]** that outcome you might say, you know what?
**[3:23]** I've changed online, I want to increase
**[3:25]** the learning rate to 0.05. So, if
**[3:28]** you're not sure what the best value
**[3:30]** for the learning rate to use. You might
**[3:32]** try one value of the learning rate alpha
**[3:35]** and see their cost function j go down
**[3:37]** like this, then you might try a larger
**[3:39]** value for the learning rate alpha and
**[3:41]** see the cost function blow up and
**[3:43]** diverge. Then, you might try another
**[3:45]** version and see it go down really fast.
**[3:47]** it's inverse to higher value. You might
**[3:49]** try another version and
**[3:51]** see the cost function J do that then.
**[3:53]** I'll be trying to set the values. So you might
**[3:55]** say, okay looks like this the value of
**[3:57]** alpha. It gives me a pretty fast learning
**[4:00]** and allows me to converge to a lower
**[4:02]** cost function j and so I'm going to use
**[4:04]** this value of alpha. You saw in a
**[4:06]** previous slide that there are a lot of
**[4:08]** different hybrid parameters. It turns
**[4:10]** out that when you're starting on the new
**[4:11]** application, you should find it very
**[4:13]** difficult to know in advance exactly
**[4:15]** what is the best value of the hyper
**[4:17]** parameters. So, what often happens is you
**[4:20]** just have to try out many different
**[4:22]** values and go around this cycle your
**[4:24]** try out some values, really try five hidden
**[4:26]** layers. With this many number of hidden
**[4:28]** units implement that, see if it works, and
**[4:31]** then iterate. So the title of this slide
**[4:34]** is that applying deep learning is a very
**[4:36]** empirical process, and empirical process
**[4:38]** is maybe a fancy way of saying you just
**[4:40]** have to try a lot of things and see what
**[4:42]** works. Another effect I've seen is that
**[4:45]** deep learning today is applied to so
**[4:47]** many problems ranging from computer
**[4:48]** vision, to speech recognition, to natural
**[4:51]** language processing, to a lot of
**[4:53]** structured data applications such as
**[4:55]** maybe a online advertising, or web search,
**[4:59]** or product recommendations, and so on.
**[5:02]** What I've seen is that first, I've seen
**[5:05]** researchers from one discipline, any one
**[5:08]** of these, and try to go to a different one.
**[5:10]** And sometimes the intuitions about hyper
**[5:12]** parameters carries over and sometimes it
**[5:14]** doesn't, so I often advise people,
**[5:16]** especially when starting on a new
**[5:17]** problem, to just try out a range of
**[5:20]** values and see what w. In the next
**[5:23]** course we'll
**[5:25]** see some systematic ways for trying out
**[5:27]** a range of values. Second,
**[5:30]** even if you're working on one
**[5:32]** application for a long time, you know
**[5:33]** maybe you're working on online
**[5:35]** advertising, as you make progress on the
**[5:37]** problem it is quite possible that the best
**[5:39]** value for the learning rate, a number of
**[5:41]** hidden units, and so on might change. So
**[5:43]** even if you tune your system to the best
**[5:46]** value of hyper parameters today it's
**[5:49]** possible you'll find that the best value
**[5:51]** might change a year from now maybe
**[5:53]** because the computer infrastructure,
**[5:55]** be it you know CPUs, or the type of GPU
**[5:57]** running on, or something has changed.
**[5:59]** So maybe one rule of thumb is
**[6:01]** every now and then, maybe every few
**[6:03]** months, if you're working on a problem
**[6:05]** for an extended period of time for many
**[6:06]** years just try a few values for the
**[6:09]** hyper parameters and double check if
**[6:10]** there's a better value for the hyper
**[6:12]** parameters. As you do so you slowly
**[6:15]** gain intuition as well about the hyper
**[6:17]** parameters that work best for your
**[6:18]** problems.
**[6:19]** I know that this might seem like an
**[6:21]** unsatisfying part of deep learning that
**[6:24]** you just have to try on all the values
**[6:25]** for these hyper parameters, but maybe
**[6:27]** this is one area where deep learning
**[6:30]** research is still advancing, and maybe
**[6:32]** over time we'll be able to give better
**[6:33]** guidance for the best hyper parameters
**[6:36]** to use. It's also possible that
**[6:38]** because CPUs and GPUs and networks and
**[6:41]** data sets are all changing, and it is
**[6:43]** possible that the guidance won't
**[6:45]** converge for some time. You just need
**[6:47]** to keep trying out different values and
**[6:49]** evaluate them on a hold on
**[6:50]** cross-validation set or something and
**[6:52]** pick the value that works for your
**[6:54]** problems. So that was a brief discussion
**[6:56]** of hyper parameters. In the second course,
**[6:58]** we'll also give some suggestions for how
**[7:01]** to systematically explore the space of
**[7:03]** hyper parameters but by now you actually
**[7:06]** have pretty much all the tools you need
**[7:07]** to do their programming exercise before
**[7:09]** you do that adjust or share view one
**[7:11]** more set of ideas which is I often ask
**[7:14]** what does deep learning have to do the
**[7:16]** human brain?
