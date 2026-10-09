---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 1
section: Setting Up your Optimization Problem
item_title: Vanishing / Exploding Gradients
duration: 6 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/C9iQO/vanishing-exploding-gradients
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Vanishing / Exploding Gradients — Transcript

**[0:00]** One of the problems of training neural network,
**[0:02]** especially very deep neural networks,
**[0:04]** is data vanishing and exploding gradients.
**[0:07]** What that means is that when you're training
**[0:09]** a very deep network your derivatives or your slopes can sometimes get either very,
**[0:13]** very big or very, very small,
**[0:15]** maybe even exponentially small,
**[0:17]** and this makes training difficult.
**[0:19]** In this video you see what this problem of
**[0:21]** exploding and vanishing gradients really means,
**[0:25]** as well as how you can use careful choices of
**[0:28]** the random weight initialization to significantly reduce this problem.
**[0:32]** Unless you're training a very deep neural network like this,
**[0:36]** to save space on the slide,
**[0:37]** I've drawn it as if you have only two hidden units per layer,
**[0:40]** but it could be more as well.
**[0:42]** But this neural network will have parameters W1,
**[0:45]** W2, W3 and so on up to WL.
**[0:51]** For the sake of simplicity,
**[0:53]** let's say we're using an activation function G of Z equals Z,
**[0:56]** so linear activation function.
**[0:58]** And let's ignore B, let's say B of L equals zero.
**[1:02]** So in that case you can show that the output Y will be
**[1:07]** WL times WL minus one times WL minus two,
**[1:13]** dot, dot, dot down to the W3,
**[1:18]** W2, W1 times X.
**[1:21]** But if you want to just check my math,
**[1:23]** W1 times X is going to be Z1,
**[1:27]** because B is equal to zero.
**[1:30]** So Z1 is equal to, I guess,
**[1:33]** W1 times X and then plus B which is zero.
**[1:37]** But then A1 is equal to G of Z1.
**[1:42]** But because we use linear activation function,
**[1:45]** this is just equal to Z1.
**[1:47]** So this first term W1X is equal to A1.
**[1:50]** And then by the reasoning you can figure out that W2 times W1 times X is equal to A2,
**[1:57]** because that's going to be G of Z2,
**[2:00]** is going to be G of
**[2:03]** W2 times A1 which you can plug that in here.
**[2:12]** So this thing is going to be equal to A2,
**[2:16]** and then this thing is going to be
**[2:21]** A3 and so on until the protocol of all these matrices gives you Y-hat, not Y.
**[2:29]** Now, let's say that each of you weight matrices
**[2:33]** WL is just a little bit larger than one times the identity.
**[2:39]** So it's 1.5_1.5_0_0.
**[2:43]** Technically, the last one has different dimensions so
**[2:46]** maybe this is just the rest of these weight matrices.
**[2:49]** Then Y-hat will be,
**[2:51]** ignoring this last one with different dimension,
**[2:54]** this 1.5_0_0_1.5 matrix to the power of L minus 1 times X,
**[3:01]** because we assume that each one of these matrices is equal to this thing.
**[3:08]** It's really 1.5 times the identity matrix, then you end up with this calculation.
**[3:12]** And so Y-hat will be essentially 1.5 to the power of L,
**[3:19]** to the power of L minus 1 times X,
**[3:21]** and if L was large for very deep neural network,
**[3:24]** Y-hat will be very large.
**[3:26]** In fact, it just grows exponentially,
**[3:28]** it grows like 1.5 to the number of layers.
**[3:32]** And so if you have a very deep neural network,
**[3:34]** the value of Y will explode.
**[3:36]** Now, conversely, if we replace this with 0.5,
**[3:40]** so something less than 1,
**[3:42]** then this becomes 0.5 to the power of L.
**[3:45]** This matrix becomes 0.5 to the L minus one times X, again ignoring WL.
**[3:51]** And so each of your matrices are less than 1,
**[3:57]** then let's say X1, X2 were one one,
**[4:00]** then the activations will be one half,
**[4:02]** one half, one fourth,
**[4:04]** one fourth, one eighth, one eighth,
**[4:07]** and so on until this becomes one over two to the L. So
**[4:11]** the activation values will decrease exponentially as a function of the def,
**[4:16]** as a function of the number of layers L of the network.
**[4:19]** So in the very deep network, the activations end up decreasing exponentially.
**[4:26]** So the intuition I hope you can take away from this is that at the weights W,
**[4:30]** if they're all just a little bit bigger than one
**[4:33]** or just a little bit bigger than the identity matrix,
**[4:36]** then with a very deep network the activations can explode.
**[4:41]** And if W is just a little bit less than identity.
**[4:45]** So this maybe here's 0.9, 0.9,
**[4:49]** then you have a very deep network,
**[4:50]** the activations will decrease exponentially.
**[4:53]** And even though I went through this argument in terms of
**[4:56]** activations increasing or decreasing exponentially as a function of L,
**[5:00]** a similar argument can be used to show that
**[5:03]** the derivatives or the gradients the computer is going to send
**[5:05]** will also increase exponentially
**[5:08]** or decrease exponentially as a function of the number of layers.
**[5:11]** With some of the modern neural networks, L equals 150.
**[5:16]** Microsoft recently got great results with 152 layer neural network.
**[5:19]** But with such a deep neural network,
**[5:22]** if your activations or gradients increase or decrease exponentially as a function of L,
**[5:27]** then these values could get really big or really small.
**[5:31]** And this makes training difficult,
**[5:33]** especially if your gradients are exponentially smaller than L,
**[5:36]** then gradient descent will take tiny little steps.
**[5:40]** It will take a long time for gradient descent to learn anything.
**[5:44]** To summarize, you've seen how deep networks suffer from
**[5:47]** the problems of vanishing or exploding gradients.
**[5:50]** In fact, for a long time this problem was
**[5:52]** a huge barrier to training deep neural networks.
**[5:56]** It turns out there's a partial solution that doesn't completely solve
**[5:59]** this problem but it helps a lot which is
**[6:01]** careful choice of how you initialize the weights.
**[6:04]** To see that, let's go to the next video.
