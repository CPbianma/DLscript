---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 2
section: Activation Functions
item_title: Choosing activation functions
duration: 8 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/aWivF/choosing-activation-functions
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# Choosing activation functions — Transcript

**[0:00]** Let's take a look at how you can choose
**[0:03]** the activation function for
**[0:05]** different neurons in your neural network.
**[0:07]** We'll start with some guidance for how
**[0:09]** to choose it for the output layer.
**[0:12]** It turns out that depending on what
**[0:13]** the target label or the ground truth label y is,
**[0:17]** there will be one fairly natural choice
**[0:20]** for the activation function for the output layer,
**[0:23]** and we'll then go and look at the choice of
**[0:25]** the activation function also for
**[0:28]** the hidden layers of your neural network.
**[0:30]** Let's take a look. You can choose
**[0:32]** different activation functions for
**[0:34]** different neurons in your neural network,
**[0:37]** and when considering the activation function
**[0:40]** for the output layer,
**[0:42]** it turns out that there'll often
**[0:44]** be one fairly natural choice,
**[0:47]** depending on what is
**[0:48]** the target or the ground truth label y.
**[0:51]** Specifically, if you are working on
**[0:54]** a classification problem where y is either zero or one,
**[0:58]** so a binary classification problem,
**[1:00]** then the sigmoid activation function
**[1:03]** will almost always be the most natural choice,
**[1:06]** because then the neural network learns to
**[1:10]** predict the probability that y is equal to one,
**[1:13]** just like we had for logistic regression.
**[1:15]** My recommendation is, if you're
**[1:17]** working on a binary classification problem,
**[1:20]** use sigmoid at the output layer.
**[1:22]** Alternatively, if you're solving a regression problem,
**[1:26]** then you might choose a different activation function.
**[1:29]** For example, if you are trying to predict how
**[1:34]** tomorrow's stock price will
**[1:35]** change compared to today's stock price.
**[1:38]** Well, it can go up or down,
**[1:39]** and so in this case y would be a number that can
**[1:41]** be either positive or negative,
**[1:44]** and in that case I would recommend
**[1:46]** you use the linear activation function.
**[1:49]** Why is that? Well,
**[1:51]** that's because then the outputs of your neural network,
**[1:53]** f of x, which is equal to a^3 in the example above,
**[1:57]** would be g applied
**[1:59]** to z^3 and with the linear activation function,
**[2:03]** g of z can take on either positive or negative values.
**[2:07]** So y can be positive or negative,
**[2:09]** use a linear activation function.
**[2:11]** Finally, if y can only take on non-negative values,
**[2:17]** such as if you're predicting the price of a house,
**[2:19]** that can never be negative,
**[2:21]** then the most natural choice will be
**[2:23]** the ReLU activation function because as you see here,
**[2:27]** this activation function only
**[2:29]** takes on non-negative values,
**[2:31]** either zero or positive values.
**[2:33]** In choosing the activation function
**[2:35]** to use for your output layer,
**[2:37]** usually depending on what
**[2:40]** is the label y you're trying to predict,
**[2:42]** there'll be one fairly natural choice.
**[2:44]** In fact, the guidance on this slide is how I pretty
**[2:49]** much always choose my activation function
**[2:51]** as well for the output layer of a neural network.
**[2:54]** How about the hidden layers of a neural network?
**[2:57]** It turns out that the ReLU activation function is by far
**[3:02]** the most common choice in how neural networks
**[3:05]** are trained by many practitioners today.
**[3:09]** Even though we had initially described neural networks
**[3:13]** using the sigmoid activation function, and in fact,
**[3:17]** in the early history of
**[3:18]** the development of neural networks,
**[3:20]** people use sigmoid activation functions in many places,
**[3:24]** the field has evolved to use
**[3:26]** ReLU much more often and sigmoids hardly ever.
**[3:31]** Well, the one exception that you do use
**[3:33]** a sigmoid activation function in
**[3:34]** the output layer if you have
**[3:36]** a binary classification problem.
**[3:38]** So why is that? Well, there are a few reasons.
**[3:41]** First, if you compare
**[3:43]** the ReLU and the sigmoid activation functions,
**[3:46]** the ReLU is a bit faster to compute because it
**[3:49]** just requires computing max of 0, z,
**[3:53]** whereas the sigmoid requires taking
**[3:55]** an exponentiation and then a inverse and so on,
**[3:58]** and so it's a little bit less efficient.
**[4:00]** But the second reason which turns
**[4:02]** out to be even more important is that
**[4:04]** the ReLU function goes
**[4:07]** flat only in one part of the graph;
**[4:10]** here on the left is completely flat,
**[4:13]** whereas the sigmoid activation function,
**[4:15]** it goes flat in two places.
**[4:18]** It goes flat to the left of the graph and
**[4:21]** it goes flat to the right of the graph.
**[4:25]** If you're using gradient descent
**[4:27]** to train a neural network,
**[4:28]** then when you have
**[4:31]** a function that is fat in a lot of places,
**[4:34]** gradient descents would be really slow.
**[4:37]** I know that gradient descent
**[4:39]** optimizes the cost function J of W,
**[4:42]** B rather than optimizes the activation function,
**[4:46]** but the activation function is
**[4:48]** a piece of what goes into computing,
**[4:50]** and that results in more places
**[4:52]** in the cost function J of W,
**[4:54]** B that are flats as well and with
**[4:57]** a small gradient and it slows down learning.
**[5:01]** I know that that was just an intuitive explanation,
**[5:04]** but researchers have found that using
**[5:06]** the ReLU activation function can cause
**[5:08]** your neural network to learn a bit faster as well,
**[5:11]** which is why for most practitioners if you're trying to
**[5:14]** decide what activation functions
**[5:16]** to use with hidden layer,
**[5:17]** the ReLU activation function has
**[5:19]** become now by far the most common choice.
**[5:22]** In fact that I'm building a neural network,
**[5:25]** this is how I choose
**[5:26]** activation functions for the hidden layers as well.
**[5:30]** To summarize, here's what I recommend in terms
**[5:34]** of how you choose
**[5:35]** the activation functions for your neural network.
**[5:38]** For the output layer,
**[5:40]** use a sigmoid,
**[5:41]** if you have a binary classification problem; linear,
**[5:44]** if y is a number
**[5:47]** that can take on positive or negative values,
**[5:49]** or use ReLU if y can take on
**[5:51]** only positive values or
**[5:53]** zero positive values or non-negative values.
**[5:55]** Then for the hidden layers I would recommend
**[5:59]** just using ReLU as a default activation function,
**[6:04]** and in TensorFlow, this is how you would implement it.
**[6:08]** Rather than saying activation equals sigmoid
**[6:11]** as we had previously,
**[6:13]** for the hidden layers,
**[6:15]** that's the first hidden layer,
**[6:16]** the second hidden layer as
**[6:18]** TensorFlow to use the ReLU activation function,
**[6:22]** and then for the output layer in this example,
**[6:26]** I've asked it to use the sigmoid activation function,
**[6:29]** but if you wanted to use the linear activation function,
**[6:33]** is that, that's the syntax for it,
**[6:35]** or if you wanted to use
**[6:36]** the ReLU activation function
**[6:38]** that shows the syntax for it.
**[6:41]** With this richer set of activation functions,
**[6:44]** you'll be well-positioned to build
**[6:46]** much more powerful neural networks
**[6:48]** than just once using
**[6:50]** only the sigmoid activation function.
**[6:53]** By the way, if you look at the research literature,
**[6:56]** you sometimes hear of authors
**[6:58]** using even other activation functions,
**[7:00]** such as the tan h activation function or
**[7:03]** the LeakyReLU activation function
**[7:06]** or the swish activation function.
**[7:09]** Every few years, researchers sometimes come
**[7:11]** up with another interesting activation function,
**[7:14]** and sometimes they do work a little bit better.
**[7:17]** For example, I've used
**[7:18]** the LeakyReLU activation function
**[7:21]** a few times in my work,
**[7:22]** and sometimes it works a little bit better than
**[7:24]** the ReLU activation function
**[7:26]** you've learned about in this video.
**[7:28]** But I think for the most part,
**[7:30]** and for the vast majority of applications
**[7:33]** what you learned about in
**[7:34]** this video would be good enough.
**[7:36]** Of course, if you want to
**[7:38]** learn more about other activation functions,
**[7:40]** feel free to look on the Internet,
**[7:42]** and there are just a small handful of cases where
**[7:45]** these other activation functions
**[7:47]** could be even more powerful as well.
**[7:50]** With that, I hope you also enjoy practicing these ideas,
**[7:55]** these activation functions in
**[7:57]** the optional labs and in the practice labs.
**[8:00]** But this raises yet another question.
**[8:03]** Why do we even need activation functions at all?
**[8:06]** Why don't we just use
**[8:07]** the linear activation function or
**[8:09]** use no activation function anywhere?
**[8:12]** It turns out this does not work at all.
**[8:15]** In the next video, let's take
**[8:17]** a look at why that's the case and why
**[8:19]** activation functions are so
**[8:20]** important for getting your neural networks to work.
