---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 2
section: Activation Functions
item_title: Why do we need activation functions?
duration: 6 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/mb9bw/why-do-we-need-activation-functions
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Why do we need activation functions? — Transcript

**[0:01]** Let's take a look at why
**[0:04]** neural networks need activation functions
**[0:07]** and why they just
**[0:08]** don't work if we were to use
**[0:10]** the linear activation function in
**[0:12]** every neuron in the neural network.
**[0:15]** Recall this demand prediction example.
**[0:18]** What would happen if we were to use
**[0:21]** a linear activation function for
**[0:23]** all of the nodes in this neural network?
**[0:26]** It turns out that this big neural network will
**[0:28]** become no different than just linear regression.
**[0:32]** So this would defeat the entire purpose of
**[0:35]** using a neural network because it would then
**[0:38]** just not be able to fit anything more complex
**[0:41]** than the linear regression model
**[0:43]** that we learned about in the first course.
**[0:46]** Let's illustrate this with a simpler example.
**[0:50]** Let's look at the example of a neural network where
**[0:53]** the input x is just a number and we have
**[0:57]** one hidden unit with
**[1:00]** parameters w1 and b1 that outputs a1,
**[1:05]** which is here, just a number,
**[1:07]** and then the second layer is the output layer and it has
**[1:12]** also just one output unit with parameters
**[1:15]** w2 and b2 and then output a2,
**[1:18]** which is also just a number,
**[1:20]** just a scalar, which is
**[1:21]** the output of the neural network f of x.
**[1:24]** Let's see what this neural network
**[1:26]** would do if we were to use
**[1:28]** the linear activation function
**[1:30]** g of z equals z everywhere.
**[1:34]** So to compute a1 as a function of x,
**[1:38]** the neural network will use a1 equals g
**[1:42]** of w1 times x plus b1.
**[1:47]** But g of z is equal to z.
**[1:49]** So this is just w1 times x plus b1.
**[1:54]** Then a2 is equal to w2 times a1 plus b2,
**[2:01]** because g of z equals z.
**[2:03]** Let me take this expression for
**[2:06]** a1 and substitute it in there.
**[2:09]** So that becomes w2 times w1 x plus b1 plus b2.
**[2:19]** If we simplify, this becomes w2,
**[2:23]** w1 times x plus w2, b1 plus b2.
**[2:32]** It turns out that if I were to set w equals w2
**[2:37]** times w1 and set b equals this quantity over here,
**[2:42]** then what we've just shown is that a2 is
**[2:45]** equal to w x plus b.
**[2:48]** So a2 is just a linear function of the input x.
**[2:54]** Rather than using a neural network
**[2:56]** with one hidden layer and one output layer,
**[2:57]** we might as well have just
**[2:59]** used a linear regression model.
**[3:01]** If you're familiar with linear algebra,
**[3:04]** this result comes from the fact that
**[3:06]** a linear function of
**[3:07]** a linear function is itself a linear function.
**[3:10]** This is why having multiple layers in
**[3:12]** a neural network doesn't let the neural network compute
**[3:15]** any more complex features or learn
**[3:17]** anything more complex than just a linear function.
**[3:21]** So in the general case,
**[3:25]** if you had a neural network with
**[3:27]** multiple layers like this and say you were to use
**[3:30]** a linear activation function for
**[3:32]** all of the hidden layers and
**[3:34]** also use a linear activation function
**[3:36]** for the output layer,
**[3:37]** then it turns out this model will compute
**[3:41]** an output that is completely
**[3:43]** equivalent to linear regression.
**[3:45]** The output a4 can be expressed as
**[3:48]** a linear function of the input features x plus b.
**[3:53]** Or alternatively, if we were to
**[3:56]** still use a linear activation function
**[3:58]** for all the hidden layers,
**[3:59]** for these three hidden layers here,
**[4:01]** but we were to use
**[4:03]** a logistic activation function for the output layer,
**[4:06]** then it turns out you can show that this model
**[4:09]** becomes equivalent to logistic regression,
**[4:13]** and a4, in this case,
**[4:16]** can be expressed as 1 over 1 plus e to
**[4:18]** the negative wx plus b for some values of w and b.
**[4:23]** So this big neural network doesn't do anything
**[4:26]** that you can't also do with logistic regression.
**[4:29]** That's why a common rule of thumb is don't use
**[4:32]** the linear activation function
**[4:33]** in the hidden layers of the neural network.
**[4:35]** In fact, I recommend typically using
**[4:38]** the ReLU activation function should do just fine.
**[4:42]** So that's why a neural network needs
**[4:45]** activation functions other than
**[4:47]** just the linear activation function everywhere.
**[4:50]** So far, you've learned to build neural networks for
**[4:53]** binary classification problems where
**[4:55]** y is either zero or one.
**[4:58]** As well as for regression problems where
**[5:00]** y can take negative or positive values,
**[5:03]** or maybe just positive and non-negative values.
**[5:06]** In the next video,
**[5:08]** I'd like to share with you a generalization of
**[5:11]** what you've seen so far for classification.
**[5:14]** In particular, when y doesn't just take on two values,
**[5:19]** but may take on
**[5:20]** three or four or ten or even more categorical values.
**[5:25]** Let's take a look at how you can build
**[5:27]** a neural network for that type of classification problem.
