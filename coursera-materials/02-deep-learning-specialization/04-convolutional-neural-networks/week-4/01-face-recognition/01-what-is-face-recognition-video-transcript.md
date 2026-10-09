---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 4
section: Face Recognition
item_title: What is Face Recognition?
duration: 5 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/lUBYU/what-is-face-recognition
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# What is Face Recognition? — Transcript

**[0:00]** Hi, and welcome to this fourth and final week
**[0:03]** of this course on convolutional neural networks.
**[0:06]** By now, you've learned a lot about confidence.
**[0:08]** What I want to do this week is show you
**[0:11]** a couple important special applications of confidence.
**[0:15]** We'll start the face recognition,
**[0:17]** and then go on later this week to neuro style transfer,
**[0:21]** which you get to implement in the problem exercise as well to create your own artwork.
**[0:26]** But first, let's start the face recognition and just for fun,
**[0:30]** I want to show you a demo.
**[0:31]** When I was leading by those AI group,
**[0:33]** one of the teams I worked with led by Yuanqing Lin had built
**[0:37]** a face recognition system that I thought is really cool. Let's take a look.
**[0:41]** So, I'm going to play this video here,
**[0:43]** but I can also get whoever is editing this raw video configure out to this
**[0:48]** better to splice in the raw video or take the one I'm playing here.
**[0:55]** I want to show you a face recognition demo.
**[0:57]** I'm in Baidu's headquarters in China.
**[0:58]** Most companies require that to get inside,
**[1:01]** you swipe an ID card like this one but here we don't need that.
**[1:04]** Using face recognition, check what I can do.
**[1:07]** When I walk up, it recognizes my face, it says,
**[1:09]** "Welcome Andrew," and I just walk right through without ever having to use my ID card.
**[1:15]** Let me show you something else.
**[1:16]** I'm actually here with Lin Yuanqing,
**[1:17]** the director of IDL which developed all of this face recognition technology.
**[1:22]** I'm gonna hand him my ID card,
**[1:24]** which has my face printed on it,
**[1:26]** and he's going to use it to try to sneak in using my picture instead of a live human.
**[1:30]** I'm gonna use Andrew's card and try to sneak in and see what happens.
**[1:37]** So the system is not recognizing it,
**[1:43]** it refuses to recognize.
**[1:47]** Okay. Now, I'm going to use my own face.
**[1:53]** So face recognition technology like this is taking off very rapidly in China
**[1:59]** ,and I hope that this type of technology soon makes it way to other countries.
**[2:04]** So, pretty cool, right?
**[2:07]** The video you just saw demoed both face recognition as well as liveness detection.
**[2:12]** The latter meaning making sure that you are a live human.
**[2:16]** It turns out liveness detection can be implemented using supervised learning as well
**[2:20]** to predict live human versus not live human but I want to spend less time on that.
**[2:25]** Instead, I want to focus our time on talking about how to
**[2:28]** build the face recognition portion of the system.
**[2:31]** First, let's start by going over some of the terminology used in face recognition.
**[2:36]** In the face recognition literature,
**[2:38]** people often talk about face verification and face recognition.
**[2:42]** This is the face verification problem which is if you're
**[2:45]** given an input image as well as a name or ID
**[2:49]** of a person and the job of the system is to
**[2:53]** verify whether or not the input image is that of the claimed person.
**[2:57]** So, sometimes this is also called a one to
**[3:00]** one problem where you just want to know if the person is the person they claim to be.
**[3:04]** So, the recognition problem is much harder than the verification problem.
**[3:09]** To see why, let's say,
**[3:11]** you have a verification system that's 99 percent accurate.
**[3:15]** So, 99 percent might not be too bad, but now suppose
**[3:19]** that K is equal to 100 in a recognition system.
**[3:23]** If you apply this system to a recognition task with a 100 people in your database,
**[3:30]** you now have a hundred times of chance of making
**[3:33]** a mistake and if the chance of making mistakes on each person is just one percent.
**[3:38]** So, if you have a database of
**[3:39]** a 100 persons, and if you want an acceptable recognition error,
**[3:45]** you might actually need a verification system with maybe
**[3:48]** 99.9 or even higher accuracy before you can run
**[3:52]** it on a database of 100 persons that have
**[3:55]** a high chance and still have a high chance of getting incorrect.
**[3:59]** In fact, if you have a database of 100 persons currently just be even
**[4:03]** quite a bit higher than 99 percent for that to work well.
**[4:07]** But what we do in the next few videos is focus on building
**[4:11]** a face verification system as a building block and then if the accuracy is high enough,
**[4:17]** then you probably use that in a recognition system as well.
**[4:21]** So in the next video,
**[4:23]** we'll start describing how you can build a face verification system.
**[4:27]** It turns out one of the reasons that is
**[4:29]** a difficult problem is you need to solve a one shot learning problem.
**[4:34]** Let's see in the next video what that means.
