---
type: video-transcript
specialization: Machine Learning Specialization
course: "Supervised Machine Learning: Regression and Classification"
week: 1
section: Regression Model
item_title: Cost function formula
duration: 9 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/1Z0TT/cost-function-formula
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Cost function formula — Transcript

**[0:00]** In order to implement linear regression
**[0:03]** the first key step is first to
**[0:05]** define something called a cost function.
**[0:07]** This is something we'll build in this video,
**[0:10]** and the cost function will tell us how well
**[0:13]** the model is doing so that
**[0:15]** we can try to get it to do better.
**[0:17]** Let's look at what this means.
**[0:18]** Recall that you have a training set that contains
**[0:21]** input features x and output targets y.
**[0:26]** The model you're going to use to fit this training set
**[0:29]** is this linear function f_w,
**[0:32]** b of x equals to w times x plus b.
**[0:36]** To introduce a little bit more terminology the w
**[0:40]** and b are called the parameters of the model.
**[0:44]** In machine learning parameters of the model are
**[0:48]** the variables you can adjust during
**[0:50]** training in order to improve the model.
**[0:53]** Sometimes you also hear the parameters w and b
**[0:57]** referred to as coefficients or as weights.
**[1:01]** Now let's take a look at what
**[1:04]** these parameters w and b do.
**[1:07]** Depending on the values you've chosen for w and
**[1:10]** b you get a different function f of x,
**[1:14]** which generates a different line on the graph.
**[1:17]** Remember that we can write f of x as
**[1:20]** a shorthand for f_w, b of x.
**[1:24]** We're going to take a look at some plots
**[1:26]** of f of x on a chart.
**[1:29]** Maybe you're already familiar
**[1:31]** with drawing lines on charts,
**[1:32]** but even if this is a review for you,
**[1:34]** I hope this will help you build intuition
**[1:37]** on how w and b the parameters
**[1:39]** determine f. When w is equal to 0 and b is equal to 1.5,
**[1:47]** then f looks like this horizontal line.
**[1:50]** In this case, the function f of x is 0 times x
**[1:55]** plus 1.5 so f is always a constant value.
**[2:00]** It always predicts 1.5 for
**[2:03]** the estimated value of y. Y hat is always equal to b
**[2:08]** and here b is also called
**[2:10]** the y intercept because that's where it
**[2:13]** crosses the vertical axis or the y axis on this graph.
**[2:17]** As a second example,
**[2:20]** if w is 0.5 and b is equal 0,
**[2:24]** then f of x is 0.5 times x.
**[2:28]** When x is 0,
**[2:30]** the prediction is also 0,
**[2:31]** and when x is 2,
**[2:33]** then the prediction is 0.5 times 2, which is 1.
**[2:38]** You get a line that looks like this and notice that
**[2:41]** the slope is 0.5 divided by 1.
**[2:45]** The value of w gives you the slope
**[2:49]** of the line, which is 0.5.
**[2:52]** Finally, if w equals 0.5 and b equals 1,
**[2:58]** then f of x is 0.5 times x plus 1 and when x is 0,
**[3:05]** then f of x equals b,
**[3:08]** which is 1 so the line intersects
**[3:10]** the vertical axis at b, the y intercept.
**[3:14]** Also when x is 2,
**[3:17]** then f of x is 2,
**[3:19]** so the line looks like this.
**[3:20]** Again, this slope is 0.5 divided by
**[3:24]** 1 so the value of w gives you the slope which is 0.5.
**[3:28]** Recall that you have
**[3:30]** a training set like the one shown here.
**[3:33]** With linear regression,
**[3:35]** what you want to do is to choose
**[3:36]** values for the parameters w and
**[3:38]** b so that the straight line you get from
**[3:41]** the function f somehow fits the data well.
**[3:43]** Like maybe this line shown here.
**[3:46]** When I see that the line fits the data visually,
**[3:51]** you can think of this to mean that the line
**[3:53]** defined by f is roughly passing
**[3:55]** through or somewhere close to the training examples
**[3:59]** as compared to other possible lines
**[4:01]** that are not as close to these points.
**[4:04]** Just to remind you of some notation,
**[4:07]** a training example like this point
**[4:10]** here is defined by x superscript i,
**[4:14]** y superscript i where y is the target.
**[4:20]** For a given input x^i,
**[4:23]** the function f also makes a predictive value for
**[4:28]** y and a value that it predicts to
**[4:31]** y is y hat i shown here.
**[4:34]** For our choice of a model f of x^i is w times x^i plus b.
**[4:41]** Stated differently, the prediction y hat i
**[4:44]** is f of wb of x^i where
**[4:49]** for the model we're using f
**[4:52]** of x^i is equal to wx^i plus b.
**[4:58]** Now the question is how do you find values for
**[5:03]** w and b so that the prediction y hat i is
**[5:07]** close to the true target y^i for
**[5:11]** many or maybe all training examples x^i, y^i.
**[5:16]** To answer that question,
**[5:18]** let's first take a look at how to
**[5:20]** measure how well a line fits the training data.
**[5:24]** To do that, we're going to construct a cost function.
**[5:28]** The cost function takes the prediction y hat and compares
**[5:33]** it to the target y by taking y hat minus y.
**[5:39]** This difference is called the error,
**[5:42]** we're measuring how far off to
**[5:44]** prediction is from the target.
**[5:47]** Next, let's computes the square of this error.
**[5:52]** Also, we're going to want to compute this term for
**[5:55]** different training examples i in the training set.
**[5:59]** When measuring the error,
**[6:00]** for example i,
**[6:02]** we'll compute this squared error term.
**[6:05]** Finally, we want to measure
**[6:07]** the error across the entire training set.
**[6:09]** In particular, let's sum up the squared errors like this.
**[6:13]** We'll sum from i equals 1,2,
**[6:16]** 3 all the way up to
**[6:18]** m and remember that m is the number of training examples,
**[6:23]** which is 47 for this dataset.
**[6:25]** Notice that if we have more training examples m is
**[6:28]** larger and your cost function
**[6:31]** will calculate a bigger number.
**[6:32]** This is summing over more examples.
**[6:35]** To build a cost function that
**[6:37]** doesn't automatically get bigger
**[6:39]** as the training set size gets larger by convention,
**[6:44]** we will compute the average squared error instead of
**[6:48]** the total squared error and we do
**[6:50]** that by dividing by m like this.
**[6:54]** We're nearly there. Just one last thing.
**[6:58]** By convention,
**[7:00]** the cost function that machine learning people use
**[7:02]** actually divides by 2 times m. The extra division
**[7:07]** by 2 is just meant to make some of
**[7:09]** our later calculations look neater,
**[7:12]** but the cost function still works whether you
**[7:14]** include this division by 2 or not.
**[7:17]** This expression right here is
**[7:18]** the cost function and we're going to write
**[7:21]** J of wb to refer to the cost function.
**[7:27]** This is also called the squared error cost function,
**[7:31]** and it's called this because you're taking
**[7:34]** the square of these error terms.
**[7:36]** In machine learning different people
**[7:39]** will use different cost functions
**[7:41]** for different applications,
**[7:42]** but the squared error cost function is by far the most
**[7:46]** commonly used one for
**[7:48]** linear regression and for that matter,
**[7:50]** for all regression problems where it
**[7:53]** seems to give good results for many applications.
**[7:56]** Just as a reminder, the prediction y hat
**[8:00]** is equal to the outputs of the model f at x.
**[8:05]** We can rewrite the cost function J of
**[8:09]** wb as 1 over 2m times
**[8:14]** the sum from i equals 1 to m of f
**[8:17]** of x^i minus y^i the quantity squared.
**[8:23]** Eventually we're going to want to find values of
**[8:26]** w and b that make the cost function small.
**[8:29]** But before going there,
**[8:31]** let's first gain more intuition about what
**[8:34]** J of wb is really computing.
**[8:38]** At this point you might be thinking we've done
**[8:40]** a whole lot of math to define the cost function.
**[8:43]** But what exactly is it doing?
**[8:46]** Let's go on to the next video where we'll step
**[8:49]** through one example of what the cost function
**[8:51]** is really computing that I hope will
**[8:53]** help you build intuition about what it
**[8:56]** means if J of wb is large versus if the cost j is small.
**[9:01]** Let's go on to the next video.
