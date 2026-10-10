---
type: video-transcript
specialization: Deep Learning Specialization
course: Structuring Machine Learning Projects
week: 2
section: Learning from Multiple Tasks
item_title: Transfer Learning
duration: 11 min
source_url: https://www.coursera.org/learn/machine-learning-projects/lecture/WNPap/transfer-learning
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Transfer Learning — Transcript

**[0:00]** One of the most powerful ideas in deep learning is that sometimes you can take knowledge
**[0:05]** the neural network has learned from one task and apply that knowledge to a separate task.
**[0:10]** So for example, maybe you could have the neural network
**[0:12]** learn to recognize objects like cats and then use
**[0:15]** that knowledge or use part of that knowledge to
**[0:18]** help you do a better job reading x-ray scans.
**[0:21]** This is called transfer learning. Let's take a look.
**[0:24]** Let's say you've trained your neural network on image recognition.
**[0:30]** So you first take a neural network and train it on X Y pairs,
**[0:34]** where X is an image and Y is some object.
**[0:37]** An image is a cat or a dog or a bird or something else.
**[0:41]** If you want to take this neural network and adapt,
**[0:43]** or we say transfer,
**[0:45]** what is learned to a different task,
**[0:47]** such as radiology diagnosis,
**[0:51]** meaning really reading X-ray scans,
**[0:54]** what you can do is take this last output layer of the neural network and
**[0:59]** just delete that and delete also the weights feeding into that last output layer
**[1:03]** and create a new set of randomly initialized weights just for the last layer
**[1:08]** and have that now output radiology diagnosis.
**[1:15]** So to be concrete, during the first phase of
**[1:17]** training when you're training on an image recognition task,
**[1:19]** you train all of the usual parameters for the neural network, all the weights,
**[1:23]** all the layers and you have something that
**[1:27]** now learns to make image recognition predictions.
**[1:32]** Having trained that neural network,
**[1:35]** what you now do to implement transfer learning is swap in a new data set X Y,
**[1:41]** where now these are radiology images.
**[1:47]** And Y are the diagnoses you want to
**[1:50]** predict and what you do is initialize the last layers' weights.
**[1:58]** Let's call that W.L.
**[2:00]** and P.L. randomly.
**[2:02]** And now, retrain the neural network on this new data set,
**[2:07]** on the new radiology data set.
**[2:09]** You have a couple options of how you retrain the neural network with radiology data.
**[2:14]** You might, if you have a small radiology dataset,
**[2:16]** you might want to just retrain the weights of the last layer, just W.L.
**[2:20]** P.L., and keep the rest of the parameters fixed.
**[2:22]** If you have enough data,
**[2:23]** you could also retrain all the layers of the rest of the neural network.
**[2:27]** And the rule of thumb is maybe if you have a small data set,
**[2:32]** then just retrain the one last layer at the output layer.
**[2:35]** Or maybe that last one or two layers.
**[2:37]** But if you have a lot of data,
**[2:38]** then maybe you can retrain all the parameters in the network.
**[2:42]** And if you retrain all the parameters in the neural network,
**[2:45]** then this initial phase of training on
**[2:49]** image recognition is sometimes called pre-training,
**[2:53]** because you're using image recognitions data
**[2:57]** to pre-initialize or really pre-train the weights of the neural network.
**[3:01]** And then if you are updating all the weights afterwards,
**[3:04]** then training on the radiology data sometimes that's called fine tuning.
**[3:09]** So if you hear the words pre-training and fine tuning in a deep learning context,
**[3:15]** this is what they mean when they refer to
**[3:17]** pre-training and fine tuning weights in a transfer learning source.
**[3:21]** And what you've done in this example,
**[3:22]** is you've taken knowledge learned from
**[3:25]** image recognition and applied it or transferred it to radiology diagnosis.
**[3:31]** And the reason this can be helpful is that
**[3:33]** a lot of the low level features such as detecting edges,
**[3:36]** detecting curves, detecting positive objects.
**[3:39]** Learning from that, from a very large image recognition data set,
**[3:43]** might help your learning algorithm do better in radiology diagnosis.
**[3:47]** It's just learned a lot about the structure and the nature of how images
**[3:51]** look like and some of that knowledge will be useful.
**[3:56]** So having learned to recognize images,
**[3:58]** it might have learned enough about you know,
**[4:00]** just what parts of different images look like,
**[4:03]** that that knowledge about lines,
**[4:05]** dots, curves, and so on,
**[4:07]** maybe small parts of objects,
**[4:09]** that knowledge could help
**[4:10]** your radiology diagnosis network learn a bit faster or learn with less data.
**[4:15]** Here's another example.
**[4:17]** Let's say that you've trained a speech recognition system so
**[4:20]** now X is input of audio or audio snippets,
**[4:24]** and Y is some ink transcript.
**[4:27]** So you've trained a speech recognition system to output your transcripts.
**[4:34]** And let's say that you now want to build a "wake words" or
**[4:39]** a "trigger words" detection system.
**[4:45]** So, recall that a wake word or the trigger word are the words we say
**[4:49]** in order to wake up speech control devices in our houses such as saying
**[4:54]** "Alexa" to wake up an Amazon Echo or "OK Google" to wake up a Google device or
**[4:58]** "hey Siri" to wake up an Apple device or saying "Ni hao baidu" to wake up a baidu device.
**[5:03]** So in order to do this,
**[5:05]** you might take out the last layer of
**[5:09]** the neural network again and create a new output node.
**[5:13]** But sometimes another thing you could do is actually create not just a single new output,
**[5:18]** but actually create several new layers to your neural network to try
**[5:23]** to predict the labels Y for your wake word detection problem.
**[5:28]** Then again, depending on how much data you have,
**[5:30]** you might just retrain the new layers of the network or maybe
**[5:34]** you could retrain even more layers of this neural network.
**[5:38]** So, when does transfer learning make sense?
**[5:42]** Transfer learning makes sense when you have a lot of data for the problem you're
**[5:46]** transferring from and usually
**[5:49]** relatively less data for the problem you're transferring to.
**[5:52]** So for example, let's say you have a million examples for image recognition task.
**[5:58]** So that's a lot of data to learn a lot of
**[6:00]** low level features or to learn a lot of
**[6:03]** useful features in the earlier layers in neural network.
**[6:06]** But for the radiology task,
**[6:08]** maybe you have only a hundred examples.
**[6:12]** So you have very low data for the radiology diagnosis problem,
**[6:15]** maybe only 100 x-ray scans.
**[6:17]** So a lot of knowledge you learn from image recognition can be transferred and can
**[6:23]** really help you get going with
**[6:24]** radiology recognition even if you don't have all the data for radiology.
**[6:29]** For speech recognition, maybe you've trained
**[6:31]** the speech recognition system on 10000 hours of data.
**[6:35]** So, you've learned a lot about what human voices
**[6:37]** sounds like from that 10000 hours of data, which really is a lot.
**[6:41]** But for your trigger word detection,
**[6:43]** maybe you have only one hour of data.
**[6:45]** So, that's not a lot of data to fit a lot of parameters.
**[6:48]** So in this case, a lot of what you learn about what human voices sound like,
**[6:53]** what are components of human speech and so on,
**[6:56]** that can be really helpful for building a good wake word detector,
**[7:00]** even though you have a relatively small dataset or
**[7:03]** at least a much smaller dataset for the wake word detection task.
**[7:08]** So in both of these cases,
**[7:09]** you're transferring from a problem with a lot of
**[7:11]** data to a problem with relatively little data.
**[7:15]** One case where transfer learning would not make sense,
**[7:19]** is if the opposite was true.
**[7:22]** So, if you had a hundred images for image recognition and you had
**[7:27]** 100 images for radiology diagnosis or even a thousand images for radiology diagnosis,
**[7:34]** one would think about it is that to do well on radiology diagnosis,
**[7:38]** assuming what you really want to do well on this radiology diagnosis,
**[7:41]** having radiology images is much more valuable than having cat and dog and so on images.
**[7:47]** So each example here is much more valuable than each example there,
**[7:52]** at least for the purpose of building a good radiology system.
**[7:55]** So, if you already have more data for radiology,
**[7:58]** it's not that likely that having 100 images of
**[8:01]** your random objects of cats and dogs and cars and so on will be that helpful,
**[8:06]** because the value of one example of image from your image recognition task of cats and
**[8:12]** dogs is just less valuable than one example of
**[8:15]** an x-ray image for the task of building a good radiology system.
**[8:19]** So, this would be one example where transfer learning, well,
**[8:22]** it might not hurt but I wouldn't expect it to give you any meaningful gain either.
**[8:27]** And similarly, if you'd built a speech recognition system on 10 hours of
**[8:31]** data and you actually have 10 hours or maybe even more,
**[8:34]** say 50 hours of data for wake word detection,
**[8:38]** you know it won't, it may or may not hurt,
**[8:40]** maybe it won't hurt to include that 10 hours of data to your transfer learning,
**[8:44]** but you just wouldn't expect to get a meaningful gain.
**[8:47]** So to summarize, when does transfer learning make sense?
**[8:51]** If you're trying to learn from
**[8:53]** some Task A and transfer some of the knowledge to some Task B,
**[9:00]** then transfer learning makes sense when Task A and B have the same input X.
**[9:07]** In the first example,
**[9:10]** A and B both have images as input.
**[9:12]** In the second example,
**[9:13]** both have audio clips as input.
**[9:17]** It tends to make sense when you have a lot more data for Task A than for Task B.
**[9:22]** All this is under the assumption that what you really want to do well on is Task B.
**[9:27]** And because data for Task B is more valuable for Task B,
**[9:32]** usually you just need a lot more data for Task A because you know,
**[9:36]** each example from Task A is just less valuable for Task B than each example for Task B.
**[9:43]** And then finally, transfer learning will tend to make more sense if you suspect
**[9:47]** that low level features from Task A could be helpful for learning Task B.
**[9:52]** And in both of the earlier examples,
**[9:54]** maybe learning image recognition teaches you enough about
**[9:57]** images to have a radiology diagnosis and maybe
**[9:59]** learning speech recognition teaches you about
**[10:02]** human speech to help you with trigger word or wake word detection.
**[10:06]** So to summarize, transfer learning has been most
**[10:08]** useful if you're trying to do well on some Task B,
**[10:11]** usually a problem where you have relatively little data.
**[10:14]** So for example, in radiology,
**[10:16]** you know it's difficult to get that
**[10:18]** many x-ray scans to build a good radiology diagnosis system.
**[10:21]** So in that case, you might find a related but different task,
**[10:25]** such as image recognition,
**[10:26]** where you can get maybe a million images and learn a lot of load-over features from that,
**[10:30]** so that you can then try to do well on Task B on
**[10:34]** your radiology task despite not having that much data for it.
**[10:38]** When transfer learning makes sense?
**[10:40]** It does help the performance of your learning task significantly.
**[10:43]** But I've also seen sometimes seen transfer learning applied in settings where
**[10:47]** Task A actually has less data than Task B and in those cases,
**[10:52]** you kind of don't expect to see much of a gain.
**[10:55]** So, that's it for transfer learning where you
**[10:57]** learn from one task and try to transfer to a different task.
**[11:00]** There's another version of learning from
**[11:02]** multiple tasks which is called multitask learning,
**[11:05]** which is when you try to learn from multiple tasks at
**[11:07]** the same time rather than learning from one and then sequentially,
**[11:10]** or after that, trying to transfer to a different task.
**[11:14]** So in the next video,
**[11:15]** let's discuss multitask learning.
