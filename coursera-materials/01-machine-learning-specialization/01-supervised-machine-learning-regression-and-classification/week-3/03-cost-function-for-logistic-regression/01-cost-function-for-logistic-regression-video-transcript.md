---
type: video-transcript
specialization: Machine Learning Specialization
course: Supervised Machine Learning: Regression and Classification
week: 3
section: Cost function for logistic regression
item_title: Cost function for logistic regression
duration: 12 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/0hpr8/cost-function-for-logistic-regression
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Cost function for logistic regression — Transcript

**[0:00]** Remember that the cost function gives you a way to
**[0:05]** measure how well a specific set of
**[0:06]** parameters fits the training data.
**[0:09]** Thereby gives you a way to
**[0:11]** try to choose better parameters.
**[0:13]** In this video, we'll look at how
**[0:16]** the squared error cost function is
**[0:18]** not an ideal cost function for logistic regression.
**[0:21]** We'll take a look at a different cost function that
**[0:24]** can help us choose
**[0:25]** better parameters for logistic regression.
**[0:28]** Here's what the training set for
**[0:30]** our logistic regression model might look like.
**[0:33]** Where here each row might correspond to patients
**[0:38]** that was paying a visit to
**[0:39]** the doctor and one dealt with some diagnosis.
**[0:44]** As before, we'll use
**[0:46]** m to denote the number of training examples.
**[0:50]** Each training example has one or more features,
**[0:54]** such as the tumor size, the patient's age,
**[0:57]** and so on for a total of n features.
**[1:01]** Let's call the features X_1 through X_n.
**[1:06]** Since this is a binary classification task,
**[1:09]** the target label y takes on only two values,
**[1:13]** either 0 or 1.
**[1:15]** Finally, the logistic regression model
**[1:18]** is defined by this equation.
**[1:21]** The question you want to answer is,
**[1:24]** given this training set,
**[1:26]** how can you choose parameters w and b?
**[1:29]** Recall for linear regression,
**[1:32]** this is the squared error cost function.
**[1:35]** The only thing I've changed is that I put
**[1:37]** the one half inside
**[1:39]** the summation instead of outside the summation.
**[1:42]** You might remember that in the case of linear regression,
**[1:45]** where f of x is the linear function,
**[1:48]** w dot x plus b.
**[1:50]** The cost function looks like this,
**[1:52]** is a convex function or a bowl shape or hammer shape.
**[1:56]** Gradient descent will look like this,
**[1:59]** where you take one step,
**[2:00]** one step, and so on to converge at the global minimum.
**[2:05]** Now you could try to use
**[2:07]** the same cost function for logistic regression.
**[2:10]** But it turns out that if I were to write f of
**[2:12]** x equals 1 over 1 plus e to
**[2:16]** the negative wx plus b and
**[2:19]** plot the cost function using this value of f of x,
**[2:22]** then the cost will look like this.
**[2:25]** This becomes what's called a
**[2:27]** non-convex cost function is not convex.
**[2:32]** What this means is that if
**[2:34]** you were to try to use gradient descent.
**[2:37]** There are lots of local minima that you can get sucking.
**[2:41]** It turns out that for logistic regression,
**[2:44]** this squared error cost function is not a good choice.
**[2:48]** Instead, there will be
**[2:50]** a different cost function that can
**[2:52]** make the cost function convex again.
**[2:55]** The gradient descent can be
**[2:57]** guaranteed to converge to the global minimum.
**[3:00]** The only thing I've changed is that I put the one half
**[3:02]** inside the summation instead of outside the summation.
**[3:06]** This will make the math you
**[3:07]** see later on this slide a little bit simpler.
**[3:10]** In order to build a new cost function,
**[3:13]** one that we'll use for logistic regression.
**[3:16]** I'm going to change a little bit
**[3:18]** the definition of the cost function J of w and b.
**[3:22]** In particular, if you look inside this summation,
**[3:25]** let's call this term inside
**[3:27]** the loss on a single training example.
**[3:32]** I'm going to denote the loss via this capital
**[3:37]** L and as a function
**[3:39]** of the prediction of the learning algorithm,
**[3:42]** f of x as well as of the true label y.
**[3:47]** The loss given the predictor f of x and the true label
**[3:53]** y is equal in this case to 1.5 of the squared difference.
**[3:58]** We'll see shortly that by choosing
**[4:00]** a different form for this loss function,
**[4:03]** will be able to keep the overall cost function,
**[4:06]** which is 1 over n times the sum of
**[4:09]** these loss functions to be a convex function.
**[4:12]** Now, the loss function inputs f of x and
**[4:17]** the true label y and tells
**[4:20]** us how well we're doing on that example.
**[4:23]** I'm going to just write down here at
**[4:26]** the definition of the loss function
**[4:28]** we'll use for logistic regression.
**[4:30]** If the label y is equal to 1,
**[4:34]** then the loss is negative log of f of
**[4:38]** x and if the label y is equal to 0,
**[4:42]** then the loss is negative log of 1 minus f of x.
**[4:48]** Let's take a look at why
**[4:51]** this loss function hopefully makes sense.
**[4:55]** Let's first consider the case of y equals 1 and plot
**[5:00]** what this function looks like to gain
**[5:02]** some intuition about what this loss function is doing.
**[5:06]** Remember, the loss function
**[5:08]** measures how well you're doing on
**[5:10]** one training example and is by summing
**[5:13]** up the losses on all of
**[5:14]** the training examples that you then get,
**[5:16]** the cost function, which measures how
**[5:18]** well you're doing on the entire training set.
**[5:21]** If you plot log of f,
**[5:25]** it looks like this curve here,
**[5:28]** where f here is on the horizontal axis.
**[5:32]** A plot of a negative of the log of f looks like this,
**[5:37]** where we just flip the curve along the horizontal axis.
**[5:41]** Notice that it intersects the horizontal axis at
**[5:45]** f equals 1 and continues downward from there.
**[5:50]** Now, f is the output of logistic regression.
**[5:54]** Thus, f is always between zero and one because
**[5:57]** the output of logistic regression
**[5:59]** is always between zero and one.
**[6:02]** The only part of the function that's relevant is
**[6:05]** therefore this part over here,
**[6:09]** corresponding to f between 0 and 1.
**[6:12]** Let's zoom in and take
**[6:15]** a closer look at this part of the graph.
**[6:17]** If the algorithm predicts a probability close to
**[6:21]** 1 and the true label is 1,
**[6:25]** then the loss is very small.
**[6:28]** It's pretty much 0
**[6:29]** because you're very close to the right answer.
**[6:33]** Now continue with the example
**[6:36]** of the true label y being 1,
**[6:38]** say everything is a malignant tumor.
**[6:41]** If the algorithm predicts 0.5,
**[6:45]** then the loss is at this point here,
**[6:48]** which is a bit higher but not that high.
**[6:51]** Whereas in contrast, if the algorithm were
**[6:54]** to have outputs at 0.1 if it
**[6:57]** thinks that there is
**[6:58]** only a 10 percent chance of the tumor being
**[7:00]** malignant but y really is 1.
**[7:04]** If really is malignant,
**[7:05]** then the loss is this much higher value over here.
**[7:10]** When y is equal to 1,
**[7:12]** the loss function incentivizes or nurtures,
**[7:16]** or helps push the algorithm to make
**[7:18]** more accurate predictions because the loss is lowest,
**[7:21]** when it predicts values close to 1.
**[7:24]** Now on this slide,
**[7:26]** we'll be looking at what the loss is
**[7:27]** when y is equal to 1.
**[7:29]** On this slide, let's look at the second part of
**[7:32]** the loss function corresponding to when y is equal to 0.
**[7:36]** In this case, the loss is negative log of 1 minus f of x.
**[7:42]** When this function is plotted,
**[7:45]** it actually looks like this.
**[7:47]** The range of f is limited to 0 to 1
**[7:51]** because logistic regression only
**[7:53]** outputs values between 0 and 1.
**[7:56]** If we zoom in,
**[7:57]** this is what it looks like.
**[8:00]** In this plot, corresponding to y equals 0,
**[8:04]** the vertical axis shows the value of
**[8:08]** the loss for different values of f of x.
**[8:12]** When f is 0 or very close to 0,
**[8:17]** the loss is also going to be very small which means that
**[8:21]** if the true label is
**[8:22]** 0 and the model's prediction is very close to 0,
**[8:25]** well, you nearly got it right so
**[8:27]** the loss is appropriately very close to 0.
**[8:31]** The larger the value of f of x gets,
**[8:34]** the bigger the loss because the prediction
**[8:37]** is further from the true label 0.
**[8:40]** In fact, as that prediction approaches 1,
**[8:43]** the loss actually approaches infinity.
**[8:46]** Going back to the tumor prediction example just says if
**[8:51]** the model predicts that the patient's tumor is
**[8:53]** almost certain to be malignant, say,
**[8:55]** 99.9 percent chance of malignancy,
**[8:58]** that turns out to actually not be malignant,
**[9:00]** so y equals 0 then we
**[9:02]** penalize the model with a very high loss.
**[9:06]** In this case of y equals 0,
**[9:09]** so this is in the case of
**[9:10]** y equals 1 on the previous slide,
**[9:12]** the further the prediction f of x is
**[9:14]** away from the true value of y,
**[9:16]** the higher the loss.
**[9:18]** In fact, if f of x approaches 0,
**[9:23]** the loss here actually goes
**[9:25]** really large and in fact approaches infinity.
**[9:29]** When the true label is 1,
**[9:32]** the algorithm is strongly incentivized
**[9:35]** not to predict something too close to 0.
**[9:38]** In this video, you saw why
**[9:40]** the squared error cost function
**[9:41]** doesn't work well for logistic regression.
**[9:44]** We also defined the loss for
**[9:47]** a single training example and
**[9:50]** came up with a new definition for
**[9:53]** the loss function for logistic regression.
**[9:57]** It turns out that with this choice of loss function,
**[10:00]** the overall cost function will be convex and thus you can
**[10:04]** reliably use gradient descent
**[10:06]** to take you to the global minimum.
**[10:09]** Proving that this function is convex,
**[10:12]** it's beyond the scope of this cost.
**[10:14]** You may remember that the cost function is
**[10:18]** a function of the entire training set and is,
**[10:21]** therefore, the average or 1 over
**[10:24]** m times the sum of
**[10:26]** the loss function on the individual training examples.
**[10:29]** The cost on a certain set of parameters, w and b,
**[10:34]** is equal to 1 over
**[10:36]** m times the sum of
**[10:39]** all the training examples of
**[10:41]** the loss on the training examples.
**[10:43]** If you can find the value of the parameters, w and b,
**[10:47]** that minimizes this, then you'd have
**[10:51]** a pretty good set of values for the parameters
**[10:53]** w and b for logistic regression.
**[10:56]** In the upcoming optional lab,
**[10:58]** you'll get to take a look at how
**[11:00]** the squared error cost function
**[11:02]** doesn't work very well for classification,
**[11:04]** because you see that the surface plot results in
**[11:07]** a very wiggly costs surface with many local minima.
**[11:11]** Then you'll take a look at
**[11:14]** the new logistic loss function.
**[11:17]** As you can see here,
**[11:19]** this produces a nice and smooth convex surface plot
**[11:23]** that does not have all those local minima.
**[11:26]** Please take a look at the cost and
**[11:28]** the plots after this video.
**[11:32]** We've seen a lot in this video.
**[11:35]** In the next video,
**[11:36]** let's go back and take
**[11:37]** the loss function for a single train example
**[11:40]** and use that to define
**[11:41]** the overall cost function for the entire training set.
**[11:45]** We'll also figure out
**[11:47]** a simpler way to write out the cost function,
**[11:50]** which will then later allow us to run
**[11:52]** gradient descent to find
**[11:53]** good parameters for logistic regression.
**[11:56]** Let's go on to the next video.
