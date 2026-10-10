---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 1
section: Heroes of Deep Learning (Optional)
item_title: Yoshua Bengio Interview
duration: 26 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/bqUgf/yoshua-bengio-interview
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Yoshua Bengio Interview — Transcript

**[0:03]** Hi, Yoshua, I'm really glad you could join us here today.
**[0:05]** >> I'm very glad, too.
**[0:06]** >> Today you're not just a researcher or engineer in deep learning.
**[0:11]** You've become one of the institutions and one of the icons of deep learning, but
**[0:16]** I'd really like to hear the story of how it started.
**[0:19]** So how did you end up getting into deep learning, and then pursuing this journey?
**[0:26]** >> Right, well, actually, it started when I was a kid, adolescent,
**[0:31]** reading a lot of science fiction, like, I guess, many of us.
**[0:35]** And when I started my graduate studies in 1985, I started reading neural net papers,
**[0:42]** and that's where I got all excited, and it became really a passion.
**[0:48]** >> And actually, what was that like in, what, mid 80s, right, 1985,
**[0:52]** reading these papers, do you remember?
**[0:54]** >> Yeah.
**[0:59]** Well, coming from the courses I had taking in classical AI with expert systems,
**[1:05]** and suddenly discovering that there was all this world of thinking
**[1:09]** about how humans might be learning, and human intelligence.
**[1:14]** And how we might draw connections between that and artificial intelligence and
**[1:19]** computers.
**[1:21]** That was really exciting for me when I discovered this literature, and
**[1:25]** I started reading the connectionists, of course.
**[1:27]** So the papers from Geoff Hinton, [INAUDIBLE], and so on.
**[1:31]** And I worked on recurrent nets, I worked on speech recognition,
**[1:38]** I worked on HMNs, so graphical models.
**[1:42]** And then quickly, I moved to AT&T Bell Labs and MIT, where I did postdocs.
**[1:50]** And that's where I discovered some of the issues with the long-term
**[1:54]** dependencies with training neural nets.
**[1:57]** And then shortly after, I got recruited at UdeM back in Montreal,
**[2:02]** where I had spent most of my adolescent years.
**[2:08]** >> So as someone who's been there for the last several decades and seen it all,
**[2:12]** certainly seen a lot of it, tell me a bit about how you're thinking
**[2:17]** about deep learning, about neural networks has evolved over this time?
**[2:22]** >> We start with experiments, with intuitions, and
**[2:25]** theory sort of comes later.
**[2:27]** We now understand a lot better, for example,
**[2:30]** why Backdrop is working so well, why depth is so important.
**[2:35]** And these kinds of notions, we didn't have any solid justification for in those days.
**[2:41]** When we started working on deep nets in the early 2000s, we had the intuition that
**[2:46]** it made a lot of sense that a deeper network should be more powerful.
**[2:50]** But we didn't know how to take that and
**[2:54]** prove it, and of course, our experiments, initially, didn't work.
**[2:59]** >> And actually,
**[2:59]** what were the most important things that you think turned out to be right?
**[3:04]** And what were the biggest surprises of what turned out to be wrong,
**[3:08]** compared to what we knew 30 years ago?
**[3:11]** >> Sure, so one of the biggest mistakes I made was to think,
**[3:15]** like everyone else in the 90s,
**[3:18]** that you needed smooth nonlinearities in order for Backdrop to work.
**[3:24]** because I thought that if we had something like rectifying nonlinearities,
**[3:31]** where you have a flat part, that it would be really hard to train,
**[3:35]** because the derivative would be zero in so many places.
**[3:38]** And when we started experimenting with ReLU,
**[3:41]** with deep nets around 2010, I was obsessed with the idea that,
**[3:48]** we should be careful about whether neurons won't saturate too much on the zero part.
**[3:55]** But in the end, it turned out that, actually, the ReLU was working a lot
**[3:59]** better than the sigmoids and attach, and that was a big surprise.
**[4:03]** We did this, exploring this because of the biological connection, actually,
**[4:07]** not because we thought that it would be easier to optimize.
**[4:11]** But it turned out to work better, whereas I thought it would be harder to train.
**[4:16]** >> So let me ask you,
**[4:17]** what is the relationship between deep learning and the brain?
**[4:20]** There's the obvious answer, but I'm curious what's your answer to that?
**[4:25]** >> Well, the initial insight that really got me excited with
**[4:31]** neural nets was this idea from the connectionists that information is
**[4:37]** distributed across the activation of many neurons.
**[4:43]** Rather than being represented by sort of the grandmother cell,
**[4:47]** as they were calling it, a symbolic representation.
**[4:51]** That was the traditional view in classical AI.
**[4:54]** And I still believe this is a really important thing, and
**[4:58]** I see people rediscovering the importance of that, even recently.
**[5:03]** So that was really a foundation.
**[5:06]** The depth thing is something that came later, in the early 2000s,
**[5:12]** but it wasn't something I was thinking about in the 90s, for example.
**[5:16]** >> Right, right, and I remember you built a lot of relatively shallow, but
**[5:21]** very distributed representations for the word embeddings, right, very early on.
**[5:26]** >> Right, that's right, yeah,
**[5:28]** that's one of the things that I got really excited about in the late 90s.
**[5:33]** Actually, my brother, Samy, and I worked on the idea that we could use neural nets
**[5:38]** to tackle the curse of dimensionality, which was believed to be one
**[5:42]** of the central issues with the statistical learning.
**[5:45]** And that fact that we could have these distributed presentations could be used
**[5:51]** to represent joint distributions over many random variables in a very efficient way.
**[5:57]** And it turned out to work quite well, and then I extended this to joint
**[6:01]** distributions over sequences of words, and this is how the word embeddings were born.
**[6:04]** Because I thought, this will allow generalization
**[6:10]** across words that have similar semantic meaning and so on.
**[6:16]** >> So over the last couple decades, your research group has invented more ideas
**[6:20]** than anyone can summarize in a few minutes.
**[6:24]** So I'm curious, what are the inventions or
**[6:26]** ideas you're most proud of from your group?
**[6:29]** >> Right, so I think I mentioned long-term dependencies, the study of that.
**[6:35]** I think people still don't understand it well enough.
**[6:40]** Then there's the story I mentioned about curse of dimensionality,
**[6:45]** joint distributions with neural nets, which became, more recently,
**[6:49]** the that Hugo Larochelle did.
**[6:52]** And then, as I said, that gave rise to all sort of work
**[6:55]** on learning word embeddings for joint distributions for words.
**[6:59]** Then came, I think, probably the best known events of the work we did with
**[7:04]** deep learning, with stacks of auto encoders and stacks of RBMs.
**[7:09]** One thing then, it was the work on understanding better the difficulties
**[7:15]** of training deep nets with with the initialization ideas,
**[7:20]** and also, the vanishing gradient in deep nets.
**[7:24]** And that work actually was the one which gave rise to the experiments showing
**[7:29]** the importance of piecewise linear activation functions.
**[7:34]** Then I would say some of the most important work regards the work
**[7:38]** we did with unsupervised learning, the denoising auto-encoders, the GANs,
**[7:43]** which are very popular these days, the generative adversarial networks.
**[7:48]** The work we did with neural machine translation using attention,
**[7:54]** which turned out to be really important for making translation work.
**[8:01]** And it's currently used in industrial systems, like Google Translate.
**[8:05]** But this attention thing actually really changed my views on neural nets.
**[8:09]** Neural nets we used to think as machines that can map a vector to a vector.
**[8:14]** But really with attention mechanisms, you can now handle any kind of data structure.
**[8:19]** And this is really opening up a lot of interesting avenues.
**[8:24]** Direction of actually connecting to biology,
**[8:27]** one thing that I've been working on in the last couple of years is,
**[8:31]** how could we come up with something like backprop but that brains could implement.
**[8:36]** And we have a few papers in that direction that seems to be interesting for
**[8:41]** the neuroscience people.
**[8:43]** And then we're continuing in that direction of course.
**[8:47]** >> One of the topics that I know you've been thinking a lot about is
**[8:50]** the relationship between deep learning and
**[8:52]** the brain, can you tell us a bit more about that?
**[8:56]** >> The biological thing is something I've been thinking about for a while actually
**[9:03]** and having a lot of, I would say daydreaming about.
**[9:08]** Because I think of it like a puzzle.
**[9:12]** So we have these pieces of evidence from what we know from the brain and
**[9:16]** from learning in the brain like spike timing dependent plasticity.
**[9:21]** And on the other hand, we have all of these concepts from machine learning.
**[9:27]** The idea of globally training the whole system with respect to
**[9:31]** an objective function, and the idea of backprop.
**[9:35]** And what does backprop mean?
**[9:37]** Like, what does credit assignment really mean?
**[9:42]** When I started thinking about how brains could do something like backprop,
**[9:47]** it prompted me to think about, well, maybe there's some more general concepts behind
**[9:53]** backprop which make it so efficient which allow us to be efficient with backprop.
**[9:58]** And maybe there's a larger family of ways to do credit assignment, and
**[10:02]** that connects to questions that people in reinforcement learning have been asking.
**[10:06]** So it's interesting how sometimes asking a simple question leads
**[10:12]** you to thinking about so many different things, and forces you to think about so
**[10:18]** many elements that you like to bring together like a big puzzle.
**[10:23]** So this has gone for a number of years.
**[10:26]** And I need to say that this whole endeavor, like many of the ones that I
**[10:30]** have followed, has been highly inspired by Jeff Hinton's thoughts.
**[10:34]** So in particular, he gave this talk in 2007 I think,
**[10:41]** the first deep learning workshop on what he
**[10:46]** thought was the way that the brain is working.
**[10:52]** How kind of temporal code could be used for
**[10:56]** potentially doing some of the job of backprop.
**[11:00]** And that led to a lot of the ideas that I've explored in recent years with this.
**[11:07]** Yeah, so it's kind of an interesting story that has been
**[11:13]** running for a decade now, basically.
**[11:17]** >> One of the topics I've heard you speak about multiple times as well is
**[11:21]** unsupervised learning.
**[11:23]** Can you share your perspective on that?
**[11:26]** >> Yes, yes, so unsupervised learning is really important.
**[11:29]** Right now, our industrial systems are based on supervised learning,
**[11:34]** which essentially requires humans to define what the important concepts are for
**[11:40]** the problem and to label those concepts in the data.
**[11:43]** And we build all these amazing toys and services and systems using this.
**[11:49]** But humans are able to do much more.
**[11:52]** They are able to explore and discover new concepts by observation and
**[11:57]** interaction with the world.
**[12:00]** A two year old is able to understand intuitive physics.
**[12:05]** In other words, she understands gravity, she understands pressure,
**[12:08]** she understands inertia.
**[12:11]** She understands liquid, solids.
**[12:14]** And of course, her parents never told her about any of this stuff, right?
**[12:18]** So how did she figure it out?
**[12:21]** So that's the kind of question that unsupervised learning is trying to answer.
**[12:26]** It's not just about we have labels or we don't have labels.
**[12:30]** It's about actually building a mental
**[12:33]** construction that explains how the world works by observation.
**[12:38]** And more recently, I've been combining
**[12:42]** the ideas in unsupervised learning with the ideas in reinforcement learning.
**[12:45]** Because I believe that there is a very strong indication
**[12:50]** about the important underlying concepts that we're trying to disentangle,
**[12:54]** we're trying to separate from each other.
**[12:58]** That a human or machine can get by interacting with the world,
**[13:03]** by exploring the world and trying things and trying to control things.
**[13:08]** So these are I think tightly coupled to the original ideas of unsupervised
**[13:13]** learning.
**[13:14]** So my take on unsupervised learning,
**[13:17]** 15 years ago when we started doing the the and the RBMs and so
**[13:22]** on was very focused on the idea of learning good representations.
**[13:26]** And I still think this is an essential question.
**[13:29]** But the thing we don't know is how and what is a good representation?
**[13:34]** How do we figure out an objective function, for example?
**[13:39]** So we've tried many things over the years.
**[13:41]** And that's actually one of the cool things about unsupervised learning research,
**[13:46]** that there are so many different ideas, so
**[13:48]** different ways that this problem can be attacked.
**[13:51]** And that's just, maybe there's another one we'll discover next year that's completely
**[13:56]** different and maybe the brain is using something else completely different.
**[14:01]** So it's not incremental research,
**[14:03]** it's something that in itself is very exploratory.
**[14:07]** We don't have a good definition of what's the right objective function to even
**[14:11]** measure that a system is doing a good job on unsupervised learning.
**[14:14]** So of course, it's challenging, but at the same time,
**[14:19]** it leaves open a wide field of possibilities,
**[14:23]** which is what researchers really love, at least that's something that appeals to me.
**[14:28]** >> So today, there's so much going on in deep learning.
**[14:31]** And I think we've passed the point where it's possible for
**[14:34]** any one human to read every single deep learning paper being published.
**[14:38]** So I'm curious, what in deep learning today excites you the most?
**[14:44]** >> So I'm very ambitious, and I feel like the current state of
**[14:49]** the science of deep learning is far from where I'd like to see it.
**[14:54]** And I have the impression that our systems right now make the kind of mistakes
**[15:01]** that suggest they have a very superficial understanding of the world.
**[15:06]** So what excites me the most now is sort of direction of research where we're not
**[15:11]** trying to build systems that are going to do something useful.
**[15:15]** We're just going back to principles about, how can a computer observe the world,
**[15:21]** interact with the world, and discover how that world works?
**[15:26]** Even if that world is simple, something that we can program as a kind of video
**[15:30]** game, we don't know how to do that well.
**[15:32]** And that's cool, because I don't have to compete with Google, and Facebook, and
**[15:36]** Baidu, and so on, right?
**[15:38]** Because this is a kind of basic
**[15:41]** research that can be done by anyone in their garage and could change the world.
**[15:45]** So there are many, of course, many directions to attack this.
**[15:50]** But I see a lot of the fruitful interactions between ideas in deep
**[15:54]** learning and reinforcement learning being really important there.
**[15:59]** And I'm really excited that the progress in this direction
**[16:03]** Could have a huge impact on practical applications actually.
**[16:06]** Because if you look at some of the big challenges that we have in applications,
**[16:11]** like how we deal with new domains, or
**[16:14]** categories on which we have too few examples.
**[16:16]** And in cases where humans are very good at solving those problems.
**[16:21]** So these transfer learning and dramatization issues,
**[16:25]** they would become much easier to tackle if we had systems that had
**[16:30]** a better understanding of how the world works.
**[16:33]** A deeper understanding, right?
**[16:35]** What is actually going on?
**[16:36]** What are the causes of what I'm seeing?
**[16:40]** And how could I influence what I'm seeing by my actions?
**[16:44]** So these are the kinds of questions I'm really excited about these days.
**[16:50]** I think the connect, also the deep learning research that has evolved
**[16:56]** over the last couple of decades with even older questions in AI.
**[17:01]** Because a lot of the success in deep learning has been with perception.
**[17:07]** So what's left, right?
**[17:08]** What's left is sort of high level condition,
**[17:11]** which is about understanding at an abstract level how things work.
**[17:14]** So we are program of understanding high level abstractions I think has not
**[17:19]** reached those high levels of abstractions and so we have to get there.
**[17:23]** We have to think about reasoning, about sequential processing of information.
**[17:28]** We have to think of how causality works and
**[17:31]** how machines can discover all these things by themselves.
**[17:34]** Potentially guided by humans, but as much as possible in an autonomous way.
**[17:39]** >> And it sounds like from part of what you said that
**[17:42]** you're a fan of research approaches where you experiment on,
**[17:46]** I'm going to use term toy problem, not in a disparaging way.
**[17:49]** >> Right. >> But on the small problem.
**[17:51]** And you're optimistic that that transfers to bigger problems later.
**[17:55]** >> Yes, yes, it transfers in a way.
**[18:00]** Of course we're going to have to do some work to scale up and
**[18:05]** address those problems.
**[18:08]** But my main motivation for going for
**[18:11]** those toy problems is that we can understand better our failures and
**[18:17]** we can reduce the problem to something we can intuitively
**[18:22]** sort of manipulate and understand more easily.
**[18:26]** So sort of a classical divide and conquer science approach.
**[18:31]** And also, I think, something people don't think about it enough is
**[18:35]** the research cycle can be much faster, right?
**[18:38]** So if I can do an experiment in a few hours, I can progress much faster.
**[18:44]** If I have to try out a huge model that tries to capture the whole common
**[18:49]** sense and everything in the general knowledge, which eventually we'll do.
**[18:55]** It's just each experiment just takes too much time with current hardware.
**[18:59]** So while our hardware friends are building machines that are going to be a thousand
**[19:02]** or a million times faster, I'm doing those toy experiments.
**[19:06]** [LAUGH] >> You know, I've also heard you speak
**[19:11]** about the science of deep learning, not just as an engineering discipline,
**[19:15]** but doing more work to understand what's really going on.
**[19:19]** Do you want to share your thoughts on that?
**[19:22]** >> Yeah, absolutely.
**[19:24]** I fear that a lot of the work that we're doing is sort of like blind people trying
**[19:29]** to find their way.
**[19:30]** [LAUGH] And you can get a lot of luck and find interesting things that way.
**[19:37]** But really if we sort of stop a little bit and
**[19:40]** try to understand what we're doing in a way that's transferable,
**[19:45]** because we go down to principles to theory, but
**[19:49]** when I say theory I don't mean, necessarily, math.
**[19:53]** Of course I like math and so on, but I don't think that we need that everything
**[19:57]** be formalized mathematically but be formalized logically.
**[20:01]** In the sense that I can convince somebody that this should work,
**[20:05]** whether this makes sense.
**[20:07]** This is the most important aspect.
**[20:09]** And then math allows us to make that stronger and tighter.
**[20:14]** But really it's more about understanding.
**[20:17]** And it's about also doing our research,
**[20:21]** not to be the next baseline, or benchmark, or
**[20:25]** beat the other guys in the other lab, or the other company.
**[20:30]** It's more about what kind of question should we ask that would allow us to
**[20:35]** understand better the phenomena of interest.
**[20:38]** What makes, for example,
**[20:40]** training in deeper networks harder, or current nets harder?
**[20:45]** We have some ideas, but a lot of things we don't understand yet.
**[20:49]** So we can maybe design experiments whose goal is not to have a better algorithm,
**[20:54]** but just to understand better the algorithms we currently have or
**[20:58]** what circumstances make the particular algorithm work better and why.
**[21:03]** It's the why that really matters.
**[21:05]** That's what's science is about.
**[21:06]** It's why.
**[21:07]** >> Right. Today there are a lot of people that want
**[21:09]** to enter the field.
**[21:10]** And I'm sure you've answered this a lot in one-on-one settings, but
**[21:14]** with all the people watching this on video, what advice would you have for
**[21:18]** people that want to get into AI, get into deep learning?
**[21:21]** >> Right, so first of all, there are different motivations and
**[21:26]** different things you can do.
**[21:28]** What you need to become a deep learning researcher may not be the same as if you
**[21:33]** want to be an engineer who's going to use deep learning to build products.
**[21:37]** There's a different level of understanding that's needed in both cases.
**[21:40]** But in any case in both cases, practice.
**[21:46]** So to really master a subject like deep learning,
**[21:51]** of course you have to read a lot.
**[21:54]** You have to practice programming the things yourself.
**[21:58]** Very often I interview students who have used software.
**[22:02]** And these days there's so many good software around that you can just plug and
**[22:06]** play and understand nothing of what you're doing.
**[22:09]** Or at such as a superficial level that then it becomes hard to
**[22:12]** figure out when it doesn't work and what's going wrong.
**[22:16]** So actually trying to implement things yourself, even if it's inefficient.
**[22:19]** But just to make sure you really understand what is going on is really
**[22:24]** useful, and trying things yourself.
**[22:26]** >> So don't just use one of the programming frameworks where you can do
**[22:29]** everything in a few lines of code, but you don't really know what just happened.
**[22:33]** >> Exactly, exactly, and I would say even more than that.
**[22:37]** Trying to derive the thing yourself from first principles, if you can.
**[22:42]** That really helps.
**[22:44]** But yeah, the usual things you have to do like reading,
**[22:48]** looking at other people's code, writing your own code,
**[22:52]** doing lots of experiment, making sure you understand everything you do.
**[22:57]** So especially for the science part of it,
**[23:00]** trying to ask why am I doing this, why are people doing this?
**[23:05]** Maybe the answer is somewhere in the book and you have to read more.
**[23:11]** But it's even better if you can actually figure it out by yourself.
**[23:15]** Yeah, cool, yeah.
**[23:16]** And in fact, of the things I read, you and Ian [INAUDIBLE] and
**[23:21]** Aaron [INAUDIBLE] wrote a highly regarded book.
**[23:25]** >> Thank you, thank you.
**[23:27]** Yes, it's selling a lot.
**[23:28]** It's a bit crazy.
**[23:30]** I feel like there is more people reading this book than people who can
**[23:35]** read it [LAUGH] right now.
**[23:36]** But yeah, also proceedings of the ICLR I
**[23:40]** conference is probably the best concentrated place of good papers.
**[23:44]** Of course there are really good papers at NIPS and ICML and other conferences.
**[23:49]** But if you really want to go for a lot of good papers, just read the last few
**[23:54]** ICLR proceedings, and that will give you really good view of the field.
**[23:59]** >> Cool, yeah.
**[24:01]** Any other thoughts?
**[24:02]** When people ask you for advice, how does someone become good at deep learning?
**[24:09]** >> Well, it depends on where you come from.
**[24:14]** Don't be afraid by the math.
**[24:17]** Just develop the intuitions, and then the math become really easier to
**[24:22]** understand once you get the hang of what's going on at the intuitive level.
**[24:27]** And one good news is that you don't need five years of PhD to become
**[24:32]** proficient at deep learning.
**[24:34]** You can actually learn pretty quickly.
**[24:35]** If you have a good background in computer science and
**[24:40]** math, you can learn enough to use it and build things and
**[24:44]** start research experiments in just a few months.
**[24:48]** Something like six months for people with the right training.
**[24:53]** Maybe they don't know anything about machine learning, but
**[24:56]** if they're good at math and computer science, it can be very fast.
**[24:59]** And of course, so that means you need to have the right training in math and
**[25:02]** computer science.
**[25:03]** Sometimes what you learn in just computer science courses is not enough.
**[25:08]** You need some continuous math, especially.
**[25:13]** So this is probability, algebra and optimization, for example.
**[25:20]** >> I see. And calculus.
**[25:22]** >> And calculus, yeah.
**[25:24]** >> Thanks a lot, Joshua, for sharing all of the comments and insights and advice.
**[25:28]** Even though I've known you for a long time, there are many details of your early
**[25:32]** history that I didn't know until now, so thank you.
**[25:35]** >> Well, thank you, Andrew, for doing this
**[25:39]** special recording and what you're doing.
**[25:44]** I hope it's going to be used by a lot of people.
