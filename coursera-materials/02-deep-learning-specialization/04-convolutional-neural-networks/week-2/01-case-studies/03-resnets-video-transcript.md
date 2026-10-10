---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 2
section: Case Studies
item_title: ResNets
duration: 7 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/HAhz9/resnets
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# ResNets — Transcript

**[0:00]** Very, very deep neural networks are difficult to train, because
**[0:03]** of vanishing and exploding gradient types of problems.
**[0:07]** In this video, you'll learn about
**[0:08]** skip connections which allows you to take the activation from
**[0:12]** one layer and suddenly feed it to another layer even much deeper in the neural network.
**[0:17]** And using that, you'll build ResNet which enables you to train very, very deep networks.
**[0:22]** Sometimes even networks of over 100 layers. Let's take a look.
**[0:26]** ResNets are built out of something called a residual block,
**[0:30]** let's first describe what that is.
**[0:33]** Here are two layers of a neural network where you
**[0:35]** start off with some activations in layer a[l],
**[0:38]** then goes a[l+1] and then deactivation two layers later is a[l+2].
**[0:43]** So let's to through the steps in this computation you have a[l],
**[0:48]** and then the first thing you do is you apply this linear operator to it,
**[0:54]** which is governed by this equation.
**[0:57]** So you go from a[l] to compute z[l
**[1:01]** +1] by multiplying by the weight matrix and adding that bias vector.
**[1:07]** After that, you apply the ReLU nonlinearity, to get a[l+1].
**[1:17]** And that's governed by this equation where a[l+1] is g(z[l+1]).
**[1:24]** Then in the next layer,
**[1:26]** you apply this linear step again,
**[1:30]** so is governed by that equation.
**[1:33]** So this is quite similar to this equation we saw on the left.
**[1:38]** And then finally, you apply another ReLU operation which is
**[1:43]** now governed by that equation where G here would be the ReLU nonlinearity.
**[1:52]** And this gives you a[l+2].
**[1:56]** So in other words,
**[1:57]** for information from a[l] to flow to a[l+2],
**[2:03]** it needs to go through all of these steps which I'm going to call
**[2:07]** the main path of this set of layers.
**[2:13]** In a residual net,
**[2:14]** we're going to make a change to this.
**[2:16]** We're going to take a[l],
**[2:18]** and just first forward it, copy it,
**[2:22]** match further into the neural network to here,
**[2:26]** and just at a[l],
**[2:28]** before applying to non-linearity, the ReLU non-linearity.
**[2:34]** And I'm going to call this the shortcut.
**[2:37]** So rather than needing to follow the main path,
**[2:40]** the information from a[l] can now follow
**[2:43]** a shortcut to go much deeper into the neural network.
**[2:46]** And what that means is that this last equation
**[2:49]** goes away and we instead have that the output
**[2:52]** a[l+2] is the ReLU non-linearity g applied to z[l+2] as before,
**[3:00]** but now plus a[l].
**[3:02]** So, the addition of this a[l] here,
**[3:05]** it makes this a residual block.
**[3:07]** And in pictures, you can also modify this picture on
**[3:11]** top by drawing this picture shortcut to go here.
**[3:15]** And we are going to draw it as it going into this second layer here
**[3:20]** because the short cut is actually added before the ReLU non-linearity.
**[3:26]** So each of these nodes here,
**[3:27]** where there applies a linear function and a ReLU.
**[3:30]** So a[l] is being injected after the linear part but before the ReLU part.
**[3:34]** And sometimes instead of a term short cut,
**[3:37]** you also hear the term skip connection,
**[3:40]** and that refers to a[l] just skipping over a layer or kind of skipping over
**[3:44]** almost two layers in order to process information deeper into the neural network.
**[3:51]** So, what the inventors of ResNet,
**[3:54]** so that'll will be Kaiming He, Xiangyu Zhang,
**[3:55]** Shaoqing Ren and Jian Sun.
**[3:58]** What they found was that using residual blocks
**[4:02]** allows you to train much deeper neural networks.
**[4:05]** And the way you build a ResNet is by taking many of these residual blocks,
**[4:10]** blocks like these, and stacking them together to form a deep network.
**[4:15]** So, let's look at this network.
**[4:18]** This is not the residual network,
**[4:19]** this is called as a plain network.
**[4:22]** This is the terminology of the ResNet paper.
**[4:26]** To turn this into a ResNet,
**[4:28]** what you do is you add all those
**[4:31]** skip connections although those short like a connections like so.
**[4:36]** So every two layers ends up with
**[4:39]** that additional change that we saw on
**[4:44]** the previous slide to turn each of these into residual block.
**[4:49]** So this picture shows five residual blocks stacked together,
**[4:53]** and this is a residual network.
**[4:56]** And it turns out that if you use
**[4:59]** your standard optimization algorithm such as
**[5:02]** a gradient descent or one of
**[5:04]** the fancier optimization algorithms to the train or plain network.
**[5:07]** So without all the extra residual,
**[5:10]** without all the extra short cuts or skip connections I just drew in.
**[5:14]** Empirically, you find that as you increase the number of layers,
**[5:18]** the training error will tend to decrease after
**[5:21]** a while but then they'll tend to go back up.
**[5:24]** And in theory as you make a neural network deeper,
**[5:29]** it should only do better and better on the training set.
**[5:32]** Right. So, the theory, in theory,
**[5:35]** having a deeper network should only help.
**[5:37]** But in practice or in reality,
**[5:40]** having a plain network, so no ResNet,
**[5:42]** having a plain network that is very deep means that
**[5:45]** all your optimization algorithm just has a much harder time training.
**[5:50]** And so, in reality,
**[5:51]** your training error gets worse if you pick a network that's too deep.
**[5:55]** But what happens with ResNet is that even as the number of layers gets deeper,
**[6:01]** you can have the performance of the training error kind of keep on going down.
**[6:06]** Even if we train a network with over a hundred layers.
**[6:10]** And then now some people experimenting with networks of
**[6:12]** over a thousand layers although I don't see that it used much in practice yet.
**[6:17]** But by taking these activations be it X or
**[6:20]** these intermediate activations and allowing it to go much deeper in the neural network,
**[6:24]** this really helps with the vanishing and exploding gradient problems
**[6:30]** and allows you to train
**[6:31]** much deeper neural networks without really appreciable loss in performance,
**[6:36]** and maybe at some point, this will plateau, this will flatten out,
**[6:39]** and it doesn't help that much deeper and deeper networks.
**[6:43]** But ResNet is not even effective at helping train very deep networks.
**[6:49]** So you've now gotten an overview of how ResNets work.
**[6:52]** And in fact, in this week's programming exercise,
**[6:55]** you get to implement these ideas and see it work for yourself.
**[6:59]** But next, I want to share with you better intuition or
**[7:02]** even more intuition about why ResNets work so well,
**[7:06]** let's go onto the next video.
