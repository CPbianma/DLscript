---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 3
section: Continuous state spaces
item_title: "Algorithm refinement: Improved neural network architecture"
duration: 3 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/hpmUe/algorithm-refinement-improved-neural-network-architecture
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Algorithm refinement: Improved neural network architecture — Transcript

**[0:00]** In the last video, we saw
**[0:03]** a neural network architecture that will input
**[0:06]** the state and action and attempt
**[0:09]** to output the Q function, Q of s, a.
**[0:12]** It turns out that there's a change to
**[0:14]** neural network architecture that
**[0:16]** make this algorithm much more efficient.
**[0:18]** Most implementations of DQN actually use
**[0:21]** this more efficient architecture
**[0:23]** that we'll see in this video. Let's take a look.
**[0:26]** This was the neural network architecture
**[0:28]** we saw previously,
**[0:30]** where it would input 12 numbers and output Q of s, a.
**[0:35]** Whenever we are in some state s,
**[0:38]** we would have to carry out inference in
**[0:41]** the neural network separately four times to
**[0:44]** compute these four values so as to pick
**[0:47]** the action a that gives us the largest Q value.
**[0:51]** This is inefficient because we have to carry
**[0:54]** our inference four times from every single state.
**[0:58]** Instead, it turns out to be more efficient
**[1:01]** to train a single neural network to
**[1:03]** output all four of these values simultaneously.
**[1:08]** This is what it looks like.
**[1:10]** Here's a modified neural network
**[1:12]** architecture where the input
**[1:14]** is eight numbers corresponding
**[1:18]** to the state of the lunar lander.
**[1:21]** It then goes through the neural network
**[1:22]** with 64 units in the first hidden layer,
**[1:25]** 64 units in the second hidden layer.
**[1:27]** Now the output unit has four output units,
**[1:32]** and the job of the neural network is to have
**[1:35]** the four output units output Q of s,
**[1:38]** nothing, Q of s, left,
**[1:40]** Q of s, main,
**[1:42]** and q of s, right.
**[1:43]** The job of the neural network is to compute
**[1:46]** simultaneously the Q value for all four possible actions
**[1:51]** for when we are in the state
**[1:54]** s. This turns out to be more efficient
**[1:57]** because given the state s we can run inference
**[2:00]** just once and get all four of these values,
**[2:04]** and then very quickly pick the action
**[2:06]** a that maximizes Q of s, a.
**[2:09]** You notice also in Bellman's equations,
**[2:12]** there's a step in which we have to compute max over
**[2:15]** a prime Q of s prime a prime,
**[2:19]** this multiplied by gamma and then there was
**[2:21]** plus R of s up here.
**[2:23]** This neural network also makes it
**[2:25]** much more efficient to compute this
**[2:28]** because we're getting Q of s prime a
**[2:30]** prime for all actions a prime at the same time.
**[2:33]** You can then just pick the max to compute
**[2:35]** this value for
**[2:37]** the right-hand side of Bellman's equations.
**[2:39]** This change to the neural network architecture
**[2:41]** makes the algorithm much more efficient,
**[2:43]** and so we will be using
**[2:44]** this architecture in the practice lab.
**[2:48]** Next, there's one other
**[2:49]** idea that'll help the algorithm a
**[2:51]** lot which is something called an Epsilon-greedy policy,
**[2:54]** which affects how you choose
**[2:55]** actions even while you're still learning.
**[2:58]** Let's take a look at the next video
**[2:59]** , and what that means.
