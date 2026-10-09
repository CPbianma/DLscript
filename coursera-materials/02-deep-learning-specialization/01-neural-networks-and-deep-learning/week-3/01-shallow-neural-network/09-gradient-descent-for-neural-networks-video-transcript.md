---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 3
section: Shallow Neural Network
item_title: Gradient Descent for Neural Networks
duration: 10 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/Wh8NI/gradient-descent-for-neural-networks
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Gradient Descent for Neural Networks — Transcript

**[0:00]** All right. I think this'll be an exciting video.
**[0:02]** In this video, you'll see how to implement
**[0:04]** gradient descent for your neural network with one hidden layer.
**[0:08]** In this video, I'm going to just give you the equations you need to
**[0:12]** implement in order to get back-propagation or to get gradient descent working,
**[0:16]** and then in the video after this one,
**[0:18]** I'll give some more intuition about why
**[0:20]** these particular equations are the accurate equations,
**[0:24]** are the correct equations for computing the gradients you need for your neural network.
**[0:28]** So, your neural network,
**[0:29]** with a single hidden layer for now,
**[0:31]** will have parameters W1,
**[0:34]** B1, W2, and B2.
**[0:39]** So, as a reminder,
**[0:40]** if you have NX or alternatively N0 input features,
**[0:48]** and N1 hidden units,
**[0:51]** and N2 output units in our examples.
**[0:57]** So far I've only had N2 equals one,
**[0:59]** then the matrix W1 will be N1 by N0.
**[1:05]** B1 will be an N1 dimensional vector,
**[1:08]** so we can write that as N1 by one-dimensional matrix,
**[1:12]** really a column vector.
**[1:14]** The dimensions of W2 will be N2 by N1,
**[1:18]** and the dimension of B2 will be N2 by one.
**[1:25]** Right, so far we've only seen examples where N2 is equal to one,
**[1:28]** where you have just one single hidden unit.
**[1:32]** So, you also have a cost function for a neural network.
**[1:39]** For now, I'm just going to assume that you're doing binary classification.
**[1:43]** So, in that case,
**[1:45]** the cost of your parameters as follows is going to be one
**[1:50]** over M of the average of that loss function.
**[1:56]** So, L here is the loss when your neural network predicts Y hat, right.
**[2:02]** This is really A2 when the gradient label is equal to Y.
**[2:06]** If you're doing binary classification,
**[2:08]** the loss function can be exactly what you use for logistic regression earlier.
**[2:13]** So, to train the parameters of your algorithm,
**[2:15]** you need to perform gradient descent.
**[2:19]** When training a neural network,
**[2:21]** it is important to initialize the parameters randomly rather than to all zeros.
**[2:26]** We'll see later why that's the case,
**[2:28]** but after initializing the parameter to something,
**[2:31]** each loop or gradient descents with computed predictions.
**[2:34]** So, you basically compute your Y hat I,
**[2:38]** for I equals one through M, say.
**[2:41]** Then, you need to compute the derivative.
**[2:44]** So, you need to compute DW1,
**[2:47]** and that's the derivative of the cost function with respect to the parameter W1,
**[2:54]** you can compute another variable,
**[2:56]** shall I call DB1,
**[2:58]** which is the derivative or the slope of your cost function with
**[3:02]** respect to the variable B1 and so on.
**[3:06]** Similarly for the other parameters W2 and B2.
**[3:09]** Then finally, the gradient descent update would be to update W1 as W1 minus Alpha.
**[3:17]** The learning rate times D, W1.
**[3:21]** B1 gets updated as B1 minus the learning rate,
**[3:26]** times DB1, and similarly for W2 and B2.
**[3:32]** Sometimes, I use colon equals and sometimes equals,
**[3:35]** as either notation works fine.
**[3:37]** So, this would be one iteration of gradient descent,
**[3:40]** and then you repeat this some number of
**[3:42]** times until your parameters look like they're converging.
**[3:45]** So, in previous videos,
**[3:46]** we talked about how to compute the predictions,
**[3:49]** how to compute the outputs,
**[3:50]** and we saw how to do that in a vectorized way as well.
**[3:52]** So, the key is to know how to compute these partial derivative terms,
**[3:57]** the DW1, DB1 as well as the derivatives DW2 and DB2.
**[4:03]** So, what I'd like to do is just give you
**[4:06]** the equations you need in order to compute these derivatives.
**[4:11]** I'll defer to the next video, which is an optional video, to go
**[4:15]** greater into Jeff about how we came up with those formulas.
**[4:19]** So, let me just summarize again the equations for propagation.
**[4:25]** So, you have Z1 equals W1X plus B1,
**[4:32]** and then A1 equals the activation function in that layer applied element wise as Z1,
**[4:42]** and then Z2 equals W2,
**[4:46]** A1 plus V2, and then finally,
**[4:52]** just as all vectorized across your training set, right?
**[4:55]** A2 is equal to G2 of Z2.
**[5:00]** Again, for now, if we assume we're doing binary classification,
**[5:03]** then this activation function really should be the sigmoid function,
**[5:07]** same just for that end neural.
**[5:08]** So, that's the forward propagation or the left to
**[5:11]** right for computation for your neural network.
**[5:14]** Next, let's compute the derivatives.
**[5:16]** So, this is the back propagation step.
**[5:21]** Then I compute DZ2 equals A2 minus the gradient of Y,
**[5:30]** and just as a reminder,
**[5:33]** all this is vectorized across examples.
**[5:35]** So, the matrix Y is this one by
**[5:38]** M matrix that lists all of your M examples stacked horizontally.
**[5:44]** Then it turns out DW2 is equal to this,
**[5:50]** and in fact, these first three equations are
**[5:54]** very similar to gradient descents for logistic regression.
**[6:00]** X is equals one,
**[6:03]** comma, keep dims equals true.
**[6:08]** Just a little detail this np.sum is
**[6:13]** a Python NumPy command for summing across one-dimension of a matrix.
**[6:18]** In this case, summing horizontally,
**[6:21]** and what keepdims does is, it prevents Python from
**[6:25]** outputting one of those funny rank one arrays, right?
**[6:30]** Where the dimensions was your N comma.
**[6:33]** So, by having keepdims equals true,
**[6:36]** this ensures that Python outputs for DB a vector that is N by one.
**[6:43]** In fact, technically this will be I guess N2 by one.
**[6:47]** In this case, it's just a one by one number,
**[6:49]** so maybe it doesn't matter.
**[6:51]** But later on, we'll see when it really matters.
**[6:55]** So, so far what we've done is very similar to logistic regression.
**[6:59]** But now as you continue to run back propagation,
**[7:04]** you will compute this,
**[7:05]** DZ2 times G1 prime of Z1.
**[7:16]** So, this quantity G1 prime is
**[7:19]** the derivative of whether it was the activation function you use for the hidden layer,
**[7:23]** and for the output layer,
**[7:25]** I assume that you are doing binary classification with the sigmoid function.
**[7:29]** So, that's already baked into that formula for DZ2,
**[7:32]** and his times is element-wise product.
**[7:37]** So, this here is going to be an N1 by M matrix, and this here,
**[7:45]** this element-wise derivative thing is also going to be an N1 by N matrix,
**[7:51]** and so this times there is an element-wise product of two matrices.
**[7:55]** Then finally, DW1 is equal to that,
**[8:00]** and DB1 is equal to this,
**[8:07]** and p.sum DZ1 axis
**[8:14]** equals one, keepdims equals true.
**[8:20]** So, whereas previously the keepdims maybe matter less if N2 is equal to one.
**[8:26]** Result is just a one by one thing, is just a real number.
**[8:29]** Here, DB1 will be a N1 by one vector,
**[8:36]** and so you want Python, you want Np.sons.
**[8:39]** I'll put something of this dimension rather than a funny rank one array
**[8:43]** of that dimension which could end up messing up some of your data calculations.
**[8:49]** The other way would be to not have to keep the parameters,
**[8:52]** but to explicitly reshape the output of NP.sum into this dimension,
**[9:01]** which you would like DB to have.
**[9:04]** So, that was forward propagation in I guess four equations,
**[9:09]** and back-propagation in I guess six equations.
**[9:13]** I know I just wrote down these equations,
**[9:15]** but in the next optional video,
**[9:17]** let's go over some intuitions for how
**[9:20]** the six equations for the back propagation algorithm were derived.
**[9:24]** Please feel free to watch that or not.
**[9:26]** But either way, if you implement these algorithms,
**[9:28]** you will have a correct implementation of forward prop and back prop.
**[9:33]** You'll be able to compute the derivatives you need in order to apply gradient descent,
**[9:38]** to learn the parameters of your neural network.
**[9:40]** It is possible to implement this algorithm and
**[9:43]** get it to work without deeply understanding the calculus.
**[9:46]** A lot of successful deep learning practitioners do so.
**[9:49]** But, if you want,
**[9:50]** you can also watch the next video,
**[9:52]** just to get a bit more intuition of what the derivation of these equations.
