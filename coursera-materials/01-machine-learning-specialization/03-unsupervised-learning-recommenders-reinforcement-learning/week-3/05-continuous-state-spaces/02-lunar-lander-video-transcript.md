---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 3
section: Continuous state spaces
item_title: Lunar lander
duration: 6 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/C9BJf/lunar-lander
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Lunar lander — Transcript

**[0:02]** The lunar lander lets you land a simulated vehicle on the moon.
**[0:06]** It's like a fun little video game that's been used by a lot of reinforcement
**[0:11]** learning researchers.
**[0:12]** Let's take a look at what it is.
**[0:14]** In this application you're in command
**[0:16]** of a lunar lander that is rapidly approaching the surface of the moon.
**[0:21]** And your job is the fire thrusters at the appropriate times to land it
**[0:26]** safely on the landing pad.
**[0:28]** To give you a sense of what it looks like.
**[0:30]** This is the lunar lander landing successfully and
**[0:33]** it's firing thrusters downward and to the left and
**[0:36]** right to position itself to land between these two yellow flags.
**[0:41]** Or if the reinforcement landing algorithm policy does not do well then this is what
**[0:46]** it might look like where the lander unfortunately has crashed
**[0:49]** on the surface of the moon.
**[0:51]** In this application you have four possible actions on every time step.
**[0:58]** You could either do nothing, in which case the forces of inertia and
**[1:02]** gravity pull you towards the surface of the moon.
**[1:05]** Or you can fire a left thruster when you see a little red dot come out on the left,
**[1:10]** that's firing the left.
**[1:12]** They'll tend to push the lunar lander to the right or
**[1:16]** you can fire the main engine that's thrusting down the bottom here.
**[1:22]** Or you can fire the right thruster and
**[1:25]** that's firing the right thruster which will push you to the left and
**[1:30]** your job is to keep on picking actions over time.
**[1:34]** So it's the lunar lander safely between these two flags here on the landing pad.
**[1:40]** In order to give the actions a shorter name I'm sometimes going to call
**[1:44]** the actions nothing meaning do nothing or left meaning fire left thruster or
**[1:50]** main meaning fire the main engine downward or right.
**[1:53]** So I'm going to call the actions nothing left.
**[1:56]** main and right for short later in this video.
**[1:59]** How about the states space of this?
**[2:01]** Mtp the states are its position X and Y.
**[2:06]** So how far to the left or right and how high up is it as well as
**[2:10]** velocity x.y how fast is it moving in the horizontal and
**[2:15]** vertical directions and then also is angle.
**[2:18]** So how far is the lunar lander tilted to the left or tilted to the right?
**[2:23]** Is angular velocity theta dot.
**[2:25]** And then finally, because a small difference in positioning makes a big
**[2:30]** difference in whether or not it's landed.
**[2:32]** We're going to have two other variables in the state vector which we call l and r.
**[2:39]** Which corresponds to whether the left leg is grounded, meaning whether or not
**[2:43]** the left leg is sitting on the ground as well as r which corresponds to whether or
**[2:48]** not the right leg is sitting on the ground.
**[2:51]** So whereas xy x.theta theta.our numbers l and
**[2:55]** r will be binary valued and can take on only values zero or
**[2:59]** one depending on whether the left and right legs are touching the ground.
**[3:06]** Finally his reward function for the lunar lander.
**[3:08]** If it manages to get to the landing pad, didn't receive the reward between 100 and
**[3:14]** 140 depending on how well it's flown when gotten to the center of the landing pad.
**[3:19]** We also give it an additional reward for moving toward or away from the pad so
**[3:24]** it moves closer to the pad it receives a positive reward and it moves away and
**[3:29]** drifts away.
**[3:30]** It receives a negative reward.
**[3:32]** If it crashes it gets a large -100 reward,
**[3:36]** it achieves a soft landing, that is a landing.
**[3:40]** There's another crash, it gets a +100 reward for each leg,
**[3:44]** the left leg or the right link that it gets grounded.
**[3:47]** It receives a +10 reward and finally to encourage it not to waste too
**[3:52]** much fuel and fire thrusters aren't necessarily.
**[3:56]** Every time it fires the main engine we give it a -0.3 rewards and
**[4:01]** every time it fires the left or the right side thrusters we give it a -0.03 reward.
**[4:08]** Notice that this is a moderately complex reward function.
**[4:12]** The designers of the lunar lander application actually put some thought into
**[4:17]** exactly what behavior you want and codified it in the reward function.
**[4:22]** To incentivize more of the behaviors you want and
**[4:25]** fewer of the behaviors like crashing that you don't want.
**[4:29]** You find when you're building your own reinforcement learning application
**[4:34]** usually takes some thought to specify exactly what you want or don't want and
**[4:38]** to codify that in the reward function.
**[4:41]** But specify the reward function should still turn out to be much easier to
**[4:46]** specify the exact right action to take from every single state.
**[4:50]** Which is much harder for this and many other reinforcement learning applications.
**[4:54]** So the lunar lander problem is as follows.
**[4:58]** Our goal is to learn a policy pi.
**[5:02]** That when given a state S as written
**[5:06]** here picks an action a equals pi of S.
**[5:12]** So as to maximize the return the sum of discounted rewards.
**[5:17]** And usually for the lunar lander would use a fairly large value for gamma ra.
**[5:22]** In fact for the would use the value of gamma that's equal to 0.985 so
**[5:27]** pretty close to one.
**[5:29]** And if you can learn a policy pi that does this then you successfully land
**[5:34]** this lunar lander exciting application and we're now finally ready to
**[5:39]** develop a learning algorithm which will turn out to use deep learning or
**[5:44]** neural networks to come up with a policy to land the lunar lander.
**[5:49]** Let's go into the next video where we start to learn about deep reinforcement.
