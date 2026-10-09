---
type: video-transcript
specialization: Deep Learning Specialization
course: Structuring Machine Learning Projects
week: 2
section: End-to-end Deep Learning
item_title: Whether to use End-to-end Deep Learning
duration: 10 min
source_url: https://www.coursera.org/learn/machine-learning-projects/lecture/H56eb/whether-to-use-end-to-end-deep-learning
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Whether to use End-to-end Deep Learning — Transcript

**[0:00]** Let's say in building a machine learning system you're trying to
**[0:02]** decide whether or not to use an end-to-end approach.
**[0:05]** Let's take a look at some of the pros and cons of
**[0:08]** end-to-end deep learning so that you can come
**[0:10]** away with some guidelines on whether or
**[0:12]** not an end-to-end approach seems promising for your application.
**[0:17]** Here are some of the benefits of applying end-to-end learning.
**[0:20]** First is that end-to-end learning really just lets the data speak.
**[0:25]** So if you have enough X,Y data
**[0:29]** then whatever is the most appropriate function mapping from X to Y,
**[0:33]** if you train a big enough neural network,
**[0:35]** hopefully the neural network will figure it out.
**[0:38]** And by having a pure machine learning approach,
**[0:41]** your neural network learning input from X to Y may be
**[0:44]** more able to capture whatever statistics are in the data,
**[0:48]** rather than being forced to reflect human preconceptions.
**[0:52]** So for example, in the case of speech recognition
**[0:55]** earlier speech systems had this notion of
**[0:58]** a phoneme which was a basic unit of sound like C,
**[1:01]** A, and T for the word cat.
**[1:04]** And I think that phonemes are an artifact created by human linguists.
**[1:09]** I actually think that phonemes are a fantasy of
**[1:12]** linguists that are a reasonable description of language,
**[1:15]** but it's not obvious that you want to force your learning algorithm to think in phonemes.
**[1:21]** And if you let your learning algorithm learn whatever representation it wants to
**[1:25]** learn rather than forcing your learning algorithm to use phonemes as a representation,
**[1:30]** then its overall performance might end up being better.
**[1:34]** The second benefit to end-to-end deep learning is
**[1:37]** that there's less hand designing of components needed.
**[1:40]** And so this could also simplify your design work flow,
**[1:43]** that you just don't need to spend a lot of time hand designing features,
**[1:47]** hand designing these intermediate representations.
**[1:51]** How about the disadvantages.
**[1:52]** Here are some of the cons.
**[1:54]** First, it may need a large amount of data.
**[1:57]** So to learn this X to Y mapping directly,
**[2:00]** you might need a lot of data of X,
**[2:03]** Y and we were seeing in a previous video some examples of
**[2:06]** where you could obtain a lot of data for subtasks.
**[2:10]** Such as for face recognition,
**[2:13]** we could find a lot data for finding a face in the image,
**[2:17]** as well as identifying the face once you found a face,
**[2:20]** but there was just less data available for the entire end-to-end task.
**[2:24]** So X, this is the input end of the end-to-end learning and Y is the output end.
**[2:32]** And so you need all the data X Y with
**[2:36]** both the input end and the output end in order to train these systems,
**[2:40]** and this is why we call it end-to-end learning value as well because you're learning
**[2:45]** a direct mapping from one end of the system all the way to the other end of the system.
**[2:52]** The other disadvantage is that it excludes potentially useful hand designed components.
**[2:58]** So machine learning researchers tend to speak disparagingly of hand designing things.
**[3:04]** But if you don't have a lot of data,
**[3:06]** then your learning algorithm doesn't have
**[3:09]** that much insight it can gain from your data if your training set is small.
**[3:13]** And so hand designing a component can really be a way for
**[3:17]** you to inject manual knowledge into the algorithm,
**[3:21]** and that's not always a bad thing.
**[3:24]** I think of a learning algorithm as having two main sources of knowledge.
**[3:28]** One is the data and the other is whatever you hand design,
**[3:33]** be it components, or features, or other things.
**[3:37]** And so when you have a ton of data it's less
**[3:39]** important to hand design things but when you don't have much data,
**[3:44]** then having a carefully hand-designed system can actually allow humans to inject
**[3:49]** a lot of knowledge about the problem
**[3:51]** into an algorithm deck and that should be very helpful.
**[3:54]** So one of the downsides of end-to-end deep learning is
**[3:58]** that it excludes potentially useful hand-designed components.
**[4:02]** And hand-designed components could be very helpful if well designed.
**[4:06]** They could also be harmful if it really limits your performance,
**[4:09]** such as if you force an algorithm to think in phonemes
**[4:12]** when maybe it could have discovered a better representation by itself.
**[4:16]** So it's kind of a double edged sword that could
**[4:19]** hurt or help but it does tend to help more,
**[4:21]** hand-designed components tend to help more when you're training on a small training set.
**[4:26]** So if you're building a new machine learning system and you're trying to
**[4:29]** decide whether or not to use end-to-end deep learning,
**[4:32]** I think the key question is,
**[4:34]** do you have sufficient data to learn the function of
**[4:37]** the complexity needed to map from X to Y?
**[4:41]** I don't have a formal definition of this phrase,
**[4:44]** complexity needed, but intuitively,
**[4:49]** if you're trying to learn a function from X to Y,
**[4:52]** that is looking at an image like this
**[4:54]** and recognizing the position of the bones in this image,
**[4:57]** then maybe this seems like a relatively simple problem to
**[5:01]** identify the bones of the image and maybe they'll need that much data for that task.
**[5:06]** Or given a picture of a person,
**[5:12]** maybe finding the face of that person in the image doesn't seem like that hard a problem,
**[5:18]** so maybe you don't need too much data to find the face of a person.
**[5:23]** Or at least maybe you can find enough data to solve that task, whereas in contrast,
**[5:28]** the function needed to look at the hand and map that directly to the age of a child,
**[5:34]** that seems like a much more complex problem that intuitively maybe you need
**[5:38]** more data to learn if you were to apply a pure end-to-end deep learning approach.
**[5:45]** So let me finish this video with a more complex example.
**[5:50]** You may know that I've been spending time helping out
**[5:52]** an autonomous driving company, Drive.ai.
**[5:55]** So I'm actually very excited about autonomous driving.
**[6:00]** So how do you build a car that drives itself?
**[6:03]** Well, here's one thing you could do,
**[6:06]** and this is not an end-to-end deep learning approach.
**[6:08]** You can take as input an image of what's in front of your car, maybe radar, lidar,
**[6:15]** other sensor readings as well,
**[6:17]** but to simplify the description,
**[6:20]** let's just say you take a picture of what's in front or what's around your car.
**[6:24]** And then to drive your car safely you need to detect
**[6:28]** other cars and you also need to detect pedestrians.
**[6:33]** You need to detect other things, of course,
**[6:35]** but we'll just present a simplified example here.
**[6:39]** Having figured out where are the other cars and pedestrians,
**[6:42]** you then need to plan your own route.
**[6:48]** So in other words,
**[6:50]** if you see where are the other cars,
**[6:54]** where are the pedestrians, you need to decide how to steer your own car,
**[6:58]** what path to steer your own car for the next several seconds.
**[7:02]** And having decided that you're going to drive a certain path,
**[7:08]** maybe this is a top down view of a road and that's your car.
**[7:14]** Maybe you've decided to drive that path,
**[7:17]** that's what the path or what the route is,
**[7:18]** then you need to execute this by generating the appropriate steering,
**[7:25]** as well as acceleration and braking commands.
**[7:28]** So in going from your image or your sensory inputs to detecting cars and pedestrians,
**[7:34]** that can be done pretty well using deep learning,
**[7:37]** but then having figured out where the other cars and pedestrians are going,
**[7:40]** to select this route to exactly how you want to move your car,
**[7:45]** usually that's not to done with deep learning.
**[7:47]** Instead that's done with a piece of software called Motion Planning.
**[7:51]** And if you ever take a course in robotics you'll learn about motion planning.
**[7:55]** And then having decided what's the path you want to steer your car through,
**[7:59]** there'll be some other algorithm,
**[8:00]** we're going to say it's a control algorithm that then generates the exact decision,
**[8:06]** that then decides exactly how much to turn
**[8:09]** the steering wheel and how much to step on the accelerator or step on the brake.
**[8:13]** So I think what this example illustrates is that
**[8:16]** you want to use machine learning or use deep learning to learn
**[8:21]** some individual components and when applying supervised learning you should
**[8:30]** carefully choose what types of X to Y mappings you want to
**[8:37]** learn depending on what task
**[8:44]** you can get data for.
**[8:48]** And in contrast, it is exciting to talk about
**[8:51]** a pure end-to-end deep learning approach where you input
**[8:54]** an image and directly output a steering.
**[8:57]** But given data availability
**[9:04]** and the types of things we can learn with neural networks today,
**[9:08]** this is actually not the most promising approach or this is
**[9:12]** not an approach that I think teams have gotten to work best.
**[9:18]** And I think this pure end-to-end deep learning approach is actually
**[9:22]** less promising than more sophisticated approaches like this,
**[9:27]** given the availability of data and our ability to train neural networks today.
**[9:32]** So that's it for end-to-end deep learning.
**[9:35]** It can sometimes work really well but you also have to be
**[9:38]** mindful of where you apply end-to-end deep learning.
**[9:42]** Finally, thank you and congrats on making it this far with me.
**[9:46]** If you finish last week's videos and this week's videos then I
**[9:50]** think you will already be much smarter and much more strategic
**[9:53]** and much more able to make good prioritization decisions in
**[9:57]** terms of how to move forward on your machine learning project,
**[10:01]** even compared to a lot of machine learning engineers
**[10:03]** and researchers that I see here in Silicon Valley.
**[10:06]** So congrats on all that you've learned so far and I hope you now also take a look at
**[10:11]** this week's homework problems which should give you
**[10:13]** another opportunity to practice these ideas and make sure that you're mastering them.
