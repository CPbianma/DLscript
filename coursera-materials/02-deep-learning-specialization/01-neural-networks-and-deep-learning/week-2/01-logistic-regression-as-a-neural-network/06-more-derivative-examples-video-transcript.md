---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 2
section: Logistic Regression as a Neural Network
item_title: More Derivative Examples
duration: 10 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/oEcPT/more-derivative-examples
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# More Derivative Examples — Transcript

**[0:00]** In this video, I'll show you a slightly more complex example
**[0:03]** where the slope of the function can be different to different points in the function.
**[0:06]** Let's start with an example.
**[0:08]** You have plotted the function f(a) = a².
**[0:11]** Let's take a look at the point a=2.
**[0:15]** So a² or f(a) = 4.
**[0:19]** Let's nudge a slightly to the right, so now a=2.001.
**[0:24]** f(a) which is a² is going to be approximately 4.004.
**[0:31]** It turns out that the exact value,
**[0:33]** you call the calculator and figured this out is actually 4.004001.
**[0:39]** I'm just going to say 4.004 is close enough.
**[0:42]** So what this means is that when a=2,
**[0:44]** let's draw this on the plot.
**[0:46]** So what we're saying is that if a=2,
**[0:49]** then f(a) = 4 and here is the x and y axis are not drawn to scale.
**[0:56]** Technically, does vertical height should be much higher than
**[0:59]** this horizontal height so the x and y axis are not on the same scale.
**[1:03]** But if I now nudge a to 2.001 then f(a) becomes roughly 4.004.
**[1:10]** So if we draw this little triangle again,
**[1:13]** what this means is that if I nudge a to the right by 0.001,
**[1:18]** f(a) goes up four times as much by 0.004.
**[1:23]** So in the language of calculus,
**[1:25]** we say that a slope that is the derivative of f(a) at
**[1:30]** a=2 is 4 or to write this out of our calculus notation,
**[1:36]** we say that d/da of f(a) = 4 when a=2.
**[1:42]** Now one thing about this function f(a) = a²
**[1:45]** is that the slope is different for different values of a.
**[1:49]** This is different than the example we saw on the previous slide.
**[1:52]** So let's look at a different point.
**[1:55]** If a=5, so instead of a=2,
**[1:58]** and now a=5 then a²=25, so that's f(a).
**[2:04]** If I nudge a to the right again,
**[2:07]** it's tiny little nudge to a,
**[2:09]** so now a=5.001 then f(a) will be approximately 25.010.
**[2:18]** So what we see is that by nudging a up by .001,
**[2:23]** f(a) goes up ten times as much.
**[2:25]** So we have that d/da f(a) = 10 when
**[2:30]** a=5 because f(a) goes up ten times as
**[2:33]** much as a does when I make a tiny little nudge to a.
**[2:36]** So one way to see why did derivatives is different at different points is that if you
**[2:41]** draw that little triangle right at different locations on this,
**[2:45]** you'll see that the ratio of the height of the triangle over
**[2:49]** the width of the triangle is very different at different points on the curve.
**[2:53]** So here, the slope=4 when a=2, a=10, when a=5.
**[2:59]** Now if you pull up a calculus textbook,
**[3:02]** a calculus textbook will tell you that d/da of f(a),
**[3:06]** so f(a) = a²,
**[3:08]** so that's d/da of a².
**[3:09]** One of the formulas you find are the calculus textbook is that this thing,
**[3:13]** the slope of the function a², is equal to 2a.
**[3:16]** Not going to prove this, but the way you find this out is that
**[3:19]** you open up a calculus textbook to
**[3:22]** the table formulas and they'll tell you that derivative of 2 of a² is 2a.
**[3:28]** And indeed, this is consistent with what we've worked out.
**[3:31]** Namely, when a=2, the slope of function to a is 2x2=4.
**[3:39]** And when a=5 then the slope of the function 2xa is 2x5=10.
**[3:46]** So, if you ever pull up a calculus textbook and you see this formula,
**[3:50]** that the derivative of a²=2a,
**[3:54]** all that means is that for any given value of a,
**[3:57]** if you nudge upward by 0.001 already your tiny little value,
**[4:04]** you will expect f(a) to go up by 2a.
**[4:09]** That is the slope or the derivative times
**[4:12]** other much you had nudged to the right the value of a.
**[4:16]** Now one tiny little detail,
**[4:18]** I use these approximate symbols here and this wasn't exactly 4.004,
**[4:23]** there's an extra .001 hanging out there.
**[4:26]** It turns out that this extra .001,
**[4:29]** this little thing here is because we were nudging a to the right by 0.001,
**[4:34]** if we're instead nudging it to the right by
**[4:37]** this infinitesimally small value then this extra every term will go
**[4:43]** away and you find that the amount that f(a) goes out is exactly equal
**[4:48]** to the derivative times the amount that you nudge a to the right.
**[4:53]** And the reason why is not 4.004 exactly is because derivatives are defined using
**[4:59]** this infinitesimally small nudges to a rather than 0.001 which is not.
**[5:05]** And while 0.001 is small,
**[5:08]** it's not infinitesimally small.
**[5:09]** So that's why the amount that f(a) went up isn't exactly given
**[5:13]** by the formula but it's only a kind of approximately given by the derivative.
**[5:17]** To wrap up this video,
**[5:19]** let's just go through a few more quick examples.
**[5:21]** The example you've already seen is that if f(a) = a² then
**[5:27]** the calculus textbooks formula table will tell you that the derivative is equal to 2a.
**[5:34]** And so the example we went through was it if (a) = 2,
**[5:38]** f(a) = 4, and we nudge a,
**[5:41]** since it's a little bit bigger than f(a) is about
**[5:45]** 4.004 and so f(a) went up four times as much and indeed when a=2,
**[5:51]** the derivatives is equal to 4.
**[5:53]** Let's look at some other examples.
**[5:55]** Let's say, instead the f(a) = a³.
**[5:58]** If you go to a calculus textbook and look up the table of formulas,
**[6:03]** you see that the slope of this function, again,
**[6:06]** the derivative of this function is equal to 3a².
**[6:10]** So you can get this formula out of the calculus textbook.
**[6:14]** So what this means?
**[6:16]** So the way to interpret this is as follows.
**[6:19]** Let's take a=2 as an example again.
**[6:21]** So f(a) or a³=8, that's two to the power of three.
**[6:27]** So we give a a tiny little nudge,
**[6:30]** you find that f(a) is about 8.012 and feel free to check this.
**[6:37]** Take 2.001 to the power of three,
**[6:40]** you find this is very close to 8.012.
**[6:41]** And indeed, when a=2 that's 3x2² does equal to 3x4,
**[6:49]** you see that's 12.
**[6:50]** So the derivative formula predicts that if you nudge a to the right by tiny little bit,
**[6:55]** f(a) should go up 12 times as much.
**[6:58]** And indeed, this is true when a went up by .001,
**[7:01]** f(a) went up 12 times as much by .012.
**[7:06]** Just one last example and then we'll wrap up.
**[7:08]** Let's say that f(a) is equal to the log function.
**[7:12]** So on the right log of a,
**[7:14]** I'm going to use this as the base e logarithm.
**[7:17]** So some people write that as log(a).
**[7:20]** So if you go to calculus textbook,
**[7:22]** you find that when you take the derivative of log(a).
**[7:26]** So this is a function that just looks like that,
**[7:30]** the slope of this function is given by 1/a.
**[7:34]** So the way to interpret this is that if a has any value then let's just keep
**[7:40]** using a=2 as an example and you nudge a to the right by .001,
**[7:46]** you would expect f(a) to go up by
**[7:51]** 1/a that is by the derivative times the amount that you increase a.
**[7:56]** So in fact, if you pull up a calculator,
**[8:00]** you find that if a=2,
**[8:02]** f(a) is about 0.69315 and if you
**[8:10]** increase f and if you increase a to 2.001 then f(a) is about 0.69365,
**[8:21]** this has gone up by 0.0005.
**[8:27]** And indeed, if you look at the formula for the derivative when a=2,
**[8:32]** d/da f(a) = 1/2.
**[8:36]** So this derivative formula predicts that if you pump up a by .001,
**[8:41]** you would expect f(a) to go up by only 1/2 as much and 1/2 of .001
**[8:46]** is 0.0005 which is exactly what we got.
**[8:51]** Then when a goes up by .001, going from a=2 to
**[8:56]** a=2.001, f(a) goes up by half as much.
**[9:01]** So, the answers are going up by approximately .0005.
**[9:04]** So if we draw that little triangle if you will is that if on
**[9:08]** the horizontal axis just goes up by .001 on the vertical axis,
**[9:13]** log(a) goes up by half of that so .0005.
**[9:18]** And so that 1/a or 1/2 in this case,
**[9:22]** 1a=2 that's just the slope of this line when a=2.
**[9:27]** So that's it for derivatives.
**[9:30]** There are just two take home messages from this video.
**[9:32]** First is that the derivative of the function just means the slope of
**[9:36]** a function and the slope of a function
**[9:39]** can be different at different points on the function.
**[9:41]** In our first example where f(a) = 3a those a straight line.
**[9:45]** The derivative was the same everywhere,
**[9:47]** it was three everywhere.
**[9:48]** For other functions like f(a) = a² or f(a) = log(a),
**[9:52]** the slope of the line varies.
**[9:54]** So, the slope or the derivative can be different at different points on the curve.
**[9:59]** So that's a first take away.
**[10:00]** Derivative just means slope of a line.
**[10:03]** Second takeaway is that if you want to look up the derivative of a function,
**[10:06]** you can flip open your calculus textbook or look up Wikipedia and
**[10:10]** often get a formula for the slope of these functions at different points.
**[10:15]** So that, I hope you have an intuitive understanding of derivatives or slopes of lines.
**[10:20]** Let's go into the next video.
**[10:21]** We'll start to talk about the computation graph and how to
**[10:24]** use that to compute derivatives of more complex functions.
