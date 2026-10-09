---
type: video-transcript
specialization: Machine Learning Specialization
course: Supervised Machine Learning: Regression and Classification
week: 1
section: Regression Model
item_title: Linear regression model part 2
duration: 7 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/nucNi/linear-regression-model-part-2
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Linear regression model part 2 — Transcript

**[0:00]** Let's look in this video at
**[0:03]** the process of how supervised learning works.
**[0:06]** Supervised learning algorithm will input a dataset and
**[0:09]** then what exactly does it do and what does it output?
**[0:12]** Let's find out in this video.
**[0:14]** Recall that a training set in
**[0:17]** supervised learning includes both the input features,
**[0:20]** such as the size of the house and
**[0:21]** also the output targets,
**[0:24]** such as the price of the house.
**[0:25]** The output targets are
**[0:27]** the right answers to the model we'll learn from.
**[0:30]** To train the model,
**[0:32]** you feed the training set,
**[0:33]** both the input features and
**[0:35]** the output targets to your learning algorithm.
**[0:39]** Then your supervised learning algorithm
**[0:42]** will produce some function.
**[0:44]** We'll write this function as lowercase f,
**[0:47]** where f stands for function.
**[0:49]** Historically, this function used to
**[0:52]** be called a hypothesis,
**[0:54]** but I'm just going to call it a function f in this class.
**[0:58]** The job with f is to take a new input
**[1:02]** x and output and estimate or a prediction,
**[1:08]** which I'm going to call y-hat,
**[1:11]** and it's written like
**[1:13]** the variable y with this little hat symbol on top.
**[1:17]** In machine learning, the convention is that
**[1:21]** y-hat is the estimate or the prediction for y.
**[1:26]** The function f is called the model.
**[1:31]** X is called the input or the input feature,
**[1:35]** and the output of the model is the prediction, y-hat.
**[1:40]** The model's prediction is the estimated value of y.
**[1:45]** When the symbol is just the letter y,
**[1:48]** then that refers to the target,
**[1:51]** which is the actual true value in the training set.
**[1:55]** In contrast, y-hat is an estimate.
**[1:58]** It may or may not be the actual true value.
**[2:01]** Well, if you're helping your client
**[2:03]** to sell the house, well,
**[2:05]** the true price of the house
**[2:06]** is unknown until they sell it.
**[2:08]** Your model f, given the size,
**[2:11]** outputs the price which is the estimator,
**[2:14]** that is the prediction of what the true price will be.
**[2:18]** Now, when we design a learning algorithm,
**[2:22]** a key question is,
**[2:24]** how are we going to represent the function f?
**[2:27]** Or in other words,
**[2:29]** what is the math formula we're going to use to compute f?
**[2:34]** For now, let's stick with f being a straight line.
**[2:39]** You're function can be written as f_w,
**[2:43]** b of x equals,
**[2:47]** I'm going to use w times x plus
**[2:50]** b. I'll define w and b soon.
**[2:54]** But for now, just know that w and b are numbers,
**[2:58]** and the values chosen for w and b will determine
**[3:02]** the prediction y-hat based on the input feature x.
**[3:08]** This f_w b of x
**[3:11]** means f is a function that takes x as input,
**[3:15]** and depending on the values of w and b,
**[3:18]** f will output some value of a prediction y-hat.
**[3:23]** As an alternative to writing this,
**[3:26]** f_w, b of x,
**[3:29]** I'll sometimes just write f of x without
**[3:32]** explicitly including w and b into subscript.
**[3:35]** Is just a simpler notation that means
**[3:38]** exactly the same thing as f_w b of x.
**[3:42]** Let's plot the training set on
**[3:44]** the graph where the input feature x is on
**[3:47]** the horizontal axis and
**[3:49]** the output target y is on the vertical axis.
**[3:53]** Remember, the algorithm learns from this data and
**[3:57]** generates the best-fit line like maybe this one here.
**[4:01]** This straight line is the linear function
**[4:05]** f_w b of x equals w times x plus b.
**[4:11]** Or more simply, we can drop w and b and just
**[4:16]** write f of x equals wx plus b.
**[4:20]** Here's what this function is doing,
**[4:22]** it's making predictions for the value of
**[4:24]** y using a streamline function of x.
**[4:28]** You may ask, why are we choosing a linear function,
**[4:32]** where linear function is just a fancy term for
**[4:35]** a straight line instead of
**[4:36]** some non-linear function like a curve or a parabola?
**[4:40]** Well, sometimes you want to fit
**[4:42]** more complex non-linear functions as well,
**[4:45]** like a curve like this.
**[4:47]** But since this linear function is
**[4:49]** relatively simple and easy to work with,
**[4:51]** let's use a line as
**[4:53]** a foundation that will eventually help
**[4:55]** you to get to more complex models that are non-linear.
**[4:59]** This particular model has a name,
**[5:02]** it's called linear regression.
**[5:04]** More specifically, this is
**[5:06]** linear regression with one variable,
**[5:08]** where the phrase one variable means that there's
**[5:11]** a single input variable or feature x,
**[5:14]** namely the size of the house.
**[5:16]** Another name for a linear model with
**[5:19]** one input variable is univariate linear regression,
**[5:23]** where uni means one in Latin,
**[5:26]** and where variate means variable.
**[5:29]** Univariate is just a fancy way of saying one variable.
**[5:34]** In a later video,
**[5:35]** you'll also see a variation of regression where you'll
**[5:39]** want to make a prediction based not
**[5:40]** just on the size of a house,
**[5:42]** but on a bunch of other things that you may know
**[5:45]** about the house such as number of
**[5:46]** bedrooms and other features.
**[5:48]** By the way, when you're done with this video,
**[5:51]** there is another optional lab.
**[5:53]** You don't need to write any code.
**[5:55]** Just review it, run the code and see what it does.
**[5:58]** That will show you how to define in
**[6:00]** Python a straight line function.
**[6:03]** The lab will let you choose the values of
**[6:06]** w and b to try to fit the training data.
**[6:09]** You don't have to do the lab if you don't want to,
**[6:12]** but I hope you play with it when you're
**[6:14]** done watching this video.
**[6:16]** That's linear regression.
**[6:18]** In order for you to make this work,
**[6:20]** one of the most important things you have to do
**[6:22]** is construct a cost function.
**[6:24]** The idea of a cost function is one of
**[6:26]** the most universal and important ideas
**[6:29]** in machine learning,
**[6:31]** and is used in both linear regression and in
**[6:34]** training many of the most
**[6:35]** advanced AI models in the world.
**[6:37]** Let's go on to the next video and take a look
**[6:40]** at how you can construct a cost function.
