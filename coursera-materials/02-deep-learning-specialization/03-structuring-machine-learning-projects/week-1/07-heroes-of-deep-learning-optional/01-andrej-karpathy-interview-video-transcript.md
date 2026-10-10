---
type: video-transcript
specialization: Deep Learning Specialization
course: Structuring Machine Learning Projects
week: 1
section: Heroes of Deep Learning (Optional)
item_title: Andrej Karpathy Interview
duration: 15 min
source_url: https://www.coursera.org/learn/machine-learning-projects/lecture/Ggkxn/andrej-karpathy-interview
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Andrej Karpathy Interview — Transcript

**[0:02]** So welcome Andrej, I'm really glad you could join me today.
**[0:06]** >> Yeah, thank you for having me.
**[0:08]** >> So a lot of people already know your work in deep learning, but
**[0:12]** not everyone knows your personal story.
**[0:14]** So let us start by telling us,
**[0:17]** how did you end up doing all these work in deep learning?
**[0:20]** >> Yeah, absolutely.
**[0:21]** So I think my first exposure to deep learning once when I was an undergraduate
**[0:25]** at the University of Toronto.
**[0:26]** And so Geoff Hinton was there, and he was teaching a class on deep learning.
**[0:28]** And at that time, it was restricted both from machines trained on endless digits.
**[0:32]** And I just really like the way Geoff talked about
**[0:35]** training the network, like the mind of the network, and he was using these terms.
**[0:38]** And I just thought there was a flavor of
**[0:42]** something magical happening when this was training on those digits.
**[0:46]** And so that's my first exposure to it,
**[0:50]** although I didn't get into it in a lot of detail at that time.
**[0:52]** And then when I was doing my master's degree at University of British Columbia,
**[0:57]** I took a class with [professor] and that was again on machine learning.
**[0:59]** And that's the first time I delved deeper into these networks and so on.
**[1:03]** And kinf of, what was interesting is that I was very interested in
**[1:07]** artificial intelligence, and so I took classes in artificial intelligence.
**[1:10]** But a lot of what I was seeing there was just very not satisfying.
**[1:12]** It was a lot of depth-first search, breadth-first search, alpha-beta pruning,
**[1:16]** and all these things.
**[1:17]** And I was not understanding how, I was not satisfied.
**[1:20]** And so when I was seeing neural networks for the first time in machine learning,
**[1:23]** which is this term that I think is more technical and
**[1:25]** not as well known in most people talk about artificial intelligence.
**[1:29]** Machine learning was more a technical term, I would almost say.
**[1:32]** And so I was dissatisfied with artificial intelligence.
**[1:34]** When I saw machine learning, I was like,
**[1:36]** this is the AI that I want to spend time on, this is what's really interesting.
**[1:41]** And that's what took me down those directions is that this is
**[1:45]** almost a new computing paradigm, I would say.
**[1:48]** Because normally, humans write code, but
**[1:50]** here in this case, the optimization writes code.
**[1:54]** And so you're creating the input/out specification,
**[1:56]** and then you have lots of examples of it, and then the optimization writes code, and
**[1:59]** sometimes it can write code better than you.
**[2:01]** And so I thought that was just a very new way of thinking about programming, and
**[2:06]** that's what intrigued me about it.
**[2:08]** >> Then through your work, one of the things you've come to be known for
**[2:11]** is that you're now the human benchmark for the image classification competition.
**[2:18]** How did that come about?
**[2:19]** >> So basically, their ImageNet challenge is it's sometimes compared to
**[2:23]** the world cup of computer vision.
**[2:24]** So a lot of people kind of care about this benchmark and number,
**[2:27]** our error rate goes down over time.
**[2:29]** And it was not obvious to me where a human would be on this scale.
**[2:33]** I've done a similar smaller scale experiment on CIFAR-10 dataset earlier.
**[2:37]** So what I did in CIFAR-10 is I was just looking at these 32 x 32 images, and
**[2:40]** I was trying to classify them myself.
**[2:42]** At the time, this was only ten categories, so
**[2:43]** it's fairly simple to create an interface for it.
**[2:45]** And I think I had an error rate of about 6% on that.
**[2:48]** And then based on what I was seeing and how hard a task was,
**[2:52]** I think I predicted that the lowest error rate we'd achieve would be.
**[2:56]** Look, okay, I can't remember the exact numbers.
**[2:58]** I think, I guess, 10%, and we're now down to 3 or 2% or something crazy.
**[3:03]** So that was my first fun experiment of human baseline.
**[3:09]** And I thought it was really important for
**[3:11]** the same purposes that you point out in some of your lectures.
**[3:13]** I mean, you really want that number to understand how well humans are doing it,
**[3:18]** so we can compare machine learning algorithms to it.
**[3:20]** And for ImageNet, it seems that there was a discrepancy between how important this
**[3:24]** benchmark was and how much focus there was on getting a lower number and
**[3:27]** us not even understanding how humans are doing on this benchmark.
**[3:31]** So I created this JavaScript interface, and I was showing myself the images,
**[3:35]** and then the problem with ImageNet is you don't have just 10 categories,
**[3:38]** you have 1,000.
**[3:39]** It was almost like a UI challenge.
**[3:41]** Obviously, I can't remember 1,000 categories, so how do I make it so
**[3:44]** that it's something fair?
**[3:45]** And so I listed out all the categories, and I gave myself examples of them.
**[3:48]** And so for each image, I was scrolling through 1,000 categories and
**[3:52]** just trying to see, based on the examples I was seeing for each category,
**[3:56]** what this image might be.
**[3:57]** And I thought it was an extremely instructed exercise by itself.
**[4:01]** I mean, I did not understand that a third of ImageNet is dogs and dog species,
**[4:06]** and so that was interesting to see that network
**[4:10]** spends a huge amount of time caring about dogs, I think.
**[4:12]** A third of its performance comes from dogs.
**[4:14]** And yeah, so this was something that I did for maybe a week or two.
**[4:20]** I put everything else on hold.
**[4:21]** I thought it was a very fun exercise.
**[4:24]** I got a number in the end, and then I thought that one person is not enough.
**[4:26]** I wanted to have multiple other people, and so
**[4:28]** I was trying to organize within the lab to get other people to do the same thing.
**[4:32]** And I think people are not as willing to contribute, say like a week or
**[4:36]** two of pretty painstaking work, just like yeah
**[4:41]** sitting down for five hours and trying to figure out which dog breed
**[4:44]** this is. And so I was not able to get enough data in that respect, but
**[4:47]** we got at least some approximate performance, which I thought was fun.
**[4:53]** And then this was picked up, and it wasn't obvious to me at the time.
**[4:57]** I just wanted to know the number, but this became like a thing.
**[4:59]** [LAUGH] And people really liked the fact that this happened, and
**[5:03]** I'm refer to jokingly as the reference human.
**[5:06]** And of course, that's hilarious to me, yeah.
**[5:10]** [LAUGH] >> Were you surprised when software,
**[5:15]** finally surpassed your performance?
**[5:18]** >> Absolutely.
**[5:19]** So yeah, absolutely.
**[5:21]** I mean, especially, sometimes it's really hard to see in the image what it is.
**[5:26]** It's just like a tiny blob of a black dot is obviously somewhere there.
**[5:30]** And I'm not seeing.
**[5:31]** I'm guessing between like 20 categories, and the network just gets it, and
**[5:34]** I don't understand how that comes about.
**[5:37]** So there's some superhumanness to it.
**[5:39]** But also, I think the network is extremely good at these kind of statistics of
**[5:44]** work types and textures.
**[5:46]** I think in that respect, I was not surprised that the network could better
**[5:49]** measure those fine statistics across lots of images.
**[5:53]** In many cases, I was surprised because some of the images require you to read.
**[5:57]** It's just a bottle, and you can't see what it is, but
**[5:59]** it actually tells you what it is in text.
**[6:00]** And so as a human, I can read it, and it's fine, but the network would have to learn
**[6:04]** to read to identify the object, because it wasn't obvious from it.
**[6:07]** >> One of the things you've become well-known for, and
**[6:10]** that the deep learning community has been grateful to you for,
**[6:13]** has been your teaching the class and putting that online.
**[6:17]** Tell me a little bit about how that came about.
**[6:20]** >> Yeah, absolutely.
**[6:20]** So I think I felt very strongly that basically,
**[6:26]** this technology was transformative in that a lot of people want to use it.
**[6:29]** It's almost like a hammer.
**[6:30]** And what I wanted to do,
**[6:31]** I was in a position to randomly hand out this hammer to a lot of people.
**[6:36]** And I just found that very compelling.
**[6:37]** It's not necessarily advisable from the perspective of the PhD student,
**[6:40]** because you're putting your research on hold.
**[6:42]** I mean, this became like 120% of my time.
**[6:44]** And I had to put all of research on hold for
**[6:46]** maybe, I mean, I thought the class twice, and each time, it's maybe four months.
**[6:50]** And so that time is basically spent entirely on the class, so it's not
**[6:52]** super advisable from that perspective, but it was basically the highlight of my PhD.
**[6:56]** It's not even related to research.
**[6:57]** I think teaching a class was definitely the highlight of my PhD.
**[7:01]** Just seeing the students,
**[7:02]** just the fact that they're real excited, it was a very different class.
**[7:06]** Normally, you're being taught things that were discovered in 1800 or
**[7:08]** something like that.
**[7:09]** But we were able to come to class and say, look, there's this paper from a week ago,
**[7:12]** or even yesterday.
**[7:13]** And there's new results, and I think the undergraduate students and
**[7:16]** the other students, they just really enjoyed that aspect of the class and
**[7:18]** the fact that they actually understood.
**[7:20]** So this is not nuclear physics or rocket science.
**[7:25]** This is you need to know calculus, and then your algebra, and
**[7:28]** you can actually understand everything that happens under the hood.
**[7:31]** So I think just the fact that it's so powerful, the fact that it keeps changing
**[7:36]** on a daily basis, people felt right they're on the forefront of something big.
**[7:39]** And I think that's why people really enjoy that class a lot.
**[7:42]** >> And you've really helped a lot of people and had a lot of hammers.
**[7:47]** >> Yeah.
**[7:48]** >> As someone that's been doing deep learning for
**[7:52]** quite some time now, the field is evolving rapidly.
**[7:56]** I'd be curious to hear, how has your own thinking,
**[7:59]** how has your understanding of deep learning changed over these many years?
**[8:02]** >> Yeah, it's basically like when I was seeing Restricted Boltzmann machines for
**[8:06]** the first time on DIGITS.
**[8:08]** >> It wasn't obvious to me how this technology was going to be used and
**[8:11]** how big of a deal it would be.
**[8:12]** And also, when I was starting to work in computer vision, convolutional networks,
**[8:15]** they were around, but they were not something that a lot of the computer
**[8:18]** vision community anticipated using anytime soon.
**[8:21]** I think the perception was that this works for small cases but
**[8:25]** would never scale for large images.
**[8:27]** >> And that was just extremely incorrect.
**[8:28]** [LAUGH] And so basically, I'm just surprised by how general
**[8:34]** technology is and how good the
**[8:36]** results are. That was largest surprise, I would say, and it's not only that.
**[8:39]** So that's one thing that it worked so well on, say, like ImageNet.
**[8:42]** But the other thing that I think no one saw coming, or at least for
**[8:45]** sure I did not see coming, is that you can take these pretrained networks and
**[8:48]** that you can transfer.
**[8:49]** You can fine tune them on arbitrary other tasks.
**[8:51]** Because now, you're not just solving ImageNet, and
**[8:52]** you need millions of examples.
**[8:53]** This also happens to be very general feature extractor, and
**[8:56]** I think that's a second insight that I think fewer people saw coming.
**[9:00]** And there were these papers, they are just like here.
**[9:04]** All the things that people have been working on in computer vision.
**[9:06]** Sync classification, action recognition, object recognition,
**[9:10]** base attributes and so on.
**[9:13]** And people are just crushing each task just by fine tuning the network.
**[9:16]** And so that, to me, was very surprising.
**[9:21]** >> Yes, and somehow I guess supervised learning gets most of the press, and
**[9:25]** even though pretrained fine-tuning or transfer learning is
**[9:30]** actually working very well, people seem to talk less about that for some reason.
**[9:34]** >> Right, exactly.
**[9:36]** Yeah, I think what has not worked as much is some of these hopes are on unsupervised
**[9:39]** learning, which I think has been really why a lot of researchers have gotten into the field in around
**[9:44]** 2007 and so on.
**[9:48]** And I think the promise of that has still not been delivered, and I think I
**[9:52]** find that also surprising is that the supervised learning part worked so well.
**[9:56]** And the enterprise learning, it's still in a state of, yeah,
**[9:59]** it's still not obvious how it's going to be used or how that's going to work,
**[10:03]** even though a lot of people are still deep believers,
**[10:05]** I would say to use the term, in this area >> So I know that you're
**[10:10]** one of the persons who's been thinking a lot about the long-term future of AI.
**[10:14]** Do you want to share your thoughts on that?
**[10:16]** >> So I spent the last maybe year and
**[10:18]** a half at OpenAI thinking a lot about these topics, and
**[10:23]** it seems to me like the field will kind of split into two trajectories.
**[10:29]** One will be applied AI, which is just making these neural networks, training them,
**[10:34]** mostly with supervised learning, potentially unsupervised learning.
**[10:37]** And getting better, say, image recognizers or something like that.
**[10:40]** And I think the other will be artificial general intelligence directions, which
**[10:45]** is how do you get neural networks that are entirely dynamical system that thinks and
**[10:50]** speaks and can do everything that a human can do and is intelligent in that way.
**[10:54]** And I think that what's been interesting is that, for example in computer vision.
**[10:58]** The way we approached it in the beginning, I think,
**[10:59]** was wrong in that we tried to break it down by different parts.
**[11:02]** So we were like, okay, humans recognize people, humans recognize scenes,
**[11:05]** humans recognize objects.
**[11:06]** So we're just going to do everything that humans do,
**[11:09]** and then once we have all those things, and now we have different areas.
**[11:12]** And once we have all those things,
**[11:13]** we're going to figure out how to put them together.
**[11:16]** And I think that was a wrong approach,
**[11:17]** and we've seen how that going to played out historically.
**[11:21]** And so I think there's something similar that's going on that's likely on a higher
**[11:24]** level with AI.
**[11:24]** So people are asking, well, okay, people plan, people
**[11:28]** do experiments to figure out how the world works, or people talk to other people, so we need language.
**[11:32]** And people are trying to decompose it by function, accomplish each piece, and
**[11:35]** then put it together into some kind of brain.
**[11:37]** And I just think it's just incorrect approach.
**[11:40]** And so what I've been a much bigger fan of is not decomposing that way but
**[11:45]** having a single kind of neural network that is the complete dynamical system
**[11:50]** that you're always working with a full agent.
**[11:53]** And then the question is,
**[11:54]** how do you actually create objectives such that when you optimize over
**[11:58]** the weights that make up that brain, you get intelligent behavior out?
**[12:02]** And so that's been something that I've been thinking about a lot at OpenAI.
**[12:05]** I think there are a lot of different ways that
**[12:08]** people have thought about approaching this problem.
**[12:11]** For example,
**[12:12]** going in a supervised learning direction, I have this essay online.
**[12:15]** It's not an essay, it's a short story that I wrote.
**[12:17]** And the short story tries to come up with a hypothetical world of what it might look
**[12:20]** like if the way we approach this AGI is just by scaling up supervised learning,
**[12:25]** which we know works.
**[12:27]** And so that gets into something that looks like Amazon Mechanical Turk where people
**[12:32]** associates into lots of robot bodies, and they perform tasks, and
**[12:35]** then we train on that as a supervised learning dataset to imitate humans and
**[12:38]** what that might look like, and so on.
**[12:39]** And so then there are other directions,
**[12:41]** like unsurpervised learning from algorithmic information theory, things like AIXI,
**[12:46]** or from artificial life, things that'll look more like artificial evolution.
**[12:50]** And so that's what I spend my time thinking a lot about.
**[12:54]** And I think I had the correct answer, but I'm not willing to reveal it here.
**[12:57]** [LAUGH] >> I can at least learn more by reading
**[13:01]** your blog post.
**[13:02]** >> Yeah, absolutely.
**[13:03]** >> So you've already given out a lot of advice, and today,
**[13:08]** there are a lot of people still wanting to enter the field of AI into deep learning.
**[13:13]** So for people in that position, what advice do you have for them?
**[13:17]** >> Yeah, absolutely.
**[13:18]** So I think when people talk to me about CS231n and why they thought it was a very
**[13:22]** useful course, what I keep hearing again and again is just people appreciate
**[13:25]** the fact that we got all the way through the low-level details.
**[13:29]** And they were not working with the library, they saw the real code.
**[13:31]** And they saw how everything was implemented, and
**[13:34]** implemented chunks of it themselves.
**[13:36]** And so just going all the way down and understanding everything under you,
**[13:42]** it's really important to not abstract away things.
**[13:44]** You need to have a full understanding of the whole stack.
**[13:46]** And that's where I learned the most myself as well when I was learning this stuff
**[13:49]** is just implementing it myself from scratch was the most important.
**[13:52]** It was the piece that I felt gave me the best kind of bang for
**[13:57]** the buck in terms of understanding.
**[13:59]** So I wrote my own library.
**[14:00]** It's called ConvNetJS.
**[14:01]** It was written in Javascript, and it implements convolutional neural network.
**[14:03]** That was my way of learning about application.
**[14:06]** And so that's something that I keep advising people is that you not work with
**[14:11]** flow or something else.
**[14:12]** You can work with it once you have written at something yourself on the lowest
**[14:15]** detail, you understand everything under you, and now you are comfortable to.
**[14:19]** Now, it's possible to use some these frameworks that abstract some of it away
**[14:21]** from you, but you know what's under the hood.
**[14:23]** And so that's been something that helped me the most.
**[14:26]** That's something that people appreciate the most when they take 231n, and
**[14:29]** that's what I would advise a lot of people.
**[14:30]** >> So rather than run neural network, and it'll all happen like that.
**[14:35]** >> Yeah, and in some kind of sequence of layers, and I know that when I add some
**[14:38]** dropout layers, it makes it work better, like that's not what you want.
**[14:41]** In that case, you're not going to be able to debug effectively,
**[14:45]** you're not going to be able to improve on models effectively.
**[14:48]** >> Yeah, with that answer, I'm really glad that deep learning course got AI course.
**[14:52]** It starts a lot with many weeks of Python programming first and then [INAUDIBLE].
**[14:56]** >> Yeah, good, good.
**[14:57]** >> Thank you very much for sharing your insights and advice.
**[15:00]** You're already heroes of many people in the deep learning world, so
**[15:04]** I'm really glad, really grateful you could join us here today.
**[15:07]** >> Yeah, thank you for having me.
