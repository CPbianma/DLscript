---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 2
section: Multiclass Classification
item_title: Neural Network with Softmax output
duration: 7 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/ZQPG3/neural-network-with-softmax-output
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Neural Network with Softmax output — Transcript

**[0:01]** In order to build a Neural Network that can carry out multi class classification,
**[0:07]** we're going to take the Softmax regression model and
**[0:10]** put it into essentially the output layer of a Neural Network.
**[0:14]** Let's take a look at how to do that.
**[0:16]** Previously, when we were doing handwritten digit recognition with just two classes.
**[0:22]** We use a new Neural Network with this architecture.
**[0:26]** If you now want to do handwritten digit classification with 10 classes,
**[0:32]** all the digits from zero to nine, then we're going to change
**[0:37]** this Neural Network to have 10 output units like so.
**[0:42]** And this new output layer will be a Softmax output layer.
**[0:46]** So sometimes we'll say this Neural Network has a Softmax output or
**[0:51]** that this upper layer is a Softmax layer.
**[0:54]** And the way forward propagation works in this Neural Network is
**[0:59]** given an input X A1 gets computed exactly the same as before.
**[1:04]** And then A2, the activations for
**[1:06]** the second hidden layer also get computed exactly the same as before.
**[1:12]** And we now have to compute the activations for this output layer, that is a3.
**[1:19]** This is how it works.
**[1:21]** If you have 10 output classes, we will compute Z1,
**[1:25]** Z2 through Z10 using these expressions.
**[1:29]** So this is actually very similar to what we had previously for
**[1:33]** the formula you're using to compute Z.
**[1:35]** Z1 is W1.product with a2, the activations from
**[1:40]** the previous layer plus b1 and so on for Z1 through Z10.
**[1:46]** Then a1 is equal to e to the Z1 divided
**[1:52]** by e to the Z1 plus up to e to the Z10.
**[1:57]** And that's our estimate of the chance that y is equal to 1.
**[2:02]** And similarly for a2 and similarly all the way up to a10.
**[2:09]** And so this gives you your estimates of the chance of y being good to one,
**[2:14]** two and so on up through the 10th possible label for y.
**[2:19]** And just for completeness,
**[2:21]** if you want to indicate that these are the quantities associated with layer three,
**[2:26]** technically, I should add these super strip three's there.
**[2:31]** It does make the notation a little bit more cluttered.
**[2:33]** But this makes explicit that this is, for example,
**[2:38]** the Z(3), 1 value and this is the parameters associated
**[2:43]** with the first unit of layer three of this Neural Network.
**[2:48]** And with this, your Softmax open layer now gives you estimates
**[2:54]** of the chance of y being any of these 10 possible output labels.
**[2:59]** I do want to mention that the Softmax layer will sometimes also called
**[3:03]** the Softmax activation function, it is a little bit unusual in one
**[3:07]** respect compared to the other activation functions we've seen so
**[3:11]** far, like sigma, radial and linear, which is that when we're
**[3:15]** looking at sigmoid or value or linear activation functions,
**[3:19]** a1 was a function of Z1 and a2 was a function of Z2 and only Z2.
**[3:29]** In other words, to obtain the activation values,
**[3:32]** we could apply the activation function g be it sigmoid or rarely or
**[3:37]** something else element wise to Z1 and Z2 and so on to get a1 and a2 and a3 and a4.
**[3:43]** But with the Softmax activation function,
**[3:47]** notice that a1 is a function of Z1 and Z2 and Z3 all the way up to Z10.
**[3:54]** So each of these activation values, it depends on all of the values of Z.
**[4:00]** And this is a property that's a bit unique to the Softmax output or
**[4:05]** the Softmax activation funct tion or
**[4:09]** stated differently if you want to compute a1 through a10,hat
**[4:14]** is a function of Z1 all the way up to Z 10 simultaneously.
**[4:20]** And this is unlike the other activation functions we've seen so far.
**[4:23]** Finally, let's look at how you would implement this in tensorflow.
**[4:29]** If you want to implement the neural network that I've shown here on
**[4:34]** this slide, this is the code to do so.
**[4:37]** Similar as before there are three steps to specifying and training the model.
**[4:41]** The first step is to tell tensorflow to sequentially string together three layers.
**[4:46]** First layer, is this 25 units with rail you activation function.
**[4:51]** Second layer, 15 units of rally activation function.
**[4:54]** And then the third layer, because there are now 10 output units,
**[4:58]** you want to output a1 through a10, so they're now 10 output units.
**[5:02]** And we'll tell tensorflow to use the Softmax activation function.
**[5:08]** And the cost function that you saw in the last video,
**[5:12]** tensorflow calls that the SparseCategoricalCrossentropy function.
**[5:19]** So I know this name is a bit of a mouthful, whereas for
**[5:22]** logistic regression we had the BinaryCrossentropy function,
**[5:27]** here we're using the SparseCategoricalCrossentropy function.
**[5:32]** And what sparse categorical refers to
**[5:35]** is that you're still classified y into categories.
**[5:39]** So it's categorical.
**[5:40]** This takes on values from 1 to 10.
**[5:44]** And sparse refers to that y can only take on one of these 10 values.
**[5:48]** So each image is either 0 or 1 or 2 or so on up to 9.
**[5:52]** You're not going to see a picture that is simultaneously the number two and
**[5:57]** the number seven so
**[5:58]** sparse refers to that each digit is only one of these categories.
**[6:02]** But so that's why the loss function that you saw in the last video,
**[6:07]** it's called intensive though the sparse categorical cross entropy loss function.
**[6:12]** And then the code for training the model is just the same as before.
**[6:17]** And if you use this code,
**[6:19]** you can train a neural network on a multi class classification problem.
**[6:24]** Just one important note, if you use this code exactly as I've written here, it will
**[6:29]** work, but don't actually use this code because it turns out that in tensorflow,
**[6:35]** there's a better version of the code that makes tensorflow work better.
**[6:40]** So even though the code shown in this slide works.
**[6:43]** Don't use this code the way I've written it here,
**[6:46]** because in a later video this week you see a different version that's
**[6:49]** actually the recommended version of implementing this, that will work better.
**[6:54]** But we'll take a look at that in a later video.
**[6:57]** So now, you know how to train a neural network with a softmax output layer
**[7:03]** with one caveal.
**[7:04]** There's a different version of the code that will make tensorflow
**[7:09]** able to compute these probabilities much more accurately.
**[7:13]** Let's take a look at that in the next video, we should also show you the actual
**[7:18]** code that I recommend you use if you're training a Softmax neural network.
**[7:21]** Let's go on to the next video.
