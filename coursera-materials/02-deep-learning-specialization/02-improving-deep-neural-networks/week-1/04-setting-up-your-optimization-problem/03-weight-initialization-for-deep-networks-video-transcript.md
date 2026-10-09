---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 1
section: Setting Up your Optimization Problem
item_title: Weight Initialization for Deep Networks
duration: 6 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/RwqYe/weight-initialization-for-deep-networks
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Weight Initialization for Deep Networks — Transcript

**[0:00]** In the last video you saw how very deep neural networks
**[0:04]** can have the problems of vanishing and exploding gradients.
**[0:08]** It turns out that a partial solution to this,
**[0:11]** doesn't solve it entirely but helps a lot,
**[0:13]** is better or more careful choice of the random initialization for your neural network.
**[0:18]** To understand this, let's start with the example of initializing the ways for
**[0:23]** a single neuron, and then we're go on to generalize this to a deep network.
**[0:27]** Let's go through this with an example with
**[0:30]** just a single neuron, and then we'll talk about the deep net later.
**[0:33]** So with a single neuron, you might input four features, x1 through x4, and then you have some
**[0:39]** a=g(z) and then it outputs some y.
**[0:42]** And later on for a deeper net, you know these inputs will be right,
**[0:46]** some layer a(l), but for now let's just call this x for now.
**[0:51]** So z is going to be equal to w1x1 + w2x2 +... + I guess WnXn.
**[1:03]** And let's set b=0 so, you know, let's just ignore b for now.
**[1:08]** So in order to make z not blow up and not become
**[1:12]** too small, you notice that the larger n is,
**[1:16]** the smaller you want Wi to be, right?
**[1:22]** Because z is the sum of the WiXi. And
**[1:25]** so if you're adding up a lot of these terms, you want each of these terms to be smaller.
**[1:30]** One reasonable thing to do would be to set the variance of W to be equal to 1 over n,
**[1:41]** where n is the number of input features that's going into a neuron.
**[1:45]** So in practice, what you can do is set the weight matrix W for a certain layer
**[1:51]** to be np.random.randn you know,
**[1:58]** and then whatever the shape of the matrix is for this out here,
**[2:02]** and then times square root of 1
**[2:06]** over the number of features that I fed into each neuron in layer l.
**[2:12]** So there's going to be n(l-1)
**[2:14]** because that's the number of units that I'm feeding into each of the units
**[2:20]** in layer l. It turns out that if you're using
**[2:23]** a ReLu activation function that, rather than 1 over n it turns out that,
**[2:28]** set in the variance of 2 over n works a little bit better.
**[2:32]** So you often see that in initialization, especially if you're using
**[2:35]** a ReLu activation function. So if gl(z) is ReLu(z),
**[2:42]** oh and it depends on how familiar you are with random variables.
**[2:45]** It turns out that something,
**[2:46]** a Gaussian random variable and then multiplying it by a square root of this,
**[2:50]** that sets the variance to be quoted this way,
**[2:54]** to be 2 over n. And the reason I went from n to this n superscript l-1 was,
**[2:59]** in this example with logistic regression which is at
**[3:02]** n input features, but the more general case
**[3:05]** layer l would have n(l-1) inputs each of the units in that layer.
**[3:12]** So if the input features of activations are roughly mean 0 and standard variance
**[3:19]** and variance 1 then this would cause z to also
**[3:22]** take on a similar scale. And this doesn't solve,
**[3:26]** but it definitely helps reduce the vanishing,
**[3:30]** exploding gradients problem, because it's trying to set each of
**[3:33]** the weight matrices w, you know, so that it's not too much
**[3:36]** bigger than 1 and not too much less than 1 so it doesn't explode or vanish too quickly.
**[3:42]** I've just mention some other variants.
**[3:45]** The version we just described is assuming
**[3:47]** a ReLu activation function and this by a paper by her et al.
**[3:51]** A few other variants,
**[3:53]** if you are using a TanH activation function
**[3:57]** then there's a paper that shows that instead of using the constant 2,
**[4:02]** it's better use the constant 1 and so 1 over this
**[4:06]** instead of 2. And so you multiply it by the square root of this.
**[4:12]** So this square root term will replace
**[4:16]** this term and you use this if you're using a TanH activation function.
**[4:23]** This is called Xavier initialization.
**[4:26]** And another version we're taught by Yoshua Bengio and his colleagues,
**[4:30]** you might see in some papers,
**[4:32]** but is to use this formula,
**[4:36]** which you know has some other theoretical justification,
**[4:40]** but I would say if you're using a ReLu activation function,
**[4:43]** which is really the most common activation function,
**[4:46]** I would use this formula.
**[4:48]** If you're using TanH you could try this version instead, and some authors will also
**[4:53]** use this. But in practice I think all of these formulas just give you a starting point.
**[4:58]** It gives you a default value to use for the variance of
**[5:01]** the initialization of your weight matrices.
**[5:04]** If you wish the variance here,
**[5:06]** this variance parameter could be another thing that you could
**[5:09]** tune with your hyperparameters. So you could have
**[5:13]** another parameter that multiplies into this formula and tune
**[5:16]** that multiplier as part of your hyperparameter surge.
**[5:21]** Sometimes tuning the hyperparameter has a modest size effect.
**[5:26]** It's not one of the first hyperparameters I would usually try
**[5:29]** to tune, but I've also seen some problems where tuning this
**[5:33]** helps a reasonable amount. But this is usually lower down for me in terms
**[5:37]** of how important it is relative to the other hyperparameters you can tune.
**[5:42]** So I hope that gives you some intuition about the problem of vanishing or exploding
**[5:47]** gradients as well as choosing a
**[5:49]** reasonable scaling for how you initialize the weights.
**[5:52]** Hopefully that makes your weights not explode too quickly
**[5:55]** and not decay to zero too quickly, so you can
**[5:58]** train a reasonably deep network without
**[6:01]** the weights or the gradients exploding or vanishing too much.
**[6:05]** When you train deep networks, this is another trick that will help
**[6:08]** you make your neural networks trained much more quickly.
