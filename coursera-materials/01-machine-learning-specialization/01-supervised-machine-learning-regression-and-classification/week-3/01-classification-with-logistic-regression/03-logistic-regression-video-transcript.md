---
type: video-transcript
specialization: Machine Learning Specialization
course: "Supervised Machine Learning: Regression and Classification"
week: 3
section: Classification with logistic regression
item_title: Logistic regression
duration: 10 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/zNxaw/logistic-regression
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Logistic regression — Transcript

**[0:00]** Let's talk about logistic regression,
**[0:02]** which is probably the single most
**[0:04]** widely used classification algorithm in the world.
**[0:07]** This is something that I use all the time in my work.
**[0:10]** Let's continue with the example of
**[0:12]** classifying whether a tumor is malignant.
**[0:15]** Whereas before we're going to use the label 1 or
**[0:19]** yes to the positive class to represent malignant tumors,
**[0:22]** and zero or no and negative examples
**[0:25]** to represent benign tumors.
**[0:27]** Here's a graph of the dataset where
**[0:29]** the horizontal axis is
**[0:31]** the tumor size and
**[0:33]** the vertical axis takes on only values of 0 and 1,
**[0:37]** because is a classification problem.
**[0:40]** You saw in the last video that
**[0:42]** linear regression is not
**[0:43]** a good algorithm for this problem.
**[0:45]** In contrast, what logistic regression we end
**[0:50]** up doing is fit a curve that looks like this,
**[0:54]** S-shaped curve to this dataset.
**[0:58]** For this example, if a patient
**[1:01]** comes in with a tumor of this size,
**[1:04]** which I'm showing on the x-axis,
**[1:07]** then the algorithm will output 0.7
**[1:11]** suggesting that is closer or maybe more
**[1:13]** likely to be malignant and benign.
**[1:16]** Will say more later what
**[1:18]** 0.7 actually means in this context.
**[1:22]** But the output label y is never 0.7 is only ever 0 or 1.
**[1:28]** To build out to the logistic regression algorithm,
**[1:32]** there's an important mathematical function I like to
**[1:34]** describe which is called the Sigmoid function,
**[1:38]** sometimes also referred to as the logistic function.
**[1:42]** The Sigmoid function looks like this.
**[1:46]** Notice that the x-axis of
**[1:48]** the graph on the left and right are different.
**[1:51]** In the graph to the left on the x-axis is the tumor size,
**[1:56]** so is all positive numbers.
**[1:58]** Whereas in the graph on the right,
**[2:00]** you have 0 down here,
**[2:02]** and the horizontal axis takes
**[2:06]** on both negative and positive values and have
**[2:09]** label the horizontal axis Z. I'm showing
**[2:13]** here just a range of negative 3 to plus 3.
**[2:17]** So the Sigmoid function outputs value is between 0 and 1.
**[2:22]** If I use g of z to denote this function,
**[2:26]** then the formula of g of z is equal
**[2:29]** to 1 over 1 plus e to the negative z.
**[2:33]** Where here e is a mathematical
**[2:36]** constant that takes on a value of about 2.7,
**[2:40]** and so e to the negative z is that
**[2:42]** mathematical constant to the power of negative z.
**[2:46]** Notice if z where really be, say a 100,
**[2:50]** e to the negative z is e to the
**[2:53]** negative 100 which is a tiny number.
**[2:57]** So this ends up being 1
**[3:00]** over 1 plus a tiny little number,
**[3:03]** and so the denominator will be basically very close to 1.
**[3:08]** Which is why when z is large,
**[3:11]** g of z that is a Sigmoid function
**[3:14]** of z is going to be very close to 1.
**[3:17]** Conversely, you can also check for yourself
**[3:21]** that when z is a very large negative number,
**[3:25]** then g of z becomes 1 over a giant number,
**[3:30]** which is why g of z is very close to 0.
**[3:35]** That's why the sigmoid function has
**[3:37]** this shape where it starts very close to
**[3:40]** zero and slowly builds up or grows to the value of one.
**[3:46]** Also, in the Sigmoid function when z is equal to 0,
**[3:51]** then e to the negative z is
**[3:54]** e to the negative 0 which is equal to 1,
**[3:57]** and so g of z is equal to 1 over 1 plus 1 which is 0.5,
**[4:05]** so that's why it passes the vertical axis at 0.5.
**[4:10]** Now, let's use this to build up
**[4:13]** to the logistic regression algorithm.
**[4:15]** We're going to do this in two steps.
**[4:18]** In the first step, I hope you
**[4:20]** remember that a straight line function,
**[4:23]** like a linear regression function can be defined
**[4:26]** as w. product of x plus b.
**[4:31]** Let's store this value in
**[4:34]** a variable which I'm going to call z,
**[4:37]** and this will turn out to be the same z
**[4:39]** as the one you saw on the previous slide,
**[4:41]** but we'll get to that in a minute.
**[4:43]** The next step then is to take this value of
**[4:47]** z and pass it to the Sigmoid function,
**[4:51]** also called the logistic function,
**[4:53]** g. Now, g of
**[4:56]** z then outputs a value computed by this formula,
**[5:02]** 1 over 1 plus e to the negative z.
**[5:04]** There's going to be between 0 and 1.
**[5:07]** When you take these two equations and put them together,
**[5:12]** they then give you the logistic regression model f of x,
**[5:17]** which is equal to g of wx plus b.
**[5:23]** Or equivalently g of z,
**[5:27]** which is equal to this formula over here.
**[5:32]** This is the logistic regression model,
**[5:36]** and what it does is it inputs feature or set
**[5:40]** of features X and outputs a number between 0 and 1.
**[5:44]** Next, let's take a look at how to
**[5:47]** interpret the output of logistic regression.
**[5:50]** We'll return to the tumor classification example.
**[5:54]** The way I encourage you to think of
**[5:57]** logistic regressions output is to think
**[6:00]** of it as outputting
**[6:01]** the probability that the class or the label
**[6:04]** y will be equal to 1 given a certain input x.
**[6:10]** For example, in this application,
**[6:14]** where x is the tumor size and y is either 0 or 1,
**[6:18]** if you have a patient come in
**[6:20]** and she has a tumor of a certain size x,
**[6:23]** and if based on this input x,
**[6:26]** the model I'll plus 0.7,
**[6:29]** then what that means is that the model is
**[6:32]** predicting or the model thinks there's
**[6:35]** a 70 percent chance that the true label
**[6:37]** y would be equal to 1 for this patient.
**[6:40]** In other words, the model is telling
**[6:43]** us that it thinks the patient has
**[6:45]** a 70 percent chance of
**[6:47]** the tumor turning out to be malignant.
**[6:50]** Now, let me ask you a question.
**[6:53]** See if you can get this right.
**[6:56]** We know that y has to be either 0 or 1,
**[7:00]** so if y has a 70 percent chance of being 1,
**[7:04]** what is the chance that it is 0?
**[7:07]** So y has got to be either 0 or 1,
**[7:11]** and thus the probability of it being
**[7:13]** 0 or 1 these two numbers
**[7:16]** have to add up to one or to a 100 percent chance.
**[7:20]** That's why if the chance of y being
**[7:22]** 1 is 0.7 or 70 percent chance,
**[7:25]** then the chance of it being 0 has got to
**[7:28]** be 0.3 or 30 percent chance.
**[7:31]** If someday you read
**[7:33]** research papers or blog pulls
**[7:35]** of all logistic regression,
**[7:37]** sometimes you see this notation that f
**[7:40]** of x is equal to p of
**[7:43]** y equals 1 given
**[7:46]** the input features x and with parameters w and b.
**[7:50]** What the semicolon here is used to
**[7:53]** denote is just that w and b are
**[7:56]** parameters that affect this computation of what is
**[8:00]** the probability of y being equal to 1
**[8:02]** given the input feature x?
**[8:05]** For the purpose of this class,
**[8:07]** don't worry too much about what
**[8:08]** this vertical line and what the semicolon mean.
**[8:11]** You don't need to remember or
**[8:14]** follow any of this mathematical notation for this class.
**[8:16]** I'm mentioning this only
**[8:18]** because you may see this in other places.
**[8:20]** In the optional lab that follows this video,
**[8:23]** you also get to see how
**[8:24]** the Sigmoid function is implemented in code.
**[8:28]** You can see a plot that uses
**[8:30]** the Sigmoid function so as to do
**[8:32]** better on the classification tasks
**[8:34]** that you saw in the previous optional lab.
**[8:36]** Remember that the code will be provided to you,
**[8:39]** so you just have to run it.
**[8:41]** I hope you take a look and get familiar with the code.
**[8:45]** Congrats on getting here.
**[8:47]** You now know what is the logistic regression model
**[8:51]** as well as the mathematical formula
**[8:53]** that defines logistic regression.
**[8:55]** For a long time,
**[8:57]** a lot of Internet advertising was actually driven
**[9:00]** by basically a slight variation of logistic regression.
**[9:04]** This was very lucrative for some large companies,
**[9:07]** and this is basically the algorithm
**[9:08]** that decided what ad was
**[9:10]** shown to you and many others on some large websites.
**[9:13]** Now, there's, even more,
**[9:15]** to learn about this algorithm.
**[9:17]** In the next video,
**[9:18]** we'll take a look at the details of logistic regression.
**[9:22]** We'll look at some visualizations and also
**[9:24]** examines something called the decision boundary.
**[9:28]** This will give you a few different ways to
**[9:30]** map the numbers that this model outputs,
**[9:33]** such as 0.3, or 0.7,
**[9:36]** or 0.65 to a prediction of whether y is actually 0 or 1.
**[9:42]** Let's go on to the next video to learn
**[9:44]** more about logistic regression.
