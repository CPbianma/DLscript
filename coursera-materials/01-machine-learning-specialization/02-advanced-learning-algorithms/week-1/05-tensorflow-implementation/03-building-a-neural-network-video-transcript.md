---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 1
section: TensorFlow implementation
item_title: Building a neural network
duration: 8 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/J6Vli/building-a-neural-network
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# Building a neural network — Transcript

**[0:01]** So you've seen a bunch of tensor flow code by now learned about how to build a layer
**[0:05]** in tensor flow, how to do forward prop through a single layer in tensor flow.
**[0:10]** And also learned about data in TensorFlow.
**[0:13]** Let's put it all together and
**[0:15]** talk about how to build a neural network in TensorFlow.
**[0:19]** This is also the last video on tensor flow for this week.
**[0:22]** And in this video you also learn about a different way of building a neural
**[0:26]** network, that will be even a little bit simpler than what you've seen so far.
**[0:31]** So let's dive in what you saw previously was.
**[0:35]** If you want to do forward prop, you initialize the data X create layer
**[0:40]** one then compute a one, then create layer two and compute a two.
**[0:46]** So this was an explicit way of carrying out forward
**[0:50]** prop one layer of computation at the time.
**[0:55]** It turns out that tensor flow has a different way
**[0:59]** of implementing forward prop as well as learning.
**[1:04]** Let me show you a different way of building a neural network in TensorFlow,
**[1:09]** which is that same as before you're going to create layer one and create layer two.
**[1:15]** But now instead of you manually taking the data and passing it to layer one and
**[1:20]** then taking the activations from layer one and pass it to layer two.
**[1:25]** We can instead tell tensor flow that we would like it to take layer one and
**[1:30]** layer two and string them together to form a neural network.
**[1:35]** That's what the sequential function in TensorFlow does which is it says,
**[1:40]** Dear TensorFlow, please create a neural network for
**[1:44]** me by sequentially string together these two layers that I just created.
**[1:50]** It turns out that with the sequential framework tensor
**[1:54]** flow can do a lot of work for you.
**[1:57]** Let's say you have a training set like this on the left.
**[2:00]** This is for the coffee example.
**[2:02]** You can then take the training data as inputs X and
**[2:08]** put them into a numpy array.
**[2:10]** This here is a four by two matrix and the target labels.
**[2:16]** Y can then be written as follows.
**[2:21]** And this is just a one dimensional array of length four
**[2:26]** Y this set of targets can then be stored as a 1-D array like
**[2:31]** this 1001 corresponding to four train examples.
**[2:35]** And it turns out that given the data, X and
**[2:40]** Y stored in this matrix X and this array, Y.
**[2:45]** If you want to train this neural network, all you need to do is call to
**[2:50]** functions you need to call model dot compile with some parameters.
**[2:55]** We'll talk more about this next week, so don't worry about it for now.
**[2:59]** And then you need to call model dot fit X Y,
**[3:03]** which tells tensor flow to take this neural network that
**[3:08]** are created by sequentially string together layers one and
**[3:13]** two, and to train it on the data, X and Y.
**[3:17]** But we'll learn how but we'll learn the details of how to do this next week and
**[3:22]** then finally how do you do inference on this neural network?
**[3:25]** How do you do forward prop if you have a new example, say X new,
**[3:31]** which is NP array with these two features than to carry out forward
**[3:35]** prop instead of having to do it one layer at a time yourself,
**[3:40]** you just have to call model predict on X new and
**[3:45]** this will output the corresponding value of a two for
**[3:50]** you given this input value of X.
**[3:55]** So model predicts carries out forward propagation and carries an inference for
**[4:00]** you, using this neural network that you compiled using the sequential function.
**[4:05]** Now I want to take these three lines of code on top and
**[4:09]** just simplify it a little bit further, which is when coding in Tensorflow.
**[4:15]** By convention we don't explicitly assign the two layers to two variables,
**[4:21]** layer one and layer two as follows.
**[4:24]** But by convention I would usually just write a code like this,
**[4:28]** when we say the model is a sequential model of a few layers strung together.
**[4:32]** Sequentially where the first layer one is a dense layer with three units and
**[4:38]** activation of sigmoid and the second layer,
**[4:41]** is a dense layer with one unit and again a sigmoid activation function.
**[4:47]** So if you look at others tensor flow code,
**[4:50]** you often see it look more like this rather than having an explicit
**[4:55]** assignment to these layer one and layer two variables.
**[4:59]** And so that's it.
**[5:01]** This is pretty much the code you need in order to train as well as
**[5:06]** to inference on a neural network in TensorFlow.
**[5:10]** Where again we'll talk more about the training bits of this two
**[5:14]** combined the compiler and the fit function next week.
**[5:18]** Let's redo this for the digit classification example as well.
**[5:22]** So previously we had X, in this input layer one is a layer a one equals.
**[5:29]** They want to apply to X and so on through layer two and
**[5:33]** layer three in order to try to classify a digit,
**[5:36]** with this new coding convention with using tensor flow sequential function,
**[5:42]** you can instead specify what are layer one, layer two,
**[5:46]** layer three and tell tensor flow to string the layers together for
**[5:51]** you into a new network and same as before.
**[5:54]** You can then store the data in the matrix and
**[5:58]** run the compile function and fit the model as follows.
**[6:03]** Again, more on this next week.
**[6:06]** Finally to do inference or to make predictions you can use model predict on
**[6:11]** X new and similar to what you saw before with the coffee classification network
**[6:16]** by convention, instead of assigning layer one, layer two, layer three,
**[6:22]** explicitly like this, we would more commonly just take these layers and
**[6:27]** put them directly into the sequential function.
**[6:30]** So you end up with this more compact code which just tell tensor flow,
**[6:34]** create a model for me that sequentially strings together these three layers and
**[6:39]** then the rest of the code works the same as before.
**[6:42]** So that's how you have built a neural network in TensorFlow.
**[6:46]** Now I know that when you're learning about these techniques, sometimes someone may
**[6:50]** ask you to implement these five lines of code and then you type five lines of code
**[6:54]** and then someone says congratulations with just five lines of code.
**[6:58]** You built this crazy complicated state of the art neural network and sometimes that
**[7:02]** makes you wonder, what exactly did I do with just these five lines of codes?
**[7:07]** One thing I want you to take away from the machine learning specialization
**[7:11]** is the ability to use cutting edge libraries like tensor flow to do your work
**[7:15]** efficiently.
**[7:16]** But I don't really want you to just call five lines of code and
**[7:20]** not really also know what the code is actually doing underneath the hood.
**[7:25]** So in the next video I'll let you go back and
**[7:28]** share with you how you can implement from scratch by yourself.
**[7:32]** forward propagation in python, so that you can understand the whole thing for
**[7:36]** yourself in practice.
**[7:38]** Most machine learning engineers don't actually implement forward
**[7:42]** propagation in python that often we just use libraries like tensorflow and pytorch, but
**[7:47]** because I want you to understand how these algorithms work yourself so
**[7:51]** that if something goes wrong, you can think through for yourself,
**[7:55]** what you might need to change, what's likely to work, what's less likely to work.
**[7:59]** Let's also go through what it would take for you to implement for
**[8:03]** propagation from scratch because that way, even when you're calling a library and
**[8:08]** having it run efficiently and do great things in your application,
**[8:12]** I want you in the back of your mind to also have that deeper understanding of
**[8:17]** what your code is actually doing, so that let's go on to the next video.
