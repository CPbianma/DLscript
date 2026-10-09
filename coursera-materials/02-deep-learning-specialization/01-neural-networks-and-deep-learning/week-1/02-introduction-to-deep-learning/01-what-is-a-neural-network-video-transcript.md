---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 1
section: Introduction to Deep Learning
item_title: What is a Neural Network?
duration: 7 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/eAE2G/what-is-a-neural-network
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# What is a Neural Network? — Transcript

**[0:01]** The term, Deep Learning, refers to training Neural Networks,
**[0:03]** sometimes very large Neural Networks.
**[0:06]** So what exactly is a Neural Network?
**[0:08]** In this video, let's try to give you some of the basic intuitions.
**[0:12]** Let's start with a Housing Price Prediction example.
**[0:16]** Let's say you have a data set with six houses, so you know the size of the houses
**[0:20]** in square feet or square meters and you know the price of the house and you want
**[0:24]** to fit a function to predict the price of a house as a function of its size.
**[0:28]** So if you are familiar with linear regression you might say, well let's
**[0:33]** put a straight line to this data, so, and we get a straight line like that.
**[0:38]** But to be put fancier, you might say, well we know that prices
**[0:41]** can never be negative, right?
**[0:43]** So instead of the straight line fit, which eventually will become negative,
**[0:48]** let's bend the curve here.
**[0:49]** So it just ends up zero here.
**[0:51]** So this thick blue line ends up being your function for
**[0:56]** predicting the price of the house as a function of its size.
**[0:59]** Where it is zero here and then there is a straight line fit to the right.
**[1:04]** So you can think of this function that you have just fit to housing prices
**[1:08]** as a very simple neural network.
**[1:11]** It is almost the simplest possible neural network.
**[1:14]** Let me draw it here.
**[1:17]** We have as the input to the neural network the size of a house which we call x.
**[1:22]** It goes into this node, this little circle and
**[1:26]** then it outputs the price which we call y.
**[1:30]** So this little circle, which is a single neuron in a neural network,
**[1:37]** implements this function that we drew on the left.
**[1:43]** And all that the neuron does is it inputs the size, computes this linear function,
**[1:48]** takes a max of zero, and then outputs the estimated price.
**[1:53]** And by the way in the neural network literature, you will see this function a lot.
**[1:58]** This function which goes to zero sometimes and
**[2:00]** then it'll take of as a straight line.
**[2:03]** This function is called a ReLU function which stands for
**[2:09]** rectified linear units.
**[2:17]** So R-E-L-U. And
**[2:18]** rectify just means taking a max of 0 which is why you get a function shape like this.
**[2:23]** You don't need to worry about ReLU units for
**[2:25]** now but it's just something you will see again later in this course.
**[2:30]** So if this is a single neuron, neural network,
**[2:33]** really a tiny little neural network, a larger neural network
**[2:38]** is then formed by taking many of the single neurons and stacking them together.
**[2:44]** So, if you think of this neuron that's being like a single Lego brick, you then
**[2:50]** get a bigger neural network by stacking together many of these Lego bricks.
**[2:55]** Let's see an example.
**[2:57]** Let’s say that instead of predicting the price of a house just from the size,
**[3:02]** you now have other features.
**[3:04]** You know other things about the house, such as the number of bedrooms,
**[3:08]** which we would write as "#bedrooms", and you might think that one of the things
**[3:13]** that really affects the price of a house is family size, right?
**[3:18]** So can this house fit your family of three, or family of four, or
**[3:21]** family of five?
**[3:22]** And it's really based on the size in square feet or square meters, and
**[3:26]** the number of bedrooms that determines whether or
**[3:28]** not a house can fit your family's family size.
**[3:31]** And then maybe you know the zip codes,
**[3:34]** in different countries it's called a postal code of a house.
**[3:40]** And the zip code maybe as a feature tells you, walkability?
**[3:48]** So is this neighborhood highly walkable?
**[3:51]** Think just walks to the grocery store?
**[3:53]** Walk to school?
**[3:54]** Do you need to drive?
**[3:55]** And some people prefer highly walkable neighborhoods.
**[3:57]** And then the zip code as well as the wealth maybe tells you, right.
**[4:06]** Certainly in the United States but some other countries as well.
**[4:09]** Tells you how good is the school quality.
**[4:13]** So each of these little circles I'm drawing, can be one of those ReLU,
**[4:17]** rectified linear units or some other slightly non linear function.
**[4:22]** So that based on the size and number of bedrooms,
**[4:24]** you can estimate the family size, their zip code, based on walkability,
**[4:28]** based on zip code and wealth can estimate the school quality.
**[4:32]** And then finally you might think that well the way people decide how much they're
**[4:35]** willing to pay for a house, is they look at the things that really matter to them.
**[4:38]** In this case family size, walkability, and school quality and
**[4:43]** that helps you predict the price.
**[4:46]** So in the example x is all of these four inputs.
**[4:53]** And y is the price you're trying to predict.
**[4:57]** And so by stacking together a few of the single neurons or the simple predictors
**[5:03]** we have from the previous slide, we now have a slightly larger neural network.
**[5:07]** How you manage neural network is that when you implement it,
**[5:10]** you need to give it just the input x and
**[5:15]** the output y for a number of examples in your training set and
**[5:20]** all these things in the middle, they will figure out by itself.
**[5:25]** So what you actually implement is this.
**[5:29]** Where, here, you have a neural network with four inputs.
**[5:32]** So the input features might be the size, number of bedrooms,
**[5:35]** the zip code or postal code, and the wealth of the neighborhood.
**[5:40]** And so given these input features,
**[5:44]** the job of the neural network will be to predict the price y.
**[5:50]** And notice also that each of these circles, these are called hidden units in
**[5:55]** the neural network, that each of them takes its inputs all four input features.
**[6:02]** So for example, rather than saying this first node represents family size and
**[6:08]** family size depends only on the features X1 and X2.
**[6:12]** Instead, we're going to say, well neural network,
**[6:15]** you decide whatever you want this node to be.
**[6:18]** And we'll give you all four input features to compute whatever you want.
**[6:21]** So we say that layer that this is input layer and
**[6:26]** this layer in the middle of the neural network are densely connected.
**[6:28]** Because every input feature is connected to every one
**[6:31]** of these circles in the middle.
**[6:33]** And the remarkable thing about neural networks is that, given enough data about
**[6:38]** x and y, given enough training examples with both x and y, neural networks
**[6:43]** are remarkably good at figuring out functions that accurately map from x to y.
**[6:48]** So, that's a basic neural network.
**[6:51]** It turns out that as you build out your own neural networks,
**[6:54]** you'll probably find them to be most useful, most powerful
**[6:57]** in supervised learning incentives, meaning that you're trying to take an input x and
**[7:01]** map it to some output y, like we just saw in the housing price prediction example.
**[7:06]** In the next video let's go over some more examples of supervised learning and
**[7:11]** some examples of where you might find your networks to be incredibly helpful for
**[7:15]** your applications as well.
