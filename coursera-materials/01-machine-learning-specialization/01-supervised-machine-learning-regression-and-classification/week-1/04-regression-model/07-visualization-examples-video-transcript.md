---
type: video-transcript
specialization: Machine Learning Specialization
course: "Supervised Machine Learning: Regression and Classification"
week: 1
section: Regression Model
item_title: Visualization examples
duration: 6 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/Ov8Zt/visualization-examples
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Visualization examples — Transcript

**[0:03]** Let's look at some more visualizations of
**[0:05]** w and b. Here's one example.
**[0:08]** Over here, you have a particular point on the graph j.
**[0:14]** For this point, w equals about negative
**[0:17]** 0.15 and b equals about 800.
**[0:22]** This point corresponds to one pair of values for
**[0:26]** w and b that use a particular cost j.
**[0:30]** In fact, this booklet pair of values for w and
**[0:33]** b corresponds to this function f of x,
**[0:37]** which is this line you can see on the left.
**[0:40]** This line intersects the vertical axis at 800 because
**[0:45]** b equals 800 and the slope of the line is negative 0.15,
**[0:50]** because w equals negative 0.15.
**[0:53]** Now, if you look at the data points in the training set,
**[0:56]** you may notice that this line
**[0:58]** is not a good fit to the data.
**[1:01]** For this function f of x,
**[1:03]** with these values of w and b,
**[1:07]** many of the predictions for the value of y are quite far
**[1:11]** from the actual target value of
**[1:13]** y that is in the training data.
**[1:15]** Because this line is not a good fit,
**[1:18]** if you look at the graph of j,
**[1:20]** the cost of this line is out here,
**[1:24]** which is pretty far from the minimum.
**[1:27]** There's a pretty high cost because this choice of
**[1:30]** w and b is just not that good a fit to the training set.
**[1:34]** Now, let's look at
**[1:36]** another example with a different choice of w and b.
**[1:41]** Now, here's another function that
**[1:43]** is still not a great fit for the data,
**[1:46]** but maybe slightly less bad.
**[1:48]** This points here represents
**[1:51]** the cost for this booklet pair
**[1:52]** of w and b that creates that line.
**[1:56]** The value of w is equal to 0 and
**[1:59]** the value b is about 360.
**[2:03]** This pair of parameters corresponds to this function,
**[2:07]** which is a flat line,
**[2:08]** because f of x equals 0 times x plus 360.
**[2:13]** I hope that makes sense.
**[2:15]** Let's look at yet another example.
**[2:18]** Here's one more choice for w and b,
**[2:21]** and with these values,
**[2:23]** you end up with this line f of x.
**[2:25]** Again, not a great fit to the data,
**[2:27]** is actually further away from the minimum
**[2:29]** compared to the previous example.
**[2:32]** Remember that the minimum is at
**[2:34]** the center of that smallest ellipse.
**[2:38]** Last example, if you look at f of x on the left,
**[2:43]** this looks like a pretty good fit to the training set.
**[2:46]** You can see on the right,
**[2:49]** this point representing the cost is very
**[2:52]** close to the center of the smaller ellipse,
**[2:56]** it's not quite exactly the minimum,
**[2:58]** but it's pretty close.
**[2:59]** For this value of w and b,
**[3:02]** you get to this line, f of x.
**[3:06]** You can see that if you measure
**[3:08]** the vertical distances between
**[3:10]** the data points and
**[3:11]** the predicted values on the straight line,
**[3:14]** you'd get the error for each data point.
**[3:18]** The sum of squared errors for all of
**[3:21]** these data points is pretty close to
**[3:24]** the minimum possible sum of
**[3:25]** squared errors among all possible straight line fits.
**[3:30]** I hope that by looking at these figures,
**[3:33]** you can get a better sense of how different choices
**[3:35]** of the parameters affect the line f
**[3:38]** of x and how this
**[3:40]** corresponds to different values for the cost j,
**[3:44]** and hopefully you can see how
**[3:48]** the better fit lines correspond to points on the graph of
**[3:52]** j that are closer to the minimum possible cost
**[3:55]** for this cost function j of w and b.
**[4:00]** In the optional lab that follows this video,
**[4:04]** you'll get to run
**[4:05]** some codes and remember all the code is given,
**[4:09]** so you just need to hit
**[4:10]** Shift Enter to run it and take a look at it
**[4:13]** and the lab will show you how
**[4:15]** the cost function is implemented in code.
**[4:18]** Given a small training set
**[4:20]** and different choices for the parameters,
**[4:23]** you'll be able to see how the cost varies
**[4:25]** depending on how well the model fits the data.
**[4:29]** In the optional lab,
**[4:30]** you also can play with in
**[4:32]** interactive console plot. Check this out.
**[4:35]** You can use your mouse cursor to click
**[4:37]** anywhere on the contour plot and you will
**[4:39]** see the straight line defined by
**[4:41]** the values you chose for the parameters w and b.
**[4:45]** You'll see a dot up here also on
**[4:48]** the 3D surface plot showing the cost.
**[4:51]** Finally, the optional lab also has
**[4:54]** a 3D surface plot that you can manually
**[4:57]** rotate and spin around using
**[4:59]** your mouse cursor to take
**[5:01]** a better look at what the cost function looks like.
**[5:04]** I hope you'll enjoy playing with the optional lab.
**[5:07]** Now in linear regression,
**[5:09]** rather than having to manually try to read
**[5:12]** a contour plot for the best value for w and b,
**[5:15]** which isn't really a good procedure and also won't work
**[5:18]** once we get to more complex machine learning models.
**[5:21]** What you really want is
**[5:22]** an efficient algorithm that you can write in code for
**[5:26]** automatically finding the values of parameters w
**[5:28]** and b they give you the best fit line.
**[5:31]** That minimizes the cost function j.
**[5:34]** There is an algorithm for doing
**[5:36]** this called gradient descent.
**[5:38]** This algorithm is one of
**[5:40]** the most important algorithms in machine learning.
**[5:42]** Gradient descent and variations
**[5:45]** on gradient descent are used to train,
**[5:47]** not just linear regression,
**[5:49]** but some of the biggest and most
**[5:50]** complex models in all of AI.
**[5:53]** Let's go to the next video to dive into
**[5:56]** this really important algorithm called gradient descent.
