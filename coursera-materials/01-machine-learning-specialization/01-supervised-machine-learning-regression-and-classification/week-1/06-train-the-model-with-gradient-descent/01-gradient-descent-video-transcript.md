---
type: video-transcript
specialization: Machine Learning Specialization
course: Supervised Machine Learning: Regression and Classification
week: 1
section: Train the model with gradient descent
item_title: Gradient descent
duration: 8 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/2f2PA/gradient-descent
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Gradient descent — Transcript

**[0:00]** Welcome back. In the last video,
**[0:03]** we saw visualizations of
**[0:05]** the cost function j and how you can try
**[0:08]** different choices of the parameters w and
**[0:10]** b and see what cost value they get you.
**[0:13]** It would be nice if we had
**[0:15]** a more systematic way to find the values of w and b,
**[0:19]** that results in the smallest possible cost,
**[0:21]** j of w, b.
**[0:23]** It turns out there's an algorithm called
**[0:26]** gradient descent that you can use to do that.
**[0:29]** Gradient descent is used
**[0:31]** all over the place in machine learning,
**[0:32]** not just for linear regression,
**[0:34]** but for training for example some of
**[0:37]** the most advanced neural network models,
**[0:40]** also called deep learning models.
**[0:42]** Deep learning models are something you
**[0:45]** learned about in the second course.
**[0:47]** Learning these two of gradient descent will set you
**[0:51]** up with one of the most
**[0:52]** important building blocks in machine learning.
**[0:55]** Here's an overview of what
**[0:56]** we'll do with gradient descent.
**[0:58]** You have the cost function j of w,
**[1:01]** b right here that you want to minimize.
**[1:05]** In the example we've seen so far,
**[1:07]** this is a cost function for linear regression,
**[1:11]** but it turns out that gradient descent
**[1:13]** is an algorithm that you
**[1:14]** can use to try to minimize any function,
**[1:17]** not just a cost function for linear regression.
**[1:21]** Just to make this discussion on
**[1:24]** gradient descent more general,
**[1:26]** it turns out that gradient descent
**[1:28]** applies to more general functions,
**[1:30]** including other cost functions that work
**[1:33]** with models that have more than two parameters.
**[1:37]** For instance, if you have a cost function
**[1:40]** J as a function of w_1,
**[1:43]** w_2 up to w_n and b,
**[1:47]** your objective is to minimize j
**[1:50]** over the parameters w_1 to w_n and b.
**[1:55]** In other words, you want to pick values
**[1:58]** for w_1 through w_n and b,
**[2:02]** that gives you the smallest possible value of j.
**[2:05]** It turns out that gradient descent
**[2:08]** is an algorithm that you can apply
**[2:09]** to try to minimize this cost function j as well.
**[2:14]** What you're going to do is just to start off
**[2:17]** with some initial guesses for w and b.
**[2:21]** In linear regression, it won't matter too
**[2:24]** much what the initial value are,
**[2:26]** so a common choice is to set them both to 0.
**[2:30]** For example, you can set w to 0
**[2:33]** and b to 0 as the initial guess.
**[2:35]** With the gradient descent algorithm,
**[2:37]** what you're going to do is,
**[2:39]** you'll keep on changing the parameters w and b a bit
**[2:43]** every time to try to reduce the cost j of w,
**[2:47]** b until hopefully j settles at or near a minimum.
**[2:52]** One thing I should note is that for some functions
**[2:56]** j that may not be a bow shape or a hammock shape,
**[2:59]** it is possible for there to be
**[3:01]** more than one possible minimum.
**[3:05]** Let's take a look at an example of
**[3:08]** a more complex surface plot j
**[3:10]** to see what gradient is doing.
**[3:13]** This function is not a squared error cost function.
**[3:17]** For linear regression with
**[3:18]** the squared error cost function,
**[3:20]** you always end up with a bow shape or a hammock shape.
**[3:24]** But this is a type of cost function you
**[3:27]** might get if you're training a neural network model.
**[3:30]** Notice the axes, that is w and b on the bottom axis.
**[3:38]** For different values of w and b,
**[3:41]** you get different points on this surface,
**[3:43]** j of w, b,
**[3:46]** where the height of the surface at
**[3:47]** some point is the value of the cost function.
**[3:51]** Now, let's imagine that
**[3:53]** this surface plot is actually a view of
**[3:56]** a slightly hilly outdoor park or
**[3:59]** a golf course where the high points are
**[4:01]** hills and the low points are valleys like so.
**[4:04]** I'd like you to imagine if you will,
**[4:07]** that you are physically standing
**[4:09]** at this point on the hill.
**[4:12]** If it helps you to relax,
**[4:14]** imagine that there's lots of
**[4:16]** really nice green grass and
**[4:17]** butterflies and flowers is a really nice hill.
**[4:21]** Your goal is to start up here and get
**[4:25]** to the bottom of one of
**[4:27]** these valleys as efficiently as possible.
**[4:31]** What the gradient descent algorithm does is,
**[4:34]** you're going to spin around 360 degrees
**[4:38]** and look around and ask yourself,
**[4:40]** if I were to take
**[4:42]** a tiny little baby step in one direction,
**[4:44]** and I want to go downhill as quickly
**[4:47]** as possible to or one of these valleys.
**[4:49]** What direction do I choose to take that baby step?
**[4:53]** Well, if you want to walk down
**[4:55]** this hill as efficiently as possible,
**[4:58]** it turns out that if you're standing
**[5:00]** at this point in the hill and you look around,
**[5:02]** you will notice that the best direction to take
**[5:05]** your next step downhill is roughly that direction.
**[5:08]** Mathematically, this is
**[5:10]** the direction of steepest descent.
**[5:13]** It means that when you take a tiny baby little step,
**[5:16]** this takes you downhill faster than
**[5:18]** a tiny little baby step you could
**[5:20]** have taken in any other direction.
**[5:22]** After taking this first step,
**[5:25]** you're now at this point on the hill over here.
**[5:29]** Now let's repeat the process.
**[5:31]** Standing at this new point,
**[5:33]** you're going to again spin
**[5:35]** around 360 degrees and ask yourself,
**[5:38]** in what direction will I take
**[5:40]** the next little baby step in order to move downhill?
**[5:44]** If you do that and take another step,
**[5:46]** you end up moving a bit in
**[5:48]** that direction and you can keep going.
**[5:52]** From this new point,
**[5:54]** you can again look around and decide
**[5:56]** what direction would take you downhill most quickly.
**[5:59]** Take another step, another step, and so on,
**[6:02]** until you find yourself at the bottom of this valley,
**[6:06]** at this local minimum, right here.
**[6:09]** What you just did was go through
**[6:10]** multiple steps of gradient descent.
**[6:13]** It turns out, gradient descent
**[6:15]** has an interesting property.
**[6:18]** Remember that you can choose a starting point at
**[6:22]** the surface by choosing
**[6:23]** starting values for the parameters w and b.
**[6:26]** When you perform gradient descent a moment ago,
**[6:29]** you had started at this point over here.
**[6:33]** Now, imagine if you try gradient descent again,
**[6:37]** but this time you choose
**[6:39]** a different starting point by choosing
**[6:41]** parameters that place your starting point
**[6:43]** just a couple of steps to the right over here.
**[6:47]** If you then repeat the gradient descent process,
**[6:50]** which means you look around,
**[6:52]** take a little step in the direction of
**[6:53]** steepest ascent so you end up here.
**[6:57]** Then you again look around,
**[6:58]** take another step, and so on.
**[7:01]** If you were to run gradient descent this second time,
**[7:05]** starting just a couple steps in
**[7:07]** the right of where we did it the first time,
**[7:09]** then you end up in a totally different valley.
**[7:13]** This different minimum over here on the right.
**[7:17]** The bottoms of both the first and
**[7:20]** the second valleys are called local minima.
**[7:23]** Because if you start going down the first valley,
**[7:27]** gradient descent won't lead you to the second valley,
**[7:30]** and the same is true if you
**[7:32]** started going down the second valley,
**[7:34]** you stay in that second minimum and
**[7:37]** not find your way into the first local minimum.
**[7:40]** This is an interesting property
**[7:43]** of the gradient descent algorithm,
**[7:45]** and you see more about this later.
**[7:47]** In this video, you saw how
**[7:50]** gradient descent helps you go downhill.
**[7:53]** In the next video,
**[7:54]** let's look at the mathematical expressions that you
**[7:57]** can implement to make gradient descent work.
**[8:00]** Let's go on to the next video.
