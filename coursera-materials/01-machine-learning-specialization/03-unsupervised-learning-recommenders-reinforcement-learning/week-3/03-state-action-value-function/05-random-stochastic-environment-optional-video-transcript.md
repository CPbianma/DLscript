---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 3
section: State-action value function
item_title: Random (stochastic) environment (Optional)
duration: 8 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/rL525/random-stochastic-environment-optional
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Random (stochastic) environment (Optional) — Transcript

**[0:01]** In some applications, when you take an action,
**[0:05]** the outcome is not always completely reliable.
**[0:08]** For example, if you command your Mars rover to
**[0:11]** go left maybe there's a little bit of a rock slide,
**[0:14]** or maybe the floor is really slippery and so
**[0:16]** it slips and goes in the wrong direction.
**[0:18]** In practice, many robots don't
**[0:21]** always manage to do exactly what you
**[0:23]** tell them because of wind blowing
**[0:25]** and off course and the wheel slipping or something else.
**[0:28]** There's a generalization of
**[0:30]** the reinforcement learning framework
**[0:32]** we've talked about so far,
**[0:33]** which models random or stochastic environments.
**[0:37]** In this optional video,
**[0:39]** we'll talk about how
**[0:40]** these reinforcement learning problems work,
**[0:42]** continuing with our simplifying Mars Rover example,
**[0:46]** let's say you take the action and command it to go left.
**[0:50]** Most of the time you'll succeed but what if
**[0:53]** 10 percent of the time or 0.1 of the time,
**[0:56]** it actually ends up accidentally
**[0:59]** slipping and going in the opposite direction?
**[1:02]** If you command it to go left,
**[1:04]** it has a 90 percent chance or 0.9
**[1:07]** chance of correctly going in the left direction.
**[1:10]** But the 0.1 chance of actually
**[1:12]** heading to the right so that it has
**[1:16]** a 90 percent chance of ending up in state three in
**[1:18]** this example and a 10 percent chance
**[1:20]** of ending up in state five.
**[1:22]** Conversely, if you were to command it to
**[1:24]** go right and take the action, right,
**[1:27]** it has a 0.9 chance of ending up in state
**[1:31]** five and 0.1 chance of ending up in state three.
**[1:35]** This would be an example of a stochastic environment.
**[1:40]** Let's see what happens in
**[1:42]** this reinforcement learning problem.
**[1:44]** Let's say you use this policy shown here,
**[1:48]** where you go left in states
**[1:51]** 2 3 4 and go rights or try to go right in state five.
**[1:56]** If you were to start in state four
**[1:58]** and you were to follow this policy,
**[2:01]** then the actual sequence of
**[2:04]** states you visit may be random.
**[2:06]** For example, in state four,
**[2:08]** you will go left,
**[2:10]** and maybe you're a little bit lucky,
**[2:13]** and it actually gets the state three,
**[2:15]** and then you try to go left again,
**[2:17]** and maybe it actually gets there.
**[2:19]** You tell it to go left again,
**[2:21]** and it gets to that state.
**[2:23]** If this is what happens,
**[2:24]** you end up with the sequence of rewards 000100.
**[2:30]** But if you were to try this exact same policy
**[2:33]** a second time,
**[2:34]** maybe you're a little less lucky,
**[2:37]** the second time you start here.
**[2:39]** Try to go left and say it succeeds
**[2:41]** so a zero from state four zero from state three,
**[2:44]** here you tell it to go left,
**[2:45]** but you've got unlucky this time and the robot
**[2:48]** slips and ends up heading back to state four instead.
**[2:51]** Then you tell it to go left, and left,
**[2:54]** and left, and eventually get to that reward of 100.
**[2:58]** In that case, this will
**[2:59]** be the sequence of rewards you observe.
**[3:02]** This one from four to three to four three two then one,
**[3:06]** or is even possible,
**[3:08]** if you tell from state four to go
**[3:10]** left following the policy you may get
**[3:12]** unlucky even on the first step and you end
**[3:14]** up going to state five because it slipped.
**[3:17]** Then state five, you command it to go right,
**[3:20]** and it succeeds as you end up here.
**[3:21]** In this case, the sequence of
**[3:24]** rewards you see will be 0040,
**[3:26]** because it went from four to five,
**[3:28]** and then states six,
**[3:30]** we had previously written out the return
**[3:33]** as this sum of discounted rewards.
**[3:37]** But when
**[3:39]** the reinforcement learning problem is stochastic,
**[3:42]** there isn't one sequence of rewards that you see for
**[3:45]** sure instead you see this sequence of different rewards.
**[3:49]** In a stochastic reinforcement learning problem,
**[3:53]** what we're interested in is not
**[3:55]** maximizing the return because that's a random number.
**[3:59]** What we're interested in is maximizing
**[4:02]** the average value of the sum of discounted rewards.
**[4:06]** By average value, I mean if you were to take your policy
**[4:10]** and try it out a thousand
**[4:12]** times or a 100,000 times or a million times,
**[4:15]** you get lots of different reward sequences like
**[4:17]** that and if you were to take the average
**[4:19]** over all of these different sequences
**[4:21]** of the sum of discounted rewards,
**[4:24]** then that's what we call the expected return.
**[4:28]** In statistics, the term expected
**[4:31]** is just another way of saying average.
**[4:34]** But what this means is we want to maximize what we expect
**[4:39]** to get on average in
**[4:42]** terms of the sum of discounted rewards.
**[4:44]** The mathematical notation for this is to
**[4:47]** write this as E. E stands
**[4:50]** for expected value of R1 plus Gamma R2 plus, and so on.
**[4:57]** The job of reinforcement learning algorithm is to choose
**[5:00]** a policy Pi to maximize
**[5:03]** the average or the expected sum of discounted rewards.
**[5:07]** To summarize, when you have
**[5:09]** a stochastic reinforcement learning problem or
**[5:12]** a stochastic Markov decision process
**[5:14]** the goal is to choose a policy
**[5:16]** to tell us what action to take in
**[5:18]** state S so as to maximize the expected return.
**[5:22]** The last way that this changes,
**[5:24]** what we've talked about is it
**[5:25]** modifies Bellman equation a little bit.
**[5:29]** Here's the Bellman equation
**[5:31]** exactly as we've written down.
**[5:32]** But the difference now is that
**[5:34]** when you take the action a in state s,
**[5:37]** the next state s prime you get to is random.
**[5:40]** When you're in state 3 and you tell it to go
**[5:42]** left the next state s prime it could be the state 2,
**[5:46]** or it could be the state 4.
**[5:49]** S prime is now random,
**[5:51]** which is why we also put
**[5:53]** an average operator or unexpected operator here.
**[5:57]** We say that the total return from state s,
**[6:01]** taking action a, once in a behaving optimally,
**[6:04]** is equal to the reward you get right away,
**[6:07]** also called the immediate reward
**[6:09]** plus the discount factor,
**[6:11]** Gamma plus what you expect to get on
**[6:14]** average of the future returns.
**[6:18]** If you want to sharpen your intuition about what
**[6:22]** happens with these
**[6:23]** stochastic reinforcement learning problems.
**[6:26]** You'd go back to the optional lab
**[6:28]** that I had shown you just now,
**[6:30]** where this parameter misstep problem is
**[6:33]** the probability of your Mars Rover
**[6:37]** going in the opposite direction,
**[6:39]** than you had commanded it to.
**[6:41]** If we said misstep prop two is 0.1 and
**[6:44]** re-execute the Notebook and so these numbers
**[6:48]** up here are the optimal return
**[6:52]** if you were to take the best possible actions,
**[6:56]** take this optimal policy but the robot were to step in
**[7:00]** the wrong direction 10 percent of the time
**[7:03]** and these are the q values for this stochastic NTP.
**[7:07]** Notice that these values are now a little bit
**[7:09]** lower because you can't
**[7:11]** control the robot as well as before.
**[7:14]** The q values, as well as the optimal returns,
**[7:16]** have gone down a bit.
**[7:18]** In fact, if you were to increase the misstep probability,
**[7:22]** say 40 percent of
**[7:23]** the time the robot doesn't even go into directions.
**[7:26]** You're commanding it to only 60 percent of the time.
**[7:29]** It goes where you told it to,
**[7:30]** then these values end up even lower because
**[7:34]** your degree of control over the robot has decreased.
**[7:37]** I encourage you to play with
**[7:39]** the optional lab and change the value of
**[7:42]** the misstep probability and see how that
**[7:44]** affects the for return or the auto expected return,
**[7:48]** as well as the Q values, q of s a.
**[7:51]** Now, in everything we've done so far,
**[7:55]** we've been using this Markov decision process,
**[7:58]** this Mars rover with just six states.
**[8:01]** For many practical applications,
**[8:03]** the number of states will be much larger.
**[8:06]** In the next video,
**[8:07]** we'll take the reinforcement learning or
**[8:09]** Markov decision process framework
**[8:11]** we've talked about so far and
**[8:13]** generalize it to this much
**[8:14]** richer and maybe even more interesting set of
**[8:17]** problems with much larger and in
**[8:19]** particular with continuous state spaces,
**[8:22]** let's take a look at that in the next video.
