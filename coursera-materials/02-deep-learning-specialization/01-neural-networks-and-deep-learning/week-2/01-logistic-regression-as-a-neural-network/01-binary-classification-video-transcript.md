---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 2
section: Logistic Regression as a Neural Network
item_title: Binary Classification
duration: 8 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/Z8j0R/binary-classification
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Binary Classification — Transcript

**[0:00]** Hello, and welcome back.
**[0:02]** In this week we're going to go over the basics of neural network programming.
**[0:08]** It turns out that when you implement a neural network there
**[0:11]** are some techniques that are going to be really important.
**[0:16]** For example, if you have a training set of m training examples,
**[0:21]** you might be used to processing the training set by having a four loop
**[0:25]** step through your m training examples.
**[0:28]** But it turns out that when you're implementing a neural network,
**[0:31]** you usually want to process your entire training set
**[0:34]** without using an explicit four loop to loop over your entire training set.
**[0:39]** So, you'll see how to do that in this week's materials.
**[0:42]** Another idea, when you organize the computation of a neural network,
**[0:47]** usually you have what's called a forward pass or forward propagation step,
**[0:51]** followed by a backward pass or what's called a backward propagation step.
**[0:56]** And so in this week's materials, you also get an introduction about why
**[1:00]** the computations in learning a neural network can be organized in this forward
**[1:04]** propagation and a separate backward propagation.
**[1:09]** For this week's materials I want to convey these ideas using
**[1:12]** logistic regression in order to make the ideas easier to understand.
**[1:16]** But even if you've seen logistic regression before, I think that there'll
**[1:19]** be some new and interesting ideas for you to pick up in this week's materials.
**[1:23]** So with that, let's get started.
**[1:25]** Logistic regression is an algorithm for binary classification.
**[1:30]** So let's start by setting up the problem.
**[1:33]** Here's an example of a binary classification problem.
**[1:36]** You might have an input of an image, like that, and
**[1:41]** want to output a label to recognize this image as either being a cat,
**[1:47]** in which case you output 1, or not-cat in which case you output 0,
**[1:52]** and we're going to use y to denote the output label.
**[1:57]** Let's look at how an image is represented in a computer.
**[2:01]** To store an image your computer stores three separate matrices
**[2:05]** corresponding to the red, green, and blue color channels of this image.
**[2:10]** So if your input image is 64 pixels by 64 pixels,
**[2:15]** then you would have 3 64 by 64 matrices
**[2:21]** corresponding to the red, green and blue pixel intensity values for your images.
**[2:27]** Although to make this little slide I drew these as much smaller matrices, so
**[2:31]** these are actually 5 by 4 matrices rather than 64 by 64.
**[2:35]** So to turn these pixel intensity values- Into a feature vector, what we're
**[2:41]** going to do is unroll all of these pixel values into an input feature vector x.
**[2:48]** So to unroll all these pixel intensity values into a feature vector, what we're
**[2:53]** going to do is define a feature vector x corresponding to this image as follows.
**[2:59]** We're just going to take all the pixel values 255, 231, and so on.
**[3:03]** 255, 231, and so on until we've listed all the red pixels.
**[3:10]** And then eventually 255 134 255, 134 and so
**[3:15]** on until we get a long feature vector listing out all the red,
**[3:20]** green and blue pixel intensity values of this image.
**[3:25]** If this image is a 64 by 64 image, the total dimension
**[3:31]** of this vector x will be 64 by 64 by 3 because that's
**[3:36]** the total numbers we have in all of these matrixes.
**[3:41]** Which in this case, turns out to be 12,288,
**[3:44]** that's what you get if you multiply all those numbers.
**[3:47]** And so we're going to use nx=12288
**[3:51]** to represent the dimension of the input features x.
**[3:55]** And sometimes for brevity, I will also just use lowercase n
**[3:59]** to represent the dimension of this input feature vector.
**[4:02]** So in binary classification, our goal is to learn a classifier that can input
**[4:07]** an image represented by this feature vector x.
**[4:10]** And predict whether the corresponding label y is 1 or 0,
**[4:15]** that is, whether this is a cat image or a non-cat image.
**[4:19]** Let's now lay out some of the notation that we'll
**[4:21]** use throughout the rest of this course.
**[4:23]** A single training example is represented by a pair,
**[4:29]** (x,y) where x is an x-dimensional feature
**[4:34]** vector and y, the label, is either 0 or 1.
**[4:39]** Your training sets will comprise lower-case m training examples.
**[4:44]** And so your training sets will be written (x1, y1) which is the input and
**[4:50]** output for your first training example (x(2), y(2)) for
**[4:55]** the second training example up to (xm, ym) which is your last training example.
**[5:01]** And then that altogether is your entire training set.
**[5:05]** So I'm going to use lowercase m to denote the number of training samples.
**[5:10]** And sometimes to emphasize that this is the number of train examples,
**[5:14]** I might write this as M = M train.
**[5:16]** And when we talk about a test set,
**[5:18]** we might sometimes use m subscript test to denote the number of test examples.
**[5:24]** So that's the number of test examples.
**[5:27]** Finally, to output all of the training examples into a more compact notation,
**[5:33]** we're going to define a matrix, capital X.
**[5:36]** As defined by taking you training set inputs x1, x2 and
**[5:41]** so on and stacking them in columns.
**[5:44]** So we take X1 and put that as a first column of this matrix,
**[5:49]** X2, put that as a second column and so on down to Xm,
**[5:54]** then this is the matrix capital X.
**[5:58]** So this matrix X will have M columns, where M is the number of train
**[6:03]** examples and the number of railroads, or the height of this matrix is NX.
**[6:08]** Notice that in other causes, you might see the matrix capital
**[6:14]** X defined by stacking up the train examples in rows like so,
**[6:19]** X1 transpose down to Xm transpose.
**[6:23]** It turns out that when you're implementing neural networks using
**[6:27]** this convention I have on the left, will make the implementation much easier.
**[6:32]** So just to recap, x is a nx by m dimensional matrix, and
**[6:37]** when you implement this in Python,
**[6:40]** you see that x.shape, that's the python command for
**[6:45]** finding the shape of the matrix, that this an nx, m.
**[6:50]** That just means it is an nx by m dimensional matrix.
**[6:53]** So that's how you group the training examples, input x into matrix.
**[6:58]** How about the output labels Y?
**[7:01]** It turns out that to make your implementation of a neural network easier,
**[7:04]** it would be convenient to also stack Y In columns.
**[7:10]** So we're going to define capital Y to be equal to Y 1, Y 2,
**[7:14]** up to Y m like so.
**[7:18]** So Y here will be a 1 by m dimensional matrix.
**[7:24]** And again, to use the notation without the shape of Y will be 1, m.
**[7:30]** Which just means this is a 1 by m matrix.
**[7:34]** And as you implement your neural network later in this course you'll find that a useful
**[7:39]** convention would be to take the data associated with different training
**[7:43]** examples, and by data I mean either x or y, or other quantities you see later.
**[7:48]** But to take the stuff or
**[7:49]** the data associated with different training examples and
**[7:52]** to stack them in different columns, like we've done here for both x and y.
**[7:58]** So, that's a notation we'll use for a logistic regression and for
**[8:01]** neural networks networks later in this course.
**[8:04]** If you ever forget what a piece of notation means, like what is M or
**[8:07]** what is N or
**[8:08]** what is something else, we've also posted on the course website a notation guide
**[8:12]** that you can use to quickly look up what any particular piece of notation means.
**[8:17]** So with that, let's go on to the next video where we'll start to fetch out
**[8:20]** logistic regression using this notation.
