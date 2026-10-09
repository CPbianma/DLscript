---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 3
section: Reinforcement learning introduction
item_title: Making decisions: Policies in reinforcement learning
duration: 3 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/BsteY/making-decisions-policies-in-reinforcement-learning
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Making decisions: Policies in reinforcement learning — Transcript

**[0:01]** Let's formalize how
**[0:03]** a reinforcement learning algorithm picks actions.
**[0:05]** In this video, you'll learn about what is
**[0:08]** a policy in reinforcement learning algorithm.
**[0:11]** Let's take a look.
**[0:12]** As we've seen, there are many different ways that you
**[0:15]** can take actions in the reinforcement learning problem.
**[0:19]** For example, we could decide
**[0:21]** to always go for the nearer reward,
**[0:25]** so you go left if this leftmost reward is
**[0:29]** nearer or go right if this rightmost reward is nearer.
**[0:33]** Another way we could choose actions is to always go for
**[0:37]** the larger reward or
**[0:40]** we could always go for smaller reward,
**[0:43]** doesn't seem like a good idea,
**[0:44]** but it is another option,
**[0:46]** or you could choose to go left
**[0:49]** unless you're just one step away from the lesser reward,
**[0:52]** in which case, you go for that one.
**[0:54]** In reinforcement learning, our goal is to come up with
**[0:59]** a function which is called a policy Pi,
**[1:05]** whose job it is to take as input
**[1:08]** any state s and map it
**[1:11]** to some action a that it wants us to take.
**[1:15]** For example, for this policy here at the bottom,
**[1:19]** this policy would say that if you're in state 2,
**[1:23]** then it maps us to the left action.
**[1:27]** If you're in state 3,
**[1:28]** the policy says go left.
**[1:30]** If you are in state 4 also go
**[1:33]** left and if you're in state 5, go right.
**[1:38]** Pi applied to state S,
**[1:40]** tells us what action it wants us to take in that state.
**[1:44]** The goal of reinforcement learning is to find a policy Pi
**[1:51]** or Pi of S that tells you what action to
**[1:53]** take in every state so as to maximize the return.
**[1:57]** By the way, I don't know if policy is
**[2:00]** the most descriptive term of what pi is,
**[2:04]** but it's one of those terms that's
**[2:06]** become standard in reinforcement learning.
**[2:08]** Maybe calling Pi a
**[2:09]** controller rather than a policy would be
**[2:12]** more natural terminology but policy
**[2:15]** is what everyone in
**[2:16]** reinforcement learning now calls this.
**[2:19]** In the last video, we've gone
**[2:20]** through quite a few concepts in
**[2:22]** reinforcement learning from states to actions to reward,
**[2:26]** to returns, to policies.
**[2:28]** Let's do a quick review of them in
**[2:29]** the next video and then we'll go on to
**[2:31]** start developing algorithms for finding that policies.
**[2:35]** Let's go on to the next video.
