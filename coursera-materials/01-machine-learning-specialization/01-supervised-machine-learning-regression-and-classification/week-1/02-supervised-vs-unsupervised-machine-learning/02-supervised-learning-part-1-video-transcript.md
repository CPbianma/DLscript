---
type: video-transcript
specialization: Machine Learning Specialization
course: "Supervised Machine Learning: Regression and Classification"
week: 1
section: Supervised vs. Unsupervised Machine Learning
item_title: Supervised learning part 1
duration: 7 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/s91wX/supervised-learning-part-1
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Supervised learning part 1 — Transcript

**[0:01]** Machine learning is creating
**[0:03]** tremendous economic value today.
**[0:05]** I think 99 percent of the economic value
**[0:08]** created by machine learning today
**[0:09]** is through one type of machine learning,
**[0:11]** which is called supervised learning.
**[0:14]** Let's take a look at what that means.
**[0:16]** Supervised machine learning or
**[0:18]** more commonly, supervised learning,
**[0:21]** refers to algorithms that learn x to
**[0:24]** y or input to output mappings.
**[0:28]** The key characteristic of supervised learning is
**[0:31]** that you give
**[0:33]** your learning algorithm examples to learn from.
**[0:36]** That includes the right answers, whereby right answer,
**[0:40]** I mean, the correct label y for a given input x,
**[0:45]** and is by seeing correct pairs of
**[0:48]** input x and desired output label y that
**[0:52]** the learning algorithm eventually learns to
**[0:54]** take just the input alone without
**[0:57]** the output label and gives
**[0:58]** a reasonably accurate prediction or guess of the output.
**[1:03]** Let's look at some examples.
**[1:05]** If the input x is
**[1:08]** an email and the output y is this email,
**[1:11]** spam or not spam,
**[1:13]** this gives you your spam filter.
**[1:16]** Or if the input is an audio clip and
**[1:21]** the algorithm's job is output the text transcript,
**[1:25]** then this is speech recognition.
**[1:29]** Or if you want to input English and have
**[1:32]** it output to corresponding Spanish,
**[1:35]** Arabic, Hindi, Chinese, Japanese,
**[1:37]** or something else translation,
**[1:39]** then that's machine translation.
**[1:42]** Or the most lucrative form of supervised learning
**[1:46]** today is probably used in online advertising.
**[1:50]** Nearly all the large online ad platforms have
**[1:53]** a learning algorithm that inputs some information about
**[1:56]** an ad and some information about you
**[1:59]** and then tries to figure out
**[2:01]** if you will click on that ad or not.
**[2:04]** Because by showing you ads they're
**[2:05]** just slightly more likely to click on,
**[2:07]** for these large online ad platforms,
**[2:09]** every click is revenue,
**[2:11]** this actually drives a lot of
**[2:13]** revenue for these companies.
**[2:15]** This is something I once done a lot of work on,
**[2:18]** maybe not the most inspiring application,
**[2:20]** but it certainly has a significant economic impact
**[2:23]** in some countries today.
**[2:25]** Or if you want to build a self-driving car,
**[2:28]** the learning algorithm would take as input
**[2:31]** an image and some information from
**[2:33]** other sensors such as a radar or
**[2:35]** other things and then try to output the position of,
**[2:39]** say, other cars so that
**[2:41]** your self-driving car can
**[2:42]** safely drive around the other cars.
**[2:45]** Or take manufacturing.
**[2:47]** I've actually done a lot of work in
**[2:49]** this sector at learning AI.
**[2:51]** You can have a learning algorithm takes as
**[2:54]** input a picture of a manufactured product,
**[2:57]** say a cell phone that just rolled off the production line
**[3:01]** and have the learning algorithm output
**[3:03]** whether or not there is a scratch,
**[3:05]** dent, or other defect in the product.
**[3:08]** This is called visual inspection and it's helping
**[3:11]** manufacturers reduce or prevent
**[3:13]** defects in their products.
**[3:15]** In all of these applications,
**[3:17]** you will first train your model with examples of
**[3:20]** inputs x and the right answers,
**[3:23]** that is the labels y.
**[3:25]** After the model has learned from these input,
**[3:28]** output, or x and y pairs,
**[3:30]** they can then take a brand new input x,
**[3:33]** something it has never seen before,
**[3:34]** and try to produce the
**[3:36]** appropriate corresponding output y.
**[3:39]** Let's dive more deeply into one specific example.
**[3:44]** Say you want to predict
**[3:46]** housing prices based on the size of the house.
**[3:49]** You've collected some data and say
**[3:52]** you plot the data and it looks like this.
**[3:55]** Here on the horizontal axis
**[3:57]** is the size of the house in square feet.
**[3:59]** Yes, I live in the United States
**[4:01]** where we still use square feet.
**[4:03]** I know most of the world uses square meters.
**[4:06]** Here on the vertical axis is the price of the house in,
**[4:10]** say, thousands of dollars.
**[4:12]** With this data, let's say a friend wants to know what's
**[4:16]** the price for their 750 square foot house.
**[4:21]** How can the learning algorithm help you?
**[4:23]** One thing a learning algorithm
**[4:25]** might be able to do is say,
**[4:26]** for the straight line to
**[4:28]** the data and reading off the straight line,
**[4:31]** it looks like your friend's house could
**[4:33]** be sold for maybe about,
**[4:35]** I don't know, $150,000.
**[4:38]** But fitting a straight line isn't
**[4:40]** the only learning algorithm you can use.
**[4:42]** There are others that could work
**[4:44]** better for this application.
**[4:46]** For example, routed and fitting a straight line,
**[4:49]** you might decide that it's better to fit a curve,
**[4:52]** a function that's slightly more
**[4:54]** complicated or more complex than a straight line.
**[4:58]** If you do that and make a prediction here,
**[5:00]** then it looks like, well,
**[5:02]** your friend's house could be sold for closer to $200,000.
**[5:07]** One of the things you see later in this class
**[5:11]** is how you can decide whether to fit a straight line,
**[5:14]** a curve, or
**[5:15]** another function that is even more complex to the data.
**[5:20]** Now, it doesn't seem appropriate to pick
**[5:22]** the one that gives your friend the best price,
**[5:25]** but one thing you see is how to get
**[5:27]** an algorithm to systematically
**[5:30]** choose the most appropriate line or
**[5:32]** curve or other thing to fit to this data.
**[5:36]** What you've seen in this slide is
**[5:38]** an example of supervised learning.
**[5:41]** Because we gave the algorithm a dataset in
**[5:43]** which the so-called right answer,
**[5:45]** that is the label or
**[5:47]** the correct price y is given for every house on the plot.
**[5:52]** The task of the learning algorithm is to
**[5:54]** produce more of these right answers,
**[5:57]** specifically predicting what is
**[5:59]** the likely price for
**[6:00]** other houses like your friend's house.
**[6:03]** That's why this is supervised learning.
**[6:06]** To define a little bit more terminology,
**[6:08]** this housing price prediction is
**[6:10]** the particular type of supervised learning
**[6:12]** called regression.
**[6:14]** By regression, I mean we're trying
**[6:17]** to predict a number from
**[6:19]** infinitely many possible numbers
**[6:21]** such as the house prices in our example,
**[6:24]** which could be 150,000 or
**[6:28]** 70,000 or 183,000 or any other number in between.
**[6:33]** That's supervised learning, learning input,
**[6:37]** output, or x to y mappings.
**[6:39]** You saw in this video an example of
**[6:42]** regression where the task is to predict number.
**[6:45]** But there's also a second major type of
**[6:48]** supervised learning problem called classification.
**[6:52]** Let's take a look at what that means in the next video.
