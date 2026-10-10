---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 3
section: Continuous state spaces
item_title: "Algorithm refinement: ϵ-greedy policy"
duration: 9 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/GyBzo/algorithm-refinement-greedy-policy
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Algorithm refinement: ϵ-greedy policy — Transcript

**[0:01]** The learning algorithm that we developed,
**[0:05]** even while you're still learning how
**[0:07]** to approximate Q(s,a),
**[0:09]** you need to take some actions in the lunar lander.
**[0:13]** How do you pick those actions
**[0:15]** while you're still learning?
**[0:16]** The most common way to do so is to use
**[0:19]** something called an Epsilon-greedy policy.
**[0:21]** Let's take a look at how that works.
**[0:24]** Here's the algorithm that you saw earlier.
**[0:27]** One of the steps in the algorithm is
**[0:29]** to take actions in the lunar lander.
**[0:33]** When the learning algorithm is still running,
**[0:36]** we don't really know what's
**[0:37]** the best action to take in every state.
**[0:39]** If we did, we'd already be done learning.
**[0:42]** But even while we're still learning and don't have
**[0:44]** a very good estimate of Q(s,a) yet,
**[0:48]** how do we take actions
**[0:49]** in this step of the learning algorithm?
**[0:52]** Let's look at some options.
**[0:54]** When you're in some state s,
**[0:56]** we might not want to take actions totally at random
**[0:59]** because that will often be a bad action.
**[1:03]** One natural option would be to pick whenever in state s,
**[1:09]** pick an action a that maximizes Q(s,a).
**[1:13]** We may say, even if Q(s,a) is not
**[1:16]** a great estimate of the Q function,
**[1:19]** let's just do our best and use our current guess
**[1:22]** of Q(s,a) and pick the action a that maximizes it.
**[1:26]** It turns out this may work okay,
**[1:29]** but isn't the best option.
**[1:32]** Instead, here's what is commonly done.
**[1:36]** Here's option 2,
**[1:37]** which is most of the time,
**[1:39]** let's say with probability of 0.95,
**[1:42]** pick the action that maximizes Q(s,a).
**[1:47]** Most of the time we try to pick
**[1:49]** a good action using our current guess of Q(s,a).
**[1:52]** But the small fraction of the time, let's say,
**[1:55]** five percent of the time,
**[1:56]** we'll pick an action a randomly.
**[1:59]** Why do we want to occasionally pick an action randomly?
**[2:02]** Well, here's why. Suppose there's
**[2:05]** some strange reason that Q(s,a) was initialized
**[2:08]** randomly so that the learning algorithm thinks
**[2:11]** that firing the main thruster is never a good idea.
**[2:15]** Maybe the neural network parameters
**[2:18]** were initialized so that Q(s,
**[2:20]** main) is always very low.
**[2:25]** If that's the case,
**[2:26]** then the neural network,
**[2:28]** because it's trying to pick the action
**[2:29]** a that maximizes Q(s,a),
**[2:31]** it will never ever try firing the main thruster.
**[2:35]** Because it never ever tries firing the main thruster,
**[2:39]** it will never learn that firing
**[2:41]** the main thruster is actually sometimes a good idea.
**[2:44]** Because of the random initialization,
**[2:47]** if the neural network somehow initially gets stuck in
**[2:50]** this mind that some things are
**[2:52]** bad idea, just by chance,
**[2:54]** then option 1,
**[2:56]** it means that it will never try out those actions and
**[2:59]** discover that maybe is
**[3:01]** actually a good idea to take that action,
**[3:04]** like fire the main thrusters sometimes.
**[3:06]** Under option 2 on every step,
**[3:08]** we have some small probability of trying out
**[3:11]** different actions so that the neural network can
**[3:15]** learn to overcome its own possible preconceptions
**[3:20]** about what might be
**[3:21]** a bad idea that turns out not to be the case.
**[3:24]** This idea of picking actions randomly is
**[3:27]** sometimes called an exploration step.
**[3:31]** Because we're going to try
**[3:33]** out something that may not be the best idea,
**[3:35]** but we're going to just try out
**[3:37]** some action in some circumstances,
**[3:39]** explore and learn more about an action in
**[3:41]** the circumstance where we may not have
**[3:43]** had as much experience before.
**[3:45]** Taking an action that maximizes Q(s,a),
**[3:49]** sometimes this is called a greedy action because we're
**[3:54]** trying to actually maximize our return by picking this.
**[4:00]** Or in the reinforcement learning literature,
**[4:02]** sometimes you'll also hear this as an exploitation step.
**[4:07]** I know that exploitation is not a good thing,
**[4:10]** nobody should ever explore anyone else.
**[4:13]** But historically, this was the term used
**[4:15]** in reinforcement learning to say,
**[4:17]** let's exploit everything we've
**[4:18]** learned to do the best we can.
**[4:20]** In the reinforcement learning literature,
**[4:22]** sometimes you hear people talk about
**[4:25]** the exploration versus exploitation trade-off,
**[4:28]** which refers to how often do
**[4:30]** you take actions randomly or take
**[4:32]** actions that may not be the best in order to learn more,
**[4:36]** versus trying to maximize your return by say,
**[4:40]** taking the action that maximizes Q (s,a).
**[4:43]** This approach, that is option 2, has a name,
**[4:46]** is called an Epsilon-greedy policy,
**[4:51]** where here Epsilon is
**[4:53]** 0.05 is the probability of picking an action randomly.
**[4:58]** This is the most common way to make
**[5:02]** your reinforcement learning algorithm
**[5:05]** explore a little bit,
**[5:07]** even whilst occasionally or maybe
**[5:09]** most of the time taking greedy actions.
**[5:11]** By the way, lot of people have commented that
**[5:14]** the name Epsilon-greedy policy is confusing because
**[5:18]** you're actually being greedy 95 percent of the time,
**[5:21]** not five percent of the time.
**[5:22]** So maybe 1 minus Epsilon-greedy policy,
**[5:26]** because it's 95 percent greedy,
**[5:28]** five percent exploring, that's
**[5:30]** actually a more accurate description of the algorithm.
**[5:32]** But for historical reasons,
**[5:35]** the name Epsilon-greedy policy is what has stuck.
**[5:38]** This is the name that people use to refer to
**[5:41]** the policy that explores
**[5:43]** actually Epsilon fraction of the time rather
**[5:46]** than this greedy Epsilon fraction of the time.
**[5:49]** Lastly, one of the trick that's sometimes used in
**[5:52]** reinforcement learning is to start off Epsilon high.
**[5:56]** Initially, you are taking
**[5:59]** random actions a lot at
**[6:01]** a time and then gradually decrease it,
**[6:04]** so that over time you are
**[6:07]** less likely to take actions randomly and
**[6:10]** more likely to use
**[6:11]** your improving estimates of
**[6:14]** the Q-function to pick good actions.
**[6:16]** For example, in the lunar lander exercise,
**[6:20]** you might start off with Epsilon very, very high,
**[6:23]** maybe even Epsilon equals 1.0.
**[6:26]** You're just picking actions completely at
**[6:27]** random initially and then
**[6:29]** gradually decrease it all the way down to say 0.01,
**[6:34]** so that eventually you're
**[6:36]** taking greedy actions 99 percent of
**[6:38]** the time and acting
**[6:40]** randomly only a very small one percent of the time.
**[6:43]** If this seems complicated, don't worry about it.
**[6:46]** We'll provide the code
**[6:47]** in the Jupiter lab that shows you how to do this.
**[6:52]** If you were to implement
**[6:54]** the algorithm as we've described it with
**[6:56]** the more efficient neural network architecture and with
**[6:59]** an Epsilon-greedy exploration policy,
**[7:02]** you find that they work pretty well on the lunar lander.
**[7:06]** One of the things that I've noticed for
**[7:08]** reinforcement learning algorithm is
**[7:10]** that compared to supervised learning,
**[7:12]** they're more finicky in terms
**[7:14]** of the choice of hyper parameters.
**[7:16]** For example, in supervised learning,
**[7:19]** if you set the learning rate a little bit too small,
**[7:22]** then maybe the algorithm will take longer to learn.
**[7:25]** Maybe it takes three times as long to train,
**[7:27]** which is annoying, but maybe not that bad.
**[7:30]** Whereas in reinforcement learning,
**[7:32]** find that if you set
**[7:34]** the value of Epsilon not quite as well,
**[7:37]** or set other parameters not quite as well,
**[7:39]** it doesn't take three times as long to learn.
**[7:42]** It may take 10 times or a 100 times as long to learn.
**[7:46]** Reinforcement learning algorithms,
**[7:48]** I think because they're are
**[7:49]** less mature than supervised learning algorithms,
**[7:52]** are much more finicky to
**[7:53]** little choices of parameters like that,
**[7:55]** and it actually sometimes is frankly more frustrating to
**[8:01]** tune these parameters with
**[8:02]** reinforcement learning algorithm compared
**[8:04]** to a supervised learning algorithm.
**[8:06]** But again, if you're worried about
**[8:08]** the practice lab, the program exercise,
**[8:11]** we'll give you a sense of
**[8:12]** good parameters to use in the program exercise
**[8:15]** so that you should be able to do that
**[8:17]** and successfully learn the lunar lander,
**[8:19]** hopefully without too many problems.
**[8:22]** In the next optional video,
**[8:24]** I want us to drive a couple more algorithm refinements,
**[8:27]** mini batching, and also using soft updates.
**[8:32]** Even without these additional refinements,
**[8:34]** the algorithm will work okay,
**[8:36]** but these are additional refinements that make
**[8:38]** the algorithm run much faster.
**[8:40]** It's okay if you skip this video,
**[8:43]** we've provided everything you need in
**[8:45]** the practice lab to hopefully successfully complete it.
**[8:48]** But if you're interested in learning about more of
**[8:50]** these details of two
**[8:51]** named reinforcement learning algorithms,
**[8:53]** then come with me and let's see in the next video,
**[8:56]** mini batching and soft updates.
