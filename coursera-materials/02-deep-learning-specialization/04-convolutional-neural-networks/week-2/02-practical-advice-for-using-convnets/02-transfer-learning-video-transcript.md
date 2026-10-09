---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 2
section: Practical Advice for Using ConvNets
item_title: Transfer Learning
duration: 9 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/4THzO/transfer-learning
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Transfer Learning — Transcript

**[0:00]** If you're building a computer vision application rather than
**[0:04]** training the ways from scratch, from random initialization,
**[0:07]** you often make much faster progress if you download
**[0:10]** ways that someone else has already trained on
**[0:12]** the network architecture and use that as pre-training
**[0:15]** and transfer that to a new task that you might be interested in.
**[0:19]** The computer vision research community has been pretty good at posting lots of
**[0:24]** data sets on the Internet so if you hear of things like Image Net, or MS COCO,
**[0:28]** or Pascal types of data sets,
**[0:31]** these are the names of different data sets that people have post
**[0:33]** online and a lot of computer researchers have trained their algorithms on.
**[0:39]** Sometimes these training takes several weeks and might take many GP use
**[0:44]** and the fact that someone else has done
**[0:47]** this and gone through the painful high-performance search process,
**[0:50]** means that you can often download open-source ways that took someone else many weeks or
**[0:55]** months to figure out and use that as
**[0:57]** a very good initialization for your own neural network.
**[1:01]** And use transfer learning to sort of transfer knowledge from some of
**[1:05]** these very large public data sets to your own problem.
**[1:08]** Let's take a deeper look at how to do this.
**[1:11]** Let's start with the example,
**[1:13]** let's say you're building a cat detector to recognize your own pet cat.
**[1:18]** According to the internet,
**[1:22]** Tigger is a common cat name and Misty is another common cat name.
**[1:32]** Let's say your cats are called Tiger and Misty and there's also neither.
**[1:41]** You have a classification problem with three clauses.
**[1:44]** Is this picture Tigger,
**[1:46]** or is it Misty, or is it neither.
**[1:49]** And in all the case of both of you cats appearing in the picture.
**[1:53]** Now, you probably don't have a lot of pictures of Tigger
**[1:57]** or Misty so your training set will be small.
**[2:00]** What can you do?
**[2:02]** I recommend you go online and download some open-source implementation of
**[2:06]** a neural network and download not just the code but also the weights.
**[2:12]** There are a lot of networks you can download that have been trained on for example,
**[2:19]** the Init Net data sets which has a thousand different clauses so the network
**[2:25]** might have a softmax unit that outputs one of a thousand possible clauses.
**[2:31]** What you can do is then get rid of the softmax layer and create
**[2:36]** your own softmax unit that outputs Tigger or Misty or neither.
**[2:46]** In terms of the network,
**[2:48]** I'd encourage you to think of all of these layers as
**[2:52]** frozen so you freeze the parameters in
**[2:56]** all of these layers of the network and you would then just
**[3:00]** train the parameters associated with your softmax layer.
**[3:05]** Which is the softmax layer with three possible outputs,
**[3:08]** Tigger, Misty or neither.
**[3:11]** By using someone else's free trade ways,
**[3:16]** you might probably get pretty good performance on this even with a small data set.
**[3:22]** Fortunately, a lot of people learning frameworks
**[3:25]** support this mode of operation and in fact,
**[3:28]** depending on the framework it might have things like trainable parameter equals zero,
**[3:35]** you might set that for some of these early layers.
**[3:37]** In others they just say,
**[3:39]** don't train those ways or sometimes you have a parameter
**[3:42]** like freeze equals one and these are
**[3:47]** different ways and different deep learning program frameworks that let you
**[3:50]** specify whether or not to train the ways associated with particular layer.
**[3:56]** In this case, you will train
**[3:58]** only the softmax layers ways but freeze all of the earlier layers ways.
**[4:04]** One other neat trick that may help for some implementations
**[4:07]** is that because all of these early leads are frozen,
**[4:12]** there are some fixed-function that doesn't change because you're not changing it,
**[4:16]** you not training it that takes this input image acts and
**[4:20]** maps it to some set of activations in that layer.
**[4:24]** One of the trick that could speed up training is we just pre-compute that layer,
**[4:30]** the features of re-activations from that layer and just save them to disk.
**[4:36]** What you're doing is using this fixed-function,
**[4:40]** in this first part of the neural network,
**[4:43]** to take this input any image X and compute some feature vector for it and then you're
**[4:49]** training a shallow softmax model from this feature vector to make a prediction.
**[4:56]** One step that could help your computation as you just pre-compute that layers activation,
**[5:04]** for all the examples in training sets and save them to
**[5:06]** disk and then just train the softmax clause right on top of that.
**[5:10]** The advantage of the safety disk or
**[5:12]** the pre-compute method or the safety disk is that you don't need to
**[5:15]** recompute those activations everytime
**[5:19]** you take a epoch or take a post through a training set.
**[5:23]** This is what you do if you have a pretty small training set for your task.
**[5:28]** Whether you have a larger training set.
**[5:31]** One rule of thumb is if you have
**[5:33]** a larger label data set so maybe you just have a ton of pictures of Tigger,
**[5:39]** Misty as well as I guess pictures neither of them,
**[5:41]** one thing you could do is then freeze fewer layers.
**[5:45]** Maybe you freeze just these layers and then train these later layers.
**[5:52]** Although if the output layer has different clauses then you need to have
**[5:57]** your own output unit any way Tigger, Misty or neither.
**[6:04]** There are a couple of ways to do this.
**[6:07]** You could take the last few layers ways
**[6:10]** and just use that as initialization and do gradient descent
**[6:17]** from there or you can also blow away these last few layers and
**[6:22]** just use your own new hidden units and in your own final softmax outputs.
**[6:27]** Either of these matters could be worth trying.
**[6:32]** But maybe one pattern is if you have more data,
**[6:35]** the number of layers you've freeze could be smaller and then
**[6:39]** the number of layers you train on top could be greater.
**[6:43]** And the idea is that if you pick a data set and maybe have
**[6:46]** enough data not just to train a single softmax unit but to train
**[6:51]** some other size neural network that comprises
**[6:54]** the last few layers of this final network that you end up using.
**[7:00]** Finally, if you have a lot of data,
**[7:03]** one thing you might do is take this open-source network and ways and use
**[7:09]** the whole thing just as initialization and train the whole network.
**[7:15]** Although again if this was a thousand of softmax and you have just three outputs,
**[7:20]** you need your own softmax output.
**[7:23]** The output of labels you care about.
**[7:26]** But the more label data you have for
**[7:29]** your task or the more pictures you have of Tigger, Misty and neither,
**[7:33]** the more layers you could train and in the extreme case,
**[7:37]** you could use the ways you download just as
**[7:40]** initialization so they would replace
**[7:42]** random initialization and then could do gradient descent,
**[7:45]** training updating all the ways and all the layers of the network.
**[7:50]** That's transfer learning for the training of ConvNets.
**[7:54]** In practice, because the open data sets on the internet are so big and the ways you
**[8:00]** can download that someone else has spent weeks training has learned from so much data,
**[8:05]** you find that for a lot of computer vision applications,
**[8:08]** you just do much better if you download
**[8:10]** someone else's open-source ways and use that as initialization for your problem.
**[8:16]** In all the different disciplines,
**[8:18]** in all the different applications of deep learning,
**[8:21]** I think that computer vision is one where transfer learning is
**[8:25]** something that you should almost always do unless,
**[8:28]** you have an exceptionally large data set to train everything else from scratch yourself.
**[8:35]** But transfer learning is just very worth seriously considering unless you have
**[8:40]** an exceptionally large data set and a very large computation budget
**[8:43]** to train everything from scratch by yourself.
