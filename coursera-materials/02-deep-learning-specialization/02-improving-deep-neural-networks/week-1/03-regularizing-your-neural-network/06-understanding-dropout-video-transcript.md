---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 1
section: Regularizing your Neural Network
item_title: Understanding Dropout
duration: 7 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/YaGbR/understanding-dropout
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Understanding Dropout — Transcript

**[0:00]** Drop out.
**[0:00]** Does this seemingly crazy thing of randomly knocking out units in your network?
**[0:05]** Why does it work?
**[0:06]** So as a regulizer, let's give some better intuition.
**[0:10]** In the previous video,
**[0:12]** I gave this intuition that drop out randomly knocks out units in your network.
**[0:16]** So it's as if on every iteration you're working with a smaller neural network.
**[0:20]** And so using a smaller neural network seems like it
**[0:23]** should have a regularizing effect.
**[0:26]** Here's the second intuition which is, you know,
**[0:29]** let's look at it from the perspective of a single unit.
**[0:33]** Right, let's say this one. Now for this unit to do his job has four inputs and
**[0:38]** it needs to generate some meaningful output.
**[0:41]** Now with drop out, the inputs can get randomly eliminated.
**[0:45]** You know, sometimes those two units will get eliminated.
**[0:48]** Sometimes a different unit will get eliminated.
**[0:50]** So what this means is that this unit which I'm circling purple.
**[0:54]** It can't rely on anyone feature because anyone feature could go away at random or
**[1:00]** anyone of its own inputs could go away at random.
**[1:03]** So in particular,
**[1:05]** I will be reluctant to put all of its bets on say just this input, right.
**[1:10]** The ways were reluctant to put too much weight on anyone input because it could
**[1:15]** go away.
**[1:15]** So this unit will be more motivated to spread out this ways and
**[1:20]** give you a little bit of weight to each of the four inputs to this unit.
**[1:26]** And by spreading out the weights this will tend to have an effect
**[1:31]** of shrinking the squared norm of the weights,
**[1:34]** and so similar to what we saw with L2 regularization.
**[1:38]** The effect of implementing dropout is that its strength the ways and
**[1:42]** similar to L2 regularization, it helps to prevent overfitting, but it turns out that
**[1:47]** dropout can formally be shown to be an adaptive form of L2 regularization,
**[1:51]** but the L2 penalty on different ways are different depending on the size of
**[1:55]** the activation is being multiplied into that way.
**[1:58]** But to summarize it is possible to show that dropout has a similar effect to.
**[2:05]** L2 regularization.
**[2:06]** Only the L2 regularization applied to different ways can be a little bit
**[2:10]** different and even more adaptive to the scale of different inputs.
**[2:13]** One more detail for when you're implementing dropout,
**[2:16]** here's a network where you have three input features.
**[2:19]** This is seven hidden units here.
**[2:21]** 7, 3, 2, 1, so one of the practice we have to choose was
**[2:26]** the keep prop which is a chance of keeping a unit in each layer.
**[2:31]** So it is also feasible to vary keep-propped by layer.
**[2:36]** So for the first layer, your matrix W1 will be 7 by 3.
**[2:42]** Your second weight matrix will be 7 by 7.
**[2:46]** W3 will be 3 by 7 and so on.
**[2:50]** And so W2 is actually the biggest weight matrix, right?
**[2:53]** Because they're actually the largest set of parameters.
**[2:56]** B and W2, which is 7 by 7.
**[2:58]** So to prevent, to reduce overfitting of that matrix, maybe for this layer,
**[3:03]** I guess this is layer 2, you might have a key prop that's relatively low,
**[3:07]** say 0.5, whereas for different layers where you might worry less about over 15,
**[3:13]** you could have a higher key problem.
**[3:15]** Maybe just 0.7, maybe this is 0.7.
**[3:20]** And then for layers we don't worry about overfitting at all.
**[3:23]** You can have a key prop of 1.0.
**[3:25]** Right?
**[3:26]** So, you know, for clarity, these are numbers I'm drawing in the purple boxes.
**[3:31]** These could be different key props for different layers.
**[3:35]** Notice that the key problem 1.0 means that you're keeping every unit.
**[3:38]** And so you're really not using drop out for that layer.
**[3:42]** But for layers where you're more worried about overfitting really the layers with
**[3:47]** a lot of parameters you could say keep prop to be smaller to apply a more
**[3:50]** powerful form of dropout.
**[3:52]** It's kind of like cranking up the regularization.
**[3:54]** Parameter lambda of L2 regularization where you try to regularize some layers
**[3:58]** more than others.
**[3:59]** And technically you can also apply drop out to the input layer where you can have
**[4:04]** some chance of just acting out one or more of the input features,
**[4:08]** although in practice, usually don't do that often.
**[4:11]** And so key problem of 1.0 is quite common for the input there.
**[4:15]** You might also use a very high value, maybe 0.9 but is much less likely that
**[4:20]** you want to eliminate half of the input features so usually keep prop.
**[4:24]** If you apply that all will be a number close to 1.
**[4:28]** If you even apply dropout at all to the input layer.
**[4:32]** So just to summarize if you're more worried about some layers of fitting than
**[4:36]** others, you can set a lower key prop for some layers than others.
**[4:40]** The downside is this gives you even more hyper parameters to search for
**[4:44]** using cross validation.
**[4:45]** One other alternative might be to have some layers where you apply dropout and
**[4:49]** some layers where you don't apply drop out and
**[4:51]** then just have one hyper parameter which is a key prop for the layers for which you
**[4:55]** do apply drop out and before we wrap up just a couple implantation all tips.
**[4:59]** Many of the first successful implementations of dropouts were to
**[5:03]** computer vision, so in computer vision, the input sizes so
**[5:07]** big in putting all these pixels that you almost never have enough data.
**[5:11]** And so drop out is very frequently used by the computer vision and there are some
**[5:15]** common vision research is that pretty much always use it almost as a default.
**[5:20]** But really, the thing to remember is that drop out is a regularization technique,
**[5:25]** it helps prevent overfitting.
**[5:27]** And so unless my avram is overfitting, I wouldn't actually bother to use drop out.
**[5:34]** So as you somewhat less often in other application areas,
**[5:37]** there's just a computer vision, you usually just don't have enough data so
**[5:41]** you almost always overfitting, which is why they tend to be some
**[5:44]** computer vision researchers swear by drop out by the intuition.
**[5:47]** I was, doesn't always generalize, I think to other disciplines.
**[5:52]** One big downside of drop out is that the cost function
**[5:57]** J is no longer well defined on every iteration.
**[6:02]** You're randomly, calling off a bunch of notes.
**[6:07]** And so if you are double checking the performance of great inter sent is
**[6:11]** actually harder to double check that, right?
**[6:14]** You have a well defined cost function J.
**[6:17]** That is going downhill on every elevation because the cost function J.
**[6:22]** That you're optimizing is actually less.
**[6:25]** Less well defined or it's certainly hard to calculate.
**[6:27]** So you lose this debugging tool to have a plot a draft like this.
**[6:32]** So what I usually do is turn off drop out or if you will set keep-propped = 1 and
**[6:37]** run my code and make sure that it is monitored quickly decreasing J.
**[6:41]** And then turn on drop out and hope that, I didn't introduce,
**[6:45]** welcome to my code during drop out because you need other ways, I guess, but
**[6:49]** not plotting these figures to make sure that your code is working,
**[6:53]** the greatest is working even with drop out.
**[6:56]** So with that there's still a few more regularization techniques that were
**[7:01]** feel knowing.
**[7:02]** Let's talk about a few more such techniques in the next video.
