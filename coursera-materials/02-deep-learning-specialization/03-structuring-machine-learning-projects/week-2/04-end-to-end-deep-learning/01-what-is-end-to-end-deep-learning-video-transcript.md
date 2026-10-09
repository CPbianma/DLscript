---
type: video-transcript
specialization: Deep Learning Specialization
course: Structuring Machine Learning Projects
week: 2
section: End-to-end Deep Learning
item_title: What is End-to-end Deep Learning?
duration: 12 min
source_url: https://www.coursera.org/learn/machine-learning-projects/lecture/k0Klk/what-is-end-to-end-deep-learning
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# What is End-to-end Deep Learning? — Transcript

**[0:00]** One of the most exciting recent developments in deep learning,
**[0:02]** has been the rise of end-to-end deep learning.
**[0:05]** So what is the end-to-end learning?
**[0:07]** Briefly, there have been some data processing systems,
**[0:10]** or learning systems that require multiple stages of processing.
**[0:13]** And what end-to-end deep learning does,
**[0:15]** is it can take all those multiple stages,
**[0:17]** and replace it usually with just a single neural network.
**[0:20]** Let's look at some examples.
**[0:24]** Take speech recognition as an example,
**[0:26]** where your goal is to take an input X such an audio clip,
**[0:30]** and map it to an output Y,
**[0:33]** which is a transcript of the audio clip.
**[0:37]** So traditionally, speech recognition required many stages of processing.
**[0:41]** First, you will extract some features,
**[0:44]** some hand-designed features of the audio.
**[0:46]** So if you've heard of MFCC,
**[0:48]** that's an algorithm for extracting a certain set of hand designed features for audio.
**[0:53]** And then having extracted some low level features,
**[0:55]** you might apply a machine learning algorithm,
**[0:58]** to find the phonemes in the audio clip.
**[1:01]** So phonemes are the basic units of sound.
**[1:04]** So for example, the word cat is made out of three sounds.
**[1:07]** The Cu- Ah- and Tu- so they extract those.
**[1:10]** And then you string together phonemes to form individual words.
**[1:13]** And then you string those together to form the transcripts of the audio clip.
**[1:19]** So, in contrast to this pipeline with a lot of stages,
**[1:23]** what end-to-end deep learning does,
**[1:24]** is you can train a huge neural network to just input the audio clip,
**[1:28]** and have it directly output the transcript.
**[1:32]** One interesting sociological effect in AI is
**[1:35]** that as end-to-end deep learning started to work better,
**[1:39]** there were some researchers that had for example spent
**[1:41]** many years of their career designing individual steps of the pipeline.
**[1:44]** So there were some researchers in different disciplines not just in speech recognition.
**[1:50]** Maybe in computer vision, and other areas as well,
**[1:52]** that had spent a lot of time you know,
**[1:53]** written multiple papers, maybe even built a large part of their career,
**[1:57]** engineering features or engineering other pieces of the pipeline.
**[2:00]** And when end-to-end deep learning just took
**[2:02]** the last training set and learned the function mapping from x and y directly,
**[2:06]** really bypassing a lot of these intermediate steps,
**[2:09]** it was challenging for some disciplines to come around to
**[2:13]** accepting this alternative way of building AI systems.
**[2:17]** Because it really obsoleted in some cases,
**[2:20]** many years of research in some of the intermediate components.
**[2:23]** It turns out that one of the challenges of end-to-end deep learning is
**[2:27]** that you might need a lot of data before it works well.
**[2:30]** So for example, if you're training on 3,000
**[2:33]** hours of data to build a speech recognition system,
**[2:35]** then the traditional pipeline,
**[2:37]** the full traditional pipeline works really well.
**[2:40]** It's only when you have a very large data set,
**[2:42]** you know one could say 10,000 hours of data,
**[2:45]** anything going up to maybe 100,000 hours of data that
**[2:49]** the end-to end-approach then suddenly starts to work really well.
**[2:53]** So when you have a smaller data set,
**[2:55]** the more traditional pipeline approach actually works just as well.
**[2:58]** Often works even better.
**[3:00]** And you need a large data set before the end-to-end approach really shines.
**[3:06]** And if you have a medium amount of data,
**[3:08]** then there are also intermediate approaches where maybe you input audio
**[3:12]** and bypass the features and just learn to output the phonemes of the neural network,
**[3:16]** and then at some other stages as well.
**[3:17]** So this will be a step toward end-to-end learning,
**[3:19]** but not all the way there. Test.
**[3:29]** So this is a picture of a face recognition turnstile built by a researcher,
**[3:34]** Yuanqing Lin at Baidu,
**[3:36]** where this is a camera and it looks at the person approaching the gate,
**[3:41]** and if it recognizes the person then,
**[3:43]** you know the turnstile automatically lets them through.
**[3:46]** So rather than needing to swipe an RFID badge to enter this facility,
**[3:51]** in increasingly many offices in
**[3:53]** China and hopefully more and more in other countries as well,
**[3:56]** you can just approach the turnstile and if it recognizes your face it
**[3:59]** just lets you through without needing you to carry an RFID badge.
**[4:04]** So, how do you build a system like this?
**[4:07]** Well, one thing you could do is just look at the image that the camera is capturing.
**[4:12]** Right? So, I guess this is my bad drawing,
**[4:14]** but maybe this is a camera image.
**[4:16]** And you know, you have someone approaching the turnstile.
**[4:19]** So this might be the image X that you that your camera is capturing.
**[4:23]** And one thing you could do is try to learn a function mapping
**[4:26]** directly from the image X to the identity of the person Y.
**[4:31]** It turns out this is not the best approach.
**[4:34]** And one of the problems is that you know,
**[4:36]** the person approaching the turnstile can approach from lots of different directions.
**[4:39]** So they could be green positions,
**[4:41]** they could be in blue position.
**[4:43]** You know, sometimes they're closer to the camera,
**[4:45]** so they appear bigger in the image.
**[4:47]** And sometimes they're already closer to the camera,
**[4:49]** so that face appears much bigger.
**[4:51]** So what it has actually done to build these turnstiles,
**[4:54]** is not to just take the raw image and
**[4:56]** feed it to a neural net to try to figure out a person's identity.
**[4:59]** Instead, the best approach to date,
**[5:02]** seems to be a multi-step approach, where first,
**[5:05]** you run one piece of software to detect the person's face.
**[5:09]** So this first detector to figure out where's the person's face.
**[5:12]** Having detected the person's face,
**[5:14]** you then zoom in to that part of
**[5:16]** the image and crop
**[5:24]** that image so that the person's face is centered.
**[5:29]** Then, it is this picture that I guess I drew here in red,
**[5:34]** this is then fed to the neural network,
**[5:36]** to then try to learn,
**[5:38]** or estimate the person's identity.
**[5:40]** And what researchers have found,
**[5:42]** is that instead of trying to learn everything on one step,
**[5:45]** by breaking this problem down into two simpler steps,
**[5:48]** first is figure out where is the face.
**[5:51]** And second, is look at the face and figure out who this actually is.
**[5:54]** This second approach allows the learning algorithm or really two learning algorithms
**[5:58]** to solve two much simpler tasks and results in overall better performance.
**[6:03]** By the way, if you want to know how
**[6:05]** the second step actually works I've simplified the discussion.
**[6:08]** By the way, if you want to know how step two here actually works,
**[6:11]** I've actually simplified the description a bit.
**[6:13]** The way the second step is actually trained,
**[6:15]** as you train your neural network,
**[6:16]** that takes as input two images,
**[6:18]** and what then your network does is it takes
**[6:22]** this input two images and it tells you if these two are the same person or not.
**[6:29]** So if you then have say 10,000 employees IDs on file,
**[6:34]** you can then take this image in red,
**[6:36]** and quickly compare it against maybe all
**[6:38]** 10,000 employee IDs on file to try to figure out if
**[6:41]** this picture in red is indeed one of your 10000 employees that you
**[6:44]** should allow into this facility or that should allow into your office building.
**[6:48]** This is a turnstile that is giving employees access to a
**[6:51]** workplace.So why is it that the two step approach works better?
**[6:55]** There are actually two reasons for that.
**[6:58]** One is that each of the two problems you're solving is actually much simpler.
**[7:02]** But second, is that you have a lot of data for each of the two sub-tasks.
**[7:10]** In particular, there is a lot of data you can obtain for face detection,
**[7:16]** for task one over here,
**[7:18]** where the task is to look at an image and figure
**[7:20]** out where is the person's face and the image.
**[7:23]** So there is a lot of data.
**[7:25]** There is a lot of label data X,
**[7:27]** comma Y where X is a picture and y shows the position of the person's face.
**[7:31]** So you could build a neural network to do task one quite well.
**[7:35]** And then separately, there's a lot of data for task two as well.
**[7:37]** Today, leading companies have let's say,
**[7:41]** hundreds of millions of pictures of people's faces.
**[7:44]** So given a closely cropped image,
**[7:46]** like this red image or this one down here,
**[7:49]** today leading face recognition teams have
**[7:51]** at least hundreds of millions of images that they could
**[7:53]** use to look at two images and try to
**[7:55]** figure out the identity or to figure out if it's the same person or not.
**[7:58]** So there's also a lot of data for task two.
**[8:02]** But in contrast, if you were to try to learn everything at the same time,
**[8:07]** there is much less data of the form X comma Y.
**[8:10]** Where X is image like this taken from the turnstile,
**[8:13]** and Y is the identity of the person.
**[8:16]** So because you don't have enough data to solve this end-to-end learning problem,
**[8:21]** but you do have enough data to solve sub-problems one and two, in practice,
**[8:27]** breaking this down to two sub-problems results in
**[8:29]** better performance than a pure end-to-end deep learning approach.
**[8:34]** Although if you had enough data for the end-to-end approach,
**[8:37]** maybe the end-to-end approach would work better,
**[8:40]** but that's not actually what works best in practice today.
**[8:44]** Let's look at a few more examples.
**[8:46]** Take machine translation.
**[8:49]** Traditionally, machine translation systems also had a long complicated pipeline,
**[8:54]** where you first take say English,
**[8:56]** text and then do text analysis.
**[8:58]** Basically, extract a bunch of features off the text, and so on.
**[9:01]** And after many many steps you'd end up with say,
**[9:04]** a translation of the English text into French.
**[9:07]** Because, for machine translation,
**[9:10]** you do have a lot of pairs of English comma French sentences.
**[9:13]** End-to-end deep learning works quite well for machine translation.
**[9:17]** And that's because today,
**[9:20]** it is possible to gather large data sets of X-Y pairs where that's
**[9:24]** the English sentence and that's the corresponding French translation.
**[9:28]** So in this example,
**[9:29]** end-to-end deep learning works well.
**[9:32]** One last example, let's say that you
**[9:35]** want to look at an X-ray picture of a hand of a child,
**[9:38]** and estimate the age of a child.
**[9:40]** You know, when I first heard about this problem,
**[9:41]** I thought this is a very cool crime scene investigation task
**[9:45]** where you find maybe tragically the skeleton of a child,
**[9:48]** and you want to figure out how old the child was.
**[9:50]** It turns out that typical application of this problem,
**[9:54]** estimating age of a child from an X-ray is
**[9:57]** less dramatic than this crime scene investigation I was picturing.
**[9:59]** It turns out that pediatricians use
**[10:02]** this to estimate whether or not a child is growing or developing normally.
**[10:06]** But a non end-to-end approach to this,
**[10:09]** would be you look at an image and then you segment out or recognize the bones.
**[10:14]** So, just try to figure out where is that bone segment?
**[10:16]** Where is that bone segment?
**[10:17]** Where is that bone segment? And so on. And then.
**[10:20]** Knowing the lengths of the different bones,
**[10:22]** you can sort of go to a look up table showing the average bone lengths in
**[10:26]** a child's hand and then use that to estimate the child's age.
**[10:30]** And so this approach actually works pretty well.
**[10:32]** In contrast, if you were to go straight from the image to the child's age,
**[10:37]** then you would need a lot of data to do that directly and as far as I know,
**[10:43]** this approach does not work as well today just
**[10:45]** because there isn't enough data to train this task in an end-to-end fashion.
**[10:50]** Whereas in contrast, you can imagine that by breaking down this problem into two steps.
**[10:56]** Step one is a relatively simple problem.
**[10:58]** Maybe you don't need that much data.
**[11:00]** Maybe you don't need that many X-ray images to segment out the bones.
**[11:03]** And task two, by collecting statistics of a number of children's hands,
**[11:08]** you can also get decent estimates of that without too much data.
**[11:11]** So this multi-step approach seems promising.
**[11:14]** Maybe more promising than the end-to-end approach,
**[11:16]** at least until you can get more data for the end-to-end learning approach.
**[11:20]** So end-to-end deep learning works.
**[11:22]** It can work really well and it can really simplify the system and not
**[11:26]** require you to build so many hand-designed individual components.
**[11:30]** But it's also not panacea,
**[11:32]** it doesn't always work.
**[11:34]** In the next video,
**[11:35]** I want to share with you a more systematic description of when you should,
**[11:39]** and maybe when you shouldn't use end-to-end deep learning and how
**[11:42]** to piece together these complex machine learning systems.
