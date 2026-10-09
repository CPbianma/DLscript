---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 1
section: Recurrent Neural Networks
item_title: Recurrent Neural Network Model
duration: 17 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/ftkzt/recurrent-neural-network-model
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Recurrent Neural Network Model — Transcript

**[0:00]** In the last video, you saw the notation we'll use to define sequence learning problems.
**[0:05]** Now, let's talk about how you can build a model,
**[0:08]** built a neural network to learn the mapping from x to y.
**[0:11]** Now, one thing you could do is try to use a standard neural network for this task.
**[0:16]** So, in our previous example,
**[0:19]** we had nine input words.
**[0:21]** So, you could imagine trying to take these nine input words,
**[0:26]** maybe the nine one-hot vectors and feeding them into a standard neural network,
**[0:31]** maybe a few hidden layers,
**[0:33]** and then eventually had this output the nine values zero or
**[0:37]** one that tell you whether each word is part of a person's name.
**[0:41]** But this turns out not to work well and there are really two main problems of this the
**[0:46]** first is that the inputs and outputs can be different lengths and different examples.
**[0:52]** So, it's not as if every single example had the same input length Tx or
**[0:57]** the same upper length Ty and maybe if every sentence has a maximum length.
**[1:03]** Maybe you could pad or zero-pad every inputs up to
**[1:06]** that maximum length but this still doesn't seem like a good representation.
**[1:11]** And then a second and maybe more serious problem is
**[1:14]** that a naive neural network architecture like this,
**[1:17]** it doesn't share features learned across different positions of texts.
**[1:21]** In particular of the neural network has learned that maybe the word
**[1:25]** Harry appearing in position one gives a sign that that's part of a person's name,
**[1:31]** then wouldn't it be nice if it automatically figures out that Harry appearing in
**[1:36]** some other position x t also means that that might be a person's name.
**[1:41]** And this is maybe similar to what you saw in convolutional neural networks where
**[1:47]** you want things learned for one part of
**[1:50]** the image to generalize quickly to other parts of the image,
**[1:53]** and we like a similar effects for sequence data as well.
**[1:57]** And similar to what you saw with confidence using
**[2:00]** a better representation will also let you reduce the number of parameters in your model.
**[2:06]** So previously, we said that each of these is a 10,000
**[2:10]** dimensional one-hot vector and so this is
**[2:13]** just a very large input layer if
**[2:17]** the total input size was maximum number of words times 10,000.
**[2:22]** A weight matrix of this first layer will end up having an enormous number of parameters.
**[2:27]** So a recurrent neural network which we'll start to describe in
**[2:31]** the next slide does not have either of these disadvantages.
**[2:36]** So, what is a recurrent neural network?
**[2:39]** Let's build one up.
**[2:41]** So if you are reading the sentence from left to right,
**[2:46]** the first word you will read is the some first words say X1,
**[2:50]** and what we're going to do is take the first word
**[2:53]** and feed it into a neural network layer.
**[2:56]** I'm going to draw it like this.
**[2:59]** So there's a hidden layer of the first neural network and we
**[3:03]** can have the neural network maybe try to predict the output.
**[3:07]** So is this part of the person's name or not.
**[3:09]** And what a recurrent neural network does is,
**[3:14]** when it then goes on to read the second word in the sentence,
**[3:19]** say x2, instead of just predicting y2 using only X2,
**[3:26]** it also gets to input some information from whether the computer that time step one.
**[3:33]** So in particular, deactivation value from time step one is passed on to time step two.
**[3:40]** Then at the next time step,
**[3:43]** recurrent neural network inputs
**[3:47]** the third word X3 and it tries to output some prediction,
**[3:53]** Y hat three and so on up until
**[4:02]** the last time step where it inputs x_TX and then it outputs y_hat_ty.
**[4:11]** At least in this example,
**[4:15]** Ts is equal to ty and the architecture will change a bit if tx and ty are not identical.
**[4:22]** So at each time step,
**[4:24]** the recurrent neural network that passes on
**[4:27]** as activation to the next time step for it to use.
**[4:30]** And to kick off the whole thing,
**[4:33]** we'll also have some either made-up activation at time zero,
**[4:38]** this is usually the vector of zeros.
**[4:41]** Some researchers will initialized a_zero randomly.
**[4:44]** You have other ways to initialize a_zero but really having a vector of
**[4:48]** zeros as the fake times zero activation is the most common choice.
**[4:54]** So that gets input to the neural network.
**[4:56]** In some research papers or in some books,
**[5:00]** you see this type of neural network drawn with the following diagram in which at
**[5:05]** every time step you input x and output y_hat.
**[5:10]** Maybe sometimes there will be
**[5:11]** a T index there and then to denote the recurrent connection,
**[5:17]** sometimes people will draw a loop like that,
**[5:19]** that the layer feeds back to the cell.
**[5:21]** Sometimes, they'll draw a shaded box to denote that this is the shaded box here,
**[5:27]** denotes a time delay of one step.
**[5:29]** I personally find these recurrent diagrams much
**[5:32]** harder to interpret and so throughout this course,
**[5:35]** I'll tend to draw the unrolled diagram like the one you have on the left,
**[5:39]** but if you see something like the diagram on
**[5:41]** the right in a textbook or in a research paper,
**[5:43]** what it really means or the way I tend to think about it is to mentally
**[5:47]** unroll it into the diagram you have on the left instead.
**[5:50]** The recurrent neural network scans through the data from left to right.
**[5:55]** The parameters it uses for each time step are shared.
**[5:59]** So there'll be a set of parameters which
**[6:01]** we'll describe in greater detail on the next slide,
**[6:04]** but the parameters governing the connection from X1 to the hidden layer,
**[6:09]** will be some set of parameters we're going to write as Wax and is
**[6:13]** the same parameters Wax that it uses for every time step.
**[6:18]** I guess I could write Wax there as well.
**[6:22]** Deactivations, the horizontal connections will be governed by
**[6:26]** some set of parameters Waa and
**[6:29]** the same parameters Waa use on every timestep and
**[6:35]** similarly the sum Wya that governs the output predictions.
**[6:43]** I'll describe on the next line exactly how these parameters work.
**[6:48]** So, in this recurrent neural network,
**[6:50]** what this means is that when making the prediction for y3,
**[6:55]** it gets the information not only from X3 but also the information from x1 and x2 because
**[7:01]** the information on x1 can pass through this way to help to prediction with Y3.
**[7:07]** Now, one weakness of this RNN is that it only uses
**[7:11]** the information that is earlier in the sequence to make a prediction.
**[7:15]** In particular, when predicting y3,
**[7:18]** it doesn't use information about the words X4,
**[7:22]** X5, X6 and so on.
**[7:24]** So this is a problem because if you are given a sentence,
**[7:29]** "He said Teddy Roosevelt was a great president."
**[7:32]** In order to decide whether or not the word Teddy is part of a person's name,
**[7:36]** it would be really useful to know not just information from the first two words but to
**[7:41]** know information from the later words in the sentence
**[7:44]** as well because the sentence could also have been,
**[7:47]** "He said teddy bears they're on sale."
**[7:49]** So given just the first three words is not possible to know
**[7:53]** for sure whether the word Teddy is part of a person's name.
**[7:57]** In the first example, it is.
**[7:58]** In the second example, it is not.
**[8:00]** But you can't tell the difference if you look only at the first three words.
**[8:05]** So one limitation of
**[8:07]** this particular neural network structure is that the prediction at a certain time
**[8:11]** uses inputs or uses information from the inputs
**[8:15]** earlier in the sequence but not information later in the sequence.
**[8:19]** We will address this in a later video where we talk about
**[8:22]** bi-directional recurrent neural networks or BRNNs.
**[8:28]** But for now,
**[8:30]** this simpler unidirectional neural network architecture
**[8:35]** will suffice to explain the key concepts.
**[8:38]** We'll just have to make a quick modifications to these ideas later to enable, say,
**[8:42]** the prediction of y_hat_three to use both information
**[8:46]** earlier in the sequence as well as information later in the sequence.
**[8:49]** We'll get to that in a later video.
**[8:51]** So, let's now write explicitly what are the calculations that this neural network does.
**[8:57]** Here's a cleaned up version of the picture of the neural network.
**[9:01]** As I mentioned previously, typically,
**[9:04]** you started off with the input a_zero equals the vector of all zeros.
**[9:09]** Next, this is what forward propagation looks like.
**[9:13]** To compute a1, you would compute that as an activation function g applied to
**[9:22]** Waa times a0 plus
**[9:28]** Wax times x1 plus a bias.
**[9:34]** I was going to write as ba,
**[9:36]** and then to compute y hat.
**[9:39]** One, the prediction at times at one,
**[9:42]** that will be some activation function,
**[9:44]** maybe a different activation function than the one above but
**[9:49]** applied to Wya times a1 plus by.
**[9:59]** The notation convention I'm going to use for the substrate of
**[10:01]** these matrices like that example, Wax.
**[10:05]** The second index means that this Wax is going to be multiplied by some X-like quantity,
**[10:11]** and this a means that this is used to compute some a-like quantity like so.
**[10:18]** Similarly, you noticed that here,
**[10:20]** Wya is multiplied by some a-like quantity to compute a y-type quantity.
**[10:29]** The activation function using or to compute
**[10:32]** the activations will often be a tanh in the choice of an RNN
**[10:39]** and sometimes very loose are also used although the tanh is actually
**[10:46]** a pretty common choice and we
**[10:49]** have other ways of preventing the vanishing gradient problem,
**[10:53]** which we'll talk about later this week.
**[10:56]** Depending on what your output y is,
**[10:59]** if it is a binary classification problem,
**[11:02]** then I guess you would use a sigmoid activation function,
**[11:05]** or it could be a softmax that you have a k-way classification problem that
**[11:09]** the choice of activation function here will depend on what type of output y you have.
**[11:15]** So, for the name entity recognition task where y was either 01,
**[11:19]** I guess a second g could be a sigmoid activation function.
**[11:23]** Then I guess you could write g2 if you want to distinguish that
**[11:28]** this could be different activation functions but I usually won't do that.
**[11:32]** Then more generally, at time t,
**[11:35]** a<t> will be g of Waa times a
**[11:41]** from the previous time step plus Wax of x from the current time step plus ba,
**[11:49]** and y hat t is equal to g. Again,
**[11:54]** it could be different activation functions but g of Wya times at plus by.
**[12:03]** So, this equation is defined forward propagation in
**[12:07]** a neural network where you would start off with a0 is the vector of all zeros,
**[12:12]** and then using a0 and x1,
**[12:14]** you will compute a1 and y hat one,
**[12:16]** and then you take x2 and use x2 and a1 to compute a2 and y hat two,
**[12:24]** and so on, and you'd carry out
**[12:26]** forward propagation going from the left to the right of this picture.
**[12:30]** Now, in order to help us develop the more complex neural networks,
**[12:34]** I'm actually going to take this notation and simplify it a little bit.
**[12:38]** So, let me copy these two equations to the next slide. Right, here they are.
**[12:45]** What I'm going to do is actually take,
**[12:48]** so to simplify the notation a bit,
**[12:50]** I'm actually going to take that and write in a slightly simpler way.
**[12:55]** So, I'm going to write this as a<t> equals g times just a matrix
**[13:01]** Wa times a new quantity which is going to be 80 minus one comma xt,
**[13:12]** and then plus ba,
**[13:16]** and so that underlying quantity on the left and right are supposed to be equivalent.
**[13:22]** So the way we define Wa is we'll take this matrix Waa,
**[13:28]** and this matrix Wax,
**[13:30]** and put them side by side,
**[13:33]** stack them horizontally as follows,
**[13:36]** and this will be the matrix Wa.
**[13:40]** So for example, if a was a 100 dimensional,
**[13:47]** and in our running example x was 10,000 dimensional,
**[13:51]** then Waa would have been a 100 by 100 dimensional matrix,
**[13:57]** and Wax would have been a 100 by 10,000 dimensional matrix.
**[14:03]** As we're stacking these two matrices together,
**[14:06]** this would be 100-dimensional.
**[14:08]** This will be 100,
**[14:10]** and this would be I guess 10,000 elements.
**[14:14]** So, Wa will be a 100 by 10100 dimensional matrix.
**[14:22]** I guess this diagram on the left is not drawn to scale,
**[14:25]** since Wax would be a very wide matrix.
**[14:29]** What this notation means,
**[14:31]** is to just take the two vectors and stack them together.
**[14:36]** So, when you use that notation to denote that,
**[14:39]** we're going to take the vector at minus one,
**[14:42]** so that's a 100 dimensional and stack it on top of at,
**[14:48]** so, this ends up being a 10100 dimensional vector.
**[14:55]** So hopefully, you can check for yourself that this matrix
**[14:59]** times this vector just gives you back the original quantity.
**[15:05]** Right. Because now, this matrix Waa times
**[15:11]** Wax multiplied by this at minus one xt vector,
**[15:17]** this is just equal to Waa times at minus one plus Wax times xt,
**[15:27]** which is exactly what we had back over here.
**[15:32]** So, the advantage of this notation is that rather than carrying
**[15:35]** around two parameter matrices, Waa and Wax,
**[15:40]** we can compress them into just one parameter matrix Wa,
**[15:44]** and just to simplify our notation for when we develop more complex models.
**[15:48]** Then for this in a similar way,
**[15:51]** I'm just going to rewrite this slightly.
**[15:54]** I'm going to write this as Wy at plus by,
**[16:00]** and now we just have two substrates in the notation Wy and by,
**[16:06]** it denotes what type of output quantity we're computing.
**[16:09]** So, Wy indicates a weight matrix or computing a y-like quantity,
**[16:13]** and here at Wa and ba on top indicates where does this
**[16:17]** parameters for computing like an a an activation output quantity.
**[16:22]** So, that's it. You now know what is a basic recurrent neural network.
**[16:26]** Next, let's talk about back propagation and how you will learn with these RNNs.
