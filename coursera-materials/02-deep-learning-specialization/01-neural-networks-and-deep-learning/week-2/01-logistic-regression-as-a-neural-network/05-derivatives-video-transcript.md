---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 2
section: Logistic Regression as a Neural Network
item_title: Derivatives
duration: 7 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/0ULGt/derivatives
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Derivatives — Transcript

**[0:00]** In this video, I want to help you gain an intuitive understanding,
**[0:04]** of calculus and the derivatives.
**[0:07]** Now, maybe you're thinking that you haven't seen calculus since your college days,
**[0:11]** and depending on when you graduated,
**[0:13]** maybe that was quite some time back.
**[0:15]** Now, if that's what you're thinking, don't worry,
**[0:18]** you don't need a deep understanding of calculus in order
**[0:22]** to apply neural networks and deep learning very effectively.
**[0:26]** So, if you're watching this video or some of the later videos and you're wondering,
**[0:29]** well, is this stuff really for me,
**[0:31]** this calculus looks really complicated.
**[0:33]** My advice to you is the following, which is that,
**[0:35]** watch the videos and then if you could do
**[0:38]** the homeworks and complete the programming homeworks successfully,
**[0:41]** then you can apply deep learning.
**[0:43]** In fact, when you see later is that in week four,
**[0:46]** we'll define a couple of types of functions that will enable you to
**[0:49]** encapsulate everything that needs to be done with respect to calculus,
**[0:53]** that these functions called forward functions and backward functions that you learn about.
**[0:56]** That lets you put everything you need to know about calculus into these functions,
**[1:01]** so that you don't need to worry about them anymore beyond that.
**[1:04]** But I thought that in this foray into deep learning that this week,
**[1:08]** we should open up the box and peer a little bit further into the details of calculus.
**[1:12]** But really, all you need is an intuitive understanding of this
**[1:16]** in order to build and successfully apply these algorithms.
**[1:19]** Finally, if you are among that maybe smaller group of people that are expert in calculus,
**[1:25]** if you are very familiar with calculus derivatives,
**[1:27]** it's probably okay for you to skip this video.
**[1:30]** But for everyone else, let's dive in,
**[1:32]** and try to gain an intuitive understanding of derivatives.
**[1:35]** I plotted here the function f(a) equals 3a.
**[1:39]** So, it's just a straight line.
**[1:41]** To get intuition about derivatives,
**[1:43]** let's look at a few points on this function.
**[1:45]** Let say that a is equal to two.
**[1:48]** In that case, f of a,
**[1:49]** which is equal to three times a is equal to six.
**[1:52]** So, if a is equal to two,
**[1:55]** then f of a will be equal to six.
**[1:58]** Let's say we give the value of a just a little bit of a nudge.
**[2:01]** I'm going to just bump up a,
**[2:03]** a little bit, so that it is now 2.001.
**[2:06]** So, I'm going to give a like a tiny little nudge, to the right.
**[2:10]** So now, let's say 2.001,
**[2:13]** just plot this into scale,
**[2:15]** 2.001, this 0.001 difference is too small to show on this plot,
**[2:20]** just give a little nudge to that right.
**[2:22]** Now, f(a),
**[2:23]** is equal to three times that.
**[2:25]** So, it's 6.003, so we plot this over here.
**[2:29]** This is not to scale, this is 6.003.
**[2:33]** So, if you look at this little triangle here that I'm highlighting in green,
**[2:37]** what we see is that if I nudge a 0.001 to the right,
**[2:42]** then f of a goes up by 0.003.
**[2:47]** The amounts that f of a,
**[2:48]** went up is three times as big as the amount that I nudge the a to the right.
**[2:54]** So, we're going to say that,
**[2:56]** the slope or the derivative of the function f of a,
**[3:01]** at a equals to or when a is equals two to the slope is three.
**[3:06]** The term derivative basically means slope,
**[3:09]** it's just that derivative sounds like a scary and more
**[3:12]** intimidating word, whereas a slope is a friendlier way to describe the concept of derivative.
**[3:16]** So, whenever you hear derivative,
**[3:18]** just think slope of the function.
**[3:20]** More formally, the slope is defined as the height
**[3:24]** divided by the width of this little triangle that we have in green.
**[3:29]** So, this is 0.003 over 0.001,
**[3:34]** and the fact that the slope is equal to three or the derivative is equal to three,
**[3:37]** just represents the fact that when you nudge a to the right by 0.001, by tiny amount,
**[3:43]** the amount at f of a goes up is three times as big as the amount that you nudged it,
**[3:49]** that you nudged a in the horizontal direction.
**[3:52]** So, that's all that the slope of a line is.
**[3:54]** Now, let's look at this function at a different point.
**[3:57]** Let's say that a is now equal to five.
**[3:59]** In that case, f of a,
**[4:01]** three times a is equal to 15.
**[4:03]** So, let's see that again,
**[4:04]** give a, a nudge to the right.
**[4:06]** A tiny little nudge, it's now bumped up to 5.001,
**[4:09]** f of a is three times that.
**[4:11]** So, f of a is equal to 15.003.
**[4:14]** So, once again, when I bump a to the right,
**[4:18]** nudg a to the right by 0.001,
**[4:21]** f of a goes up three times as much.
**[4:23]** So the slope, again, at a = 5, is also three.
**[4:28]** So, the way we write this,
**[4:29]** that the slope of the function f is equal to three:
**[4:33]** We say, d f(a)
**[4:36]** da and this just means,
**[4:38]** the slope of the function f(a)
**[4:41]** when you nudge the variable a,
**[4:43]** a tiny little amount, this is equal to three.
**[4:47]** An alternative way to write this derivative formula is as follows.
**[4:52]** You can also write this as,
**[4:54]** d da of f(a).
**[4:57]** So, whether you put f(a) on top or whether you write it down here, it doesn't matter.
**[5:03]** But all this equation means is that,
**[5:05]** if I nudge a to the right a little bit,
**[5:08]** I expect f(a) to go up by three times as much as I nudged the value of little a.
**[5:14]** Now, for this video I explained derivatives,
**[5:18]** talking about what happens if we nudged the variable a by 0.001.
**[5:25]** If you want a formal mathematical definition of the derivatives:
**[5:29]** Derivatives are defined with an even smaller value of how much you nudge a to the right.
**[5:34]** So, it's not 0.001.
**[5:35]** It's not 0.000001.
**[5:38]** It's not 0.00000000 and so on 1.
**[5:42]** It's even smaller than that,
**[5:44]** and the formal definition of derivative says,
**[5:47]** whenever you nudge a to the right by an infinitesimal amount,
**[5:50]** basically an infinitely tiny, tiny amount.
**[5:53]** If you do that, this f(a) go up three times as much as whatever was the tiny,
**[5:58]** tiny, tiny amount that you nudged a to the right.
**[6:01]** So, that's actually the formal definition of a derivative.
**[6:04]** But for the purposes of our intuitive understanding,
**[6:07]** which I'll talk about nudging a to the right by this small amount 0.001.
**[6:12]** Even if it's 0.001 isn't exactly tiny, tiny infinitesimal.
**[6:18]** Now, one property of the derivative is that,
**[6:21]** no matter where you take the slope of this function,
**[6:24]** it is equal to three,
**[6:25]** whether a is equal to two or a is equal to five.
**[6:28]** The slope of this function is equal to three,
**[6:31]** meaning that whatever is the value of a,
**[6:34]** if you increase it by 0.001,
**[6:36]** the value of f of a goes up by three times as much.
**[6:40]** So, this function has a safe slope everywhere.
**[6:42]** One way to see that is that,
**[6:44]** wherever you draw this little triangle.
**[6:47]** The height, divided by the width,
**[6:49]** always has a ratio of three to one.
**[6:52]** So, I hope this gives you a sense of what the slope or
**[6:55]** the derivative of a function means for a straight line,
**[6:58]** where in this example the slope of the function was three everywhere.
**[7:02]** In the next video, let's take a look at a slightly more complex example,
**[7:06]** where the slope to the function can be different at different points on the function.
