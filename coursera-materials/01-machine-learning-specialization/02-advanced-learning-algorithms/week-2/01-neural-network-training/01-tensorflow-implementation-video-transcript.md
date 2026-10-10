---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 2
section: Neural Network Training
item_title: TensorFlow implementation
duration: 4 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/oL0HT/tensorflow-implementation
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# TensorFlow implementation — Transcript

**[0:01]** Welcome back to the second week of
**[0:04]** this course on advanced learning algorithms.
**[0:06]** Last week you learned how to
**[0:08]** carry out inference in the neural network.
**[0:11]** This week, we're going to go
**[0:12]** over training of a neural network.
**[0:15]** I think being able to take your own data and
**[0:18]** train your own neural network on it is really fun.
**[0:21]** This week, we'll look at how you
**[0:23]** could do that. Let's dive in.
**[0:24]** Let's continue with our running example of
**[0:28]** handwritten digit recognition recognizing
**[0:31]** this image as zero or a one.
**[0:34]** Here we're using the neural network architecture
**[0:37]** that you saw last week,
**[0:38]** where you have an input X,
**[0:41]** that is the image,
**[0:43]** and then the first hidden layer was 25 units,
**[0:45]** second hidden layer with 15 units,
**[0:47]** and then one output unit.
**[0:50]** If you're given a training set of
**[0:52]** examples comprising images X,
**[0:55]** as was the ground truth label Y,
**[0:58]** how would you train the
**[0:59]** parameters of this neural network?
**[1:01]** Let me go ahead and show you the code that you
**[1:04]** can use in TensorFlow to train this network.
**[1:07]** Then in the next few videos after this,
**[1:09]** we'll dive into details to
**[1:10]** explain what the code is actually doing.
**[1:13]** This is a code you write.
**[1:15]** This first part may look familiar from
**[1:17]** the previous week where you are asking
**[1:20]** TensorFlow to sequentially string
**[1:22]** together these three layers of a neural network.
**[1:25]** The first hidden layer with
**[1:27]** 25 units and sigmoid activation,
**[1:30]** the second hidden layer,
**[1:31]** and then finally the output layer.
**[1:34]** Nothing new here relative to what you saw last week.
**[1:37]** Second step is you're to ask
**[1:39]** TensorFlow to compile the model.
**[1:42]** The key step in asking
**[1:44]** TensorFlow to compile the model is to
**[1:46]** specify what is the loss function you want to use.
**[1:49]** In this case we'll use something that goes by
**[1:52]** the binary crossentropy loss function
**[1:56]** We'll see more in the next video what this really is.
**[2:00]** Then having specified the loss function,
**[2:02]** the third step is to call the fit function,
**[2:06]** which tells TensorFlow to fit the model
**[2:08]** that you specified in step 1 using
**[2:11]** the loss of the cost function that you specified in step
**[2:13]** 2 to the dataset X, Y.
**[2:17]** Back in the first course when we
**[2:19]** talked about gradient descent,
**[2:21]** we had to decide how many steps to
**[2:23]** run gradient descent or how
**[2:24]** long to run gradient descent,
**[2:26]** so epochs is a technical term for how many steps of
**[2:29]** a learning algorithm like
**[2:31]** gradient descent you may want to run.
**[2:34]** That's it. Step 1 is to specify the model,
**[2:37]** which tells TensorFlow how to compute for the inference.
**[2:42]** Step 2 compiles the model
**[2:45]** using a specific loss function,
**[2:47]** and step 3 is to train the model.
**[2:50]** That's how you can train a neural network in TensorFlow.
**[2:53]** As usual, I hope that you people are not
**[2:56]** just call these lines of code to train the model,
**[2:59]** but that you also understand what's
**[3:01]** actually going on behind these lines of code,
**[3:04]** so you don't just call it without
**[3:06]** really understanding what's going on.
**[3:08]** I think this is important
**[3:10]** because when you're running a learning algorithm,
**[3:13]** if it doesn't work initially,
**[3:15]** having that conceptual mental framework
**[3:18]** of what's really going
**[3:19]** on will help you
**[3:20]** debug whenever things don't work the way you expect.
**[3:24]** With that, let's go on to
**[3:27]** the next video where we'll dive more deeply
**[3:29]** into what these steps in
**[3:31]** the TensorFlow implementation are actually doing.
**[3:34]** I'll see you in the next video.
