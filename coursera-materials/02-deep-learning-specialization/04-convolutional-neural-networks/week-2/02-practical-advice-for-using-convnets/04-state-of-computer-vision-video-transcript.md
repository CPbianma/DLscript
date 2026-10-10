---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 2
section: Practical Advice for Using ConvNets
item_title: State of Computer Vision
duration: 13 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/D9ra2/state-of-computer-vision
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# State of Computer Vision — Transcript

**[0:00]** Deep learning has been successfully
**[0:01]** applied to computer vision, natural language processing,
**[0:03]** speech recognition, online advertising,
**[0:05]** logistics, many, many, many problems.
**[0:08]** There are a few things that are unique about
**[0:10]** the application of deep learning to computer vision,
**[0:12]** about the status of computer vision.
**[0:15]** In this video, I will share with you some of my observations about deep learning
**[0:20]** for computer vision and I hope that that will help you better navigate the literature,
**[0:25]** and the set of ideas out there,
**[0:27]** and how you build these systems yourself for computer vision.
**[0:31]** So, you can think of most machine learning problems as falling somewhere on
**[0:38]** the spectrum between where you have relatively little data
**[0:40]** to where you have lots of data.
**[0:45]** So for example, I think that today we have a decent amount of
**[0:50]** data for speech recognition and it's relative to the complexity of the problem.
**[0:57]** And even though there are
**[0:59]** reasonably large data sets today for image recognition or image classification,
**[1:05]** because image recognition is
**[1:07]** just a complicated problem to look at all those pixels and figure out what it is.
**[1:11]** It feels like even though the online data sets are quite big like over a million images,
**[1:16]** feels like we still wish we had more data.
**[1:20]** And there are some problems like object detection where we have even less data.
**[1:28]** So, just as a reminder image recognition was the problem of
**[1:31]** looking at a picture and telling you is this a cattle or not.
**[1:34]** Whereas object detection is look in the picture and actually you're putting
**[1:39]** the bounding boxes are telling you where in
**[1:41]** the picture the objects such as the car as well.
**[1:44]** And so because of the cost of getting
**[1:46]** the bounding boxes is just more expensive to label the objects and the bounding boxes.
**[1:52]** So, we tend to have less data for object detection than for image recognition.
**[1:57]** And object detection is something we'll discuss next week.
**[2:02]** So, if you look across a broad spectrum of machine learning problems,
**[2:06]** you see on average that when you have a lot of data you tend to find people
**[2:12]** getting away with using simpler algorithms as well as less hand-engineering.
**[2:18]** So, there's just less needing to carefully design features for the problem,
**[2:23]** but instead you can have a giant neural network, even
**[2:25]** a simpler architecture, and have a neural network.
**[2:28]** Just learn whether we want to learn we have a lot of data.
**[2:32]** Whereas, in contrast when you don't have that much data then on
**[2:36]** average you see people engaging in more hand-engineering.
**[2:41]** And if you want to be ungenerous you can say there are more hacks.
**[2:46]** But I think when you don't have much data then
**[2:49]** hand-engineering is actually the best way to get good performance.
**[2:54]** So, when I look at machine learning applications
**[2:59]** I think usually we have the learning algorithm has two sources of knowledge.
**[3:04]** One source of knowledge is the labeled data,
**[3:07]** really the (x,y) pairs you use for supervised learning.
**[3:11]** And the second source of knowledge is the hand-engineering.
**[3:14]** And there are lots of ways to hand-engineer a system.
**[3:17]** It can be from carefully hand designing the features,
**[3:20]** to carefully hand designing
**[3:22]** the network architectures to maybe other components of your system.
**[3:26]** And so when you don't have much labeled data you
**[3:28]** just have to call more on hand-engineering.
**[3:32]** And so I think computer vision is trying to learn a really complex function.
**[3:38]** And it often feels like we don't have enough data for computer vision.
**[3:42]** Even though data sets are getting bigger and bigger,
**[3:45]** often we just don't have as much data as we need.
**[3:48]** And this is why this data computer vision historically and
**[3:52]** even today has relied more on hand-engineering.
**[3:57]** And I think this is also why that either computer vision
**[4:00]** has developed rather complex network architectures,
**[4:05]** is because in the absence of more data
**[4:08]** the way to get good performance is to spend more time architecting,
**[4:13]** or fooling around with the network architecture.
**[4:17]** And in case you think I'm being
**[4:19]** derogatory of hand-engineering that's not at all my intent.
**[4:23]** When you don't have enough data hand-engineering is a very difficult,
**[4:27]** very skillful task that requires a lot of insight.
**[4:32]** And someone that is insightful with hand-engineering will get better performance,
**[4:36]** and is a great contribution to a project to
**[4:39]** do that hand-engineering when you don't have enough data.
**[4:43]** It's just when you have lots of data then I wouldn't spend time hand-engineering,
**[4:47]** I would spend time building up the learning system instead.
**[4:52]** But I think historically the fear the computer vision has used very small data sets,
**[4:57]** and so historically the computer vision literature
**[4:59]** has relied on a lot of hand-engineering.
**[5:02]** And even though in the last few years the amount of data
**[5:06]** with the right computer vision task has increased dramatically,
**[5:10]** I think that that has resulted in
**[5:12]** a significant reduction in the amount of hand-engineering that's being done.
**[5:17]** But there's still a lot of hand-engineering of network architectures and computer vision.
**[5:21]** Which is why you see very complicated hyper frantic choices in computer vision,
**[5:26]** are more complex than you do in a lot of other disciplines.
**[5:31]** And in fact, because you usually have
**[5:33]** smaller object detection data sets than image recognition data sets,
**[5:38]** when we talk about object detection that is task like this next week.
**[5:43]** You see that the algorithms
**[5:48]** become even more complex and has even more specialized components.
**[5:54]** Fortunately, one thing that helps a lot when you have little data is transfer learning.
**[6:00]** And I would say for the example from the previous slide of the tigger,
**[6:10]** misty, neither detection problem,
**[6:13]** you have soluble data that transfer learning will help a lot.
**[6:18]** And so that's another set of techniques that's used
**[6:21]** a lot for when you have relatively little data.
**[6:24]** If you look at the computer vision literature,
**[6:27]** and look at the sort of ideas out there,
**[6:29]** you also find that people are really enthusiastic.
**[6:32]** They're really into doing well on
**[6:34]** standardized benchmark data sets and on winning competitions.
**[6:38]** And for computer vision researchers if you do
**[6:41]** well and the benchmark is easier to get the paper published.
**[6:45]** So, there's just a lot of attention on doing well on these benchmarks.
**[6:49]** And the positive side of this is that,
**[6:51]** it helps the whole community figure out what are the most effective algorithms.
**[6:56]** But you also see in the papers people do things that allow you to do well on a benchmark,
**[7:02]** but that you wouldn't really use in
**[7:04]** a production or a system that you deploy in an actual application.
**[7:08]** So, here are a few tips on doing well on benchmarks.
**[7:11]** These are things that I don't myself pretty much ever use if I'm
**[7:15]** putting a system to production that is actually to serve customers.
**[7:20]** But one is ensembling.
**[7:23]** And what that means is,
**[7:24]** after you've figured out what neural network you want,
**[7:27]** train several neural networks independently and average their outputs.
**[7:33]** So, initialize say 3, or 5,
**[7:35]** or 7 neural networks randomly and train up all of these neural networks,
**[7:40]** and then average their outputs.
**[7:41]** And by the way. it is important to average their outputs y hats.
**[7:44]** Don't average their weights that won't work.
**[7:47]** Look and you say seven neural networks that
**[7:50]** have seven different predictions and average that.
**[7:53]** And this will cause you to do maybe 1% better, or 2% better.
**[7:57]** So is a little bit better on some benchmark.
**[8:02]** And this will cause you to do a little bit better.
**[8:04]** Maybe sometimes as much as 1 or 2% which really help win a competition.
**[8:11]** But because ensembling means that to test on each image,
**[8:15]** you might need to run an image through anywhere
**[8:17]** from say 3 to 15 different networks quite typical.
**[8:21]** This slows down your running time by a factor of 3 to 15,
**[8:25]** or sometimes even more.
**[8:26]** And so ensembling is one of those tips that people
**[8:29]** use doing well in benchmarks and for winning competitions.
**[8:33]** But that I think is almost never use in production to serve actual customers.
**[8:38]** I guess unless you have huge computational budget and don't
**[8:41]** mind burning a lot more of it per customer image.
**[8:44]** Another thing you see in papers that really helps on benchmarks,
**[8:50]** is multi-crop at test time.
**[8:52]** So, what I mean by that is you've seen how you can do data augmentation.
**[8:58]** And multi-crop is a form of applying data augmentation to your test image as well.
**[9:04]** So for example, let's see a cat image
**[9:07]** and just copy it four times including two more versions.
**[9:12]** There's a technique called the 10-crop,
**[9:14]** which basically says let's say you take this central region that crop,
**[9:19]** and run it through your crossfire.
**[9:22]** And then take that crop up the left hand corner run through a crossfire,
**[9:24]** up right hand corner shown in green,
**[9:27]** lower left shown in yellow,
**[9:30]** lower right shown in orange,
**[9:33]** and run that through the crossfire.
**[9:34]** And then do the same thing with the mirrored image.
**[9:37]** Right. So I'll take the central crop,
**[9:38]** then take the four corners crops.
**[9:41]** So, that's one central crop here and here,
**[9:44]** there's four corners crop here and here.
**[9:46]** And if you add these up that's 10 different crops that you mentioned.
**[9:49]** So hence the name 10-crop.
**[9:51]** And so what you do, is you run these 10 images through
**[9:54]** your crossfire and then average the results.
**[9:59]** So, if you have the computational budget you could do this.
**[10:02]** Maybe you don't need as many as 10-crops,
**[10:04]** you can use a few crops.
**[10:05]** And this might get you a little bit better performance in a production system.
**[10:10]** By production I mean a system you're deploying for actual users.
**[10:16]** But this is another technique that is used much more for doing
**[10:19]** well on benchmarks than in actual production systems.
**[10:24]** And one of the big problems of ensembling is
**[10:27]** that you need to keep all these different networks around.
**[10:30]** And so that just takes up a lot more computer memory.
**[10:33]** For multi-crop I guess at least you keep just one network around.
**[10:37]** So it doesn't suck up as much memory,
**[10:41]** but it still slows down your run time quite a bit.
**[10:46]** So, these are tips you see and research papers will refer to these tips as well.
**[10:52]** But I personally do not tend to use these methods when building
**[10:56]** production systems even though they are great for doing
**[10:59]** better on benchmarks and on winning competitions.
**[11:03]** Because a lot of the computer vision problems are in the small data regime,
**[11:08]** others have done a lot of hand-engineering of the network architectures.
**[11:12]** And a neural network that works well on one vision problem often may be surprisingly,
**[11:17]** but they just often would work on other vision problems as well.
**[11:21]** So, to build a practical system often you do
**[11:25]** well starting off with someone else's neural network architecture.
**[11:29]** And you can use an open source implementation if possible,
**[11:32]** because the open source implementation might have figured out
**[11:35]** all the finicky details like the learning rate,
**[11:39]** case scheduler, and other hyper parameters.
**[11:42]** And finally someone else may have spent weeks training a model
**[11:46]** on half a dozen GP use and on over a million images.
**[11:51]** And so by using someone else's pretrained model and fine tuning on your data set,
**[11:56]** you can often get going much faster on an application.
**[12:00]** But of course if you have the compute resources and the inclination,
**[12:05]** don't let me stop you from training your own networks from scratch.
**[12:09]** And in fact if you want to invent your own computer vision algorithm,
**[12:14]** that's what you might have to do.
**[12:16]** So, that's it for this week,
**[12:18]** I hope that seeing a number of
**[12:20]** computer vision architectures helps you get a sense of what works.
**[12:24]** In this week's programming exercises you actually learn
**[12:28]** another programming framework and use that to implement resonance.
**[12:32]** So, I hope you enjoy that programming exercise and I look forward to seeing you next week.
