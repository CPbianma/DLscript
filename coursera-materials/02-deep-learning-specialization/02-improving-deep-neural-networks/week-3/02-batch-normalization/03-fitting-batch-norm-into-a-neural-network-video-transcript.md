---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 3
section: Batch Normalization
item_title: Fitting Batch Norm into a Neural Network
duration: 13 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/RN8bN/fitting-batch-norm-into-a-neural-network
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Fitting Batch Norm into a Neural Network — Transcript

**[0:00]** So you have seen the equations for how to
**[0:02]** invent Batch Norm for maybe a single hidden layer.
**[0:05]** Let's see how it fits into the training of a deep network.
**[0:08]** So, let's say you have a neural network like this,
**[0:10]** you've seen me say before that you can view each of the unit as computing two things.
**[0:16]** First, it computes Z and then it applies the activation function to compute A.
**[0:22]** And so we can think of each of these circles as representing a two-step computation.
**[0:31]** And similarly for the next layer,
**[0:33]** that is Z2 1, and A2 1, and so on.
**[0:41]** So, if you were not applying Batch Norm,
**[0:45]** you would have an input X fit into the first hidden layer,
**[0:50]** and then first compute Z1,
**[0:53]** and this is governed by the parameters W1 and B1.
**[0:57]** And then ordinarily, you would fit Z1 into the activation function to compute A1.
**[1:04]** But what would do in Batch Norm is take this value Z1,
**[1:09]** and apply Batch Norm,
**[1:12]** sometimes abbreviated BN to it,
**[1:16]** and that's going to be governed by parameters,
**[1:19]** Beta 1 and Gamma 1,
**[1:23]** and this will give you this new normalize value Z1.
**[1:28]** And then you feed that to the activation function to get A1,
**[1:32]** which is G1 applied to Z tilde 1.
**[1:38]** Now, you've done the computation for the first layer,
**[1:41]** where this Batch Norms that really occurs in between the computation from Z and A.
**[1:47]** Next, you take this value A1 and use it to compute Z2,
**[1:53]** and so this is now governed by W2, B2.
**[1:58]** And similar to what you did for the first layer,
**[2:01]** you would take Z2 and apply it through Batch Norm, and we abbreviate it to BN now.
**[2:06]** This is governed by Batch Norm parameters specific to the next layer.
**[2:11]** So Beta 2, Gamma 2,
**[2:14]** and now this gives you Z tilde 2,
**[2:17]** and you use that to compute A2 by applying the activation function, and so on.
**[2:25]** So once again, the Batch Norms that happens between computing Z and computing A.
**[2:31]** And the intuition is that,
**[2:33]** instead of using the un-normalized value Z,
**[2:36]** you can use the normalized value Z tilde, that's the first layer.
**[2:40]** The second layer as well,
**[2:41]** instead of using the un-normalized value Z2,
**[2:44]** you can use the mean and variance normalized values Z tilde 2.
**[2:48]** So the parameters of your network are going to be W1, B1.
**[2:56]** It turns out we'll get rid of the parameters but we'll see why in the next slide.
**[3:00]** But for now, imagine the parameters are the usual W1.
**[3:06]** B1, WL, BL, and we have added to this new network,
**[3:12]** additional parameters Beta 1,
**[3:14]** Gamma 1, Beta 2, Gamma 2,
**[3:18]** and so on, for each layer in which you are applying Batch Norm.
**[3:24]** For clarity, note that these Betas here,
**[3:26]** these have nothing to do with the hyperparameter beta that we had for
**[3:30]** momentum over the computing the various exponentially weighted averages.
**[3:36]** The authors of the Adam paper use Beta on their paper to denote that hyperparameter,
**[3:42]** the authors of the Batch Norm paper had used Beta to denote this parameter,
**[3:47]** but these are two completely different Betas.
**[3:49]** I decided to stick with Beta in both cases,
**[3:53]** in case you read the original papers.
**[3:55]** But the Beta 1,
**[3:57]** Beta 2, and so on,
**[3:58]** that Batch Norm tries to learn is a different Beta than
**[4:02]** the hyperparameter Beta used in momentum and the Adam and RMSprop algorithms.
**[4:11]** So now that these are the new parameters of your algorithm,
**[4:14]** you would then use whether optimization you want,
**[4:18]** such as creating descent in order to implement it.
**[4:21]** For example, you might compute D Beta L for a given layer,
**[4:26]** and then update the parameters Beta,
**[4:28]** gets updated as Beta minus learning rate times
**[4:32]** D Beta L. And you can also use
**[4:37]** Adam or RMSprop or momentum in order to update the parameters Beta and Gamma,
**[4:43]** not just gradient descent.
**[4:45]** And even though in the previous video,
**[4:48]** I had explained what the Batch Norm operation does,
**[4:51]** computes mean and variances and subtracts and divides by them.
**[4:55]** If they are using a Deep Learning Programming Framework,
**[5:00]** usually you won't have to implement the Batch Norm step on Batch Norm layer yourself.
**[5:06]** So the probing frameworks,
**[5:07]** that can be sub one line of code.
**[5:09]** So for example, in terms of flow framework,
**[5:13]** you can implement Batch Normalization with this function.
**[5:17]** We'll talk more about probing frameworks later,
**[5:19]** but in practice you might not end up needing to implement all these details yourself,
**[5:24]** knowing how it works so that you can get
**[5:27]** a better understanding of what your code is doing.
**[5:30]** But implementing Batch Norm is often one line of code in the deep learning frameworks.
**[5:36]** Now, so far, we've talked about Batch Norm as if you were training on
**[5:40]** your entire training site at the time as if you are using Batch gradient descent.
**[5:45]** In practice, Batch Norm is usually applied with mini-batches of your training set.
**[5:51]** So the way you actually apply Batch Norm is you take
**[5:54]** your first mini-batch and compute Z1.
**[5:59]** Same as we did on the previous slide using the parameters W1,
**[6:03]** B1 and then you take just this mini-batch and computer mean and variance of the Z1 on
**[6:11]** just this mini batch and then Batch Norm would
**[6:14]** subtract by the mean and divide by the standard deviation and then re-scale by Beta 1,
**[6:21]** Gamma 1, to give you Z1,
**[6:24]** and all this is on the first mini-batch,
**[6:27]** then you apply the activation function to get A1,
**[6:33]** and then you compute Z2 using W2,
**[6:38]** B2, and so on.
**[6:41]** So you do all this in order to perform one step of
**[6:45]** gradient descent on the first mini-batch and then goes to the second mini-batch X2,
**[6:50]** and you do something similar where you will now compute Z1 on
**[6:54]** the second mini-batch and then use Batch Norm to compute Z1 tilde.
**[6:59]** And so here in this Batch Norm step,
**[7:02]** You would be normalizing Z tilde using just the data in your second mini-batch,
**[7:08]** so does Batch Norm step here.
**[7:10]** Let's look at the examples in your second mini-batch,
**[7:13]** computing the mean and variances of the Z1's on just that mini-batch and
**[7:18]** re-scaling by Beta and Gamma to get Z tilde, and so on.
**[7:24]** And you do this with a third mini-batch, and keep training.
**[7:28]** Now, there's one detail to the parameterization that I want to clean up,
**[7:34]** which is previously, I said that the parameters was WL, BL,
**[7:38]** for each layer as well as Beta L, and
**[7:43]** Gamma L. Now notice that the way Z was computed is as follows,
**[7:50]** ZL = WL x A of L - 1 + B of L. But what Batch Norm does,
**[8:00]** is it is going to look at the mini-batch and normalize
**[8:02]** ZL to first of mean 0 and standard variance,
**[8:06]** and then a rescale by Beta and Gamma.
**[8:09]** But what that means is that,
**[8:10]** whatever is the value of BL is actually going to just get subtracted out,
**[8:15]** because during that Batch Normalization step,
**[8:17]** you are going to compute the means of the ZL's and subtract the mean.
**[8:22]** And so adding any constant to all of the examples in the mini-batch,
**[8:27]** it doesn't change anything.
**[8:28]** Because any constant you add will get cancelled out by the mean subtractions step.
**[8:34]** So, if you're using Batch Norm,
**[8:35]** you can actually eliminate that parameter,
**[8:38]** or if you want, think of it as setting it permanently to 0.
**[8:42]** So then the parameterization becomes ZL is just WL x AL - 1,
**[8:49]** And then you compute ZL normalized,
**[8:54]** and we compute Z tilde = Gamma ZL + Beta,
**[9:04]** you end up using this parameter Beta L in order to decide
**[9:09]** whats that mean of Z tilde L. Which is why guess post in this layer.
**[9:15]** So just to recap,
**[9:16]** because Batch Norm zeroes out the mean of these ZL values in the layer,
**[9:24]** there's no point having this parameter BL,
**[9:27]** and so you must get rid of it,
**[9:29]** and instead is sort of replaced by Beta L,
**[9:32]** which is a parameter that controls that ends up affecting the shift or the biased terms.
**[9:39]** Finally, remember that the dimension of ZL,
**[9:43]** because if you're doing this on one example,
**[9:45]** it's going to be NL by 1,
**[9:48]** and so BL, a dimension, NL by one,
**[9:53]** if NL was the number of hidden units in layer
**[9:56]** L. And so the dimension of Beta L and Gamma L
**[10:00]** is also going to be NL by 1 because that's the number of hidden units you have.
**[10:07]** You have NL hidden units, and so Beta L and Gamma L are used to scale
**[10:12]** the mean and variance of each of
**[10:14]** the hidden units to whatever the network wants to set them to.
**[10:19]** So, let's pull all together and describe how
**[10:21]** you can implement gradient descent using Batch Norm.
**[10:25]** Assuming you're using mini-batch gradient descent,
**[10:28]** it rates for T = 1 to the number of mini batches.
**[10:34]** You would implement forward prop on
**[10:39]** mini-batch XT and doing forward prop in each hidden layer,
**[10:44]** use Batch Norm to replace
**[10:50]** ZL with Z tilde L. And so then it shows that within that mini-batch,
**[10:57]** the value Z end up with some normalized mean and variance and the values and
**[11:02]** the version of the normalized mean that and variance is Z tilde L. And then,
**[11:09]** you use back prop to compute DW,
**[11:17]** DB, for all the values of L,
**[11:20]** D Beta, D Gamma.
**[11:23]** Although, technically, since you have got to get rid of B,
**[11:26]** this actually now goes away.
**[11:28]** And then finally, you update the parameters.
**[11:33]** So, W gets updated as W minus the learning rate times, as usual,
**[11:40]** Beta gets updated as Beta minus learning rate times DB,
**[11:47]** and similarly for Gamma.
**[11:49]** And if you have computed the gradient as follows,
**[11:52]** you could use gradient descent.
**[11:54]** That's what I've written down here,
**[11:56]** but this also works with gradient descent with momentum,
**[12:01]** or RMSprop, or Adam.
**[12:07]** Where instead of taking this gradient descent
**[12:08]** update,nini-batch you could use the updates given
**[12:11]** by these other algorithms as we discussed in the previous week's videos.
**[12:16]** Some of these other optimization algorithms as well can be used to update
**[12:19]** the parameters Beta and Gamma that Batch Norm added to algorithm.
**[12:25]** So, I hope that gives you a sense of how you could
**[12:27]** implement Batch Norm from scratch if you wanted to.
**[12:30]** If you're using one of
**[12:31]** the Deep Learning Programming frameworks which we will talk more about later,
**[12:34]** hopefully you can just call someone else's implementation in
**[12:37]** the Programming framework which will make using Batch Norm much easier.
**[12:41]** Now, in case Batch Norm still seems a little bit mysterious if you're
**[12:45]** still not quite sure why it speeds up training so dramatically,
**[12:49]** let's go to the next video and talk more about
**[12:52]** why Batch Norm really works and what it is really doing.
