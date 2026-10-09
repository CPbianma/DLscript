---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 2
section: Activation Functions
item_title: Alternatives to the sigmoid activation
duration: 5 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/04Maa/alternatives-to-the-sigmoid-activation
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# Alternatives to the sigmoid activation — Transcript

**[0:02]** So far, we've been using the sigmoid activation function in all the nodes in
**[0:07]** the hidden layers and in the output layer.
**[0:10]** And we have started that way because we were building
**[0:13]** up neural networks by taking logistic regression and
**[0:17]** creating a lot of logistic regression units and string them together.
**[0:22]** But if you use other activation functions,
**[0:24]** your neural network can become much more powerful.
**[0:28]** Let's take a look at how to do that.
**[0:29]** Recall the demand prediction example from last week where given price,
**[0:34]** shipping cost, marketing, material,
**[0:36]** you would try to predict if something is highly affordable.
**[0:40]** If there's good awareness and high perceived quality and
**[0:43]** based on that try to predict it was a top seller.
**[0:46]** But this assumes that awareness is maybe binary is either people are aware or
**[0:51]** they are not.
**[0:53]** But it seems like the degree to which possible buyers are aware of the t shirt
**[0:58]** you're selling may not be binary, they can be a little bit aware,
**[1:02]** somewhat aware, extremely aware or it could have gone completely viral.
**[1:07]** So rather than modeling awareness as a binary number 0, 1,
**[1:11]** that you try to estimate the probability of awareness or
**[1:15]** rather than modeling awareness is just a number between 0 and 1.
**[1:20]** Maybe awareness should be any non negative number because there can be any non
**[1:25]** negative value of awareness going from 0 up to very very large numbers.
**[1:31]** So whereas previously we had used this equation to calculate
**[1:36]** the activation of that second hidden unit estimating awareness
**[1:41]** where g was the sigmoid function and just goes between 0 and 1.
**[1:46]** If you want to allow a,1, 2 to potentially take on much larger positive values,
**[1:53]** we can instead swap in a different activation function.
**[1:58]** It turns out that a very common choice of activation function in
**[2:02]** neural networks is this function.
**[2:05]** It looks like this.
**[2:06]** It goes if z is this, then g(z) is 0 to the left and
**[2:12]** then there's this straight line 45° to the right of 0.
**[2:19]** And so when z is greater than or equal to 0, g(z) is just equal to z.
**[2:27]** That is to the right half of this diagram.
**[2:31]** And the mathematical equation for this is g(z) equals max(0, z).
**[2:38]** Feel free to verify for yourself that max(0,
**[2:43]** z) results in this curve that I've drawn over here.
**[2:49]** And if a 1, 2 is g(z) for this value of z, then a,
**[2:54]** the deactivation value cannot take on 0 or any non negative value.
**[3:02]** This activation function has a name.
**[3:05]** It goes by the name ReLU with this funny capitalization and ReLU stands for
**[3:10]** again, somewhat arcane term, but it stands for rectified linear unit.
**[3:16]** Don't worry too much about what rectified means and what linear unit means.
**[3:19]** This was just the name that the authors had given to
**[3:22]** this particular activation function when they came up with it.
**[3:26]** But most people in deep learning just say ReLU to refer to this g(z).
**[3:32]** More generally you have a choice of what to use for g(z) and
**[3:37]** sometimes we'll use a different choice than the sigmoid activation function.
**[3:43]** Here are the most commonly used activation functions.
**[3:47]** You saw the sigmoid activation function, g(z) equals this sigmoid function.
**[3:52]** On the last slide we just looked at the ReLU or
**[3:55]** rectified linear unit g(z) equals max(0, z).
**[4:00]** There's one other activation function which is worth mentioning,
**[4:04]** which is called the linear activation function, which is just g(z) equals to z.
**[4:09]** Sometimes if you use the linear activation function,
**[4:14]** people will say we're not using any activation function because
**[4:19]** if a is g(z) where g(z) equals z, then a is just equal to this w.x plus b z.
**[4:26]** And so it's as if there was no g in there at all.
**[4:28]** So when you are using this linear activation function g(z) sometimes
**[4:33]** people say, well, we're not using any activation function.
**[4:38]** Although in this class, I will refer to using the linear activation function
**[4:42]** rather than no activation function.
**[4:45]** But if you hear someone else use that terminology, that's what they mean.
**[4:48]** It just refers to the linear activation function.
**[4:51]** And these three are probably by far the most commonly used
**[4:55]** activation functions in neural networks.
**[4:59]** Later this week,
**[5:00]** we'll touch on the fourth one called the softmax activation function.
**[5:04]** But with these activation functions you'll be able to build
**[5:08]** a rich variety of powerful neural networks.
**[5:12]** So when building a neural network for each neuron,
**[5:15]** do you want to use the sigmoid activation function or the ReLU activation function?
**[5:21]** Or a linear activation function?
**[5:23]** How do you choose between these different activation functions?
**[5:26]** Let's take a look at that in the next video.
