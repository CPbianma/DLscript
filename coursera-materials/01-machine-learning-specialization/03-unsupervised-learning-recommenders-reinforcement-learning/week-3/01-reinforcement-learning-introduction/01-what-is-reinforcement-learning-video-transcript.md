---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 3
section: Reinforcement learning introduction
item_title: What is Reinforcement Learning?
duration: 9 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/RrrOL/what-is-reinforcement-learning
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# What is Reinforcement Learning? — Transcript

**[0:02]** Welcome to this final week of the machine learning specialization.
**[0:05]** It's a little bit bittersweet for me that we're approaching the end of this
**[0:09]** specialization, but I'm looking forward to this week,
**[0:12]** sharing with you some exciting ideas about reinforcement learning.
**[0:15]** In machine learning, reinforcement learning is one of those ideas that while
**[0:20]** not very widely applied in commercial applications yet today,
**[0:23]** is one of the pillars of machine learning.
**[0:26]** And has lots of exciting research backing it up and improving it every single day.
**[0:31]** So let's start by taking a look at what is reinforcement learning.
**[0:36]** Let's start with an example.
**[0:38]** Here's a picture of an autonomous helicopter.
**[0:41]** This is actually the Stanford autonomous helicopter, weighs 32 pounds and
**[0:45]** it's actually sitting in my office right now.
**[0:47]** Like many other autonomous helicopters, it's instrumented with an onboard
**[0:51]** computer, GPS, accelerometers, and gyroscopes and
**[0:54]** the magnetic compass so it knows where it is at all times quite accurately.
**[0:59]** And if I were to give you the keys to this helicopter and
**[1:02]** ask you to write a program to fly it, how would you do so?
**[1:06]** Radio controlled helicopters are controlled with joysticks like these and
**[1:11]** so the task is ten times per second you're given the position and orientation and
**[1:16]** speed and so on of the helicopter.
**[1:18]** And you have to decide how to move these two control sticks in order to keep
**[1:22]** the helicopter balanced in the air.
**[1:25]** By the way,
**[1:25]** I've flown radio controlled helicopters as well as quad rotor drones myself.
**[1:30]** And radio controlled helicopters are actually quite a bit harder to fly,
**[1:34]** quite a bit harder to keep balanced in the air.
**[1:36]** So how do you write a program to do this automatically?
**[1:39]** Let me show you a fun video of something we got
**[1:42]** a Stanford autonomous helicopter to do.
**[1:44]** Here's a video of it flying under the control of a reinforcement learning
**[1:48]** algorithm.
**[1:49]** And let me play the video.
**[1:51]** I was actually the cameraman that day and
**[1:54]** this is the helicopter flying on the computer control and
**[1:57]** if I zoom out the video, you see the trees planted in the sky.
**[2:00]** So using reinforcement learning,
**[2:02]** we actually got this helicopter to learn to fly upside down.
**[2:06]** We told it to fly upside down.
**[2:07]** And so reinforcement learning has been used to get helicopters to fly a wide
**[2:12]** range of stunts or we call them aerobatic maneuvers.
**[2:16]** By the way, if you're interested in seeing other videos,
**[2:19]** you can also check them out at this URL.
**[2:21]** So how do you get a helicopter to fly itself using reinforcement learning?
**[2:27]** The task is given the position of the helicopter to decide how to
**[2:32]** move the control sticks.
**[2:34]** In reinforcement learning, we call the position and orientation and
**[2:39]** speed and so on of the helicopter the state s.
**[2:43]** And so the task is to find a function that maps from the state of the helicopter
**[2:48]** to an action a, meaning how far to push the two control sticks in order
**[2:53]** to keep the helicopter balanced in the air and flying and without crashing.
**[2:59]** One way you could attempt this problem is to use supervised learning.
**[3:05]** It turns out this is not a great approach for autonomous helicopter flying.
**[3:09]** But you could say, well if we could get a bunch of observations of states and
**[3:15]** maybe have an expert human pilot tell us what's the best action y to take.
**[3:20]** You could then train a neural network using supervised learning to
**[3:25]** directly learn the mapping from the states s which I'm calling x here,
**[3:30]** to an action a which I'm calling the label y here.
**[3:34]** But it turns out that when the helicopter is moving through the air is
**[3:38]** actually very ambiguous, what is the exact one right action to take.
**[3:43]** Do you tilt a bit to the left or a lot more to the left or
**[3:47]** increase the helicopter stress a little bit or a lot?
**[3:50]** It's actually very difficult to get a data set of x and the ideal action y.
**[3:56]** So that's why for a lot of task of controlling a robot like a helicopter and
**[4:01]** other robots, the supervised learning approach doesn't work well and
**[4:05]** we instead use reinforcement learning.
**[4:08]** Now a key input to a reinforcement learning is something called the reward or
**[4:14]** the reward function which tells the helicopter when it's doing well and
**[4:19]** when it's doing poorly.
**[4:22]** So the way I like to think of the reward function is a bit like training a dog.
**[4:26]** When I was growing up, my family had a dog and
**[4:29]** it was my job to train the dog or the puppy to behave.
**[4:33]** So how do you get a puppy to behave well?
**[4:35]** Well, you can't demonstrate that much to the puppy.
**[4:38]** Instead you let it do its thing and whenever it does something good,
**[4:43]** you go, good dog.
**[4:44]** And whenever they did something bad, you go, bad dog.
**[4:47]** And then hopefully it learns by itself how to do more of the good dog and
**[4:52]** fewer of the bad dog things.
**[4:53]** So training with the reinforcement learning algorithm is like that.
**[4:56]** When the helicopter's flying well, you go, good helicopter and
**[5:00]** if it does something bad like crash, you go, bad helicopter.
**[5:03]** And then it's the reinforcement learning algorithm's job to figure out how to get
**[5:08]** more of the good helicopter and fewer of the bad helicopter outcomes.
**[5:11]** One way to think of why reinforcement learning is so
**[5:15]** powerful is you have to tell it what to do rather than how to do it.
**[5:20]** And specifying the reward function rather than the optimal action gives you a lot
**[5:25]** more flexibility in how you design the system.
**[5:28]** Concretely for flying the helicopter, whenever it is flying well,
**[5:33]** you may give it a reward of plus one every second it is flying well.
**[5:39]** And maybe whenever it's flying poorly you may give it a negative reward or
**[5:43]** if it ever crashes, you may give it a very large negative reward like negative 1,000.
**[5:50]** And so this would incentivize the helicopter to spend a lot more
**[5:54]** time flying well and hopefully to never crash.
**[5:57]** But here's another fun video.
**[6:00]** I was using the good dog bad dog analogy for reinforcement learning for many years.
**[6:05]** And then one day I actually managed to get my hands on a robotic dog and
**[6:10]** could actually use this reinforcement learning good dog bad dog
**[6:14]** methodology to train a robot dog to get over obstacles.
**[6:18]** So this is a video of a robot dog that using reinforcement learning,
**[6:23]** which rewards it, moving toward the left of the screen has learned
**[6:28]** how to place its feet carefully or climb over a variety of obstacles.
**[6:33]** And if you think about what it takes to program a dog like this,
**[6:37]** I have no idea, I really don't know how to tell it
**[6:41]** what's the best way to place its legs to get over a given obstacle.
**[6:45]** All of these things were figured out automatically by the robot just by giving
**[6:50]** it rewards that incentivizes it,
**[6:52]** making progress toward the goal on the left of the screen.
**[6:57]** Today, reinforcement learning has been successfully applied to a variety of
**[7:01]** applications ranging from controlling robots.
**[7:04]** And in fact later this week in the practice lab, you implement for yourself
**[7:09]** a reinforcement learning algorithm to land a lunar lander in simulation.
**[7:15]** It's also been used for factory optimization.
**[7:18]** How do you rearrange things in the factory to maximize throughput and
**[7:23]** efficiency as well as financial stock trading.
**[7:26]** For example, one of my friends was working on efficient stock execution.
**[7:31]** So if you decided to sell a million shares over the next several days, well,
**[7:35]** you may not want to dump a million shares on the stock market suddenly because
**[7:39]** that will move prices against you.
**[7:41]** So what's the best way to sequence out your trades over time so that you can sell
**[7:46]** the shares you want to sell and hopefully get the best possible price for them?
**[7:51]** Finally, there have also been many applications of reinforcement
**[7:56]** learning to playing games, everything from checkers to chess to the card
**[8:01]** game of bridge to go as well as for playing many video games.
**[8:05]** So that's reinforcement learning.
**[8:08]** Even though reinforcement learning is not used nearly as much
**[8:12]** as supervised learning, it is still used in a few applications today.
**[8:17]** And the key idea is rather than you needing to tell the algorithm what is
**[8:22]** the right output y for every single input, all you have to do instead is specify
**[8:27]** a reward function that tells it when it's doing well and when it's doing poorly.
**[8:32]** And it's the job of the algorithm to automatically figure out how to choose
**[8:37]** good actions.
**[8:38]** With that, let's now go into the next video where we'll formalize
**[8:42]** the reinforcement learning problem and also start to develop algorithms for
**[8:46]** automatically picking good actions
