---
type: video-transcript
specialization: Machine Learning Specialization
course: Supervised Machine Learning: Regression and Classification
week: 1
section: Regression Model
item_title: Linear regression model part 1
duration: 10 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/1ACA2/linear-regression-model-part-1
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Linear regression model part 1 — Transcript

**[0:00]** In this video, we'll look at what
**[0:03]** the overall process of supervised learning is like.
**[0:07]** Specifically, you see the first model of
**[0:10]** this course, Linear Regression Model.
**[0:13]** That just means fitting a straight line to your data.
**[0:17]** It's probably the most
**[0:18]** widely used learning algorithm in the world today.
**[0:21]** As you get familiar with linear regression,
**[0:24]** many of the concepts you see here will also apply to
**[0:28]** other machine learning models that
**[0:30]** you'll see later in this specialization.
**[0:33]** Let's start with a problem that you can
**[0:35]** address using linear regression.
**[0:37]** Say you want to predict the price of
**[0:39]** a house based on the size of the house.
**[0:42]** This is the example we've seen earlier this week.
**[0:44]** We're going to use a dataset on
**[0:47]** house sizes and prices from Portland,
**[0:50]** a city in the United States.
**[0:52]** Here we have a graph where
**[0:53]** the horizontal axis is
**[0:55]** the size of the house in square feet,
**[0:57]** and the vertical axis is
**[0:59]** the price of a house in thousands of dollars.
**[1:03]** Let's go ahead and plot
**[1:04]** the data points for various houses in the dataset.
**[1:07]** Here each data point,
**[1:09]** each of these little crosses is a house with
**[1:12]** the size and the price that
**[1:14]** it most recently was sold for.
**[1:17]** Now, let's say you're a real estate agent in
**[1:19]** Portland and you're helping a client to sell her house.
**[1:23]** She is asking you, how
**[1:25]** much do you think I can get for this house?
**[1:27]** This dataset might help you
**[1:29]** estimate the price she could get for it.
**[1:31]** You start by measuring the size of the house,
**[1:34]** and it turns out that the house is 1250 square feet.
**[1:38]** How much do you think this house could sell for?
**[1:41]** One thing you could do this,
**[1:43]** you can build a linear
**[1:44]** regression model from this dataset.
**[1:47]** Your model will fit a straight line to the data,
**[1:50]** which might look like this.
**[1:52]** Based on this straight line fit to the data,
**[1:55]** you can see that the house is 1250 square feet,
**[2:00]** it will intersect the best fit line over here,
**[2:03]** and if you trace that to the vertical axis on the left,
**[2:07]** you can see the price is maybe around
**[2:09]** here, say about $220,000.
**[2:12]** This is an example of what's
**[2:15]** called a supervised learning model.
**[2:17]** We call this supervised learning
**[2:19]** because you are first training a model by giving
**[2:22]** a data that has right answers because you get
**[2:24]** the model examples of
**[2:26]** houses with both the size of the house,
**[2:28]** as well as the price that
**[2:29]** the model should predict for each house.
**[2:31]** Well, here are the prices, that is,
**[2:34]** the right answers are given
**[2:35]** for every house in the dataset.
**[2:38]** This linear regression model is
**[2:40]** a particular type of supervised learning model.
**[2:43]** It's called regression model because it predicts numbers
**[2:46]** as the output like prices in dollars.
**[2:49]** Any supervised learning model that predicts
**[2:51]** a number such as 220,000 or
**[2:55]** 1.5 or negative 33.2
**[2:59]** is addressing what's called a regression problem.
**[3:03]** Linear regression is one example of a regression model.
**[3:07]** But there are other models for
**[3:09]** addressing regression problems too.
**[3:12]** We'll see some of those later in
**[3:14]** Course 2 of this specialization.
**[3:17]** Just to remind you,
**[3:19]** in contrast with the regression model,
**[3:21]** the other most common type of
**[3:24]** supervised learning model is
**[3:25]** called a classification model.
**[3:28]** Classification model predicts
**[3:30]** categories or discrete categories,
**[3:33]** such as predicting if a picture is of a cat,
**[3:36]** meow or a dog,
**[3:38]** woof, or if given medical record,
**[3:41]** it has to predict if a patient has a particular disease.
**[3:44]** You'll see more about
**[3:46]** classification models later in this course as well.
**[3:49]** As a reminder about
**[3:51]** the difference between classification and regression,
**[3:54]** in classification, there are
**[3:55]** only a small number of possible outputs.
**[3:58]** If your model is recognizing cats versus dogs,
**[4:02]** that's two possible outputs.
**[4:05]** Or maybe you're trying to recognize any of
**[4:08]** 10 possible medical conditions in a patient,
**[4:12]** so there's a discrete,
**[4:13]** finite set of possible outputs.
**[4:16]** We call it classification
**[4:17]** problem, whereas in regression,
**[4:19]** there are infinitely many possible numbers
**[4:22]** that the model could output.
**[4:24]** In addition to visualizing
**[4:25]** this data as a plot here on the left,
**[4:28]** there's one other way of looking at
**[4:30]** the data that would be useful,
**[4:33]** and that's a data table here on the right.
**[4:38]** The data comprises a set of inputs.
**[4:41]** This would be the size of the house,
**[4:43]** which is this column here.
**[4:46]** It also has outputs.
**[4:48]** You're trying to predict the price,
**[4:51]** which is this column here.
**[4:54]** Notice that the horizontal and vertical axes
**[4:58]** correspond to these two columns,
**[5:00]** the size and the price.
**[5:04]** If you have, say, 47 rows in this data table,
**[5:11]** then there are 47 of
**[5:13]** these little crosses on the plot of the left,
**[5:16]** each cross corresponding to one row of the table.
**[5:22]** For example, the first row
**[5:25]** of the table is a house with size,
**[5:28]** 2,104 square feet,
**[5:30]** so that's around here,
**[5:34]** and this house is sold for $400,000 which is around here.
**[5:41]** This first row of the table is plotted
**[5:45]** as this data point over here.
**[5:48]** Now, let's look at
**[5:50]** some notation for describing the data.
**[5:53]** This is notation that you find
**[5:55]** useful throughout your journey in machine learning.
**[5:58]** As you increasingly get
**[6:00]** familiar with machine learning terminology,
**[6:02]** this would be terminology they can
**[6:04]** use to talk about machine learning concepts
**[6:07]** with others as well since a lot of
**[6:09]** this is quite standard across AI,
**[6:12]** you'll be seeing this notation
**[6:14]** multiple times in this specialization,
**[6:16]** so it's okay if you don't
**[6:18]** remember everything for assign through,
**[6:20]** it will naturally become more familiar overtime.
**[6:24]** The dataset that you just saw and that is
**[6:28]** used to train the model is called a training set.
**[6:32]** Note that your client's house is not in
**[6:35]** this dataset because it's not yet sold,
**[6:38]** so no one knows what the price is.
**[6:41]** To predict the price of your client's house,
**[6:43]** you first train your model to learn from
**[6:46]** the training set and that model can then
**[6:49]** predict your client's houses price.
**[6:53]** In Machine Learning, the standard notation to denote
**[6:56]** the input here is lowercase x,
**[7:00]** and we call this the input variable,
**[7:03]** is also called a feature or an input feature.
**[7:09]** For example, for the first house in your training set,
**[7:13]** x is the size of the house,
**[7:15]** so x equals 2,104.
**[7:19]** The standard notation to denote
**[7:22]** the output variable which you're trying to predict,
**[7:26]** which is also sometimes called the target
**[7:29]** variable, is lowercase y.
**[7:34]** Here, y is the price of the house,
**[7:39]** and for the first training example,
**[7:41]** this is equal to 400,
**[7:44]** so y equals 400.
**[7:48]** The dataset has one row for
**[7:50]** each house and in this training set,
**[7:54]** there are 47 rows with
**[7:58]** each row representing a different training example.
**[8:03]** We're going to use lowercase m to
**[8:06]** refer it to the total number of training examples,
**[8:09]** and so here m is equal to 47.
**[8:13]** To indicate the single training example,
**[8:16]** we're going to use the notation parentheses x, y.
**[8:22]** For the first training example, (x, y),
**[8:26]** this pair of numbers is (2104, 400).
**[8:33]** Now we have a lot of different training examples.
**[8:37]** We have 47 of them in fact.
**[8:39]** To refer to a specific training example,
**[8:42]** this will correspond to
**[8:44]** a specific row in this table on the left,
**[8:47]** I'm going to use the notation
**[8:49]** x superscript in parenthesis,
**[8:52]** i, y superscript in parentheses i.
**[8:57]** The superscript tells us that
**[9:00]** this is the ith training example,
**[9:02]** such as the first,
**[9:05]** second, or third up to the 47th training example.
**[9:08]** I here, refers to a specific row in the table.
**[9:15]** For instance, here is the first example,
**[9:20]** when i equals 1 in the training set,
**[9:25]** and so x superscript 1 is
**[9:29]** equal to 2,104 and y superscript
**[9:33]** 1 is equal to
**[9:34]** 400 and let's add this superscript 1 here as well.
**[9:41]** Just to note, this superscript i
**[9:44]** in parentheses is not exponentiation.
**[9:48]** When I write this,
**[9:50]** this is not x squared.
**[9:52]** This is not x to the power 2.
**[9:55]** It just refers to the second training example.
**[9:59]** This i, is just an index into
**[10:01]** the training set and refers to row i in the table.
**[10:06]** In this video, you saw what a training set is like,
**[10:09]** as well as a standard notation
**[10:11]** for describing this training set.
**[10:13]** In the next video,
**[10:14]** let's look at what rotate to take
**[10:16]** this training set that you just saw and feed it
**[10:18]** to learning algorithm so that
**[10:21]** the algorithm can learn from this data.
**[10:23]** Let's see that in the next video.
