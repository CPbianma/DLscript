---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 2
section: Heroes of Deep Learning (Optional)
item_title: Pieter Abbeel Interview
duration: 16 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/eqiZZ/pieter-abbeel-interview
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Pieter Abbeel Interview — Transcript

**[0:02]** So, thanks a lot, Pieter,
**[0:04]** for joining me today.
**[0:06]** I think a lot of people know you as
**[0:08]** a well-known machine learning and deep learning and robotics researcher.
**[0:12]** I'd like to have people hear a bit about your story.
**[0:15]** How did you end up doing the work that you do?
**[0:18]** That's a good question and actually if you would have asked me as a 14-year-old,
**[0:22]** what I was aspiring to do,
**[0:24]** it probably would not have been this.
**[0:26]** In fact, at the time,
**[0:28]** I thought being a professional basketball player would be the right way to go.
**[0:32]** I don't think I was able to achieve it.
**[0:34]** I feel the machine learning lucked out,
**[0:36]** that the basketball thing didn't work out.
**[0:38]** Yes, that didn't work out.
**[0:39]** It was a lot of fun playing basketball but it didn't work
**[0:41]** out to try to make it into a career.
**[0:44]** So, what I really liked in school was physics and math.
**[0:48]** And so, from there,
**[0:50]** it seemed pretty natural to study engineering which
**[0:52]** is applying physics and math in the real world.
**[0:55]** And actually then, after my undergrad in electrical engineering,
**[0:58]** I actually wasn't so sure what to do because,
**[1:00]** literally, anything engineering seemed interesting to me.
**[1:03]** Understanding how anything works seems interesting.
**[1:07]** Trying to build anything is interesting.
**[1:09]** And in some sense,
**[1:11]** artificial intelligence won out because it seemed like it
**[1:13]** could somehow help all disciplines in some way.
**[1:18]** And also, it seemed somehow a little more at the core of everything.
**[1:22]** You think about how a machine can think,
**[1:24]** then maybe that's more the core of everything else than picking any specific discipline.
**[1:30]** I've been saying AI is the new electricity,
**[1:33]** sounds like the 14-year-old version of you;
**[1:35]** had an earlier version of that even.
**[1:37]** You know, in the past few years you've done a lot of work in deep reinforcement learning.
**[1:44]** What's happening? Why is deep reinforcement learning suddenly taking off?
**[1:49]** Before I worked in deep reinforcement learning,
**[1:51]** I worked a lot in reinforcement learning;
**[1:52]** actually with you and Durant at Stanford, of course.
**[1:56]** And so, we worked on autonomous helicopter flight,
**[1:59]** then later at Berkeley with some of my students who worked
**[2:02]** on getting a robot to learn to fold laundry.
**[2:05]** And kind of what characterized the work was a combination
**[2:09]** of learning that enabled things that would not be possible without learning,
**[2:13]** but also a lot of domain expertise in combination with the learning to get this to work.
**[2:18]** And it was very
**[2:20]** interesting because you needed domain expertise which
**[2:22]** was fun to acquire but, at the same time,
**[2:24]** was very time-consuming for every new application you wanted to succeed of;
**[2:28]** you needed domain expertise plus machine learning expertise.
**[2:31]** And for me it was in 2012 with
**[2:34]** the ImageNet breakthrough results from Geoff Hinton's group in Toronto,
**[2:39]** AlexNet showing that supervised learning, all of a sudden,
**[2:42]** could be done with far less engineering for the domain at hand.
**[2:48]** There was very little engineering by vision in AlexNet.
**[2:50]** It made me think we really should revisit
**[2:53]** reinforcement learning under the same kind of viewpoint and see if we can
**[2:57]** get the diversion of reinforcement learning to work and do
**[3:01]** equally interesting things as had just happened in the supervised learning.
**[3:05]** It sounds like you saw earlier than
**[3:08]** most people the potential of deep reinforcement learning.
**[3:12]** So now looking in to the future,
**[3:14]** what do you see next?
**[3:16]** What are your predictions for the
**[3:17]** next several ways to come in deep reinforcement learning?
**[3:20]** So, I think what's interesting about deep reinforcement learning is that,
**[3:23]** in some sense, there is many more questions than in supervised learning.
**[3:26]** In supervised learning, it's about learning an input output mapping.
**[3:29]** In reinforcement learning there is the notion of: Where does the data even come from?
**[3:34]** So that's the exploration problem.
**[3:36]** When you have data, how do you do credit assignment?
**[3:38]** How do you understand what actions you took early on got you the reward later?
**[3:43]** And then, there is issues of safety.
**[3:44]** When you have a system autonomously collecting data,
**[3:47]** it's actually rather dangerous in most situations.
**[3:50]** Imagine a self-driving car company that says,
**[3:51]** we're just going to run deep reinforcement learning.
**[3:53]** It's pretty likely that car would get into a lot of
**[3:55]** accidents before it does anything useful.
**[3:57]** You needed negative examples of that, right?
**[3:59]** You do need some negative examples somehow, yes;
**[4:02]** and positive ones, hopefully.
**[4:04]** So, I think there is still a lot of challenges in
**[4:07]** deep reinforcement learning in terms of
**[4:09]** working out some of the specifics of how to get these things to work.
**[4:12]** So, the deep part is the representation,
**[4:14]** but then the reinforcement learning itself still has a lot of questions.
**[4:18]** And what I feel is that,
**[4:20]** with the advances in deep learning,
**[4:22]** somehow one part of the puzzle in reinforcement learning has been largely addressed,
**[4:27]** which is the representation part.
**[4:29]** So, if there is a pattern we can
**[4:31]** probably represent it with a deep network and capture that pattern.
**[4:34]** And how to tease apart the pattern is still a big challenge in reinforcement learning.
**[4:39]** So I think big challenges are,
**[4:41]** how to get systems to reason over long time horizons.
**[4:45]** So right now, a lot of the successes
**[4:47]** in deep reinforcement learning are a very short horizon.
**[4:50]** There are problems where,
**[4:52]** if you act well over a five second horizon,
**[4:54]** you act well over the entire problem.
**[4:57]** And so a five second scale is something very different from a day long scale,
**[5:02]** or the ability to live a life as a robot or some software agent.
**[5:06]** So, I think there's a lot of challenges there.
**[5:09]** I think safety has a lot of challenges in terms of,
**[5:12]** how do you learn safely and also how do
**[5:14]** you keep learning once you're already pretty good?
**[5:17]** So, to give an example again that
**[5:20]** a lot of people would be familiar with, self-driving cars,
**[5:23]** for a self-driving car to be better than a human driver,
**[5:26]** should human drivers maybe get into bad accidents every three million miles or something.
**[5:31]** And so, that takes a long time to see the negative data;
**[5:35]** once you're as good as a human driver.
**[5:37]** But you want your self-driving car to be better than a human driver.
**[5:40]** And so, at that point the data collection becomes really really difficult to get
**[5:43]** that interesting data that makes your system improve.
**[5:48]** So, it's a lot of challenges related to exploration, that tie into that.
**[5:52]** But one of the things I'm actually most excited about right now is seeing
**[5:57]** if we can actually take a step back and also learn the reinforcement learning algorithm.
**[6:02]** So, reinforcement is very complex,
**[6:05]** credit assignment is very complex, exploration is very complex.
**[6:07]** And so maybe, just like
**[6:08]** how deep learning for supervised learning was able to replace a lot of domain expertise,
**[6:13]** maybe we can have programs that are learned,
**[6:17]** that are reinforcement learning programs that do all this,
**[6:20]** instead of us designing the details.
**[6:22]** During the reward function or during the whole program?
**[6:25]** So, this would be learning the entire reinforcement learning program.
**[6:28]** So, it would be, imagine,
**[6:30]** you have a reinforcement learning program, whatever it is,
**[6:34]** and you throw it out some problem and then you see how long it takes to learn.
**[6:38]** And then you say, well, that took a while.
**[6:41]** Now, let another program modify this reinforcement learning program.
**[6:44]** After the modification, see how fast it learns.
**[6:48]** If it learns more quickly,
**[6:49]** that was a good modification and maybe keep it and improve from there.
**[6:54]** Well, I see, right. Yes, and pace the direction.
**[6:57]** I think it has a lot to do with, maybe,
**[6:59]** the amount of compute that's becoming available.
**[7:01]** So, this would be running reinforcement learning in the inner loop.
**[7:05]** For us right now, we run reinforcement learning as the final thing.
**[7:08]** And so, the more compute we get,
**[7:11]** the more it becomes possible to maybe run something
**[7:14]** like reinforcement learning in the inner loop of a bigger algorithm.
**[7:19]** Starting from the 14-year-old,
**[7:22]** you've worked in AI for some 20 plus years now.
**[7:25]** So, tell me a bit about how your understanding of AI has evolved over this time.
**[7:32]** When I started looking at AI,
**[7:35]** it's very interesting because it really
**[7:38]** coincided with coming to Stanford to do my master's degree there,
**[7:41]** and there were some icons there like John McCarthy who I got to talk with,
**[7:46]** but who had a very different approach to,
**[7:49]** and in the year 2000,
**[7:50]** for what most people were doing at the time.
**[7:52]** And also talking with Daphne Koller.
**[7:54]** And I think a lot of my initial thinking of AI was shaped by Daphne's thinking.
**[7:59]** Her AI class, her probabilistic graphical models class,
**[8:04]** and kind of really being intrigued by
**[8:06]** how simply a distribution of her many random variables and then being able to condition
**[8:11]** on some subsets variables and draw on conclusions about others could
**[8:14]** actually give you so much if you can somehow make it computationally attractable,
**[8:19]** which was definitely the challenge to make it computable.
**[8:23]** And then from there,
**[8:25]** when I started my Ph.D. And you arrived at Stanford,
**[8:28]** and I think you give me a really good reality check,
**[8:30]** that that's not the right metric to evaluate your work by,
**[8:35]** and to really try to see the connection from what
**[8:38]** you're working on to what impact they can really have,
**[8:41]** what change it can make rather than what's the math that happened to be in your work.
**[8:46]** Right. That's amazing.
**[8:48]** I did not realize, I've forgotten that.
**[8:50]** Yes, it's actually one of the things, aside most often that people asking,
**[8:54]** if you going to cite only one thing that has stuck with you from Andrew's advice,
**[9:01]** it's making sure you can see the connection to where it's actually going to do something.
**[9:05]** You've had and you're continuing to have an amazing career in AI.
**[9:11]** So, for some of the people listening to you on video now,
**[9:14]** if they want to also enter or pursue a career in AI,
**[9:18]** what advice do you have for them?
**[9:20]** I think it's a really good time to get into artificial intelligence.
**[9:25]** If you look at the demand for people, it's so high,
**[9:28]** there is so many job opportunities,
**[9:30]** so many things you can do, researchwise,
**[9:32]** build new companies and so forth.
**[9:34]** So, I'd say yes, it's definitely a smart decision in terms of actually getting going.
**[9:39]** A lot of it, you can self-study,
**[9:41]** whether you're in school or not.
**[9:42]** There is a lot of online courses, for instance,
**[9:44]** your machine learning course,
**[9:45]** there is also, for example,
**[9:48]** Andrej Karpathy's deep learning course which has videos online,
**[9:52]** which is a great way to get started,
**[9:54]** Berkeley who has a deep reinforcement learning course
**[9:57]** which has all of the lectures online.
**[9:59]** So, those are all good places to get started.
**[10:01]** I think a big part of what's important is to make sure you try things yourself.
**[10:06]** So, not just read things or watch videos but try things out.
**[10:10]** With frameworks like TensorFlow,
**[10:14]** Chainer, Theano, PyTorch and so forth,
**[10:16]** I mean whatever is your favorite,
**[10:17]** it's very easy to get going and get something up and running very quickly.
**[10:21]** To get to practice yourself, right?
**[10:24]** With implementing and seeing what does and seeing what doesn't work.
**[10:27]** So, this past week there was an article in
**[10:29]** Mashable about a 16-year-old in United Kingdom,
**[10:31]** who is one of the leaders on Kaggle competitions.
**[10:34]** And it just said,
**[10:36]** he just went out and learned things,
**[10:39]** found things online, learned everything himself and
**[10:41]** never actually took any formal course per se.
**[10:44]** And there is a 16-year-old just being very competitive in Kaggle competition,
**[10:49]** so it's definitely possible.
**[10:50]** We live in good times.
**[10:53]** If people want to learn.
**[10:54]** Absolutely.
**[10:55]** One question I bet you get all sometimes
**[10:57]** is if someone wants to enter AI machine learning and deep learning,
**[11:00]** should they apply for a Ph.D. program or should they get the job with a big company?
**[11:06]** I think a lot of it has to do with maybe how much mentoring you can get.
**[11:12]** So, in a Ph.D. program,
**[11:14]** you're such a guaranteed,
**[11:16]** the job of the professor,
**[11:17]** who is your adviser,
**[11:18]** is to look out for you.
**[11:20]** Try to do everything they can to,
**[11:21]** kind of, shape you,
**[11:23]** help you become stronger at whatever you want to do, for example, AI.
**[11:28]** And so, there is a very clear dedicated person, sometimes you have two advisers.
**[11:32]** And that's literally their job and that's why they are professors,
**[11:34]** most of what they like about being professors often is helping
**[11:37]** shape students to become more capable at things.
**[11:41]** Now, it doesn't mean it's not possible at companies,
**[11:43]** and many companies have really good mentors and have people who love
**[11:46]** to help educate people who come in and strengthen them, and so forth.
**[11:51]** It's just, it might not be as much of a guarantee and a given,
**[11:55]** compared to actually enrolling in a Ph.D. program or that's the crooks of
**[12:00]** the program is that you're going to learn and somebody is there to help you learn.
**[12:06]** So it really depends on the company and depends on the Ph.D. program.
**[12:09]** Absolutely, yes. But I think it is key that you can learn a lot on your own.
**[12:14]** But I think you can learn a lot faster if you have somebody who's more experienced,
**[12:17]** who is actually taking it up as
**[12:20]** their responsibility to spend time with you and help accelerate your progress.
**[12:24]** So, you've been one of the most visible leaders in deep reinforcement learning.
**[12:28]** So, what are the things that
**[12:30]** deep reinforcement learning is already working really well at?
**[12:32]** I think, if you look at some deep reinforcement learning successes,
**[12:37]** it's very, very intriguing.
**[12:39]** For example, learning to play Atari games from pixels,
**[12:42]** processing this pixels which is just numbers that are being
**[12:45]** processed somehow and turned into joystick actions.
**[12:49]** Then, for example, some of the work we did at Berkeley was,
**[12:52]** we have a simulated robot inventing walking and the reward
**[12:57]** that it's given is as simple as the further you go north the
**[12:59]** better and the less hard you impact with the ground the better.
**[13:02]** And somehow it decides that walking slash running is the thing to invent whereas,
**[13:06]** nobody showed it, what walking is or running is.
**[13:10]** Or robot playing with children's stories and learn to kind of put them together,
**[13:14]** put a block into matching opening, and so forth.
**[13:16]** And so, I think it's really interesting that in all of these it's possible to learn
**[13:20]** from raw sensory inputs all the way to raw controls,
**[13:24]** for example, torques at the motors.
**[13:27]** But at the same time.
**[13:29]** So it is very interesting that you can have a single algorithm.
**[13:32]** For example, you know thrust is impulsive and you can learn,
**[13:35]** can have a robot learn to run,
**[13:36]** can have a robot learn to stand up,
**[13:38]** can have instead of a two legged robot,
**[13:40]** now you're swapping a four legged robot.
**[13:42]** You run the same reinforcement algorithm and it still learns to run.
**[13:46]** And so, there is no change in the reinforcement algorithm.
**[13:49]** It's very, very general. Same for the Atari games.
**[13:51]** DQN was the same DQN for every one of the games.
**[13:54]** But then, when it actually starts hitting
**[13:56]** the frontiers of what's not yet possible as well,
**[14:00]** it's nice it learns from scratch for each one of
**[14:03]** these tasks but would be even nicer if it could reuse things it's learned in the past;
**[14:07]** to learn even more quickly for the next task.
**[14:09]** And that's something that's still on the frontier and not yet possible.
**[14:13]** It always starts from scratch, essentially.
**[14:16]** How quickly, do you think, you see deep
**[14:19]** reinforcement learning get deployed in the robots around us,
**[14:22]** the robots they're getting deployed in the world today.
**[14:25]** I think in practice the realistic scenario is one
**[14:29]** where it starts with supervised learning,
**[14:32]** behavioral cloning; humans do the work.
**[14:35]** And I think a lot of businesses will be built
**[14:38]** that way where it's a human behind the scenes doing a lot of the work.
**[14:41]** Imagine Facebook Messenger assistant.
**[14:44]** Assistant like that could be built with a human behind
**[14:47]** the curtains doing a lot of the work; machine learning,
**[14:51]** matches up with what the human does and starts making suggestions to
**[14:54]** human so the humans has a small number of options that we can just click and select.
**[14:58]** And then over time,
**[14:59]** as it gets pretty good,
**[15:01]** you're starting fusing some reinforcement learning where you give it actual objectives,
**[15:04]** not just matching the human behind the curtains
**[15:06]** but giving objectives of achievement like,
**[15:09]** maybe, how fast were these two people able to plan their meeting?
**[15:14]** Or how fast were they able to book their flight?
**[15:16]** Or things like that. How long did it take?
**[15:18]** How happy were they with it?
**[15:20]** But it would probably have to be bootstrap of a lot of
**[15:22]** behavioral cloning of humans showing how this could be done.
**[15:27]** So it sounds behavioral cloning just supervise learning to
**[15:30]** mimic whatever the person is doing and then gradually later on,
**[15:33]** the reinforcement learning to have it think about longer time horizons?
**[15:37]** Is that a fair summary?
**[15:38]** I'd say so, yes.
**[15:39]** Just because straight up reinforcement learning from scratch is really fun to watch.
**[15:43]** It's super intriguing and very few things more fun to watch
**[15:46]** than a reinforcement learning robot starting from nothing and inventing things.
**[15:50]** But it's just time consuming and it's not always safe.
**[15:54]** Thank you very much. That was fascinating.
**[15:56]** I'm really glad we had the chance to chat.
**[15:58]** Well, Andrew thank you for having me. Very much appreciate it.
