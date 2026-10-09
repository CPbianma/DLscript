---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 3
section: Continuous state spaces
item_title: Example of continuous state space applications
duration: 6 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/kVphz/example-of-continuous-state-space-applications
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Example of continuous state space applications — Transcript

**[0:01]** Many robotic control applications,
**[0:04]** including the lunar lander application
**[0:06]** that you work on in the practice lab,
**[0:09]** have continuous state spaces.
**[0:11]** Let's take a look at what that
**[0:12]** means and how to generalize
**[0:14]** the concept we've talked about to
**[0:16]** these continuous state spaces.
**[0:18]** A simplify Mars rover example we use,
**[0:21]** I use a discrete set of states,
**[0:24]** and what that means is that simplify Mars rover could
**[0:28]** only be in one of six possible positions.
**[0:32]** But most robots can be in more than one of
**[0:35]** six or any discrete number of positions,
**[0:39]** instead, they can be in any of
**[0:41]** a very large number of continuous value positions.
**[0:46]** For example, if the Mars rover
**[0:49]** could be anywhere on a line,
**[0:52]** so its position was indicated by a number ranging from
**[0:56]** 0-6 kilometers where any number in between is valid.
**[1:01]** That would be an example of a continuous state space,
**[1:06]** because the position would be
**[1:08]** represented by a number such as that is
**[1:11]** 2.7 kilometers along or
**[1:13]** 4.8 kilometers or any other number between zero and six.
**[1:17]** Let's look at another example.
**[1:19]** I'm going to use for this example,
**[1:22]** the application of controlling a car or a truck.
**[1:25]** Here's a toy car, or actually a toy truck.
**[1:27]** This one belongs to my daughter.
**[1:29]** If you're building a self-driving car or
**[1:31]** self-driving truck and you want
**[1:33]** to control this to drive smoothly,
**[1:35]** then the state of this truck
**[1:37]** might include a few numbers such as this,
**[1:40]** x position, its y position, maybe it's orientation.
**[1:45]** What way is it facing?
**[1:47]** Assuming the truck stays on the ground,
**[1:49]** you probably don't need to worry
**[1:50]** about how tall is, how high up it is.
**[1:53]** This is state will include x,
**[1:56]** y, and is angle Theta,
**[1:59]** as well as maybe its speeds in x-direction,
**[2:02]** the speed in the y-direction,
**[2:04]** and how quickly it's turning.
**[2:06]** Is it turning at one degree
**[2:07]** per second or is it turning at
**[2:08]** 30 degrees per second or is it turning
**[2:10]** really quickly at 90 degrees per second?
**[2:13]** For a truck or a car,
**[2:16]** the state might include not just one number,
**[2:20]** like how many kilometers of this along on this line,
**[2:23]** but they might includes six numbers,
**[2:26]** is x position,
**[2:27]** is y position, is orientation,
**[2:30]** which I'm going to denote using Greek alphabet Theta,
**[2:34]** as well its velocity in the x-direction,
**[2:37]** which I will denote using x dot,
**[2:39]** so that means how quickly is this x-coordinate changing,
**[2:43]** y dot how quickly is the y
**[2:46]** coordinate changing, and then finally,
**[2:48]** Theta dot, which is how quickly is
**[2:51]** the angle of the car changing.
**[2:54]** Whereas for the 60 Mars rover example,
**[2:58]** the state was just one of six possible numbers.
**[3:01]** It could be one, two,
**[3:03]** three, four, five or six.
**[3:05]** For the car, the state would
**[3:07]** comprise this vector of six numbers,
**[3:11]** and any of these numbers can take on
**[3:13]** any value within is valid range.
**[3:17]** For example, Theta should range
**[3:20]** between zero and 360 degrees.
**[3:23]** Let's look at another example.
**[3:25]** What if you're building
**[3:26]** a reinforcement learning algorithm to
**[3:28]** control an autonomous helicopter,
**[3:31]** how would you characterize the position of a helicopter?
**[3:34]** To illustrate, I have with me here
**[3:35]** a small toy helicopter.
**[3:37]** The positioning of the helicopter would
**[3:39]** include is x position,
**[3:41]** such as how far north or south
**[3:44]** is a helicopter, is y position.
**[3:46]** Maybe how far on the east-west axis is the helicopter,
**[3:51]** and then also z, the height of
**[3:52]** the helicopter above ground.
**[3:55]** But other than the position,
**[3:57]** the helicopter also has
**[3:59]** an orientation, and conventionally,
**[4:01]** one way to capture its orientation
**[4:03]** is with three additional numbers,
**[4:05]** one of which captures of the row of the helicopter.
**[4:09]** Is it rolling to the left or the right?
**[4:11]** The pitch, is it pitching
**[4:12]** forward or pitching up, pitching back,
**[4:14]** and then finally the yaw which
**[4:17]** is west the compass orientation is it facing.
**[4:19]** If facing north or east or south or west?
**[4:22]** To summarize, the state of the helicopter
**[4:25]** includes is position in the say, north-south direction,
**[4:30]** is positioned in the east-west direction,
**[4:32]** y is height above ground,
**[4:34]** and also the row,
**[4:36]** the pitch, and also that yaw of helicopter.
**[4:42]** To write this down,
**[4:43]** the state therefore includes the position x, y, z,
**[4:48]** and then the row pitch,
**[4:51]** and yaw denoted with
**[4:54]** the Greek alphabets Phi, Theta and Omega.
**[4:59]** But to control the helicopter,
**[5:00]** we also need to know its speed in the x-direction,
**[5:05]** in the y-direction, and in the z direction,
**[5:08]** as well as its rate of turning,
**[5:11]** also called the angular velocity.
**[5:13]** How fast is this row changing and how fast is
**[5:16]** this pitch changing and how fast is its yaw changing?
**[5:21]** This is actually the state
**[5:23]** used to control autonomous helicopters.
**[5:26]** Is this list of 12 numbers that is input to a policy,
**[5:31]** and the job of a policy is look at
**[5:33]** these 12 numbers and decide
**[5:35]** what's an appropriate action to take in the helicopter.
**[5:38]** So any continuous state reinforcement learning problem or
**[5:42]** a continuous state
**[5:43]** Markov decision process, continuously MTP.
**[5:46]** The state of the problem isn't just one
**[5:50]** of a small number of possible discrete values,
**[5:52]** like a number from 1-6.
**[5:54]** Instead, it's a vector of numbers,
**[5:58]** any of which could take any of a large number of values.
**[6:03]** In the practice lab for this week,
**[6:05]** you get to implement for
**[6:06]** yourself a reinforcement learning algorithm
**[6:09]** applied to a simulated lunar lander application.
**[6:13]** Landing something on the moon is simulation.
**[6:16]** Let's take a look in the next video at
**[6:18]** what that application entails,
**[6:20]** since there will be another continuous state application.
