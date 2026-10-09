---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 3
section: Reinforcement learning introduction
item_title: Mars rover example
duration: 7 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/UrcMA/mars-rover-example
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Mars rover example — Transcript

**[0:01]** To finish out the reinforcement learning formalism,
**[0:05]** instead of looking at something as
**[0:07]** complicated as a helicopter or a robot dog,
**[0:10]** we can use a simplified example
**[0:13]** that's loosely inspired by the Mars rover.
**[0:17]** This is adapted from
**[0:18]** the example due to Stanford professor
**[0:20]** Emma Branskill and one of
**[0:21]** my collaborators, Jagriti Agrawal,
**[0:24]** who had actually written code that
**[0:26]** is actually controlling the Mars rover
**[0:28]** right now that also helped me
**[0:30]** talk through and helped develop this example.
**[0:32]** Let's take a look. We'll develop reinforcement learning
**[0:37]** using a simplified example inspired by the Mars rover.
**[0:43]** In this application, the rover can
**[0:45]** be in any of six positions,
**[0:48]** as shown by the six boxes here.
**[0:51]** The rover, it might start off, say,
**[0:53]** in disposition into fourth box shown here.
**[0:58]** The position of the Mars rover is
**[1:00]** called the state in reinforcement learning,
**[1:03]** and I'm going to call these six states,
**[1:06]** state 1, state 2,
**[1:08]** state 3, state 4,
**[1:10]** state 5, and state 6,
**[1:12]** and so the rover is starting off in state 4.
**[1:15]** Now the rover was sent to Mars to
**[1:18]** try to carry out different science missions.
**[1:21]** It can go to different places to
**[1:24]** use its sensors such as a drill, or a radar,
**[1:27]** or a spectrometer to
**[1:29]** analyze the rock at different places on the planet,
**[1:32]** or go to different places to take
**[1:34]** interesting pictures for scientists on earth to look at.
**[1:36]** In this example, state 1 here on the left has
**[1:40]** a very interesting surface that
**[1:42]** scientists would love for the rover to sample.
**[1:45]** State 6 also has
**[1:47]** a pretty interesting surface that
**[1:49]** scientists would quite like the rover to sample,
**[1:51]** but not as interesting as state 1.
**[1:54]** We would more likely to carry out
**[1:57]** the science mission at state 1 than at state 6,
**[2:01]** but state 1 is further away.
**[2:03]** The way we will reflect state 1 being
**[2:07]** potentially more valuable is through the reward function.
**[2:11]** The reward at state 1 is a 100,
**[2:15]** and the reward at stage 6 is 40,
**[2:19]** and the rewards at all of the other states in-between,
**[2:22]** I'm going to write as a reward of zero because there's
**[2:26]** not as much interesting science to
**[2:28]** be done at these states 2,
**[2:30]** 3, 4, and 5.
**[2:31]** On each step, the rover gets
**[2:34]** to choose one of two actions.
**[2:36]** It can either go to the left or it can go to the right.
**[2:42]** The question is, what should the rover do?
**[2:46]** In reinforcement learning, we pay
**[2:47]** a lot of attention to the rewards
**[2:49]** because that's how we know if
**[2:51]** the robot is doing well or poorly.
**[2:54]** Let's look at some examples of what might
**[2:57]** happen if the robot was to go left,
**[2:59]** starting from state 4.
**[3:01]** Then initially starting from state 4,
**[3:05]** it will receive a reward of zero,
**[3:07]** and after going left,
**[3:09]** it gets to state 3,
**[3:10]** where it receives again a reward of zero.
**[3:13]** Then it gets to state 2,
**[3:15]** receives the reward is 0,
**[3:16]** and finally just to state 1,
**[3:18]** where it receives a reward of 100.
**[3:21]** For this application, I'm going to assume that
**[3:24]** when it gets either state 1 or state 6,
**[3:27]** that the day ends.
**[3:29]** In reinforcement learning, we sometimes call this
**[3:32]** a terminal state,
**[3:35]** and what that means is that,
**[3:37]** after it gets to one of these terminals states,
**[3:39]** gets a reward at that state,
**[3:41]** but then nothing happens after that.
**[3:43]** Maybe the robots run out of
**[3:45]** fuel or ran out of time for the day,
**[3:47]** which is why it only gets to either enjoy
**[3:50]** the 100 or the 40 reward,
**[3:54]** but then that's it for the day.
**[3:56]** It doesn't get to earn additional rewards after that.
**[3:59]** Now instead of going left,
**[4:01]** the robot could also choose to go to the right,
**[4:04]** in which case from state 4,
**[4:06]** it would first have a reward of zero,
**[4:10]** and then it'll move right and get to state 5,
**[4:13]** have another reward of zero,
**[4:15]** and then it will get to this
**[4:17]** other terminal state on the right,
**[4:18]** state 6 and get a reward of 40.
**[4:21]** But going left and going right are the only options.
**[4:26]** One thing the robot could do is it can start from
**[4:29]** state 4 and decide to move to the right.
**[4:32]** It goes from state 4-5,
**[4:35]** gets a reward of zero in state
**[4:37]** 4 and a reward of zero in state 5,
**[4:38]** and then maybe it changes its mind and decides to start
**[4:41]** going to the left as follows, in which case,
**[4:45]** it will get a reward of zero at state 4, at state 3,
**[4:48]** at state 2, and then the reward
**[4:50]** of 100 when it gets to state 1.
**[4:53]** In this sequence of actions and states,
**[4:56]** the robot is wasting a bit of time.
**[4:58]** So this maybe isn't such a great way to take actions,
**[5:02]** but it is one choice that the algorithm could pick,
**[5:04]** but hopefully you won't pick this one.
**[5:07]** To summarize, at every time step,
**[5:10]** the robot is in some state,
**[5:13]** which I'll call S,
**[5:15]** and it gets to choose an action,
**[5:19]** and it also enjoys some rewards,
**[5:23]** R of S that it gets from that state.
**[5:26]** As a result of this action,
**[5:28]** it to some new state S prime.
**[5:32]** As a concrete example,
**[5:33]** when the robot was in state 4 and it took the action,
**[5:37]** go left, maybe didn't enjoy the reward of
**[5:43]** zero associated with that state
**[5:45]** 4 and it won't have any new state 3.
**[5:49]** When you learn about
**[5:50]** specific reinforcement learning algorithms,
**[5:52]** you see that these four things,
**[5:55]** the state, action, the reward and next state,
**[5:58]** which is what happens basically every
**[5:59]** time you take an action that just
**[6:01]** be a core elements of
**[6:03]** what reinforcement learning algorithms will
**[6:04]** look at when deciding how to take actions.
**[6:08]** Just for clarity, the reward here,
**[6:12]** R of S, this is the reward associated with this state.
**[6:16]** This reward of zero is associated
**[6:18]** with state 4 rather than with state 3.
**[6:21]** That's the formalism of how
**[6:24]** a reinforcement learning application works.
**[6:26]** In the next video,
**[6:28]** let's take a look at how we specify
**[6:30]** exactly what we want
**[6:31]** the reinforcement learning algorithm to do.
**[6:33]** In particular, we'll talk about an important idea in
**[6:36]** reinforcement learning called the return.
**[6:38]** Let's go on to the next video to see what that means.
