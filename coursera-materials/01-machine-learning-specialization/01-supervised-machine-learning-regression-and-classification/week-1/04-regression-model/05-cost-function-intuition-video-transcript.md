---
type: video-transcript
specialization: Machine Learning Specialization
course: Supervised Machine Learning: Regression and Classification
week: 1
section: Regression Model
item_title: Cost function intuition
duration: 16 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/FthLz/cost-function-intuition
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Cost function intuition — Transcript

**[0:01]** We're seeing the mathematical definition
**[0:03]** of the cost function.
**[0:05]** Now, let's build some intuition
**[0:07]** about what the cost function is really doing.
**[0:09]** In this video, we'll walk through one example to see how
**[0:13]** the cost function can be used to
**[0:14]** find the best parameters for your model.
**[0:17]** I know this video's little bit longer than the others,
**[0:19]** but bear with me, I think it'll be worth it.
**[0:22]** To recap, here's what we've
**[0:24]** seen about the cost function so far.
**[0:26]** You want to fit a straight line to the training data,
**[0:29]** so you have this model, fw,
**[0:32]** b of x is w times x, plus b.
**[0:35]** Here, the model's parameters are w, and b.
**[0:39]** Now, depending on the values chosen for these parameters,
**[0:43]** you get different straight lines like this.
**[0:46]** You want to find values for w,
**[0:49]** and b, so that
**[0:50]** the straight line fits the training data well.
**[0:53]** To measure how well a choice of w,
**[0:57]** and b fits the training data,
**[0:59]** you have a cost function J.
**[1:02]** What the cost function J does is,
**[1:05]** it measures the difference
**[1:06]** between the model's predictions,
**[1:08]** and the actual true values for y.
**[1:12]** What you see later,
**[1:14]** is that linear regression would
**[1:16]** try to find values for w,
**[1:17]** and b, then make a J of w be as small as possible.
**[1:22]** In math, we write it like this.
**[1:25]** We want to minimize,
**[1:27]** J as a function of w, and b.
**[1:32]** Now, in order for us to
**[1:35]** better visualize the cost function J,
**[1:37]** this work of a simplified version
**[1:39]** of the linear regression model.
**[1:41]** We're going to use the model fw of x,
**[1:45]** is w times x.
**[1:48]** You can think of this as taking
**[1:50]** the original model on the left,
**[1:52]** and getting rid of the parameter b,
**[1:54]** or setting the parameter b equal to 0.
**[1:58]** It just goes away from the equation,
**[2:00]** so f is now just w times x.
**[2:04]** You now have just one parameter w,
**[2:08]** and your cost function J,
**[2:10]** looks similar to what it was before.
**[2:12]** Taking the difference,
**[2:13]** and squaring it,
**[2:15]** except now, f is equal to w times xi,
**[2:20]** and J is now a function of just
**[2:23]** w. The goal becomes a little bit different as well,
**[2:28]** because you have just one parameter, w,
**[2:30]** not w and b.
**[2:32]** With this simplified model,
**[2:35]** the goal is to find the value for w,
**[2:37]** that minimizes J of w. To see this visually,
**[2:43]** what this means is that if b is set to 0,
**[2:46]** then f defines a line that looks like this.
**[2:50]** You see that the line passes through the origin here,
**[2:53]** because when x is 0,
**[2:55]** f of x is 0 too.
**[2:57]** Now, using this simplified model,
**[3:00]** let's see how the cost function changes as you choose
**[3:03]** different values for the parameter w. In particular,
**[3:08]** let's look at graphs of the model f of x,
**[3:11]** and the cost function J.
**[3:14]** I'm going to plot these side-by-side,
**[3:17]** and you'll be able to see how the two are related.
**[3:21]** First, notice that for f subscript w,
**[3:25]** when the parameter w is fixed,
**[3:27]** that is, is always a constant value,
**[3:30]** then fw is only a function of x,
**[3:35]** which means that the estimated value of y depends
**[3:38]** on the value of the input x.
**[3:42]** In contrast, looking to the right,
**[3:45]** the cost function J,
**[3:48]** is a function of w,
**[3:50]** where w controls the slope of the line defined by
**[3:53]** f w. The cost defined by J,
**[3:57]** depends on a parameter,
**[3:59]** in this case, the parameter w. Let's go ahead,
**[4:04]** and plot these functions,
**[4:06]** fw of x, and J of w
**[4:10]** side-by-side so you can see how they are related.
**[4:14]** We'll start with the model,
**[4:17]** that is the function fw of x on the left.
**[4:22]** Here are the input feature x is on the horizontal axis,
**[4:26]** and the output value y is on the vertical axis.
**[4:30]** Here's the plots of three points representing
**[4:33]** the training set at positions 1,
**[4:36]** 1, 2, 2, and 3,3.
**[4:40]** Let's pick a value for w. Say w is 1.
**[4:44]** For this choice of w,
**[4:48]** the function fw,
**[4:50]** they'll say this straight line with a slope of 1.
**[4:54]** Now, what you can do next is calculate
**[4:57]** the cost J when w equals 1.
**[5:03]** You may recall that the cost function
**[5:05]** is defined as follows,
**[5:06]** is the squared error cost function.
**[5:09]** If you substitute fw(X^i) with w times X^i,
**[5:16]** the cost function looks like this.
**[5:18]** Where this expression is now w times X^i minus Y^i.
**[5:24]** For this value of w,
**[5:26]** it turns out that the error term
**[5:28]** inside the cost function,
**[5:29]** this w times X^i minus
**[5:33]** Y^i is equal to 0 for each of the three data points.
**[5:37]** Because for this data-set,
**[5:39]** when x is 1, then y is 1.
**[5:41]** When w is also 1,
**[5:44]** then f(x) equals 1,
**[5:46]** so f(x) equals y for this first training example,
**[5:50]** and the difference is 0.
**[5:52]** Plugging this into the cost function J,
**[5:55]** you get 0 squared.
**[5:57]** Similarly, when x is 2,
**[6:00]** then y is 2,
**[6:02]** and f(x) is also 2.
**[6:04]** Again, f(x) equals y,
**[6:07]** for the second training example.
**[6:08]** In the cost function,
**[6:10]** the squared error for
**[6:11]** the second example is also 0 squared.
**[6:15]** Finally, when x is 3,
**[6:17]** then y is 3 and f(3) is also 3.
**[6:22]** In a cost function
**[6:23]** the third squared error term is also 0 squared.
**[6:27]** For all three examples in this training set,
**[6:31]** f(X^i) equals Y^i for each training example i,
**[6:36]** so f(X^i) minus Y^i is 0.
**[6:42]** For this particular data-set,
**[6:46]** when w is 1,
**[6:47]** then the cost J is equal to 0.
**[6:52]** Now, what you can do on
**[6:54]** the right is plot the cost function J.
**[6:58]** Notice that because the cost function
**[7:00]** is a function of the parameter w,
**[7:03]** the horizontal axis is now labeled w and not x,
**[7:08]** and the vertical axis is now J and not y.
**[7:14]** You have J(1) equals to 0.
**[7:20]** In other words, when w equals 1,
**[7:24]** J(w) is 0,
**[7:26]** so let me go ahead and plot that.
**[7:29]** Now, let's look at how F and J change for
**[7:33]** different values of w. W can take on a range of values,
**[7:38]** so w can take on negative values,
**[7:41]** w can be 0, and it can take on positive values too.
**[7:45]** What if w is equal to 0.5 instead of 1,
**[7:50]** what would these graphs look like then?
**[7:52]** Let's go ahead and plot that.
**[7:55]** Let's set w to be equal to 0.5,
**[7:58]** and in this case,
**[8:00]** the function f(x) now looks like this,
**[8:04]** is a line with a slope equal to 0.5.
**[8:09]** Let's also compute the cost J,
**[8:12]** when w is 0.5.
**[8:15]** Recall that the cost function is measuring
**[8:18]** the squared error or
**[8:19]** difference between the estimator value,
**[8:22]** that is y hat I,
**[8:24]** which is F(X^i),
**[8:26]** and the true value,
**[8:29]** that is Y^i for each example i. Visually you can see that
**[8:36]** the error or difference is equal to the height
**[8:39]** of this vertical line here when x is equal to 1.
**[8:44]** Because this lower line is
**[8:46]** the gap between the actual value
**[8:48]** of y and the value that the function f predicted,
**[8:52]** which is a bit further down here.
**[8:54]** For this first example,
**[8:57]** when x is 1, f(x) is 0.5.
**[9:02]** The squared error on the first example is
**[9:06]** 0.5 minus 1 squared.
**[9:10]** Remember the cost function,
**[9:12]** we'll sum over all the
**[9:13]** training examples in the training set.
**[9:15]** Let's go on to the second training example.
**[9:18]** When x is 2,
**[9:21]** the model is predicting f(x) is
**[9:24]** 1 and the actual value of y is 2.
**[9:29]** The error for the second example is equal to
**[9:32]** the height of this little line segment here,
**[9:36]** and the squared error is
**[9:38]** the square of the length of this line segment,
**[9:41]** so you get 1 minus 2 squared.
**[9:45]** Let's do the third example.
**[9:48]** Repeating this process, the error here,
**[9:51]** also shown by this line segment,
**[9:54]** is 1.5 minus 3 squared.
**[9:59]** Next, we sum up all of these terms,
**[10:01]** which turns out to be equal to 3.5.
**[10:05]** Then we multiply this term by 1 over 2m,
**[10:10]** where m is the number of training examples.
**[10:14]** Since there are three training examples m equals 3,
**[10:19]** so this is equal to 1 over 2 times 3,
**[10:25]** where this m here is 3.
**[10:29]** If we work out the math,
**[10:31]** this turns out to be 3.5 divided by 6.
**[10:35]** The cost J is about 0.58.
**[10:40]** Let's go ahead and plot that over there on the right.
**[10:44]** Now, let's try one more value for
**[10:47]** w. How about if w equals 0?
**[10:51]** What do the graphs for f and J
**[10:53]** look like when w is equal to 0?
**[10:56]** It turns out that if w is equal to 0,
**[11:00]** then f of x is
**[11:01]** just this horizontal line that is exactly on the x-axis.
**[11:07]** The error for each example is
**[11:09]** a line that goes from each point down
**[11:11]** to the horizontal line that represents f of x equals 0.
**[11:17]** The cost J when w equals
**[11:20]** 0 is 1 over 2m times the quantity,
**[11:25]** 1^2 plus 2^2 plus 3^2,
**[11:28]** and that's equal to 1 over 6 times 14,
**[11:33]** which is about 2.33.
**[11:36]** Let's plot this point where w is 0 and J
**[11:40]** of 0 is 2.33 over here.
**[11:44]** You can keep doing this for other values of
**[11:47]** w. Since w can be any number,
**[11:51]** it can also be a negative value.
**[11:53]** If w is negative 0.5,
**[11:56]** then the line f is a downward-sloping line like this.
**[12:02]** It turns out that when w is negative
**[12:05]** 0.5 then you end up with an even higher cost,
**[12:09]** around 5.25, which is this point up here.
**[12:14]** You can continue computing the cost function for
**[12:17]** different values of w and so on and plot these.
**[12:21]** It turns out that by computing a range of values,
**[12:25]** you can slowly trace out what the cost function J
**[12:28]** looks like and that's what J is.
**[12:32]** To recap, each value of
**[12:35]** parameter w corresponds to different straight line fit,
**[12:40]** f of x, on the graph to the left.
**[12:43]** For the given training set,
**[12:45]** that choice for a value of w corresponds to
**[12:49]** a single point on
**[12:52]** the graph on the right because for each value of w,
**[12:55]** you can calculate the cost J of w. For example,
**[13:00]** when w equals 1,
**[13:02]** this corresponds to this straight line fit through
**[13:06]** the data and it also
**[13:09]** corresponds to this point on the graph of J,
**[13:13]** where w equals 1 and the cost J of 1 equals 0.
**[13:18]** Whereas when w equals 0.5,
**[13:21]** this gives you this line which has a smaller slope.
**[13:25]** This line in combination with
**[13:28]** the training set corresponds to
**[13:30]** this point on the cost function graph at w equals 0.5.
**[13:36]** For each value of w you wind up with
**[13:39]** a different line and its corresponding costs,
**[13:42]** J of w,
**[13:44]** and you can use these points
**[13:46]** to trace out this plot on the right.
**[13:48]** Given this, how can you choose the value of
**[13:51]** w that results in the function f,
**[13:54]** fitting the data well?
**[13:56]** Well, as you can imagine,
**[13:58]** choosing a value of w that causes J of w
**[14:02]** to be as small as possible seems like a good bet.
**[14:05]** J is the cost function that
**[14:08]** measures how big the squared errors are,
**[14:11]** so choosing w that minimizes these squared errors,
**[14:14]** makes them as small as possible,
**[14:16]** will give us a good model.
**[14:18]** In this example, if you were to
**[14:20]** choose the value of w that results
**[14:22]** in the smallest possible value of J of
**[14:25]** w you'd end up picking w equals 1.
**[14:28]** As you can see, that's actually a pretty good choice.
**[14:31]** This results in the line that fits
**[14:33]** the training data very well.
**[14:36]** That's how in linear regression you use the cost function
**[14:41]** to find the value of w that minimizes J.
**[14:46]** In the more general case where we had
**[14:48]** parameters w and b rather than just w,
**[14:52]** you find the values of w and b that minimize J.
**[14:58]** To summarize, you saw plots of both
**[15:01]** f and J and worked through how the two are related.
**[15:05]** As you vary w or vary w and b you end up
**[15:09]** with different straight lines and when
**[15:11]** that straight line passes across the data,
**[15:13]** the cause J is small.
**[15:16]** The goal of linear regression is to find
**[15:18]** the parameters w or w and
**[15:21]** b that results in
**[15:22]** the smallest possible value for the cost function J.
**[15:26]** Now in this video,
**[15:27]** we worked through our example with
**[15:29]** a simplified problem using only w. In the next video,
**[15:34]** let's visualize what the cost function looks like for
**[15:36]** the full version of linear regression using both w and b.
**[15:42]** You see some cool 3D plots.
**[15:44]** Let's go to the next video.
