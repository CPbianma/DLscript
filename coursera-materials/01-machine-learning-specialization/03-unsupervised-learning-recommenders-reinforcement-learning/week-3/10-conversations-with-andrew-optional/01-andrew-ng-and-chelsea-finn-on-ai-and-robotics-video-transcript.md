---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 3
section: Conversations with Andrew (Optional)
item_title: Andrew Ng and Chelsea Finn on AI and Robotics
duration: 33 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/vN4Mf/andrew-ng-and-chelsea-finn-on-ai-and-robotics
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Andrew Ng and Chelsea Finn on AI and Robotics — Transcript

**[0:00]** [MUSIC]
**[0:07]** Thanks for joining me here at Stanford University, with Professor Chelsea Finn,
**[0:11]** who is with both the computer science and the electrical engineering departments.
**[0:16]** Chelsea is a research lab that does cutting edge work,
**[0:19]** applying machine learning, especially reinforcement learning,
**[0:23]** to a range of robotics applications.
**[0:25]** So I'm really glad to have you here Chelsea.
**[0:27]** >> Happy to be here.
**[0:28]** >> So, I know that before you settled into working on computer science and
**[0:33]** machine learning, you actually considered a lot of career options ranging
**[0:38]** from biology to aerospace to computer science and electrical engineering.
**[0:42]** So, what made you make this choice?
**[0:46]** Yeah, so I was always drawn to engineering because I really like solving puzzles and
**[0:52]** solving problems.
**[0:53]** And when I arrived at MIT for my undergraduate,
**[0:56]** I was considering different engineering majors.
**[1:00]** And what really drew me first to computer science was that,
**[1:03]** it gives you a lot of flexibility in terms of the different paths that you can do.
**[1:08]** Essentially computer science empowers you to build lots of different things with
**[1:12]** software, with code and with that, I could eventually go into biology.
**[1:16]** If I wanted to, I could go into robotics,
**[1:18]** there's all sorts of really exciting things you can do with computer science.
**[1:21]** So that landed me in computer science and then once I decided on that, I really
**[1:26]** enjoyed a lot of the math that goes behind AI like probability and statistics.
**[1:32]** And I was also really drawn to this challenge of how can we build a computer,
**[1:37]** that can see like humans do.
**[1:38]** That can perceive things and images and can take actions in the world, yeah.
**[1:44]** >> So it was almost as if your choice was if you do computer science,
**[1:48]** you could do anything.
**[1:50]** And so that makes it, I guess what Marc Andreesen said software is eating the world.
**[1:55]** And I think Jen Huang said AI is eating software,
**[1:58]** and it feels like when you work in machine learning,
**[2:02]** you get to poke your nose in all corners of the world and do fun things.
**[2:06]** >> Absolutely, I think machine learning is a really exciting place to be.
**[2:09]** And I mentioned that computer science is very flexible and opens lots of doors, and
**[2:13]** I think that machine learning is very similar to that.
**[2:16]** There's so many different things you can do with machine learning, and so
**[2:19]** many different applications.
**[2:20]** I'm really excited about applications in robotics.
**[2:23]** But, we've seen lots of different applications in
**[2:27]** language processing in biology and in other fields.
**[2:31]** >> So your specialization, of the many things you do,
**[2:35]** a large fraction of your work is in robotics.
**[2:38]** And, when people look at the popular media or social media,
**[2:43]** you see these videos of for example, humanoid robots jumping up and
**[2:48]** down and doing and they do incredible things.
**[2:52]** How should one think about what robots really can and cannot do today?
**[2:57]** Because there are these amazing demo videos that looks like can do almost
**[3:01]** anything.
**[3:01]** But, how should one decide what is actually doable?
**[3:07]** >> Yeah, the videos that we see online from Boston Dynamics for
**[3:11]** example of robots doing back flips or doing Parkour and of course.
**[3:16]** Are really impressive, because they look really complicated.
**[3:19]** It's really easy in some ways anthropomorphize the robot and
**[3:22]** think that if you saw a person doing that, that would be very impressive.
**[3:27]** And they would probably be able to do lots of other really impressive things.
**[3:31]** And the catch is that in robotics in those videos and
**[3:34]** in many impressive demonstrations of robotics.
**[3:37]** The robot was set up for that particular environment, and
**[3:41]** it was tuned to do well with that set up.
**[3:43]** And if you change something about the environment,
**[3:46]** about the setup about what it's supposed to do, then the demo no longer works.
**[3:51]** The the robot will fall flat.
**[3:53]** So, the really the big challenge with robotics is getting robots to generalize,
**[3:58]** to be able to handle lots of different scenarios with lots of different objects,
**[4:03]** with lots of different environments.
**[4:05]** And right now, robots can do things in very controlled environments like in
**[4:09]** factories and they are very useful in factories.
**[4:12]** And, what I'm really excited about and what's really hard in robotics is
**[4:17]** giving them the flexibility in generality that of the skills that humans can do.
**[4:22]** >> Just to dig a little bit more into the specific one off one
**[4:25]** environment thing before going into generality.
**[4:29]** When someone sees the next cool robotics demo, how should they think about it or
**[4:34]** what the questions they should ask themselves?
**[4:37]** >> Yeah, so I think that the first question that someone can ask is,
**[4:41]** what will happen if something changes in the environment.
**[4:45]** What will happen if you move a block or
**[4:47]** if you put the robot in a slightly different position when it starts.
**[4:52]** Oftentimes you don't see those kinds of tests of the system's robustness or
**[4:57]** resilience to those variations.
**[4:59]** And, if you do start seeing those those demos where actually you kind of poke
**[5:03]** the robot, or you change the environment a little bit and it still works.
**[5:06]** That's when I think we can be really impressed.
**[5:10]** >> Cool, so a lot of your work has specifically been on making robots robust,
**[5:15]** to generalize or apply to lots of different environments.
**[5:19]** Just tell me more about that work and how you approach this problem.
**[5:23]** >> Definitely, so in other areas of machine learning we've seen huge successes
**[5:28]** where we take a very large data set.
**[5:31]** Like you take all of Wikipedia, and you train a neural network to be able
**[5:36]** to model the data in that very large and broad data set.
**[5:39]** And in robotics, one thing that I'm excited about is if we can somewhat
**[5:44]** replicate that sort of success.
**[5:46]** If we can collect a similarly diverse data set and
**[5:48]** allow robots to learn from that data set.
**[5:51]** Now, this is challenging for a couple of reasons, one is that we don't already have
**[5:55]** an existing data set, we don't have Wikipedia for robot motor control.
**[5:59]** There isn't data lying on the internet,
**[6:01]** of how exactly to move a robot's fingers to tie shoes, for example.
**[6:05]** So we don't have tons of diverse data already, but fortunately,
**[6:08]** robots in principle should be able to collect data themselves.
**[6:12]** And, that is an opportunity because it means that we might be able to
**[6:16]** collect a large amount of diverse data,
**[6:19]** by allowing the robots to collect their own data.
**[6:22]** But it's also a challenge because it means that we need to figure out how to allow
**[6:26]** robots to collect data that's useful, and diverse.
**[6:29]** And so, there's lots of different things that we explore in terms of approaching
**[6:32]** this problem, some is allowing robots to collect their own data in
**[6:35]** lots of different environments.
**[6:37]** Some is showing demonstrations to a robot, of how to perform a task.
**[6:41]** We've also explored a little bit of how to use data from the internet,
**[6:45]** like videos of humans to show a robot how to do a task.
**[6:48]** And incorporating all of these different data sources to allow robots to, well,
**[6:53]** once they've hopefully seen very diverse data sets like this.
**[6:56]** They might be able to generalize not just to the one scenario that they saw,
**[7:01]** in a lab environment but possibly the real world in the long term.
**[7:06]** >> One of the things we've seen is machine learning reinforcement learning,
**[7:09]** algorithms are great at playing video games.
**[7:11]** Because you can get, essentially infinite data playing a video game with yourself.
**[7:16]** What do you think of the role of simulation.
**[7:20]** Yeah, so we've definitely seen lots of successes of AI
**[7:24]** systems doing very well at video games.
**[7:27]** And simulation is somewhat similar because we can collect lots of data in
**[7:32]** simulation as well.
**[7:34]** One challenge with simulation is that,
**[7:37]** the physics in the simulation engine are not exactly the same as the real world.
**[7:43]** We know generally the laws of physics but, the friction on a table, for example,
**[7:48]** may not be exactly known.
**[7:49]** Or the friction between the grooves on a cap and
**[7:52]** a water bottle if you try to screw a water bowl,
**[7:54]** modeling that is very difficult and there are it's prone to errors.
**[7:59]** And then when you try to train a policy in that simulator to close a water bottle,
**[8:03]** for example, And then deploy it in the real world.
**[8:05]** It actually doesn't work because of those errors in the simulation.
**[8:09]** So I think it's a promising data source.
**[8:11]** But because of these inaccuracies and this challenge of transferring something
**[8:15]** that was learned in simulation to the real world.
**[8:18]** I don't think it's the only approach that we should bet on.
**[8:21]** I think that we should try to leverage lots of real data.
**[8:25]** >> And I wonder if it is surprising to someone watching this,
**[8:29]** why is it so hard to simulate the real world?
**[8:32]** It's just a lot of bottles two pieces of plastic and
**[8:35]** somehow we can't seem to figure out what's going on with two pieces of plastic.
**[8:40]** >> Yeah. So
**[8:40]** I think that there's lots of challenges.
**[8:42]** I mean, first is just modeling the low level physics.
**[8:47]** A lot of simulation engines out there,
**[8:49]** they will model time at a certain and in reality, time is much more
**[8:54]** fluid than operating at like 100 Hertz or something like that.
**[8:59]** And to actually accurately model these things, you may need to actually model at
**[9:03]** a very fine time discrimination and that gets very expensive.
**[9:07]** And then your simulator may actually be slower than actually running
**[9:10]** things in the real world.
**[9:11]** And then it's no longer useful in comparison to collecting data in
**[9:16]** the real world.
**[9:17]** And then the second thing is the real world is super diverse.
**[9:19]** And so actually creating the content of all of the kind of objects that you
**[9:24]** encounter even in everyday life.
**[9:26]** When you're eating lunch or when you're kind of cleaning up a table,
**[9:30]** creating all of that content is actually a really manual effort.
**[9:34]** And usually in machine learning systems, you want to kind of do away with
**[9:38]** the things that require a lot of manual effort.
**[9:41]** And try to automate and automate things so that they can be scaled up.
**[9:45]** >> Yeah.
**[9:46]** And in fact, in terms of the diversity of environments today,
**[9:50]** factories work great in robots where the environment is relatively controlled,
**[9:55]** relatively few unexpected things happening on average.
**[9:58]** I know some of your work has been looking to send robots into people's homes and
**[10:02]** do things in people's kitchens.
**[10:04]** That's one of the most uncontrolled environments in the world to say,
**[10:09]** you say a bit more about that.
**[10:11]** >> Yeah, absolutely.
**[10:12]** So I think that the controlled environments are the ones where we've seen
**[10:15]** a lot of success.
**[10:16]** And in the long term, I would love to see robots that could go into any
**[10:20]** environment like a home or an office and be useful to people.
**[10:24]** And to do that, we want to actually start collecting data in those environments.
**[10:29]** Often time in robotics research,
**[10:31]** we collect the data once in a lab environment and learn based on that data.
**[10:36]** But if we only collect real data in a lab,
**[10:38]** we're never going to actually get the robots out into the real world.
**[10:42]** So we're trying to start data collection efforts, actually putting robots into
**[10:47]** the real world so that they see the diversity of all these different homes.
**[10:51]** Rather than kind of the narrow data that you see in the lab.
**[10:55]** >> So I want to get your gut about one thing which is you talked about wanting to
**[11:00]** get a robot to go into a brand new home and make a bowl of cereal, right?
**[11:04]** Challenging to liquids, cereal fridge.
**[11:08]** What's your gut about how many different homes,
**[11:11]** how many different kitchens a robot will need to see.
**[11:14]** So how many training examples do you think a robot will need in order to have
**[11:18]** a good chance of doing on the N plus first on the next kitchen?
**[11:22]** >> Yeah. So
**[11:22]** I think it really depends on how hard the task is.
**[11:25]** If the task is as simple as I don't know, maybe pressing a button on the microwave,
**[11:32]** then I think that you may not need quite as much data for that.
**[11:36]** But I think even for a new kitchen, you probably need still quite a large
**[11:42]** number of kitchens in order to generalize to a new one, maybe 20 maybe 100.
**[11:48]** If it's a task that's more complex,
**[11:49]** like making a bowl of cereal, it's something that's super simple to people.
**[11:52]** But it's actually really hard for
**[11:54]** robots because there's lots of different steps involved.
**[11:57]** For that, I think you need more data.
**[11:59]** And probably also more kitchens as well, maybe in the thousands.
**[12:04]** And I also think that even if we had thousands of kitchens of data or
**[12:08]** tens of thousands might guess is that the problem still wouldn't be solved fully.
**[12:13]** We've seen applications like autonomous driving where there's tons of data and
**[12:18]** the problem isn't quite yet solved.
**[12:19]** So I think we also need to try to go beyond the data distribution and
**[12:23]** also allow robots to adapt on the fly in a new environment.
**[12:27]** >> Well, thousands, that's higher than my gut but that's interesting to
**[12:32]** see how it plays out and so on the theme of making robots more robust.
**[12:36]** I know a lot of your research work was also on meta learning or
**[12:40]** learning how to learn rather than us telling computer this is a learning
**[12:44]** algorithm to how they get a computer to even get better at learning.
**[12:48]** Can you say a bit about that.
**[12:51]** >> Yeah, absolutely.
**[12:51]** So, part of the motivation is that if a robot encounters a new kitchen,
**[12:56]** we don't want it to just run what it learned in that new kitchen.
**[13:00]** It may actually need to adapt and learn on the fly.
**[13:03]** It may need to, for example, if it's trying to open the door to a pantry and
**[13:07]** the door is a little bit different.
**[13:09]** It may need to take a little bit of experience and trial and
**[13:12]** error on that door in order to figure out how to open it.
**[13:15]** And we want to allow systems to do this sort of learning process on
**[13:20]** the fly at test time in new scenarios.
**[13:23]** And unfortunately, if you just run machine learning from scratch at test time on
**[13:27]** a very small amount of data that won't work very well.
**[13:30]** You need large amounts of data in order to learn something.
**[13:34]** So what meta learning tries to do is it tries to take experience in previous
**[13:39]** kitchens or previous tasks.
**[13:40]** And optimize for the ability to learn new things,
**[13:44]** the ability to learn new things based on having learned lots of previous things.
**[13:50]** >> So for example, what best learning rate which wish to adapt to new
**[13:54]** kitchen setting and lots of other things, one could tune.
**[13:59]** >> Yeah, absolutely.
**[13:59]** So the simplest setting is if you're only optimizing for
**[14:02]** one parameter, like the learning rate in a new situation.
**[14:05]** And in more complex meta learning algorithms, you can sort of optimize for
**[14:09]** the entire learning algorithm.
**[14:10]** >> So I think if you as one of the world experts in meta learning, in fact,
**[14:15]** if I remember this is a big part of your PhD thesis.
**[14:18]** Which you did way back with Peter, who was my PhD student at Stanford.
**[14:23]** And so just say more about how meta learning works.
**[14:27]** >> Yeah. So
**[14:28]** there's a few different approaches to metal learning.
**[14:31]** But the approach that was in my PhD thesis was essentially putting a learning
**[14:36]** problem inside another learning problem.
**[14:39]** So it's actually forms this bilevel optimization,
**[14:42]** this two level learning problem where you are actually trying to optimize for
**[14:46]** all of the parameters in this inner learning problem.
**[14:49]** Such that you could achieve faster learning or more efficient learning.
**[14:53]** >> Yeah, I remember reading some early papers and very impressive.
**[14:58]** So lots of software algorithms, machine learning algorithms,
**[15:02]** reinforcement learning algorithms.
**[15:04]** One part of your work is you also run a robotics lab
**[15:08]** with robots running around robot arms.
**[15:11]** I'm curious for someone that has not yet spent a lot of time in a robotics lab.
**[15:16]** Can you tell us what is it like if a student were to join your lab,
**[15:20]** what's it like to show up and work in the morning and work in a robotics lab?
**[15:25]** >> Yeah. So in the lab, it's not all that different
**[15:29]** from running machine learning experiments where you run code,
**[15:34]** you try to train a model and then evaluate that model.
**[15:38]** But in addition to those everyday things,
**[15:41]** there's also interfacing with the real robot.
**[15:45]** So oftentimes a lot of projects might start with the simulation and
**[15:49]** start iterating on algorithms.
**[15:51]** Using a physics engine that might involve actually kind of designing aspects of
**[15:55]** the simulation to test the hypotheses you want to test.
**[15:58]** And also sometimes products won't involve that simulation step or
**[16:01]** maybe you've already iterated in simulation.
**[16:04]** And on the real robot, there is everything from setting up the control stack.
**[16:09]** Such that you can actually command the robot to move to a certain position,
**[16:13]** to setting up the cameras, to collecting data with the robot.
**[16:17]** You might be collecting data by using like a V R controller, for
**[16:21]** example, to tell the robot to move to certain positions.
**[16:26]** And then also actually when it comes time to evaluate a model, it involves
**[16:31]** actually running that on the robot and seeing what the robot does in real life.
**[16:37]** It's a pretty fun process at least for me, I think it's very rewarding to actually
**[16:41]** see the robot do something rather than just see some numbers or
**[16:44]** some accuracy of your model.
**[16:45]** But it's also requires a little bit of persistence because robots can break down.
**[16:52]** You might have a motor that breaks, you may not have set up the camera correctly.
**[16:57]** It might be giving you all zeros for example.
**[16:59]** There's many more bugs that can come up than in a system without a robot.
**[17:04]** >> So, number of people have had experience debugging software and
**[17:08]** then there's debugging machine learning algorithms which has different
**[17:13]** practices and ideas.
**[17:14]** And then can you say a bit about what debugging hardware in a robotics
**[17:19]** lab is like?
**[17:20]** >> Definitely.
**[17:21]** I mean, in general, with debugging, you want to rule out
**[17:26]** possible sources of errors, possible sources of bugs and
**[17:31]** often times you might have a guess that it is from the software or the hardware.
**[17:37]** And from there, I think that many of the machine learning things will apply.
**[17:44]** You want to look at your data.
**[17:45]** And because a lot of the data is actually collected in the lab,
**[17:49]** it may not be from a data set, then there may be something that is wrong about it.
**[17:54]** And you may want to actually look at the images that the robot is seeing,
**[17:58]** maybe visualize some of the features that your model has learned.
**[18:01]** I guess one thing that we did recently is we wanted to actually
**[18:06]** deploy a policy on multiple different robots.
**[18:10]** And so we would actually replay actions on a robot and make sure that
**[18:15]** the robot was reproducing a certain motion that we wanted it to reproduce.
**[18:20]** How you debug depends a lot on the problem.
**[18:28]** I don't know if there's any one way or any kind of single bug that comes up the most
**[18:32]** because there's all sorts of sources of bugs.
**[18:35]** But yeah, that gives us a little bit of a sense for what it looks like.
**[18:38]** >> And I thought one of the lovely and
**[18:40]** frustrating things about robotics as opposed to software is in software.
**[18:44]** If you make a mistake,
**[18:45]** you can always revert back to the early version of software.
**[18:48]** But that time that you do something and your robot breaks and then you go, boy,
**[18:52]** that's another two months of work or something to rebuild that.
**[18:56]** That's a unique experience in hardware.
**[18:59]** >> Definitely.
**[19:00]** And because we're doing a lot of work on the software side of things,
**[19:04]** we typically try to get robots that won't break, like nice high end robots so
**[19:08]** that we can worry more about the software and less about the hardware.
**[19:12]** But if there are cases where a robot might break, we try to get robots where you can
**[19:17]** pretty easily swap out parts where if one motor breaks,
**[19:20]** you could just swap in a new motor rather than having to repurpose the whole thing.
**[19:25]** But certainly there, there's lots of challenges that come up.
**[19:29]** >> Yeah. And
**[19:30]** you know, I used to fly autonomous helicopters.
**[19:33]** So every time a helicopter crash, fortunately, we manage to keep it safe and
**[19:38]** away from people, then this is a well frankly destroyed helicopter and then we
**[19:42]** have to just go build a new one but it's nice when you go to do that too often.
**[19:46]** >> Yeah. Fortunately, arms do not crash too much.
**[19:49]** >> I see. Yeah.
**[19:49]** Yeah, maybe I should have chosen, working on that instead isn't it.
**[19:53]** So in your robotics lab,
**[19:54]** one tool of choice that you've often used is reinforcement learning.
**[19:59]** Can you say a bit about the practical lessons, tips and tricks for how to
**[20:04]** apply reinforcement learning amazing algorithms to your hardware robots.
**[20:09]** >> Yeah. So,
**[20:10]** reinforcement learning is a really appealing framework for
**[20:13]** robotics because in principle, it would allow a robot to learn something
**[20:17]** completely on its own through trial and error from data that it collected itself.
**[20:22]** And so it's something that we're really excited about for that reason,
**[20:25]** but it's also really challenging for a number of reasons.
**[20:27]** So first reinforcement learning typically assumes that
**[20:30]** you're given some reward signal, some feedback.
**[20:33]** And if you're trying to learn how to play a game, like play a pong or
**[20:37]** another Atari game, you can just use the score as a reward function and
**[20:41]** just try to maximize your score.
**[20:43]** But the real world doesn't give you a score.
**[20:46]** It doesn't give the robot a score when it tries to learn something.
**[20:49]** And instead the robot might need to learn its own reward function.
**[20:52]** It might need to learn what it means to accomplish a task at the same time as also
**[20:56]** trying to learn how to accomplish that task in the physical world.
**[21:00]** So that's one big challenge and one way that we approach it.
**[21:04]** Another challenge is typically in this trial and error.
**[21:07]** >> And so how do you learn the reward?
**[21:09]** Like from a demonstration?
**[21:11]** How, how do you learn the reward?
**[21:12]** Yeah. >> So we learned it in a few
**[21:14]** different ways.
**[21:15]** We often give it at least give it some examples of what success looks like.
**[21:19]** And we also sometimes give it a full demonstration of this is
**[21:22]** an example of what we want you to do.
**[21:24]** And then you can get into techniques like inverse reinforcement learning,
**[21:28]** which you worked on a long time ago as well and
**[21:31]** actually try to invert the reinforcement learning process and
**[21:34]** try to figure out what reward function underlies this behavior.
**[21:37]** So beyond learning, reward functions,
**[21:39]** another challenge is autonomy in the process of reinforcement learning.
**[21:44]** So typically, you think of it as a trial-and-error process where you try to
**[21:48]** solve the task and then you want to try it again.
**[21:52]** And in between trying the task and trying it again,
**[21:55]** you need to somehow get back to some starting point.
**[21:58]** And maybe for example, if you're trying to learn how to do a back flip,
**[22:02]** trying it again will involve standing up after you fall down.
**[22:07]** But actually,
**[22:08]** sometimes learning that resetting behavior is also quite challenging.
**[22:12]** And there is this challenging interplay between learning how to do the task and
**[22:16]** also learning how to recover from all the ways that you failed at the task in
**[22:21]** the entire process of doing that.
**[22:22]** >> It's really automating the research process so that you run repeat experiments
**[22:27]** without having to lug a robot around every single time to put it back.
**[22:31]** >> Exactly.
**[22:32]** Yeah.
**[22:33]** >> Cool, really cool.
**[22:34]** And in fact, in your application of reinforcement learning,
**[22:40]** I think you're among the earliest researchers to do more or
**[22:46]** less or completely end to end robotics.
**[22:49]** End to end reinforcement learning.
**[22:51]** Can you say a bit about what that was like in the early days and
**[22:56]** why you went that route?
**[22:58]** >> Yeah. So at the start of my PhD,
**[23:00]** deep learning was just starting to become popular.
**[23:03]** After Alex Net was showing that you can do very well with deep neural
**[23:08]** networks trained end to end for computer vision.
**[23:11]** And I had just arrived at Berkeley for my phD.
**[23:14]** There were some people that were working on reinforcement learning
**[23:17]** with neural networks.
**[23:19]** And I was pretty excited about that work and I wanted to see in the past work,
**[23:23]** it was all blind.
**[23:24]** The robot wasn't using cameras in any way.
**[23:26]** And I wanted to see if we could learn a neural network that directly maps from
**[23:30]** the images taken by the robot's camera to the torques applied to the robots joints.
**[23:35]** And in that first project,
**[23:36]** it was a lot of work to try to actually get that initial result.
**[23:39]** But we were excited to see that we actually could get a single neural network
**[23:44]** that could learn something like screwing a cap on a bottle or
**[23:47]** putting a coat hanger on a coat rack with a single neural network mapping directly
**[23:52]** from pixels to torques.
**[23:54]** And it was a pretty exciting result.
**[23:56]** It was definitely very different from what the rest
**[23:59]** of the robotics community was working on.
**[24:01]** And I think the, the paper that we worked on was actually rejected twice because
**[24:05]** people didn't like deep learning, roboticists didn't like that these
**[24:09]** neural networks were very black box and you couldn't understand them.
**[24:12]** But eventually it got published and it was accepted.
**[24:15]** And now it's actually become a much more prominent paradigm in robotics where
**[24:21]** a lot more people are now training neural networks to represent the policy,
**[24:26]** to represent how the robot chooses actions based on the camera images.
**[24:31]** >> I think that early work you did was quite visionary and set an important help,
**[24:36]** set an important new direction for the field.
**[24:39]** What's your prediction for where this will go?
**[24:42]** Do you think the percentage of practical robotics work that this train end to end?
**[24:46]** How much do you think that will continue to go up or not?
**[24:51]** >> Yeah, I certainly think that it will continue to grow quite a bit.
**[24:55]** Still not all of the robotics research community is looking at these kinds of
**[24:59]** approaches, in part because there are useful techniques in control theory
**[25:03]** that are useful, especially in controlled scenarios, like we talked about.
**[25:08]** But I think that it will certainly grow.
**[25:10]** I think that especially as the machine learning field continues to make really
**[25:14]** impressive advances, I hope that that will convince more people that this
**[25:19]** sort of paradigm is really promising for robotics as well, especially in terms of
**[25:23]** handling the vast degree of variety in objects and environments in the world.
**[25:28]** In terms of looking forward, in terms of understanding what might happen in
**[25:33]** the next 10 or 20 years in robotics, one thing that I'm really excited about
**[25:38]** that we touched on a little bit, is trying to train robots on broader datasets.
**[25:43]** A lot of the field of robot learning is still collecting a dataset for
**[25:47]** a project in a lab and then training on that small data set.
**[25:51]** It's small because it has to be, because you collected it for that project.
**[25:55]** And I think if we imagine that if computer vision researchers had to collect
**[25:59]** image net for every single project that they did,
**[26:02]** they probably wouldn't be making that much progress.
**[26:05]** And so, my prediction at least for for the coming years is to move towards a paradigm
**[26:10]** where we reuse data sets a lot, we use much larger datasets, and ideally are kind
**[26:15]** of sharing data sets across institutions, across robot platforms.
**[26:19]** And scaling up the data that these systems are trained on such that
**[26:23]** they can generalize more broadly.
**[26:26]** >> That's an exciting vision.
**[26:27]** And how do we get there?
**[26:29]** For images, everyone uses PNG files, and GIF files, and
**[26:33]** JPEG files, so, the data is highly portable and highly shareable.
**[26:38]** If different research labs just have different pieces of hardware,
**[26:42]** how do you make that happen for robotics?
**[26:45]** >> Yeah, so, it's definitely challenging.
**[26:47]** The place that we're starting that I'm quite excited about is, first,
**[26:52]** trying to actually have a little bit of consensus, bring the community together
**[26:57]** to say, okay, let's start with this robot platform with roughly this setup so
**[27:02]** that we can at least standardize on some of it, and then try to collect lots and
**[27:07]** lots of diverse data on that fairly standardized platform.
**[27:11]** Start from there, and then if we're able to get some signs of life and
**[27:16]** some positive success from collecting a broad dataset with those standardized
**[27:21]** choices, then starting to standardize less and less and move on.
**[27:25]** Maybe the same robot but with a different control stack, and
**[27:28]** then maybe starting to move towards different versions of that robot,
**[27:32]** different grippers, and ultimately lots of different robots and lots of environments.
**[27:36]** >> Cool, yep, great, this is exciting vision.
**[27:41]** So, this is one of the things you're doing in robotics.
**[27:45]** Just looking more broadly, with all the work you do in reinforcement learning,
**[27:51]** some not even apply to robotics but other applications, where do you hope for
**[27:56]** reinforcement learning and robotics will go in the next many years?
**[28:00]** >> Yeah, so, I think that, I mean,
**[28:02]** I'm hoping that it will move towards these reusable datasets and very broad datasets.
**[28:08]** I also think that even beyond robotics, I think that there's lots of other
**[28:13]** applications of reinforcement learning as well.
**[28:16]** So, for example, in some of our recent work, we applied reinforcement learning,
**[28:20]** and actually meta reinforcement learning, a combination of meta learning and
**[28:24]** reinforcement learning, to education to give feedback on student work,
**[28:27]** where students would program a game like Breakout and then the system would
**[28:31]** actually play the game and find the bugs that the students made and give them
**[28:34]** feedback on how to improve their program and how to continue to learn how to code.
**[28:39]** >> Now, that's very cool.
**[28:40]** In fact, robots are so visual, sometimes it's easy to forget that reinforcement
**[28:45]** learning is a general technique for decision making with delayed rewards.
**[28:49]** That's useful for many things other than robots.
**[28:54]** Frankly, when I see more robots,
**[28:57]** I used to try to get all my students to learn to solder.
**[29:02]** I don't know if that was a- >> I learned how to solder an undergrad,
**[29:05]** although I don't think I actually ever used that in my robotics work.
**[29:09]** Wow, I see.
**[29:10]** Maybe things have moved on, but I had to, yeah.
**[29:14]** >> I think we would just buy robots that didn't need some soldering.
**[29:18]** >> So, your journey has led you to do cutting edge work in
**[29:22]** reinforcement learning and robotics.
**[29:26]** I'm curious what advice you would have for
**[29:29]** someone looking to break into reinforcement learning or to robotics.
**[29:34]** Not everyone owns a cool robot, that an easy program, but
**[29:38]** how should someone get started?
**[29:41]** >> Yeah, my main advice would just be to try to get your feet wet,
**[29:46]** and just try to build something, try to program and code something up.
**[29:52]** There's lots of different things that you can do.
**[29:54]** And I think that learning by trying to build something,
**[29:57]** by trying to do something,
**[29:58]** is one of the coolest ways to learn because you have a certain goal in mind.
**[30:02]** >> But would you build something using a simulated robot or
**[30:05]** do you think you should just build a little robot?
**[30:08]** >> I think that starting with a simulated robot is probably the easiest and
**[30:13]** there's less of a learning curve and less things that you have to do,
**[30:17]** you don't have to go out and buy hardware.
**[30:20]** That said, I think that also trying to
**[30:22]** work a little bit with hardware right off the bat is great, and
**[30:27]** it definitely teaches you about how hard robotics is, robotics is really hard.
**[30:33]** But also, by kind of struggling to get the robot to do something,
**[30:36]** it makes it all that much more rewarding when it actually does something cool,
**[30:41]** when it does something that you wanted it to do.
**[30:44]** And, I don't know, some of the robots that we use are fairly expensive.
**[30:48]** But nowadays, there's actually lots of robots that are fairly inexpensive that
**[30:54]** people can buy, or you can kind of build your own robot by connecting wheels and
**[31:00]** a camera or maybe even a smartphone together to build something.
**[31:05]** I actually got started with LEGO robotics in middle school and
**[31:08]** you could also build robots out of LEGO and get started that way.
**[31:11]** >> Yes, actually, I remember I went to LEGO robotics competitions when I was in
**[31:15]** middle school or something.
**[31:17]** That was interesting set of experiences.
**[31:20]** So, to someone taking the machine learning specialization,
**[31:25]** if their goal is to work in enforcement learning and
**[31:29]** robotics, what else would you recommend they look at?
**[31:34]** What are the other resources you think would be helpful?
**[31:37]** >> Definitely, so there are resources in terms of just learning about
**[31:41]** reinforcement learning, and there are kind of courses online,
**[31:46]** there's also kind of course videos, there's textbooks like Sutton Barto.
**[31:52]** And so, those are lots of resources.
**[31:54]** I also think that there are lots of, I don't know, videos online,
**[31:58]** tutorials ,code bases,
**[32:00]** you can actually check out a physics engine like the Majko Physics Engine,
**[32:04]** which is freely available, and try to kind of explore with that.
**[32:08]** So, yeah, those are a few resources.
**[32:10]** There's also one thing that we use a lot to interface
**[32:13]** with robots is called the Robot Operating System, or ROS.
**[32:16]** And so, learning about that can also be useful.
**[32:19]** >> That came out of my research lab wayback working with with a garage.
**[32:24]** Yeah, good times.
**[32:25]** Sorry, I didn't mean to interrupt.
**[32:27]** >> Yeah, so, I think that those are some of the resources, and yeah,
**[32:30]** not too much more than that.
**[32:31]** >> Cool, yeah, very cool.
**[32:32]** With the world moving forward and evolving, it feels like the number of path
**[32:37]** for someone wanting to get involved in this is even growing and
**[32:41]** it probably gets a little bit easier every year for someone to enter this field.
**[32:46]** So, this is exciting time to be in.
**[32:47]** >> Yeah, definitely.
**[32:48]** >> Thanks for joining me here at Stanford University.
**[32:51]** I'm with Professor Chelsea Finn who is with both the computer science and
**[32:55]** the electrical engine departments, and leads a research group that does cutting
**[33:00]** edge work on applying reinforcement learning and
**[33:03]** machine learning to robotics and other applications.
**[33:06]** Thanks for joining us, Chelsea.
**[33:08]** >> Yeah, happy to be here.
**[33:09]** [MUSIC]
