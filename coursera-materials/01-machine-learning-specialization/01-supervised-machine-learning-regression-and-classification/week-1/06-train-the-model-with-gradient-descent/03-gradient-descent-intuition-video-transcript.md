---
type: video-transcript
specialization: Machine Learning Specialization
course: "Supervised Machine Learning: Regression and Classification"
week: 1
section: Train the model with gradient descent
item_title: Gradient descent intuition
duration: 7 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/2EoN6/gradient-descent-intuition
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Gradient descent intuition — Transcript

**[0:01]** Now let's dive more deeply in gradient descent to gain
**[0:05]** better intuition about what
**[0:07]** it's doing and why it might make sense.
**[0:10]** Here's the gradient descent algorithm
**[0:12]** that you saw in the previous video.
**[0:14]** As a reminder, this variable,
**[0:17]** this Greek symbol Alpha, is the learning rate.
**[0:20]** The learning rate controls how big of a step you take
**[0:24]** when updating the model's parameters, w and b.
**[0:28]** This term here, this d over dw,
**[0:32]** this is a derivative term.
**[0:34]** By convention in math,
**[0:36]** this d is written with this funny font here.
**[0:40]** In case anyone watching this has PhD in
**[0:42]** math or is an expert in multivariate calculus,
**[0:45]** they may be wondering, that's not the derivative,
**[0:47]** that's the partial derivative. Yes, they be right.
**[0:50]** But for the purposes of
**[0:52]** implementing a machine learning algorithm,
**[0:53]** I'm just going to call it derivative.
**[0:56]** Don't worry about these little distinctions.
**[0:59]** What we're going to focus on now
**[1:01]** is get more intuition about
**[1:04]** what this learning rate and what this derivative
**[1:07]** are doing and why when multiplied together like this,
**[1:11]** it results in updates to parameters w and b.
**[1:15]** That makes sense. In order to do this let's use
**[1:19]** a slightly simpler example where we
**[1:22]** work on minimizing just one parameter.
**[1:25]** Let's say that you have a cost function J of
**[1:29]** just one parameter w with w is a number.
**[1:33]** This means the gradient descent now looks like this.
**[1:37]** W is updated to w minus the learning rate Alpha
**[1:41]** times d over dw of J of w. You're
**[1:47]** trying to minimize the cost by adjusting the
**[1:49]** parameter w. This is like
**[1:53]** our previous example where we had temporarily set b
**[1:57]** equal to 0 with one parameter w instead of two,
**[2:01]** you can look at two-dimensional graphs
**[2:04]** of the cost function j,
**[2:05]** instead of three dimensional graphs.
**[2:07]** Let's look at what
**[2:09]** gradient descent does on just function J of
**[2:12]** w. Here on the horizontal axis is parameter w,
**[2:18]** and on the vertical axis is the cost j of w. Now less
**[2:24]** initialized gradient descent with some starting value for
**[2:27]** w. Let's initialize it at this location.
**[2:30]** Imagine that you start off at
**[2:33]** this point right here on the function J,
**[2:36]** what gradient descent will do is it will update
**[2:39]** w to be w minus learning rate
**[2:43]** Alpha times d over dw of J of
**[2:46]** w. Let's look at what this derivative term here means.
**[2:51]** A way to think about the derivative at this point on
**[2:55]** the line is to draw a tangent line,
**[2:59]** which is a straight line that
**[3:00]** touches this curve at that point.
**[3:03]** Enough, the slope of this line is
**[3:06]** the derivative of the function j at this point.
**[3:10]** To get the slope, you can
**[3:12]** draw a little triangle like this.
**[3:14]** If you compute the height divided by
**[3:17]** the width of this triangle, that is the slope.
**[3:21]** For example, this slope might be 2 over 1,
**[3:26]** for instance and when
**[3:27]** the tangent line is pointing up and to the right,
**[3:30]** the slope is positive,
**[3:32]** which means that this derivative is a positive number,
**[3:36]** so is greater than 0.
**[3:39]** The updated w is going to be
**[3:42]** w minus the learning rate times some positive number.
**[3:46]** The learning rate is always a positive number.
**[3:50]** If you take w minus a positive number,
**[3:53]** you end up with a new value for w, that's smaller.
**[3:58]** On the graph, you're moving to the left,
**[4:02]** you're decreasing the value of w. You may notice
**[4:06]** that this is the right thing to do if your goal
**[4:08]** is to decrease the cost J,
**[4:11]** because when we move towards the left on this curve,
**[4:13]** the cost j decreases,
**[4:15]** and you're getting closer to the minimum
**[4:17]** for J, which is over here.
**[4:20]** So far, gradient descent,
**[4:22]** seems to be doing the right thing.
**[4:25]** Now, let's look at another example.
**[4:28]** Let's take the same function j of w as above,
**[4:31]** and now let's say that you initialized
**[4:33]** gradient descent at a different location.
**[4:36]** Say by choosing a starting value for
**[4:38]** w that's over here on the left.
**[4:41]** That's this point of the function j.
**[4:44]** Now, the derivative term,
**[4:47]** remember is d over dw of J of w,
**[4:53]** and when we look at the tangent line
**[4:55]** at this point over here,
**[4:57]** the slope of this line is
**[4:58]** a derivative of J at this point.
**[5:00]** But this tangent line is sloping down into the right.
**[5:04]** This lines sloping down into
**[5:07]** the right has a negative slope.
**[5:09]** In other words, the derivative of J at
**[5:11]** this point is a negative number.
**[5:13]** For instance, if you draw a triangle,
**[5:16]** then the height like this is
**[5:18]** negative 2 and the width is 1,
**[5:21]** the slope is negative 2 divided by 1,
**[5:25]** which is negative 2,
**[5:26]** which is a negative number.
**[5:28]** When you update w,
**[5:30]** you get w minus the learning rate times
**[5:33]** a negative number.
**[5:35]** This means you subtract from w, a negative number.
**[5:40]** But subtracting a negative number
**[5:44]** means adding a positive number,
**[5:46]** and so you end up increasing
**[5:49]** w. Because subtracting a negative number is the
**[5:53]** same as adding a positive number to
**[5:55]** w. This step of gradient descent causes w to increase,
**[6:02]** which means you're moving to the right of the graph and
**[6:05]** your cost J has decrease down to here.
**[6:09]** Again, it looks like
**[6:11]** gradient descent is doing something reasonable,
**[6:13]** is getting you closer to the minimum.
**[6:16]** Hopefully, these last two examples show
**[6:20]** some of the intuition behind what a derivative term
**[6:24]** is doing and why this host gradient descent change
**[6:27]** w to get you closer to the minimum.
**[6:31]** I hope this video gave you some sense for why
**[6:34]** the derivative term in gradient descent makes sense.
**[6:37]** One other key quantity in
**[6:39]** the gradient descent algorithm
**[6:41]** is the learning rate Alpha.
**[6:43]** How do you choose Alpha?
**[6:44]** What happens if it's too
**[6:45]** small or what happens when it's too big?
**[6:47]** In the next video,
**[6:48]** let's take a deeper look at
**[6:50]** the parameter Alpha to help
**[6:52]** build intuitions about what it does,
**[6:54]** as well as how to make a good choice for a good value
**[6:57]** of Alpha for your implementation of gradient descent.
