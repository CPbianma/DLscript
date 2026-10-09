---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 2
section: Neural Network Training
item_title: Training Details
duration: 13 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/35RQ3/training-details
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# Training Details — Transcript

**[0:01]** Let's take a look at the details
**[0:03]** of what the TensorFlow code for
**[0:05]** training a neural network is
**[0:07]** actually doing. Let's dive in.
**[0:09]** Before looking at the details
**[0:11]** of training in neural network,
**[0:12]** let's recall how you had trained
**[0:14]** a logistic regression model in the previous course.
**[0:19]** Step 1 of building
**[0:20]** a logistic regression model was you would
**[0:23]** specify how to compute the output
**[0:26]** given the input feature x and the parameters w and b.
**[0:31]** In the first course we said
**[0:33]** the logistic regression function
**[0:35]** predicts f of x is equal to G.
**[0:38]** The sigmoid function applied to W. product X plus B
**[0:42]** which was the sigmoid function applied to W.X plus B.
**[0:46]** If Z is the dot product of W of X plus B,
**[0:53]** then F of X is 1 over 1 plus e to the negative z,
**[0:59]** so those first step were to specify what is the input
**[1:03]** to output function of logistic regression,
**[1:07]** and that depends on both the input x
**[1:09]** and the parameters of the model.
**[1:11]** The second step we had to do to train
**[1:15]** the literacy regression model was to
**[1:17]** specify the loss function and also the cost function,
**[1:20]** so you may recall that the loss function said,
**[1:25]** if religious regression opus f
**[1:28]** of x and the ground truth label,
**[1:31]** the actual label and a training set was
**[1:33]** y then the loss on that single training example
**[1:37]** was negative y log f of x minus
**[1:40]** one minus y times log of one minus f of x.
**[1:44]** This was a measure of how well is logistic regression
**[1:48]** doing on a single training example x comma y.
**[1:53]** Given this definition of a loss function,
**[1:57]** we then define the cost function,
**[2:00]** and the cost function was a function of
**[2:03]** the parameters W and B,
**[2:05]** and that was just the average that is taking
**[2:08]** an average overall M training examples of
**[2:11]** the loss function computed on
**[2:13]** the M training examples, X1,
**[2:15]** Y1 through XMYM,
**[2:18]** and remember that in the convention we're
**[2:23]** using the loss function is a function of the output
**[2:27]** of the learning algorithm and the ground truth label as
**[2:30]** computed over a single training example
**[2:33]** whereas the cost function J is
**[2:36]** an average of the loss function
**[2:38]** computed over your entire training set.
**[2:40]** That was step two of what we did
**[2:43]** when building up logistic regression.
**[2:45]** Then the third and final step to train
**[2:49]** a logistic regression model was to use an algorithm
**[2:53]** specifically gradient descent to
**[2:55]** minimize that cost function J of
**[2:57]** WB to minimize it
**[3:00]** as a function of the parameters W and B.
**[3:03]** We minimize the cost J as a function of
**[3:06]** the parameters using gradient descent where W is
**[3:09]** updated as W minus the learning rate
**[3:12]** alpha times the derivative of J with respect to
**[3:16]** W. And B similarly is updated as
**[3:22]** B minus the learning rate alpha
**[3:24]** times the derivative of J with respect to B.
**[3:28]** If these three steps.
**[3:30]** Step one, specifying how to compute
**[3:32]** the outputs given the input X and parameters,
**[3:34]** step 2 specify loss and costs,
**[3:36]** and step three minimize
**[3:37]** the cost function we trained logistic regression.
**[3:40]** The same three steps is how we can
**[3:43]** train a neural network in TensorFlow.
**[3:47]** Now let's look at how these three steps
**[3:49]** map to training a neural network.
**[3:52]** We'll go over this in greater detail
**[3:55]** on the next three slides but really briefly.
**[3:58]** Step one is specify how to
**[3:59]** compute the output given the input x and
**[4:01]** parameters W and B that's done with
**[4:04]** this code snippet which should be familiar from
**[4:07]** last week of specifying
**[4:09]** the neural network and this was actually enough to
**[4:11]** specify the computations needed in
**[4:14]** forward propagation or for
**[4:15]** the inference algorithm for example.
**[4:17]** The second step is to compile
**[4:19]** the model and to tell it what loss you want to use,
**[4:23]** and here's the code that you use to specify
**[4:25]** this loss function which is
**[4:27]** the binary cross entropy loss function,
**[4:32]** and once you specify this loss taking an average over
**[4:36]** the entire training set also gives
**[4:38]** you the cost function for the neural network,
**[4:40]** and then step three is to call function to try to
**[4:43]** minimize the cost as
**[4:45]** a function of the parameters of the neural network.
**[4:48]** Let's look in greater detail in
**[4:50]** these three steps in
**[4:51]** the context of training a neural network.
**[4:54]** The first step, specify how to compute
**[4:57]** the output given the input x and parameters w and b.
**[5:00]** This code snippet specifies
**[5:02]** the entire architecture of the neural network.
**[5:04]** It tells you that there are
**[5:06]** 25 hidden units in the first hidden layer,
**[5:09]** then the 15 in the next one,
**[5:10]** and then one output unit and
**[5:12]** that we're using the sigmoid activation value.
**[5:15]** Based on this code snippet,
**[5:16]** we know also what are the parameters w1,
**[5:19]** v1 though the first layer parameters of
**[5:21]** the second layer and parameters of the third layer.
**[5:24]** This code snippet specifies
**[5:26]** the entire architecture of
**[5:28]** the neural network and therefore
**[5:30]** tells TensorFlow everything it needs in
**[5:32]** In order to compute the output a 3 or f
**[5:36]** of x as a function of the input x and the parameters,
**[5:40]** here we have written w l and b l. Let's go on to step 2.
**[5:47]** In the second step,
**[5:48]** you have to specify what is the loss function.
**[5:51]** That will also define
**[5:52]** the cost function we use to train the neural network.
**[5:56]** For the handwritten digit classification
**[5:59]** problem where images are either of a zero or a one
**[6:03]** the most common by far,
**[6:07]** loss function to use is this one is actually
**[6:09]** the same loss function as what we had for
**[6:12]** logistic regression is negative y log f of
**[6:15]** x minus 1 minus y times log 1 minus f of x,
**[6:20]** where y is the ground truth label,
**[6:22]** sometimes also called the target label y,
**[6:25]** and f of x is now the output of the neural network.
**[6:29]** In TensorFlow, this is called the
**[6:31]** binary cross-entropy loss function.
**[6:35]** Where does that name come from?
**[6:36]** Well, it turns out in statistics this function on
**[6:39]** top is called the cross-entropy loss function,
**[6:42]** so that's what cross-entropy means,
**[6:44]** and the word binary just
**[6:46]** reemphasizes or points out that this
**[6:49]** is a binary classification problem because
**[6:51]** each image is either a zero or a one.
**[6:54]** The syntax is to ask TensorFlow to
**[6:57]** compile the neural network using this loss function.
**[7:01]** Another historical note,
**[7:03]** carers was originally a library that
**[7:06]** had developed independently of
**[7:07]** TensorFlow is actually
**[7:08]** totally separate project from TensorFlow.
**[7:11]** But eventually it got merged into TensorFlow,
**[7:13]** which is why we have tf.Keras
**[7:15]** library.losses dot the name of this loss function.
**[7:20]** By the way, I don't always remember
**[7:23]** the names of all the loss functions and TensorFlow,
**[7:25]** but I just do a quick web search myself to
**[7:28]** find the right name and then I plug that into my code.
**[7:31]** Having specified the loss with
**[7:33]** respect to a single training example,
**[7:36]** TensorFlow knows that it costs you want
**[7:38]** to minimize is then the average,
**[7:41]** taking the average over
**[7:42]** all m training examples of
**[7:44]** the loss on all of the training examples.
**[7:46]** Optimizing this cost function will result in
**[7:50]** fitting the neural network to
**[7:52]** your binary classification data.
**[7:54]** In case you want to solve
**[7:56]** a regression problem rather
**[7:59]** than a classification problem.
**[8:01]** You can also tell TensorFlow to compile
**[8:04]** your model using a different loss function.
**[8:07]** For example, if you have
**[8:10]** a regression problem and if
**[8:13]** you want to minimize the squared error loss.
**[8:16]** Here is the squared error loss.
**[8:17]** The loss with respect
**[8:19]** to if your learning algorithm outputs
**[8:21]** f of x with a target or ground truth label of y,
**[8:24]** that's 1/2 of the squared error.
**[8:27]** Then you can use this loss function in TensorFlow,
**[8:31]** which is to use
**[8:32]** the maybe more intuitively named mean
**[8:35]** squared error loss function.
**[8:37]** Then TensorFlow will try to
**[8:38]** minimize the mean squared error.
**[8:40]** In this expression, I'm using j of capital w
**[8:44]** comma capital b to denote the cost function.
**[8:47]** The cost function is a function
**[8:50]** of all the parameters into neural network.
**[8:53]** You can think of capital W as including W1, W2, W3.
**[9:01]** All the W parameters and the entire new network and be
**[9:04]** as including b1, b2, and b3.
**[9:09]** If you are optimizing
**[9:12]** the cost function respect to w and b,
**[9:15]** if we tried to optimize it with respect
**[9:17]** to all of the parameters in the neural network.
**[9:20]** Up on top as well,
**[9:22]** I had written f of x as the output of the neural network,
**[9:26]** but we can also write f of
**[9:28]** w b if we want to emphasize that
**[9:31]** the output of the neural network
**[9:32]** as a function of x depends
**[9:34]** on all the parameters in
**[9:35]** all the layers of the neural network.
**[9:37]** That's the loss function and the cost function.
**[9:40]** Finally, you will ask
**[9:43]** TensorFlow to minimize the cross-function.
**[9:46]** You might remember the gradient descent algorithm
**[9:50]** from the first course.
**[9:51]** If you're using gradient descent to
**[9:54]** train the parameters of a neural network,
**[9:56]** then you are repeatedly,
**[9:57]** for every layer l and for every unit j,
**[10:02]** update wlj according to wlj
**[10:06]** minus the learning rate
**[10:07]** alpha times the partial derivative
**[10:10]** with respect to that parameter of the cost function j
**[10:15]** of wb and similarly for the parameters b as well.
**[10:20]** After doing, say,
**[10:23]** 100 iterations of gradient descent, hopefully,
**[10:26]** you get to a good value of the parameters.
**[10:30]** In order to use gradient descent,
**[10:32]** the key thing you need to
**[10:34]** compute is these partial derivative terms.
**[10:37]** What TensorFlow does, and,
**[10:40]** in fact, what is standard in neural network training,
**[10:43]** is to use an algorithm called backpropagation
**[10:46]** in order to compute these partial derivative terms.
**[10:50]** TensorFlow can do all of these things for you.
**[10:53]** It implements backpropagation all
**[10:55]** within this function called fit.
**[10:58]** All you have to do is call model.fit, x,
**[11:01]** y as your training set,
**[11:03]** and tell it to do so for 100 iterations or 100 epochs.
**[11:08]** In fact, what you see later is that TensorFlow can use
**[11:11]** an algorithm that is even a little
**[11:13]** bit faster than gradient descent,
**[11:15]** and you'll see more about that later this week as well.
**[11:18]** Now, I know that we're relying heavily on
**[11:21]** the TensorFlow library in order
**[11:23]** to implement a neural network.
**[11:25]** One pattern I've seen across
**[11:28]** multiple ideas is as the technology evolves,
**[11:31]** libraries become more mature,
**[11:33]** and most engineers will use libraries
**[11:36]** rather than implement code from scratch.
**[11:39]** There have been many other examples
**[11:41]** of this in the history of computing.
**[11:43]** Once, many decades ago,
**[11:46]** programmers had to implement
**[11:47]** their own sorting function from scratch,
**[11:50]** but now sorting libraries are quite
**[11:52]** mature that you probably
**[11:54]** call someone else's sorting function
**[11:56]** rather than implement it yourself,
**[11:58]** unless you're taking a computing class and I
**[12:00]** ask you to do it as an exercise.
**[12:02]** Today, if you want to
**[12:04]** compute the square root of a number,
**[12:06]** like what is the square root of seven, well,
**[12:09]** once programmers had to
**[12:11]** write their own code to compute this,
**[12:13]** but now pretty much everyone just
**[12:15]** calls a library to take square roots,
**[12:18]** or matrix operations,
**[12:20]** such as multiplying two matrices together.
**[12:23]** When deep learning was younger and less mature,
**[12:27]** many developers, including me,
**[12:29]** were implementing things from scratch
**[12:31]** using Python or C++ or some other library.
**[12:34]** But today, deep learning libraries have matured
**[12:37]** enough that most developers will use these libraries,
**[12:41]** and, in fact,
**[12:41]** most commercial implementations of neural networks
**[12:44]** today use a library like TensorFlow or PyTorch.
**[12:47]** But as I've mentioned,
**[12:49]** it's still useful to understand how they work under
**[12:51]** the hood so that if something unexpected happens,
**[12:53]** which still does with today's libraries,
**[12:55]** you have a better chance of knowing how to fix it.
**[12:58]** Now that you know how to train a basic neural network,
**[13:02]** also called a multilayer perceptron,
**[13:05]** there are some things you can change about
**[13:07]** the neural network that will make it even more powerful.
**[13:10]** In the next video,
**[13:12]** let's take a look at how you can swap
**[13:14]** in different activation functions
**[13:16]** as an alternative to
**[13:18]** the sigmoid activation function we've been using.
**[13:21]** This will make your neural networks
**[13:23]** work even much better.
**[13:24]** Let's go take a look at that in the next video.
