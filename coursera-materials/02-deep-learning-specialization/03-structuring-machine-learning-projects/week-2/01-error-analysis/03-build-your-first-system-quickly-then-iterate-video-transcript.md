---
type: video-transcript
specialization: Deep Learning Specialization
course: Structuring Machine Learning Projects
week: 2
section: Error Analysis
item_title: Build your First System Quickly, then Iterate
duration: 5 min
source_url: https://www.coursera.org/learn/machine-learning-projects/lecture/jyWpn/build-your-first-system-quickly-then-iterate
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Build your First System Quickly, then Iterate — Transcript

**[0:00]** If you're working on a brand new machine learning application,
**[0:04]** one of the pieces of advice I often give people is that,
**[0:06]** I think you should build your first system quickly and then iterate.
**[0:11]** Let me show you what I mean. I've worked on speech recognition for many years.
**[0:14]** And if you're thinking of building a new speech recognition system,
**[0:18]** there's actually a lot of directions you could
**[0:20]** go in and a lot of things you could prioritize.
**[0:22]** For example, there are specific techniques for making
**[0:25]** speech recognition systems more robust to noisy background.
**[0:29]** And noisy background could mean cafe noise,
**[0:32]** like a lot of people talking in the background or car noise,
**[0:35]** the sounds of cars and highways or other types of noise.
**[0:38]** There are ways to make a speech recognition system more robust to accented speech.
**[0:43]** There are specific problems associated with speakers that are far from the microphone,
**[0:48]** this is called far-field speech recognition.
**[0:50]** Young children speech poses special challenges,
**[0:53]** both in terms of how they pronounce individual words as well
**[0:56]** as their choice of words and the vocabulary they tend to use.
**[0:59]** And if sometimes the speaker stutters or if they use nonsensical phrases like oh, ah,
**[1:07]** um, there are different choices and
**[1:09]** different techniques for making the transcript that you output,
**[1:12]** still read more fluently.
**[1:15]** So, there are these and
**[1:17]** many other things you could do to improve a speech recognition system.
**[1:22]** And more generally, for almost any machine learning application,
**[1:26]** there could be 50 different directions you could go in
**[1:30]** and each of these directions is reasonable and would make your system better.
**[1:34]** But the challenge is,
**[1:35]** how do you pick which of these to focus on.
**[1:38]** And even though I've worked in speech recognition for many years,
**[1:42]** if I'm building a new system for a new application domain,
**[1:46]** I would still find it maybe a little bit difficult to
**[1:48]** pick without spending some time thinking about the problem.
**[1:52]** So what I would recommend you do,
**[1:54]** if you're starting on building a brand new machine learning application,
**[1:58]** is to build your first system quickly and then iterate.
**[2:02]** What I mean by that is I recommend that
**[2:04]** you first quickly set up a dev/test set and metric.
**[2:08]** So this is really deciding where to place your target.
**[2:12]** And if you get it wrong, you can always move it later,
**[2:14]** but just set up a target somewhere.
**[2:16]** And then I recommend you build an initial machine learning system quickly.
**[2:20]** Find the training set, train it and see.
**[2:23]** Start to see and understand how well you're
**[2:25]** doing against your dev/test set and your valuation metric.
**[2:29]** When you build your initial system,
**[2:32]** you will then be able to use bias/variance analysis which we talked about
**[2:37]** earlier as well as error analysis which we talked about just in the last several videos,
**[2:42]** to prioritize the next steps.
**[2:45]** In particular, if error analysis
**[2:49]** causes you to realize that a lot of the errors are
**[2:52]** from the speaker being very far from the microphone,
**[2:55]** which causes special challenges to speech recognition,
**[2:58]** then that will give you a good reason to focus on techniques to address this called
**[3:03]** far-field speech recognition which
**[3:06]** basically means handling when the speaker is very far from the microphone.
**[3:10]** Of all the value of building this initial system,
**[3:14]** it can be a quick and dirty implementation,
**[3:16]** you know, don't overthink it,
**[3:18]** but all the value of the initial system is having some learned system,
**[3:22]** having some trained system allows you to localize bias/variance,
**[3:26]** to try to prioritize what to do next,
**[3:28]** allows you to do error analysis,
**[3:30]** look at some mistakes,
**[3:31]** to figure out all the different directions you can go in,
**[3:34]** which ones are actually the most worthwhile.
**[3:37]** So to recap, what I recommend you do is build your first system quickly, then iterate.
**[3:44]** This advice applies less strongly if you're working on
**[3:47]** an application area in which you have significant prior experience.
**[3:52]** It also applies a bit less strongly if there's a significant body of
**[3:56]** academic literature that you can draw on
**[3:58]** for pretty much the exact same problem you're building.
**[4:01]** So, for example, there's a large academic literature on face recognition.
**[4:05]** And if you're trying to build a face recognizer,
**[4:08]** it might be okay to build a more complex system from the get-go
**[4:11]** by building on this large body of academic literature.
**[4:16]** But if you are tackling a new problem for the first time,
**[4:19]** then I would encourage you to really not
**[4:23]** overthink or not make your first system too complicated.
**[4:27]** But, just build something quick and dirty and then use that
**[4:30]** to help you prioritize how to improve your system.
**[4:33]** So I've seen a lot of machine learning projects and I've
**[4:36]** seen some teams overthink the solution and build something too complicated.
**[4:40]** I've also seen some teams underthink and then build something maybe too simple.
**[4:44]** Well on average, I've seen a lot more teams
**[4:46]** overthink and build something too complicated.
**[4:49]** And I've seen teams build something too simple.
**[4:52]** So I hope this helps,
**[4:53]** and if you are applying to your machine learning algorithms to a new application,
**[4:58]** and if your main goal is to build something that works,
**[5:01]** as opposed to if your main goal is to invent
**[5:04]** a new machine learning algorithm which is a different goal,
**[5:08]** then your main goal is to get something that works really well.
**[5:11]** I'd encourage you to build something quick and dirty.
**[5:13]** Use that to do bias/variance analysis,
**[5:14]** use that to do error analysis and
**[5:17]** use the results of those analysis to help you prioritize where to go next.
