---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 3
section: Reinforcement learning introduction
item_title: Review of key concepts
duration: 6 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/fvSTb/review-of-key-concepts
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Review of key concepts — Transcript

**[0:00]** We've developed a reinforcement learning formalism
**[0:04]** using the six state Mars rover example.
**[0:08]** Let's do a quick review of the key concepts and also see
**[0:11]** how this set of concepts can be
**[0:13]** used for other applications as well.
**[0:15]** Some of the concepts we've discussed
**[0:18]** are states of a reinforcement learning problem,
**[0:22]** the set of actions, the rewards,
**[0:26]** a discount factor, then how rewards and
**[0:28]** the discount factor altogether
**[0:30]** use to compute the return,
**[0:32]** and then finally, a policy whose job it
**[0:35]** is to help you pick actions so as to maximize the return.
**[0:39]** For the Mars rover example,
**[0:40]** we had six states that we numbered
**[0:43]** 1-6 and the actions were to go left or to go right.
**[0:48]** The rewards were 100 for the leftmost state,
**[0:51]** 40 for the rightmost state,
**[0:53]** and zero in between
**[0:55]** and I was using a discount factor of 0.5.
**[0:59]** The return was given by this formula and we could have
**[1:03]** different policies Pi depict
**[1:05]** actions depending on what state you're in.
**[1:07]** This same formalism or states, actions,
**[1:10]** rewards, and so on can be used
**[1:12]** for many other applications as well.
**[1:14]** Take the problem or find an autonomous helicopter.
**[1:17]** To set a state would be the set of
**[1:21]** possible positions and orientations and
**[1:23]** speeds and so on of the helicopter.
**[1:26]** The possible actions would be the set of
**[1:29]** possible ways to move
**[1:30]** the controls stick of a helicopter,
**[1:32]** and the rewards may be a plus one if it's flying well,
**[1:36]** and a negative 1,000
**[1:38]** if it doesn't fall really bad or crashes.
**[1:41]** Reward function that tells you
**[1:42]** how well the helicopter is flying.
**[1:45]** The discount factor, a number
**[1:47]** slightly less than one maybe say,
**[1:49]** 0.99 and then based
**[1:51]** on the rewards and the discount factor,
**[1:53]** you compute the return using the same formula.
**[1:57]** The job of a reinforcement learning
**[1:59]** algorithm would be to find
**[2:01]** some policy Pi of s so that given as input,
**[2:05]** the position of the helicopter s,
**[2:07]** it tells you what action to take.
**[2:09]** That is, tells you how to move the control sticks.
**[2:12]** Here's one more example.
**[2:13]** Here's a game-playing one.
**[2:15]** Say you want to use
**[2:16]** reinforcement learning to learn to play chess.
**[2:18]** The state of this problem would
**[2:21]** be the position of all the pieces on the board.
**[2:24]** By the way, if you play chess and know the rules well,
**[2:27]** I know that's little bit more information
**[2:30]** than just the position of
**[2:31]** the pieces is important for chess,
**[2:33]** but I'll simplify it a little bit for this video.
**[2:36]** The actions are the possible legal moves in the game,
**[2:40]** and then a common choice of reward would be if you
**[2:44]** give your system a reward of plus one if it wins a game,
**[2:47]** minus one if it loses the game,
**[2:50]** and a reward of zero if it ties a game.
**[2:53]** For chess, usually a discount factor
**[2:56]** very close to one will be used,
**[2:58]** so maybe 0.99 or even 0.995 or
**[3:02]** 0.999 and the return
**[3:05]** uses the same formula as the other applications.
**[3:08]** Once again, the goal is given
**[3:12]** a board position to pick a good action using a policy Pi.
**[3:17]** This formalism of a reinforcement learning application
**[3:21]** actually has a name.
**[3:23]** It's called a Markov decision process,
**[3:26]** and I know that sounds like
**[3:27]** a big technical complicated term.
**[3:29]** But if you ever hear this term Markov decision process
**[3:33]** or MDP for short,
**[3:36]** that's just the formalism that we've been
**[3:38]** talking about in the last few videos.
**[3:40]** The term Markov in the MDP or
**[3:43]** Markov decision process refers to that the future
**[3:47]** only depends on the current state and not on anything
**[3:50]** that might have occurred prior
**[3:52]** to getting to the current state.
**[3:54]** In other words, in a Markov decision process,
**[3:57]** the future depends only on where you are now,
**[4:00]** not on how you got here.
**[4:02]** One other way to think of
**[4:03]** the Markov decision process formalism is
**[4:07]** that we have a robot or
**[4:10]** some other agent that
**[4:13]** we wish to control and what we get to do
**[4:16]** is choose actions a and based on those actions,
**[4:23]** something will happen in the world or in the environment,
**[4:28]** such as our position in the world changes or we
**[4:31]** get to sample a piece of
**[4:32]** rock and execute the science mission.
**[4:34]** The way we choose the action a is with
**[4:36]** a policy Pi and based on what happens in the world,
**[4:41]** we then get to see or we
**[4:43]** observe back what state we're in,
**[4:46]** as well as what rewards are that we get.
**[4:51]** You sometimes see different authors use a diagram like
**[4:54]** this to represent the Markov decision process or
**[4:58]** the MDP formalism but this is just another way of
**[5:02]** illustrating the set of concepts
**[5:04]** that you learn about in the last few videos.
**[5:06]** You now know how a reinforcement learning problem works.
**[5:11]** In the next video we'll start to develop
**[5:13]** an algorithm for picking good actions.
**[5:16]** The first step toward that will be to define and then
**[5:19]** eventually learn to compute
**[5:20]** the state action value function.
**[5:23]** This turns out to be one of the key quantities
**[5:25]** for when we want to develop a learning algorithm.
**[5:29]** Let's go onto the next video to see what is this,
**[5:32]** state action value function.
