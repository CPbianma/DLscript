---
type: video-transcript
specialization: Deep Learning Specialization
course: Structuring Machine Learning Projects
week: 2
section: Heroes of Deep Learning (Optional)
item_title: Ruslan Salakhutdinov Interview
duration: 17 min
source_url: https://www.coursera.org/learn/machine-learning-projects/lecture/kR8gk/ruslan-salakhutdinov-interview
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Ruslan Salakhutdinov Interview — Transcript

**[0:03]** Welcome, Rus, I'm really glad you could join us here today.
**[0:06]** >> Thank you, thank you Andrew.
**[0:08]** >> So today you're the director of research at Apple, and
**[0:11]** you also have a faculty, a professor for Carnegie Mellon University.
**[0:16]** So I'd love to hear a bit about your personal story.
**[0:20]** How did you end up doing this deep learning work that you do?
**[0:24]** Yeah, it's actually, to some extent it was,
**[0:27]** I started in deep learning to some extent by luck.
**[0:32]** I did my master's degree at Toronto, and then I took a year off.
**[0:35]** I was actually working in the financial sector.
**[0:37]** It's a little bit surprising.
**[0:40]** And at that time, I wasn't quite sure whether I want to go for my PhD or not.
**[0:44]** And then something happened, something surprising happened.
**[0:46]** I was going to work one morning, and I bumped into Geoff Hinton.
**[0:50]** And Geoff told me, hey, I have this terrific idea.
**[0:55]** Come to my office, I'll show you.
**[0:56]** And so, we basically walked together and he started telling me about these
**[1:01]** Boltzmann Machines and contrasting divergence, and some of the tricks which
**[1:06]** I didn't at that time quite understand what he was talking about.
**[1:10]** But that really, really excited, that was very exciting and really excited me.
**[1:15]** And then basically, within three months I started my PhD with Geoff.
**[1:21]** So that was kind of the beginning, because that was back in 2005, 2006.
**[1:28]** And this is where some of the original deep learning algorithms, using
**[1:32]** Restricted Boltz Machines, unsupervised pre-training, were kind of popping up.
**[1:37]** And so that's how I started it, was really.
**[1:41]** That one particular morning when I bumped into Geoff completely changed my
**[1:46]** future career moving forward.
**[1:48]** >> And then in fact you were co-author on
**[1:52]** one of the very early papers on Restricted
**[1:55]** Boltzmann Machines that really helped with this resurgence of neural networks and deep learning.
**[2:00]** Tell me a bit more what that was like working on that
**[2:03]** seminal- >> Yeah, this was actually a really, this
**[2:06]** was exciting, yeah, it was the first year, it was my first year as a P.h.D. student.
**[2:10]** And Geoff and
**[2:11]** I were trying to explore these ideas of using Restricted Boltz Machines and
**[2:17]** using pre-training tricks to train multiple layers.
**[2:21]** And specifically we were trying to focus on auto-encoders,
**[2:25]** how do we do a non-linear extension of PCA effectively?
**[2:29]** And it was very exciting, because we got these systems to work on endless digits
**[2:34]** which was exciting, but then the next steps for
**[2:37]** us were to really see whether we can extend these models to dealing with faces.
**[2:42]** I remember we had this Olivetti faces dataset.
**[2:45]** And then we started looking at can we do compression for documents?
**[2:48]** And we started looking at all these different data, real value count,
**[2:52]** binary, and throughout a year,
**[2:57]** I was a first year PhD student, so it was a big learning experience for me.
**[3:03]** But and really within
**[3:06]** six or seven months, we were able to get really interesting results, I mean really good results.
**[3:11]** I think that we were able to train these very deep auto-encoders.
**[3:14]** This is something that you couldn't do at that time using sort of
**[3:19]** traditional optimization techniques.
**[3:22]** And then it turned out into really, really exciting period for us.
**[3:27]** That was super exciting, yeah, because it was a lot of learning for me,
**[3:33]** but at the same time, the results turned out to be really,
**[3:38]** really impressive for what we were trying to do.
**[3:42]** >> So in the early days of those researches of deep learning,
**[3:45]** a lot of the activity was centered on Restricted Boltzmann Machines, and
**[3:49]** then Deep Boltzmann Machines.
**[3:52]** There's still a lot of exciting research there being done,
**[3:54]** including some in your group, but what's happening with Boltzmann Machines and
**[3:58]** Restricted Boltzmann Machines?
**[3:59]** >> Yeah, that's a very good question.
**[4:00]** I think that,
**[4:01]** in the early days, the way that we were using Restricted Boltz Machines
**[4:07]** is you sort of can imagine training a stack of these Restricted Boltz Machines
**[4:10]** that would allow you to learn effectively one layer at a time.
**[4:14]** And there's a good theory behind when you add a particular layer,
**[4:17]** it improves variational bound and so forth under certain conditions.
**[4:21]** So there was a theoretical justification, and these models were working
**[4:24]** quite well in terms of being able to pre-train these systems.
**[4:28]** And then around 2009, 2010, once the Computes started showing up,
**[4:35]** GPUs, then a lot of us started realizing that actually directly optimizing these
**[4:41]** deep neural networks was giving similar results or even better results.
**[4:47]** >> So just standard backprop without the pre-training or
**[4:50]** the Restricted Boltz Machine.
**[4:51]** >> That's right, that's right.
**[4:52]** And that's sort of over three or four years, and it was exciting for
**[4:56]** the whole community, because people felt that wow,
**[4:58]** you can actually train these deep models using these pre-training mechanisms.
**[5:02]** And then, with more Compute people started realizing that you can just
**[5:06]** basically do standard backpropagation, something that we couldn't do back in 2005 or
**[5:11]** 2004, because it would take us months to do it on CPU's.
**[5:17]** And so that was a big change.
**[5:20]** The other thing that I think that we haven't really figured out
**[5:24]** what to do with Boltz Machines and Deep Boltzmann Machines.
**[5:28]** I believe they're very powerful models,
**[5:29]** because you can think of them generative models.
**[5:32]** They're trying to model coupling distributions in the data, but
**[5:36]** when we start looking at learning algorithms, learning algorithms right now,
**[5:40]** they require using Markov Chain Monte Carlo and variational learning and such,
**[5:45]** which is not as scalable as backpropagation algorithms.
**[5:50]** So we yet have to figure out more efficient ways of training these models,
**[5:55]** and also the use of convolution,
**[5:57]** it's something that's fairly difficult to integrate into these models.
**[6:02]** I remember some of your work on using probabilistic max pooling for
**[6:07]** sort of building these generative models of different objects, and
**[6:12]** using these ideas of convolution was also very, very exciting, but
**[6:16]** at the same time, it's still extremely hard to train these models, so.
**[6:20]** >> How likely is work?
**[6:21]** >> Yes, how likely is work, right?
**[6:22]** And so we still have to figure out where.
**[6:27]** On the other side, some of the recent work using variational auto-encoders, for
**[6:31]** example, which could be viewed as interactive versions of Bolzmann Machines.
**[6:35]** We have figured out ways of training these modules, a work by Max Welling and
**[6:40]** Diederik Kingma, on using reparameterization tricks.
**[6:44]** And now we can use backpropagation algorithm within the stochastic system,
**[6:50]** which is driving a lot of progress right now.
**[6:53]** But we haven't quite figured out how to do that in the case of Boltzmann Machines.
**[6:59]** >> So that's actually a very interesting perspective I actually wasn't aware of, which is that in an early era where
**[7:04]** computers were slower, that the RBM, pre-training
**[7:09]** was really important, it was only faster computation
**[7:11]** that drove switching to standard backprop.
**[7:17]** In terms of the evolution of the community's thinking in deep learning and
**[7:21]** other topics, I know you spend a lot time thinking about this,
**[7:24]** the generative, unsupervised versus supervised approaches.
**[7:28]** Do you share a bit about how your thinking about that has evolved over time?
**[7:32]** >> Yeah, I think that's a really, I feel like it's a very important topic,
**[7:37]** particularly if we think about unsupervised, semi-supervised or
**[7:41]** generative models because to some extent a lot of successes that we've seen very
**[7:46]** recently is due to supervised learning, and back in the early days,
**[7:50]** unsupervised learning was primarily viewed as unsupervised pre-training,
**[7:55]** because we didn't know how to train these multi layer systems.
**[7:59]** And even today, if you're working in settings where you have lots and
**[8:04]** lots of unlabeled data and a small fraction of labeled examples,
**[8:08]** these unsupervised pre-training models,
**[8:11]** building these generative models, can help for supervised eyes.
**[8:15]** So I think that a lot of us in the community, it kind of was the belief.
**[8:20]** When I started doing my PhD, was all about generative models and trying to learn
**[8:25]** these stacks of model because that was the only way for us to train these systems.
**[8:30]** Today, there is a lot of work right now in generative modeling.
**[8:35]** If you look at Generative Adversarial Networks.
**[8:38]** If you look at variational auto-encoders,
**[8:40]** deep energy models is something that my lab is working on right now as well.
**[8:45]** I think it's very exciting research, but perhaps we haven't quite figured it out,
**[8:50]** again, for many of you who are thinking about getting into deep learning field,
**[8:55]** this is one area that's, I think we'll make a lot of progress in,
**[8:59]** hopefully in the near future.
**[9:01]** >> So, unsupervised learning.
**[9:02]** >> Unsupervised learning, right.
**[9:04]** Or maybe you can think of it as unsupervised learning, or semi-supervised learning, where you have,
**[9:07]** I give you some hints or some examples of
**[9:12]** what different things mean and I throw you lots and lots of unlabeled data.
**[9:18]** >> So that was actually a very important insight that in an earlier era of
**[9:21]** deep learning where computers where just slower,
**[9:23]** the Restricted Boltzmann Machine and Deep Boltzmann Machine that was needed for
**[9:27]** initializing the neural network weights, but as computers got faster,
**[9:31]** straight backprop then started to work much better.
**[9:34]** So one other topic that I know you spend a lot of time thinking about is
**[9:39]** the supervised learning versus generative models, unsupervised learning approaches.
**[9:45]** So how does your,
**[9:47]** tell me a bit about how your thinking on that debate has evolved over time?
**[9:51]** >> I think that we all believe that we should be able to make progress there.
**[9:56]** It's just all the work on Boltz machines, variational auto-encoders, GANs.
**[10:03]** You think a lot of these models as generative models, but we haven't quite
**[10:08]** figured it out how to really make them work and
**[10:13]** how can you make use of large moments.
**[10:16]** And even for, I see a lot of in IT sector,
**[10:21]** companies have lots and lots of data, lots of unlabeled data, lots of
**[10:26]** efforts for going through annotations because that's the only way for
**[10:30]** us to make progress right now.
**[10:33]** And it seems like we should be able to
**[10:36]** make use of unlabeled data because it's just abundance of it.
**[10:40]** And we haven't quite figured out how to do that yet.
**[10:44]** >> So you mentioned for people wanting to enter deep learning research,
**[10:48]** unsupervised learning is exciting area.
**[10:50]** Today there are a lot of people wanting to enter deep learning,
**[10:54]** either research or applied work, so for this global community,
**[10:57]** either research or applied work, what advice would you have?
**[11:01]** >> Yes, I think that one of the key advices I think I
**[11:06]** should give is people entering that field,
**[11:10]** I would encourage them to just try different things and
**[11:14]** not be afraid to try new things, and not be afraid to try to innovate.
**[11:18]** I can give you one example,
**[11:20]** which is when I was a graduate student, we were looking at neural nets,
**[11:24]** and these are highly non-convex systems that are hard to optimize.
**[11:29]** And I remember talking to my friends within the optimization community.
**[11:33]** And the feedback was always that, well, there's no way you can solve these
**[11:38]** problems because these are non-convex, we don't understand optimization,
**[11:41]** how could you ever even do that compared to doing convex optimization?
**[11:46]** And it was surprising, because in our lab we never really
**[11:51]** cared that much about those specific problems.
**[11:55]** We're thinking about how can we optimize and
**[11:58]** whether we can get interesting results.
**[11:59]** And that effectively was driving the community so
**[12:04]** we we're not scared, maybe to some extent because we were
**[12:09]** lacking actually the theory behind optimization.
**[12:13]** But I would encourage people to just try and
**[12:16]** not be afraid to try to tackle hard problems.
**[12:19]** >> Yeah, and I remember you once said, don't learn to code just into high level
**[12:22]** deep learning frameworks, but actually understand deep learning.
**[12:25]** >> Yes, that's right.
**[12:26]** I think that it's one of the things that I try to do when I teach a deep learning
**[12:30]** class is, one of the homeworks, I'm asking people to actually code
**[12:35]** backpropogation algorithms for convolutional neural networks.
**[12:39]** And it's painful, but at the same time, if you do it once,
**[12:43]** you'll really understand how these systems operate, and how they work.
**[12:49]** And how you can efficiently implement them on GPU, and
**[12:53]** I think it's important for you to, when you go into research or industry,
**[12:58]** you have a really good understanding of what these systems are doing.
**[13:03]** So it's important, I think.
**[13:05]** >> Since you have both academic experience as professor, and
**[13:09]** corporate experience, I'm curious, if someone wants to enter deep learning,
**[13:13]** what are the pros and cons of doing a PhD versus joining a company?
**[13:18]** >> Yeah, I think that's actually a very good question.
**[13:22]** In my particular lab, I have a mix of students.
**[13:25]** Some students want to go and take an academic route.
**[13:28]** Some students want to go and take an industry route.
**[13:32]** And it's becoming very challenging because you can do amazing research in industry,
**[13:38]** and you can also do amazing research in academia.
**[13:41]** But in terms of pros and cons, in academia,
**[13:46]** I feel like you have more freedom to work on long-term problems, or if you think
**[13:53]** about some crazy problem, you can work on it, so you have a little bit more freedom.
**[13:59]** At the same time the research that you're doing in industry is also very exciting
**[14:03]** because in many cases with your research you can impact
**[14:08]** millions of users if you develop a core AI technology.
**[14:14]** And obviously, within the industry you have much more
**[14:19]** resources in terms of Compute, and be able to do really amazing things.
**[14:26]** So there are pluses and minuses, it really depends on what you want to do.
**[14:30]** And right now it's interesting,
**[14:32]** very interesting environment where academics move to industry, and
**[14:36]** then folks from industry move to academia, but not as much.
**[14:40]** And so it's, it's very exciting times.
**[14:45]** >> It sounds like academic machine learning is great and corporate machine
**[14:49]** learning is great, and the most important thing is just jump in, right?
**[14:52]** Either one, just jump in.
**[14:54]** >> It really depends on your preferences because you can do amazing research in
**[14:58]** either place.
**[14:59]** >> So you've mentioned unsupervised learning is one exciting frontier for
**[15:03]** research.
**[15:04]** Are there other areas that you consider exciting frontiers for research?
**[15:08]** >> Yeah, absolutely.
**[15:09]** I think that what I see now, in the community right now,
**[15:12]** particularly in deep learning community, is there are a few trends.
**[15:17]** One particular area I think is really exciting
**[15:20]** is the area of deep reinforcement learning.
**[15:24]** Because we were able to figure out how we could train agents in virtual worlds.
**[15:28]** And this is something that in just the last couple of years, you see a lot,
**[15:33]** of lot of progress, of how can we scale these systems, how can we develop new algorithms, how can we get
**[15:38]** agents to communicate to each other, with each other,
**[15:42]** and I think that that area is, and in general, the settings where
**[15:46]** you're interacting with the environment is super exciting.
**[15:52]** The other area that I think is really exciting as
**[15:55]** well is the area of reasoning and natural language understanding.
**[16:00]** So can we build dialogue-based systems?
**[16:03]** Can we build systems that can reason, that can read text and
**[16:09]** be able to answer questions intelligently.
**[16:12]** I think this is something that a lot of research is focusing on right now.
**[16:17]** And then there's another sort of sub-area also is
**[16:21]** this area of being able to learn from few examples.
**[16:26]** So typically people think of it as one-shot learning or transfer learning,
**[16:31]** a setting where you learn something about the world,
**[16:36]** and I throw you a new task at you and you can solve this task very quickly.
**[16:41]** Much like humans do without requiring lots and lots of labeled examples.
**[16:46]** And so this is something that's, a lot of us in the community are trying to figure out
**[16:52]** how we can do that and how can we come closer to human-like learning abilities.
**[16:58]** >> Thank you, Rus, for sharing all the comments and insights.
**[17:00]** That was interesting,
**[17:02]** hearing the story of your early days doing this as well.
**[17:04]** >> [LAUGH]. Thanks, Andrew, yeah.
**[17:07]** Thanks for having me.
