---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 2
section: Logistic Regression as a Neural Network
item_title: Computation Graph
duration: 4 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/4WdOY/computation-graph
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Computation Graph — Transcript

**[0:00]** You've heard me say
**[0:00]** that the computations
**[0:02]** of a neural network are organized
**[0:03]** in terms of a forward pass
**[0:05]** or a forward propagation step,
**[0:07]** in which we compute the output
**[0:08]** of the neural network,
**[0:10]** followed by a backward pass
**[0:11]** or back propagation step,
**[0:13]** which we use to compute gradients
**[0:15]** or compute derivatives.
**[0:16]** The computation graph explains
**[0:19]** why it is organized this way.
**[0:21]** In this video, we'll go through
**[0:23]** an example.
**[0:24]** In order to illustrate
**[0:26]** the computation graph,
**[0:28]** let's use a simpler example
**[0:30]** than logistic regression
**[0:32]** or a full blown neural network.
**[0:34]** Let's say that we're trying to compute a function, J,
**[0:37]** which is a function
**[0:38]** of three variables a, b, and c
**[0:40]** and let's say that function is 3(a+bc).
**[0:44]** Computing this function actually
**[0:46]** has three distinct steps.
**[0:49]** The first is you need to compute
**[0:50]** what is bc
**[0:52]** and let's say we store that
**[0:53]** in the variable call u.
**[0:55]** So u=bc and then you my compute V=a *u.
**[0:59]** So let's say this is V.
**[1:04]** And then finally, your output J is 3V.
**[1:09]** So this is your final function J
**[1:13]** that you're trying to compute.
**[1:15]** We can take these three steps
**[1:17]** and draw them in a computation graph as follows.
**[1:20]** Let's say, I draw your three variables
**[1:24]** a, b, and c here.
**[1:26]** So the first thing we did
**[1:27]** was compute u=bc.
**[1:31]** So I'm going to put
**[1:32]** a rectangular box around that.
**[1:35]** And so the input to that are b and c.
**[1:37]** And then, you might have V=a+u.
**[1:41]** So the inputs to that
**[1:47]** are V. So the inputs to that are u
**[1:53]** with just computed together with a.
**[1:56]** And then finally, we have J=3V.
**[2:04]** So as a concrete example, if a=5,
**[2:07]** b=3 and c=2 then u=bc would be six
**[2:10]** because a+u would be 5+6 is 11,.
**[2:15]** J is three times that, so J=33.
**[2:15]** And indeed, hopefully you can verify
**[2:22]** that this is three times five
**[2:26]** plus three times two.
**[2:29]** And if you expand that out,
**[2:30]** you actually get 33 as the value of J.
**[2:34]** So, the computation graph comes in handy
**[2:37]** when there is some distinguished
**[2:39]** or some special output variable,
**[2:41]** such as J in this case,
**[2:43]** that you want to optimize.
**[2:46]** And in the case
**[2:46]** of a logistic regression,
**[2:48]** J is of course the cost function
**[2:51]** that we're trying to minimize.
**[2:53]** And what we're seeing
**[2:54]** in this little example is that,
**[2:56]** through a left-to-right pass,
**[2:58]** you can compute the value of J
**[3:01]** and what we'll see
**[3:02]** in the next couple of slides
**[3:03]** is that in order to compute derivatives
**[3:05]** there'll be a right-to-left
**[3:08]** pass like this,
**[3:10]** kind of going in the opposite direction
**[3:11]** as the blue arrows.
**[3:14]** That would be most natural
**[3:15]** for computing the derivatives.
**[3:17]** So to recap, the computation graph
**[3:19]** organizes a computation with this blue arrow,
**[3:21]** left-to-right computation.
**[3:24]** Let's refer to the next video
**[3:25]** how you can do the backward red arrow
**[3:28]** right-to-left computation
**[3:30]** of the derivatives.
**[3:31]** Let's go on to the next video.
