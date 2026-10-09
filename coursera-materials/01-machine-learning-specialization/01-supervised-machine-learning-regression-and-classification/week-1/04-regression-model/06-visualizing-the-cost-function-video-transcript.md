---
type: video-transcript
specialization: Machine Learning Specialization
course: Supervised Machine Learning: Regression and Classification
week: 1
section: Regression Model
item_title: Visualizing the cost function
duration: 9 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/QI1h6/visualizing-the-cost-function
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Visualizing the cost function — Transcript

**[0:00]** In the last video, you saw one visualization of
**[0:04]** the cost function J of w or J of w, b.
**[0:08]** Let's look at some further
**[0:09]** richer visualizations so that you can get
**[0:12]** an even better intuition
**[0:13]** about what the cost function is doing.
**[0:16]** Here is what we've seen so far.
**[0:18]** There's the model, the model's parameters w and b,
**[0:22]** the cost function J of w and b,
**[0:25]** as well as the goal of linear regression,
**[0:28]** which is to minimize the cost function J of w
**[0:31]** and b over parameters w and b.
**[0:35]** In the last video,
**[0:36]** we had temporarily set b to
**[0:38]** zero in order to simplify the visualizations.
**[0:42]** Now, let's go back to the original model with
**[0:45]** both parameters w and b
**[0:47]** without setting b to be equal to 0.
**[0:50]** Same as last time,
**[0:51]** we want to get a visual understanding
**[0:53]** of the model function, f of x,
**[0:57]** shown here on the left,
**[0:58]** and how it relates to the cost function J of w,
**[1:03]** b, shown here on the right.
**[1:06]** Here's a training set of house sizes and prices.
**[1:10]** Let's say you pick one possible function
**[1:12]** of x, like this one.
**[1:14]** Here, I've set w to 0.06 and b to
**[1:19]** 50. f of x is 0.06 times x plus 50.
**[1:25]** Note that this is not
**[1:26]** a particularly good model for this training set,
**[1:28]** is actually a pretty bad model.
**[1:30]** It seems to consistently underestimate housing prices.
**[1:34]** Given these values for w and b let's look at what
**[1:38]** the cost function J of w and b may look like.
**[1:42]** Recall what we saw last time was when you had only w,
**[1:47]** because we temporarily set b to zero to simplify things,
**[1:51]** but then we had come up with a plot of the cost function
**[1:55]** that look like this as a function of w only.
**[2:00]** When we had only one parameter, w,
**[2:03]** the cost function had this U-shaped curve,
**[2:06]** shaped a bit like a soup bowl.
**[2:08]** That sounds delicious.
**[2:10]** Now, in this housing price example
**[2:13]** that we have on this slide,
**[2:15]** we have two parameters, w and b.
**[2:20]** The plots becomes a little more complex.
**[2:23]** It turns out that the cost function
**[2:27]** also has a similar shape like a soup bowl,
**[2:31]** except in three dimensions instead of two.
**[2:34]** In fact, depending on your training set,
**[2:37]** the cost function will look something like this.
**[2:40]** To me, this looks like a soup bowl,
**[2:42]** maybe because I'm a little bit hungry,
**[2:45]** or maybe to you it looks like
**[2:47]** a curved dinner plate or a hammock.
**[2:50]** Actually that sounds relaxing too,
**[2:52]** and there's your coconut drink.
**[2:54]** Maybe when you're done with this course,
**[2:57]** you should treat yourself to
**[2:58]** vacation and relax in a hammock like this.
**[3:01]** What you see here is a 3D-surface plot
**[3:04]** where the axes are labeled w and b.
**[3:08]** As you vary w and b,
**[3:11]** which are the two parameters of the model,
**[3:13]** you get different values for
**[3:15]** the cost function J of w, and b.
**[3:18]** This is a lot like the U-shaped curve
**[3:21]** you saw in the last video,
**[3:22]** except instead of having
**[3:24]** one parameter w as input for the j,
**[3:27]** you now have two parameters,
**[3:29]** w and b as inputs into
**[3:31]** this soup bowl or this hammock-shaped function
**[3:34]** J. I just want to point out that any single point on
**[3:38]** this surface represents some particular choice
**[3:41]** of w and b.
**[3:43]** For example, if w was minus 10 and b was minus 15,
**[3:49]** then the height of the surface
**[3:51]** above this point is the value of
**[3:53]** j when w is minus 10 and b is minus 15.
**[3:59]** Now, in order to look even more
**[4:01]** closely at specific points,
**[4:04]** there's another way of plotting
**[4:05]** the cost function J
**[4:07]** that would be useful for visualization,
**[4:09]** which is, rather than using these 3D-surface plots,
**[4:13]** I like to take this exact same function
**[4:16]** J. I'm not changing
**[4:17]** the function J at all and
**[4:19]** plot it using something called a contour plot.
**[4:22]** If you've ever seen a topographical map
**[4:25]** showing how high different mountains are,
**[4:28]** the contours in a topographical map are basically
**[4:31]** horizontal slices of the landscape of say, a mountain.
**[4:36]** This image is of Mount Fuji in Japan.
**[4:40]** I still remember my family visiting
**[4:42]** Mount Fuji when I was a teenager.
**[4:45]** It's beautiful sights.
**[4:47]** If you fly directly above the mountain,
**[4:50]** that's what this contour map looks like.
**[4:53]** It shows all the points,
**[4:55]** they're at the same height for different heights.
**[4:59]** At the bottom of this slide is a 3D-surface plot of
**[5:03]** the cost function J.
**[5:04]** I know it doesn't look very bowl-shaped,
**[5:07]** but it is actually a bowl just very stretched out,
**[5:11]** which is why it looks like that.
**[5:12]** In an optional lab,
**[5:14]** that is shortly to follow,
**[5:16]** you will be able to see this in 3D and spin around
**[5:19]** the surface yourself and it'll look
**[5:21]** more obviously bowl-shaped there.
**[5:23]** Next, here on the upper right is a contour plot of
**[5:27]** this exact same cost function
**[5:29]** as that shown at the bottom.
**[5:32]** The two axes on this contour plots are b,
**[5:36]** on the vertical axis,
**[5:38]** and w on the horizontal axis.
**[5:41]** What each of these ovals,
**[5:43]** also called ellipses,
**[5:45]** shows, is the center points on
**[5:48]** the 3D surface which are at the exact same height.
**[5:51]** In other words, the set of points which have
**[5:54]** the same value for the cost function J.
**[5:57]** To get the contour plots,
**[5:59]** you take the 3D surface at the bottom and you
**[6:03]** use a knife to slice it horizontally.
**[6:08]** You take horizontal slices of
**[6:10]** that 3D surface and get all the points,
**[6:13]** they're at the same height.
**[6:15]** Therefore, each horizontal slice ends up being shown
**[6:19]** as one of these ellipses or one of these ovals.
**[6:24]** Concretely, if you take that point,
**[6:28]** and that point, and that point,
**[6:32]** all of these three points have
**[6:34]** the same value for the cost function J,
**[6:38]** even though they have different values for w and b.
**[6:43]** In the figure on the upper left,
**[6:46]** you see also that these three points
**[6:49]** correspond to different functions,
**[6:52]** f, all three of which are actually pretty
**[6:54]** bad for predicting housing prices in this case.
**[6:58]** Now, the bottom of the bowl,
**[7:00]** where the cost function J is at a minimum,
**[7:04]** is this point right here,
**[7:08]** at the center of this concentric ovals.
**[7:11]** If you haven't seen contour plots much before,
**[7:14]** I'd like you to imagine, if you will,
**[7:17]** that you are flying high up above
**[7:20]** the bowl in an airplane or in a rocket ship,
**[7:23]** and you're looking straight down at it.
**[7:26]** That is as if you set
**[7:28]** your computer monitor flat on your desk
**[7:31]** facing up and the bowl shape
**[7:33]** is coming directly out of your screen,
**[7:35]** rising above you desk.
**[7:37]** Imagine that the bowl shape grows out of
**[7:40]** your computer screen lying flat like that,
**[7:44]** so that each of these ovals have
**[7:47]** the same height above your screen and
**[7:49]** the minimum of the bowl is right
**[7:52]** down there in the center of the smallest oval.
**[7:56]** It turns out that the contour plots are
**[7:59]** a convenient way to visualize the 3D cost function J,
**[8:03]** but in a way, there's plotted in just 2D.
**[8:07]** In this video, you saw how
**[8:09]** the 3D bowl-shaped surface plot
**[8:12]** can also be visualized as a contour plot.
**[8:15]** Using this visualization too,
**[8:17]** in the next video,
**[8:19]** let's visualize some specific choices
**[8:22]** of w and b in the linear regression model
**[8:24]** so that you can see how these different choices
**[8:27]** affect the straight line you're fitting to the data.
**[8:30]** Let's go on to the next video.
