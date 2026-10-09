---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 3
section: Batch Normalization
item_title: Why does Batch Norm work?
duration: 12 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/81oTm/why-does-batch-norm-work
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Why does Batch Norm work? — Transcript

**[0:00]** So, why does batch norm work?
**[0:02]** Here's one reason, you've seen how normalizing the input features,
**[0:06]** the X's, to mean zero and variance one,
**[0:09]** how that can speed up learning.
**[0:10]** So rather than having some features that range from zero to one,
**[0:13]** and some from one to a 1,000,
**[0:15]** by normalizing all the features, input features X,
**[0:18]** to take on a similar range of values that can speed up learning.
**[0:22]** So, one intuition behind why batch norm works is,
**[0:25]** this is doing a similar thing,
**[0:27]** but further values in your hidden units and not just for your input there.
**[0:32]** Now, this is just a partial picture for what batch norm is doing.
**[0:37]** There are a couple of further intuitions,
**[0:39]** that will help you gain a deeper understanding of what batch norm is doing.
**[0:43]** Let's take a look at those in this video.
**[0:46]** A second reason why batch norm works,
**[0:48]** is it makes weights,
**[0:50]** later or deeper than your network,
**[0:52]** say the weight on layer 10, more robust to changes to
**[0:56]** weights in earlier layers of the neural network, say, in layer one.
**[1:00]** To explain what I mean,
**[1:01]** let's look at this most vivid example.
**[1:04]** Let's see a training on network,
**[1:06]** maybe a shallow network,
**[1:07]** like logistic regression or maybe a neural network,
**[1:11]** maybe a shallow network like this regression or maybe a deep network,
**[1:17]** on our famous cat detection toss.
**[1:21]** But let's say that you've trained your data sets on all images of black cats.
**[1:26]** If you now try to apply this network to
**[1:31]** data with colored cats where
**[1:33]** the positive examples are not just black cats like on the left,
**[1:36]** but to color cats like on the right,
**[1:40]** then your cosfa might not do very well.
**[1:43]** So in pictures, if your training set looks like this,
**[1:47]** where you have positive examples here and negative examples here,
**[1:52]** but you were to try to generalize it,
**[1:54]** to a data set where maybe positive examples are here and the negative examples are here,
**[2:02]** then you might not expect a module trained on the data
**[2:05]** on the left to do very well on the data on the right.
**[2:09]** Even though there might be the same function that actually works well,
**[2:13]** but you wouldn't expect your learning algorithm to discover that green decision boundary,
**[2:19]** just looking at the data on the left.
**[2:21]** So, this idea of your data distribution changing goes
**[2:26]** by the somewhat fancy name, covariate shift.
**[2:31]** And the idea is that,
**[2:33]** if you've learned some X to Y mapping,
**[2:35]** if the distribution of X changes,
**[2:38]** then you might need to retrain your learning algorithm.
**[2:41]** And this is true even if the function,
**[2:43]** the ground true function,
**[2:45]** mapping from X to Y,
**[2:46]** remains unchanged, which it is in this example,
**[2:49]** because the ground true function is,
**[2:51]** is this picture a cat or not.
**[2:53]** And the need to retain your function becomes even more
**[2:57]** acute or it becomes even worse if the ground true function shifts as well.
**[3:03]** So, how does this problem of covariate shift apply to a neural network?
**[3:08]** Consider a deep network like this,
**[3:10]** and let's look at the learning process from the perspective of this certain layer,
**[3:15]** the third hidden layer.
**[3:16]** So this network has learned the parameters W3 and B3.
**[3:22]** And from the perspective of the third hidden layer,
**[3:24]** it gets some set of values from the earlier layers,
**[3:27]** and then it has to do some stuff to hopefully make
**[3:30]** the output Y-hat close to the ground true value Y.
**[3:34]** So let me cover up the nose on the left for a second.
**[3:38]** So from the perspective of this third hidden layer,
**[3:41]** it gets some values,
**[3:44]** let's call them A_2_1, A_2_2, A_2_3, and A_2_4.
**[3:53]** But these values might as well be features X1, X2, X3,
**[3:58]** X4, and the job of the third hidden layer is to
**[4:02]** take these values and find a way to map them to Y-hat.
**[4:08]** So you can imagine doing great intercepts,
**[4:10]** so that these parameters W_3_B_3 as well as maybe W_4_B_4,
**[4:17]** and even W_5_B_5, maybe try and learn those parameters,
**[4:21]** so the network does a good job,
**[4:23]** mapping from the values I drew in black on the left to the output values Y-hat.
**[4:29]** But now let's uncover the left of the network again.
**[4:33]** The network is also adapting parameters W_2_B_2 and W_1B_1,
**[4:42]** and so as these parameters change,
**[4:45]** these values, A_2, will also change.
**[4:49]** So from the perspective of the third hidden layer,
**[4:53]** these hidden unit values are changing all the time,
**[4:56]** and so it's suffering from the problem of
**[4:59]** covariate shift that we talked about on the previous slide.
**[5:02]** So what batch norm does,
**[5:04]** is it reduces the amount that the distribution of these hidden unit values shifts around.
**[5:10]** And if it were to plot the distribution of these hidden unit values,
**[5:14]** maybe this is technically renormalizer Z,
**[5:17]** so this is actually Z_2_1 and Z_2_2,
**[5:24]** and I also plot two values instead of four values,
**[5:27]** so we can visualize in 2D.
**[5:29]** What batch norm is saying is that,
**[5:32]** the values for Z_2_1 Z and Z_2_2 can change,
**[5:35]** and indeed they will change when the neural network updates
**[5:38]** the parameters in the earlier layers.
**[5:41]** But what batch norm ensures is that no matter how it changes,
**[5:44]** the mean and variance of Z_2_1 and Z_2_2 will remain the same.
**[5:55]** So even if the exact values of Z_2_1 and Z_2_2 change,
**[5:59]** their mean and variance will at least stay same mean zero and variance one.
**[6:07]** Or, not necessarily mean zero and variance one,
**[6:09]** but whatever value is governed by beta two and gamma two.
**[6:17]** Which, if the neural networks chooses,
**[6:19]** can force it to be mean zero and variance one.
**[6:22]** Or, really, any other mean and variance.
**[6:24]** But what this does is,
**[6:26]** it limits the amount to which updating the parameters in the earlier layers can
**[6:32]** affect the distribution of values that
**[6:35]** the third layer now sees and therefore has to learn on.
**[6:38]** And so, batch norm reduces the problem of the input values changing,
**[6:44]** it really causes these values to become more stable,
**[6:48]** so that the later layers of the neural network has more firm ground to stand on.
**[6:55]** And even though the input distribution changes a bit,
**[6:57]** it changes less, and what this does is,
**[7:00]** even as the earlier layers keep learning,
**[7:03]** the amounts that this forces the later layers to
**[7:06]** adapt to as early as layer changes is reduced or,
**[7:10]** if you will, it weakens the coupling between
**[7:12]** what the early layers parameters has to do
**[7:15]** and what the later layers parameters have to do.
**[7:18]** And so it allows each layer of the network to learn by itself,
**[7:22]** a little bit more independently of other layers,
**[7:25]** and this has the effect of speeding up of learning in the whole network.
**[7:29]** So I hope this gives some better intuition,
**[7:32]** but the takeaway is that batch norm means that,
**[7:35]** especially from the perspective of one of the later layers of the neural network,
**[7:39]** the earlier layers don't get to shift around as much,
**[7:43]** because they're constrained to have the same mean and variance.
**[7:46]** And so this makes the job of learning on the later layers easier.
**[7:50]** It turns out batch norm has a second effect,
**[7:52]** it has a slight regularization effect.
**[7:55]** So one non-intuitive thing of a batch norm is that each mini-batch,
**[7:59]** I will say mini-batch X_t,
**[8:02]** has the values Z_t,
**[8:04]** has the values Z_l,
**[8:07]** scaled by the mean and variance computed on just that one mini-batch.
**[8:12]** Now, because the mean and variance computed on
**[8:15]** just that mini-batch as opposed to computed on the entire data set,
**[8:20]** that mean and variance has a little bit of noise in it,
**[8:22]** because it's computed just on your mini-batch of,
**[8:25]** say, 64, or 128,
**[8:28]** or maybe 256 or larger training examples.
**[8:32]** So because the mean and variance is a little bit noisy because it's estimated with
**[8:35]** just a relatively small sample of data, the scaling process,
**[8:40]** going from Z_l to Z_2_l,
**[8:43]** that process is a little bit noisy as well,
**[8:46]** because it's computed, using a slightly noisy mean and variance.
**[8:51]** So similar to dropout,
**[8:54]** it adds some noise to each hidden layer's activations.
**[8:57]** The way dropout has noises,
**[8:59]** it takes a hidden unit and it multiplies it by zero with some probability.
**[9:04]** And multiplies it by one with some probability.
**[9:06]** And so your dropout has multiple of noise because it's multiplied by zero or one,
**[9:12]** whereas batch norm has multiples of noise because of scaling by the standard deviation,
**[9:18]** as well as additive noise because it's subtracting the mean.
**[9:21]** Well, here the estimates of the mean and the standard deviation are noisy.
**[9:25]** And so, similar to dropout,
**[9:29]** batch norm therefore has a slight regularization effect.
**[9:33]** Because by adding noise to the hidden units,
**[9:35]** it's forcing the downstream hidden units not to rely too much on any one hidden unit.
**[9:41]** And so similar to dropout,
**[9:43]** it adds noise to the hidden layers and therefore has a very slight regularization effect.
**[9:47]** Because the noise added is quite small,
**[9:50]** this is not a huge regularization effect,
**[9:52]** and you might choose to use batch norm together with dropout,
**[9:56]** and you might use batch norm together with dropouts if
**[9:59]** you want the more powerful regularization effect of dropout.
**[10:03]** And maybe one other slightly non-intuitive effect is that,
**[10:06]** if you use a bigger mini-batch size,
**[10:08]** right, so if you use use a mini-batch size of, say,
**[10:11]** 512 instead of 64,
**[10:13]** by using a larger mini-batch size,
**[10:15]** you're reducing this noise and therefore also reducing this regularization effect.
**[10:20]** So that's one strange property of dropout
**[10:24]** which is that by using a bigger mini-batch size,
**[10:27]** you reduce the regularization effect.
**[10:29]** Having said this, I wouldn't really use batch norm as a regularizer,
**[10:33]** that's really not the intent of batch norm,
**[10:36]** but sometimes it has this extra intended or unintended effect on your learning algorithm.
**[10:44]** But, really, don't turn to batch norm as a regularization.
**[10:48]** Use it as a way to normalize
**[10:50]** your hidden units activations and therefore speed up learning.
**[10:53]** And I think the regularization is an almost unintended side effect.
**[10:57]** So I hope that gives you better intuition about what batch norm is doing.
**[11:02]** Before we wrap up the discussion on batch norm,
**[11:04]** there's one more detail I want to make sure you know,
**[11:06]** which is that batch norm handles data one mini-batch at a time.
**[11:11]** It computes mean and variances on mini-batches.
**[11:14]** So at test time,
**[11:15]** you try and make predictors, try and evaluate the neural network,
**[11:18]** you might not have a mini-batch of examples,
**[11:20]** you might be processing one single example at the time.
**[11:24]** So, at test time you need to do something
**[11:26]** slightly differently to make sure your predictions make sense.
**[11:29]** Like in the next and final video on batch norm,
**[11:32]** let's talk over the details of what you need to do in order to take
**[11:35]** your neural network trained using batch norm to make predictions.
