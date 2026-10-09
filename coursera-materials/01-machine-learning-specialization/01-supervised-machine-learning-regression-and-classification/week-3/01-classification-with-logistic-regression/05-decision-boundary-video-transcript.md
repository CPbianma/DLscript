---
type: video-transcript
specialization: Machine Learning Specialization
course: "Supervised Machine Learning: Regression and Classification"
week: 3
section: Classification with logistic regression
item_title: Decision boundary
duration: 11 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/qrxwU/decision-boundary
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Decision boundary — Transcript

**[0:00]** In the last video, you learned about
**[0:03]** the logistic regression model.
**[0:05]** Now, let's take a look at the decision boundary to get
**[0:09]** a better sense of how
**[0:10]** logistic regression is computing these predictions.
**[0:13]** To recap, here's how
**[0:15]** the logistic regression models
**[0:17]** outputs are computed in two steps.
**[0:20]** In the first step,
**[0:22]** you compute z as w.x plus b.
**[0:26]** Then you apply the Sigmoid function g to this value z.
**[0:31]** Here again, is the formula for the Sigmoid function.
**[0:34]** Another way to write this is we can
**[0:38]** say f of x is equal to g,
**[0:41]** the Sigmoid function,
**[0:43]** also called the logistic function,
**[0:44]** applied to w.x plus b,
**[0:48]** where this is of course,
**[0:50]** the value of z.
**[0:52]** If you take the definition of
**[0:54]** the Sigmoid function and plug in the definition of z,
**[0:59]** then you find that f of x is
**[1:01]** equal to this formula over here,
**[1:04]** 1 over 1 plus e to the negative z,
**[1:08]** where z is wx plus b.
**[1:11]** You may remember we said in
**[1:13]** the previous video that we interpret this as
**[1:16]** the probability that y is equal to
**[1:19]** 1 given x and with parameters w and b.
**[1:22]** This is going to be a number like maybe a 0.7 or 0.3.
**[1:27]** Now, what if you want to learn the algorithm to predict.
**[1:31]** Is the value of y going to be zero or one?
**[1:35]** Well, one thing you might do is set
**[1:37]** a threshold above which you predict y is one,
**[1:41]** or you set y hat to prediction to be equal to
**[1:44]** one and below which you might say y hat,
**[1:47]** my prediction is going to be equal to zero.
**[1:51]** A common choice would be to pick a threshold of
**[1:55]** 0.5 so that if f of x is greater than or equal to 0.5,
**[2:00]** then predict y is one.
**[2:02]** We write that prediction as y hat equals 1,
**[2:06]** or if f of x is less than 0.5,
**[2:09]** then predict y is 0,
**[2:10]** or in other words,
**[2:12]** the prediction y hat is equal to 0.
**[2:15]** Now, let's dive deeper into when
**[2:17]** the model would predict one.
**[2:19]** In other words, when is f of x greater
**[2:22]** than or equal to 0.5.
**[2:25]** We'll recall that f of x is just equal to g of z.
**[2:30]** So f is greater than or equal to
**[2:33]** 0.5 whenever g of z is greater than or equal to 0.5.
**[2:38]** But when is g of z greater than or equal to 0.5?
**[2:43]** Well, here's a Sigmoid function over here.
**[2:47]** So g of z is greater than or equal to
**[2:50]** 0.5 whenever z is greater than or equal to 0.
**[2:56]** That is whenever z is on the right half of this axis.
**[3:02]** Finally, when is z greater than or equal to zero?
**[3:06]** Well, z is equal to w.x plus b,
**[3:11]** so z is greater than or equal to zero
**[3:14]** whenever w.x plus b is greater than or equal to zero.
**[3:19]** To recap, what you've seen
**[3:22]** here is that the model predicts
**[3:25]** 1 whenever w.x plus b is greater than or equal to 0.
**[3:32]** Conversely, when w.x plus b is less than zero,
**[3:38]** the algorithm predicts y is 0.
**[3:42]** Given this, let's now
**[3:45]** visualize how the model makes predictions.
**[3:48]** I'm going to take an example of
**[3:51]** a classification problem where you have two features,
**[3:55]** x1 and x2 instead of just one feature.
**[3:58]** Here's a training set where the little red crosses denote
**[4:03]** the positive examples and
**[4:05]** the little blue circles denote negative examples.
**[4:08]** The red crosses corresponds to y equals 1,
**[4:13]** and the blue circles correspond to y equals 0.
**[4:18]** The logistic regression model will make predictions using
**[4:22]** this function f of x equals g of z,
**[4:26]** where z is now this expression over here,
**[4:30]** w1x1 plus w2x2 plus b,
**[4:34]** because we have two features x1 and x2.
**[4:37]** Let's just say for this example that
**[4:41]** the value of the parameters are w1 equals 1,
**[4:45]** w2 equals 1, and b equals negative 3.
**[4:50]** Let's now take a look at how
**[4:52]** logistic regression makes predictions.
**[4:55]** In particular, let's figure out when
**[4:57]** wx plus b is greater than equal to
**[4:59]** 0 and when wx plus b is less than 0.
**[5:04]** To figure that out,
**[5:05]** there's a very interesting line to look at,
**[5:08]** which is when wx plus b is exactly equal to 0.
**[5:13]** It turns out that this line is also called
**[5:18]** the decision boundary because that's the line where
**[5:21]** you're just almost neutral about
**[5:24]** whether y is 0 or y is 1.
**[5:26]** Now, for the values of the parameters w_1, w_2,
**[5:31]** and b that we had written down above,
**[5:35]** this decision boundary is just x_1 plus x_2 minus 3.
**[5:43]** When is x_1 plus x_2 minus 3 equal to 0?
**[5:49]** Well, that will correspond to the line
**[5:52]** x_1 plus x_2 equals 3,
**[5:55]** and that is this line shown over here.
**[6:01]** This line turns out to be the decision boundary,
**[6:06]** where if the features x are to the right of this line,
**[6:10]** logistic regression would predict
**[6:12]** 1 and to the left of this line,
**[6:15]** logistic regression with predicts 0.
**[6:18]** In other words, what we have just visualize is
**[6:23]** the decision boundary for
**[6:25]** logistic regression when the parameters w_1,
**[6:28]** w_2, and b are 1,1 and negative 3.
**[6:32]** Of course, if you had
**[6:33]** a different choice of the parameters,
**[6:35]** the decision boundary would be a different line.
**[6:39]** Now let's look at
**[6:40]** a more complex example where
**[6:42]** the decision boundary is no longer a straight line.
**[6:45]** As before, crosses denote the class y equals 1,
**[6:50]** and the little circles denote the class y equals 0.
**[6:56]** Earlier last week, you saw
**[7:00]** how to use polynomials in linear regression,
**[7:03]** and you can do the same in logistic regression.
**[7:07]** This set z to be w_1,
**[7:11]** x_1 squared plus w_2,
**[7:13]** x_2 squared plus b.
**[7:16]** With this choice of features,
**[7:18]** polynomial features into a logistic regression.
**[7:21]** F of x, which equals g of z,
**[7:23]** is now g of this expression over here.
**[7:26]** Let's say that we ended up choosing w_1 and w_2
**[7:30]** to be 1 and b to be negative 1.
**[7:35]** Z is equal to 1 times x_1
**[7:39]** squared plus 1 times x_2 squared minus 1.
**[7:43]** The decision boundary, as before,
**[7:46]** will correspond to when z is equal to 0.
**[7:50]** This expression will be equal to 0
**[7:53]** when x_1 squared plus x_2 squared is equal to 1.
**[7:57]** If you plot on the diagram on the left,
**[8:00]** the curve corresponding to
**[8:02]** x_1 squared plus x_2 squared equals 1,
**[8:05]** this turns out to be the circle.
**[8:08]** When x_1 squared plus x_2
**[8:10]** squared is greater than or equal to 1,
**[8:12]** that's this area outside
**[8:14]** the circle and that's when you predict y to be 1.
**[8:19]** Conversely, when x_1
**[8:21]** squared plus x_2 squared is less than 1,
**[8:24]** that's this area inside
**[8:26]** the circle and that's when you predict y to be 0.
**[8:31]** Can we come up with even more
**[8:33]** complex decision boundaries than these?
**[8:36]** Yes, you can. You can do so by
**[8:39]** having even higher-order polynomial terms.
**[8:42]** Say z is w_1,
**[8:44]** x_1 plus w_2,
**[8:45]** x_2 plus w_3,
**[8:47]** x_1 squared plus w_4,
**[8:49]** x_1, x_2 plus w_5, x_2 squared.
**[8:53]** Then it's possible you can get
**[8:55]** even more complex decision boundaries.
**[8:57]** The model can define decision boundaries,
**[9:00]** such as this example,
**[9:02]** an ellipse just like this,
**[9:04]** or with a different choice of the parameters.
**[9:08]** You can even get more complex decision boundaries,
**[9:12]** which can look like functions that maybe looks like that.
**[9:15]** So this is an example of
**[9:18]** an even more complex decision boundary
**[9:20]** than the ones we've seen previously.
**[9:23]** This implementation of logistic regression
**[9:26]** will predict y equals 1
**[9:28]** inside this shape and
**[9:31]** outside the shape will predict y equals 0.
**[9:34]** With these polynomial features,
**[9:37]** you can get very complex decision boundaries.
**[9:40]** In other words, logistic regression can learn to
**[9:42]** fit pretty complex data.
**[9:45]** Although if you were to not
**[9:47]** include any of these higher-order polynomials,
**[9:50]** so if the only features you use are x_1,
**[9:52]** x_2, x_3, and so on,
**[9:54]** then the decision boundary for
**[9:56]** logistic regression will always be linear,
**[9:59]** will always be a straight line.
**[10:01]** In the upcoming optional lab,
**[10:03]** you also get to see
**[10:04]** the code implementation of the decision boundary.
**[10:08]** In the example in the lab,
**[10:10]** there will be two features so you can see
**[10:12]** that decision boundary as a line.
**[10:15]** With this visualization,
**[10:17]** I hope that you now have a sense of the range of
**[10:19]** possible models you can get with logistic regression.
**[10:23]** Now that you've seen what f of
**[10:25]** x can potentially compute,
**[10:27]** let's take a look at how you can actually
**[10:29]** train a logistic regression model.
**[10:32]** We'll start by looking at
**[10:33]** the cost function for
**[10:34]** logistic regression and after that,
**[10:37]** figured out how to apply gradient descent to it.
**[10:39]** Let's go on to the next video.
