---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 4
section: Deep Neural Network
item_title: Deep L-layer Neural Network
duration: 6 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/7dP6E/deep-l-layer-neural-network
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Deep L-layer Neural Network — Transcript

**[0:00]** Welcome to the fourth week of this course.
**[0:02]** By now, you've seen forward propagation and back propagation in the context
**[0:06]** of a neural network, with a single hidden layer, as well as logistic regression, and
**[0:10]** you've learned about vectorization, and
**[0:13]** when it's important to initialize the ways randomly.
**[0:15]** If you've done the past couple weeks homework, you've also implemented and
**[0:19]** seen some of these ideas work for yourself.
**[0:21]** So by now,
**[0:21]** you've actually seen most of the ideas you need to implement a deep neural network.
**[0:26]** What we're going to do this week, is take those ideas and put them together so
**[0:30]** that you'll be able to implement your own deep neural network.
**[0:33]** Because this week's problem exercise is longer,
**[0:36]** it just has been more work, I'm going to keep the videos for
**[0:39]** this week shorter as you can get through the videos a little bit more quickly, and
**[0:43]** then have more time to do a significant problem exercise at then end, which I hope
**[0:48]** will leave you having thoughts deep in neural network, that if you feel proud of.
**[0:52]** So what is a deep neural network?
**[0:55]** You've seen this picture for logistic regression and
**[0:59]** you've also seen neural networks with a single hidden layer.
**[1:03]** So here's an example of a neural network with two hidden layers and
**[1:07]** a neural network with 5 hidden layers.
**[1:10]** We say that logistic regression is a very "shallow" model,
**[1:15]** whereas this model here is a much deeper model, and
**[1:19]** shallow versus depth is a matter of degree.
**[1:23]** So neural network of a single hidden layer,
**[1:26]** this would be a 2 layer neural network.
**[1:30]** Remember when we count layers in a neural network, we don't count the input layer,
**[1:34]** we just count the hidden layers as was the output layer.
**[1:38]** So, this would be a 2 layer neural network is still quite shallow,
**[1:42]** but not as shallow as logistic regression.
**[1:45]** Technically logistic regression is a one layer neural network,
**[1:50]** we could then, but over the last several years the AI,
**[1:53]** on the machine learning community, has realized that there are functions that
**[1:58]** very deep neural networks can learn that shallower models are often unable to.
**[2:03]** Although for any given problem, it might be hard to predict in advance exactly how
**[2:08]** deep in your network you would want.
**[2:10]** So it would be reasonable to try logistic regression, try one and
**[2:14]** then two hidden layers, and view the number of hidden layers as another hyper
**[2:19]** parameter that you could try a variety of values of, and
**[2:22]** evaluate on all that across validation data, or on your development set.
**[2:27]** See more about that later as well.
**[2:29]** Let's now go through the notation we used to describe deep neural networks.
**[2:33]** Here's is a one, two, three, four layer neural network,
**[2:40]** With three hidden layers, and the number of units in these hidden
**[2:45]** layers are I guess 5, 5, 3, and then there's one one upper unit.
**[2:50]** So the notation we're going to use,
**[2:52]** is going to use capital L ,to denote the number of layers in the network.
**[2:56]** So in this case, L = 4, and so does the number of layers, and
**[3:03]** we're going to use N superscript [l] to denote the number of nodes,
**[3:11]** or the number of units in layer lowercase l.
**[3:17]** So if we index this, the input as layer "0".
**[3:22]** This is layer 1, this is layer 2, this is layer 3, and this is layer 4.
**[3:28]** Then we have that, for example, n[1], that would be this,
**[3:33]** the first is in there will equal 5, because we have 5 hidden units there.
**[3:39]** For this one, we have the n[2],
**[3:43]** the number of units in the second hidden layer
**[3:48]** is also equal to 5, n[3] = 3, and
**[3:53]** n[4] = n[L] this number of upper units is 01,
**[3:59]** because your capital L is equal to four,
**[4:04]** and we're also going to have here that for
**[4:08]** the input layer n[0] = nx = 3.
**[4:13]** So that's the notation we use to describe the number of nodes we have in different
**[4:17]** layers.
**[4:18]** For each layer L, we're also going to use
**[4:23]** a[l] to denote the activations in layer l.
**[4:30]** So we'll see later that in for propagation,
**[4:34]** you end up computing a[l] as the activation g(z[l]) and
**[4:40]** perhaps the activation is indexed by the layer l as well,
**[4:46]** and then we'll use W[l ]to denote, the weights for
**[4:51]** computing the value z[l] in layer l, and
**[4:55]** similarly, b[l] is used to compute z [l].
**[5:00]** Finally, just to wrap up on the notation, the input features are called x,
**[5:07]** but x is also the activations of layer zero, so a[0] = x,
**[5:12]** and the activation of the final layer, a[L] = y-hat.
**[5:17]** So a[L] is equal to the predicted output to prediction y-hat to the neural network.
**[5:25]** So you now know what a deep neural network looks like,
**[5:28]** as was the notation we'll use to describe and to compute with deep networks.
**[5:32]** I know we've introduced a lot of notation in this video, but if you ever forget
**[5:36]** what some symbol means, we've also posted on the course website, a notation sheet or
**[5:40]** a notation guide, that you can use to look up what these different symbols mean.
**[5:45]** Next, I'd like to describe what forward propagation in this type of network
**[5:48]** looks like.
**[5:49]** Let's go into the next video.
