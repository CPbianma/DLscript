---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 3
section: Multi-class Classification
item_title: Softmax Regression
duration: 12 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/HRy7y/softmax-regression
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Softmax Regression — Transcript

**[0:00]** So far, the classification examples we've talked about have used
**[0:04]** binary classification, where you had two possible labels, 0 or 1.
**[0:08]** Is it a cat, is it not a cat?
**[0:10]** What if we have multiple possible classes?
**[0:13]** There's a generalization of logistic regression called Softmax regression.
**[0:17]** The less you make predictions where you're trying to recognize one of C or
**[0:21]** one of multiple classes, rather than just recognize two classes.
**[0:26]** Let's take a look.
**[0:26]** Let's say that instead of just recognizing cats you want to recognize cats, dogs, and
**[0:31]** baby chicks.
**[0:31]** So I'm going to call cats class 1, dogs class 2, baby chicks class 3.
**[0:38]** And if none of the above, then there's an other or
**[0:40]** a none of the above class, which I'm going to call class 0.
**[0:44]** So here's an example of the images and the classes they belong to.
**[0:49]** That's a picture of a baby chick, so the class is 3.
**[0:52]** Cats is class 1, dog is class 2, I guess that's a koala, so
**[0:57]** that's none of the above, so that is class 0, class 3 and so on.
**[1:02]** So the notation we're going to use is, I'm going to use capital C to
**[1:07]** denote the number of classes you're trying to categorize your inputs into.
**[1:13]** And in this case, you have four possible classes, including the other or
**[1:17]** the none of the above class.
**[1:19]** So when you have four classes, the numbers indexing
**[1:23]** your classes would be 0 through capital C minus one.
**[1:28]** So in other words, that would be zero, one, two or three.
**[1:31]** In this case, we're going to build a new XY, where the upper layer has four,
**[1:36]** or in this case the variable capital alphabet C upward units.
**[1:43]** So N, the number of units upper layer which is layer L is going to equal to 4 or
**[1:48]** in general this is going to equal to C.
**[1:51]** And what we want is for the number of units in the upper layer to tell
**[1:56]** us what is the probability of each of these four classes.
**[2:00]** So the first node here is supposed to output, or
**[2:04]** we want it to output the probability that is the other class,
**[2:08]** given the input x, this will output probability there's a cat.
**[2:12]** Give an x, this will output probability as a dog.
**[2:16]** Give an x, that will output the probability.
**[2:20]** I'm just going to abbreviate baby chick to baby C, given the input x.
**[2:29]** So here, the output labels y hat is going to be a four by one dimensional vector,
**[2:36]** because it now has to output four numbers, giving you these four probabilities.
**[2:42]** And because probabilities should sum to one, the four numbers in the output y hat,
**[2:48]** they should sum to one.
**[2:50]** The standard model for getting your network to do this uses what's called
**[2:55]** a Softmax layer, and the output layer in order to generate these outputs.
**[3:00]** Then write down the map, then you can come back and
**[3:02]** get some intuition about what the Softmax there is doing.
**[3:06]** So in the final layer of the neural network,
**[3:08]** you are going to compute as usual the linear part of the layers.
**[3:13]** So z, capital L, that's the z variable for the final layer.
**[3:17]** So remember this is layer capital L.
**[3:21]** So as usual you compute that as wL times the activation of
**[3:26]** the previous layer plus the biases for that final layer.
**[3:32]** Now having computer z,
**[3:33]** you now need to apply what's called the Softmax activation function.
**[3:38]** So that activation function is a bit unusual for the Softmax layer, but
**[3:43]** this is what it does.
**[3:45]** First, we're going to computes a temporary variable,
**[3:50]** which we're going to call t, which is e to the z L.
**[3:54]** So this is a part element-wise.
**[3:56]** So zL here, in our example, zL is going to be four by one.
**[4:00]** This is a four dimensional vector.
**[4:03]** So t Itself e to the zL, that's an element wise exponentiation.
**[4:08]** T will also be a 4.1 dimensional vector.
**[4:13]** Then the output aL,
**[4:14]** is going to be basically the vector t will normalized to sum to 1.
**[4:20]** So aL is going to be e to the zL divided by sum from J equal 1 through 4,
**[4:28]** because we have four classes of t substitute i.
**[4:33]** So in other words we're saying that aL is also a four by one vector,
**[4:40]** and the i element of this four dimensional vector.
**[4:44]** Let's write that, aL substitute i that's
**[4:50]** going to be equal to ti over sum of ti, okay?
**[4:56]** In case this math isn't clear,
**[4:58]** we'll do an example in a minute that will make this clearer.
**[5:02]** So in case this math isn't clear,
**[5:03]** let's go through a specific example that will make this clearer.
**[5:06]** Let's say that your computer zL, and
**[5:10]** zL is a four dimensional vector, let's say is 5, 2, -1, 3.
**[5:18]** What we're going to do is use this element-wise exponentiation to
**[5:22]** compute this vector t.
**[5:23]** So t is going to be e to the 5, e to the 2, e to the -1, e to the 3.
**[5:29]** And if you plug that in the calculator, these are the values you get.
**[5:32]** E to the 5 is 1484, e squared is about 7.4,
**[5:38]** e to the -1 is 0.4, and e cubed is 20.1.
**[5:44]** And so, the way we go from the vector t to the vector aL is just
**[5:49]** to normalize these entries to sum to one.
**[5:52]** So if you sum up the elements of t,
**[5:56]** if you just add up those 4 numbers you get 176.3.
**[6:03]** So finally, aL is just going to be this vector t,
**[6:09]** as a vector, divided by 176.3.
**[6:14]** So for example, this first node here,
**[6:18]** this will output e to the 5 divided by 176.3.
**[6:23]** And that turns out to be 0.842.
**[6:27]** So saying that, for this image, if this is the value of z you get,
**[6:32]** the chance of it being called zero is 84.2%.
**[6:36]** And then the next nodes outputs e squared over 176.3,
**[6:42]** that turns out to be 0.042, so this is 4.2% chance.
**[6:48]** The next one is e to -1 over that,
**[6:53]** which is 0.042.
**[6:56]** And the final one is e cubed over that, which is 0.114.
**[7:04]** So it is 11.4% chance that this is class number three,
**[7:08]** which is the baby C class, right?
**[7:10]** So there's a chance of it being class zero, class one, class two, class three.
**[7:15]** So the output of the neural network aL, this is also y hat.
**[7:21]** This is a 4 by 1 vector where the elements
**[7:25]** of this 4 by 1 vector are going to be these four numbers.
**[7:29]** Then we just compute it.
**[7:31]** So this algorithm takes the vector zL and is four probabilities that sum to 1.
**[7:38]** And if we summarize what we just did to math from zL to aL,
**[7:44]** this whole computation confusing exponentiation to
**[7:47]** get this temporary variable t and then normalizing,
**[7:52]** we can summarize this into a Softmax activation function and
**[7:57]** say aL equals the activation function g applied to the vector zL.
**[8:03]** The unusual thing about this particular activation function is that,
**[8:08]** this activation function g, it takes a input a 4 by 1 vector and
**[8:12]** it outputs a 4 by 1 vector.
**[8:15]** So previously, our activation functions used to take in a single row value input.
**[8:19]** So for example, the sigmoid and
**[8:20]** the value activation functions input the real number and output a real number.
**[8:24]** The unusual thing about the Softmax activation function is,
**[8:28]** because it needs to normalized across the different possible outputs,
**[8:32]** and needs to take a vector and puts in outputs of vector.
**[8:35]** So one of the things that a Softmax cross layer can represent,
**[8:39]** I'm going to show you some examples where you have inputs x1, x2.
**[8:43]** And these feed directly to a Softmax layer that has three or
**[8:48]** four, or more output nodes that then output y hat.
**[8:53]** So I'm going to show you a new network with no hidden layer,
**[8:58]** and all it does is compute z1 equals w1 times the input x plus b.
**[9:04]** And then the output a1, or
**[9:07]** y hat is just the Softmax activation function applied to z1.
**[9:13]** So in this neural network with no hidden layers,
**[9:15]** it should give you a sense of the types of things a Softmax function can represent.
**[9:20]** So here's one example with just raw inputs x1 and x2.
**[9:23]** A Softmax layer with C equals 3 upper classes can represent
**[9:28]** this type of decision boundaries.
**[9:31]** Notice this kind of several linear decision boundaries,
**[9:35]** but this allows it to separate out the data into three classes.
**[9:39]** And in this diagram, what we did was we actually took the training
**[9:44]** set that's kind of shown in this figure and
**[9:47]** train the Softmax cross fire with the upper labels on the data.
**[9:52]** And then the color on this plot shows fresh
**[9:54]** holding the upward of the Softmax cross fire, and coloring in the input
**[9:59]** base on which one of the three outputs have the highest probability.
**[10:03]** So we can maybe we kind of see that this is like a generalization of logistic
**[10:07]** regression with sort of linear decision boundaries, but
**[10:11]** with more than two classes [INAUDIBLE] class 0, 1, the class could be 0, 1, or 2.
**[10:16]** Here's another example of the decision boundary that a Softmax cross fire
**[10:20]** represents when three normal datasets with three classes.
**[10:23]** And here's another one, rIght, so this is a, but one intuition is
**[10:28]** that the decision boundary between any two classes will be more linear.
**[10:34]** That's why you see for example that decision boundary between the yellow and
**[10:38]** the various classes, that's the linear boundary where the purple and red
**[10:42]** linear in boundary between the purple and yellow and other linear decision boundary.
**[10:46]** But able to use these different linear functions
**[10:49]** in order to separate the space into three classes.
**[10:52]** Let's look at some examples with more classes.
**[10:55]** So it's an example with C equals 4, so
**[10:58]** that the green class and Softmax can continue to represent these types
**[11:03]** of linear decision boundaries between multiple classes.
**[11:07]** So here's one more example with C equals 5 classes, and
**[11:11]** here's one last example with C equals 6.
**[11:15]** So this shows the type of things the Softmax crossfire can do when there is no
**[11:20]** hidden layer of class, even much deeper neural network with x and
**[11:24]** then some hidden units, and then more hidden units, and so on.
**[11:28]** Then you can learn even more complex non-linear decision boundaries to separate
**[11:32]** out multiple different classes.
**[11:35]** So I hope this gives you a sense of what a Softmax layer or
**[11:37]** the Softmax activation function in the neural network can do.
**[11:41]** In the next video,
**[11:42]** let's take a look at how you can train a neural network that uses a Softmax layer.
