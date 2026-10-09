---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 3
section: Reinforcement learning introduction
item_title: The Return in reinforcement learning
duration: 10 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/5SCL1/the-return-in-reinforcement-learning
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# The Return in reinforcement learning — Transcript

**[0:01]** You saw in the last video,
**[0:03]** what are the states of
**[0:04]** reinforcement learning application,
**[0:06]** as well as how depending on the actions
**[0:08]** you take you go through different states,
**[0:11]** and also get to enjoy different rewards.
**[0:14]** But how do you know if a particular set of rewards is
**[0:17]** better or worse than a different set of rewards?
**[0:20]** The return in reinforcement learning,
**[0:22]** which we'll define in this video,
**[0:24]** allows us to capture that.
**[0:26]** As we go through this,
**[0:27]** one analogy that you might find helpful
**[0:29]** is if you imagine
**[0:31]** you have a five-dollar bill at your feet,
**[0:33]** you can reach down and pick up,
**[0:35]** or half an hour across town,
**[0:37]** you can walk half an hour and pick up a 10-dollar bill.
**[0:41]** Which one would you rather go after?
**[0:43]** Ten dollars is much better than five dollars,
**[0:47]** but if you need to walk for half an hour
**[0:48]** to go and get that 10-dollar bill,
**[0:50]** then maybe it'd be more
**[0:51]** convenient to just pick up the five-dollar bill instead.
**[0:54]** The concept of a return captures that rewards you can get
**[0:58]** quicker are maybe more attractive than
**[1:00]** rewards that take you a long time to get to.
**[1:03]** Let's take a look at exactly how that works.
**[1:05]** Here's a Mars Rover example.
**[1:08]** If starting from state 4 you go to the left,
**[1:11]** we saw that the rewards you get would
**[1:14]** be zero on the first step from state 4,
**[1:16]** zero from state 3,
**[1:18]** zero from state 2,
**[1:19]** and then 100 at state 1, the terminal state.
**[1:23]** The return is defined as the sum
**[1:28]** of these rewards but weighted by one additional factor,
**[1:32]** which is called the discount factor.
**[1:34]** The discount factor is a number a little bit less than 1.
**[1:39]** Let me pick 0.9 as the discount factor.
**[1:41]** I'm going to weight the reward
**[1:44]** in the first step is just zero,
**[1:45]** the reward in the second step is a discount factor,
**[1:48]** 0.9 times that reward,
**[1:50]** and then plus the discount factor^2 times that reward,
**[1:54]** and then plus the discount factor^3 times that reward.
**[1:59]** If you calculate this out,
**[2:00]** this turns out to be 0.729 times 100, which is 72.9.
**[2:08]** The more general formula for the return is that if
**[2:13]** your robot goes through some sequence of
**[2:15]** states and gets reward R_1 on the first step,
**[2:19]** and R_2 on the second step,
**[2:21]** and R_3 on the third step,
**[2:24]** and so on,
**[2:25]** then the return is R_1 plus the discount factor Gamma,
**[2:31]** this Greek alphabet Gamma
**[2:33]** which I've set to 0.9 in this example,
**[2:36]** the Gamma times R_2
**[2:38]** plus Gamma^2 times R_3 plus Gamma^3 times R_4,
**[2:43]** and so on, until you get to the terminal state.
**[2:48]** What the discount factor Gamma does is it has
**[2:52]** the effect of making
**[2:55]** the reinforcement learning algorithm
**[2:56]** a little bit impatient.
**[2:58]** Because the return gives full credit to
**[3:01]** the first reward is 100 percent is 1 times R_1,
**[3:05]** but then it gives a little bit less credit to
**[3:08]** the reward you get at the second step
**[3:09]** is multiplied by 0.9,
**[3:11]** and then even less credit to the reward you
**[3:13]** get at the next time step R_3,
**[3:15]** and so on, and so getting rewards
**[3:18]** sooner results in a higher value for the total return.
**[3:22]** In many reinforcement learning algorithms,
**[3:25]** a common choice for
**[3:26]** the discount factor will be a number pretty close to 1,
**[3:29]** like 0.9, or 0.99, or even 0.999.
**[3:34]** But for illustrative purposes
**[3:36]** in the running example I'm going to use,
**[3:39]** I'm actually going to use a discount factor of 0.5.
**[3:43]** This very heavily down weights or
**[3:46]** very heavily we say discounts rewards in the future,
**[3:50]** because with every additional passing timestamp,
**[3:53]** you get only half as much credit as
**[3:55]** rewards that you would have gotten one step earlier.
**[3:59]** If Gamma were equal to 0.5,
**[4:02]** the return under the example above would have been
**[4:05]** 0 plus 0.5 times 0,
**[4:09]** replacing this equation on top,
**[4:11]** plus 0.5^2 0 plus 0.5^3 times 100.
**[4:17]** That's lost reward because state 1 to terminal state,
**[4:21]** and this turns out to be a return of 12.5.
**[4:26]** In financial applications, the discount factor also has
**[4:30]** a very natural interpretation as
**[4:32]** the interest rate or the time value of money.
**[4:35]** If you can have a dollar today,
**[4:38]** that may be worth a little bit more
**[4:40]** than if you could only get a dollar in the future.
**[4:43]** Because even a dollar today you can put in the bank,
**[4:46]** earn some interest, and end up with
**[4:47]** a little bit more money a year from now.
**[4:50]** For financial applications, often,
**[4:52]** that discount factor represents how much less
**[4:55]** is a dollar in the future where
**[4:56]** I've compared to a dollar today.
**[4:58]** Let's look at some concrete examples of returns.
**[5:02]** The return you get depends on the rewards,
**[5:05]** and the rewards depends on the actions you take,
**[5:08]** and so the return depends on the actions you take.
**[5:12]** Let's use our usual example and say for this example,
**[5:17]** I'm going to always go to the left.
**[5:21]** We already saw previously that if
**[5:24]** the robot were to start off in state 4,
**[5:27]** the return is 12.5 as
**[5:30]** we worked out on the previous slide.
**[5:32]** It turns out that if it were to start off in say three,
**[5:37]** the return would be 25 because it gets
**[5:40]** to the 100 reward one step sooner,
**[5:44]** and so it's discounted less.
**[5:47]** If it were to start off in state 2,
**[5:49]** the return would be 50.
**[5:51]** If it were to just start off and state 1, well,
**[5:53]** it gets the reward of 100 right away,
**[5:56]** so it's not discounted at all.
**[5:57]** The return if we were to start out in
**[5:59]** state 1 will be 100,
**[6:01]** and then the return in these two states are 6.25.
**[6:05]** It turns out if you start off in state 6,
**[6:07]** which is terminal state,
**[6:08]** you just get the reward and thus the return of 40.
**[6:14]** Now, if you were to take a different set of actions,
**[6:17]** the returns would actually be different.
**[6:20]** For example, if we were to always go to the right,
**[6:25]** if those were our actions,
**[6:26]** then if you were to start in state 4, get a reward of 0.
**[6:31]** Then you get to state 5, get a reward of 0,
**[6:34]** and it gets to state 6,
**[6:36]** and get a reward of 40.
**[6:38]** In this case, the return would be 0 plus 0.5,
**[6:43]** the discount factor times 0 plus 0.5 squared times 40,
**[6:48]** and that turns out to be equal to 0.5 squared is 1/4,
**[6:53]** so 1/4 of 40 is 10.
**[6:55]** The return from this state,
**[6:58]** from state 4 is 10.
**[7:00]** If you were to take actions,
**[7:01]** always go to the right.
**[7:03]** Through similar reasoning,
**[7:05]** the return from this state is 20,
**[7:07]** the return from this state is five,
**[7:09]** the return from this state is 2.5,
**[7:12]** and then the return,
**[7:13]** the determinant state is is 140.
**[7:15]** By the way,
**[7:17]** if these numbers don't fully make sense,
**[7:20]** feel free to pause the video and
**[7:21]** double-check the math and see if you
**[7:23]** can convince yourself that these
**[7:25]** are the appropriate values for the return.
**[7:27]** For if you start from different states,
**[7:30]** and if you were to always go to the right.
**[7:33]** We see that it would always go to the right.
**[7:37]** The return you expect to get is lower for most states.
**[7:42]** Maybe always going to the right isn't
**[7:44]** as good an idea as always going to the left.
**[7:48]** But it turns out that we
**[7:50]** don't have to always go to the left,
**[7:52]** always go to the right.
**[7:53]** We could also decide if you're in state 2, go left.
**[7:57]** If your in state 3, go left.
**[7:59]** If you're in state 4, go left.
**[8:01]** But if you're in state 5,
**[8:03]** then you're so close to this reward.
**[8:05]** Let's go right.
**[8:07]** This will be a different way of choosing
**[8:10]** actions to take based on what state you're in.
**[8:14]** It turns out that the return
**[8:17]** you get from the different states will be 100, 50, 25,
**[8:24]** 12.5, 20, and 40.
**[8:28]** Just to illustrate one case.
**[8:31]** If you were to start off in state 5,
**[8:34]** here you would go to the right,
**[8:35]** and so the rewards you get would be
**[8:38]** zero first in state 5, and then 4.
**[8:41]** The return is zero, the first reward,
**[8:44]** plus the discount factor is 0.5 times 40, which is 20,
**[8:49]** which is why the return from this status
**[8:51]** 20 if you take actions shown here.
**[8:54]** To summarize, the return in
**[8:57]** reinforcement learning is the sum
**[8:59]** of the rewards that the system gets,
**[9:01]** weighted by the discount factor,
**[9:03]** where rewards in the far future are weighted
**[9:06]** by the discount factor raised to a higher power.
**[9:10]** Now, this actually has
**[9:12]** an interesting effect when you have
**[9:14]** systems with negative rewards.
**[9:16]** In the example we went through,
**[9:17]** all the rewards were zero or positive.
**[9:20]** But if there are any rewards are negative,
**[9:23]** then the discount factor actually
**[9:25]** incentivizes the system to
**[9:27]** push out the negative rewards
**[9:29]** as far into the future as possible.
**[9:31]** Taking a financial example,
**[9:33]** if you had to pay someone $10,
**[9:36]** maybe that's a negative reward of minus 10.
**[9:39]** But if you could postpone payment by a few years,
**[9:43]** then you're actually better off
**[9:44]** because $10 a few years from now,
**[9:47]** because of the interest rate is actually worth
**[9:50]** less than $10 that you had to pay today.
**[9:54]** For systems with negative rewards,
**[9:56]** it causes the algorithm to try to push
**[9:59]** out the make the rewards
**[10:01]** as far into the future as possible.
**[10:03]** For financial applications and for other applications,
**[10:06]** that actually turns out
**[10:07]** to be right thing for the system to do.
**[10:09]** You now know what
**[10:11]** is the return in reinforcement learning,
**[10:13]** let's go on to the next video to
**[10:15]** formalize the goal of reinforcement learning algorithm.
