---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 3
section: State-action value function
item_title: State-action value function example
duration: 5 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/NG3vW/state-action-value-function-example
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# State-action value function example — Transcript

**[0:01]** Using the state-action value function example.
**[0:03]** You're seeing what the values of QSA are like.
**[0:07]** In order to keep holding our intuition about reinforcement learning problems and
**[0:13]** how the values of QSA change depending on the problem will provided an optional lab.
**[0:19]** That lets you play around modify the mars rover example and see for
**[0:24]** yourself how QSA will change.
**[0:26]** Let's take a look.
**[0:27]** Here's a Jupyter Notebook that I hope you play with after watching this video.
**[0:32]** I'm going to run these helper functions, now notice here that this
**[0:37]** specifies the number six that the two actions so I wouldn't change these.
**[0:42]** And this specifies the terminal left in the terminal right rewards which
**[0:47]** has been 100 and 40 and then zero was the rewards of the intermediate states.
**[0:52]** The discount factor gamma 0.5.
**[0:55]** And let's ignore the misstep probability for
**[0:57]** now we'll talk about that in a later video.
**[1:00]** And with these values if you run this code this will compute and
**[1:06]** visualize the optimal policy as well as the Q function Q of SA.
**[1:13]** You learn later about how to develop a learning algorithm to estimate or
**[1:18]** compute Q of SA yourself.
**[1:19]** So for now don't worry about what code we have written to compute Q of SA.
**[1:24]** But you see that the values here Q of SA are the values we saw in the lecture.
**[1:31]** Now here's where the fun starts.
**[1:33]** Let's change around some of the values and see how these things change.
**[1:37]** I'm going to update the terminal right reward to a much
**[1:42]** smaller value says only 10.
**[1:45]** If I now rerun the code, look at how Q of SA changes and
**[1:50]** now thinks that if you're in state 5.
**[1:53]** Then if you go left and behave optimally you get 6.25.
**[1:58]** Whereas if you go right and
**[2:00]** behave also the after that you get a return of only five.
**[2:03]** So now when the reward at the right is so small it's only 10.
**[2:08]** Even when you're so close to you rather go left all the way.
**[2:12]** And in fact the auto policy is now to go left from every single state.
**[2:17]** Let's make some other changes.
**[2:18]** I'm going to change the terminal right reward back to 40.
**[2:22]** But let me change the discount factor to 0.9,
**[2:27]** with a discount factor that's closer to one.
**[2:32]** This makes the Mars Rover less impatient is willing to take longer to hold out for
**[2:38]** a higher reward because rewards in the future are not multiplied by
**[2:43]** 0.5 to some high power is multiplied by 0.9 to some high power.
**[2:48]** And so is willing to be more patients, because rewards in the future are not
**[2:53]** discounted or multiplied by as small a number as when the discount was 0.5.
**[3:00]** So let's rerun the code.
**[3:02]** And now you see this is Q of SA for the different states and
**[3:08]** now for state 5 going left actually gives you
**[3:13]** a higher reward of 65.61 compared to 36.
**[3:18]** Notice by the way that 36 is 0.9 times this terminal reward of 40.
**[3:22]** So these numbers make sense.
**[3:24]** But when a small patient is willing to go to the left, even when you're in state 5.
**[3:29]** Now let's change gamma to a much smaller number like 0 .3.
**[3:35]** So this very heavily discounts rewards in the future.
**[3:38]** This makes it incredibly impatient.
**[3:40]** So let me rerun this code and now the behavior has changed.
**[3:44]** Noticed that now in state 4 is not going to
**[3:48]** have the patience to go for the larger 100 reward,
**[3:53]** because the discount factor gamma is now so small is 0.3.
**[3:58]** It would rather go for the reward of 40 even though it's a much smaller reward is
**[4:03]** closer and that's whether we choose to do.
**[4:06]** So I hope that you can get a sense by playing around with these numbers yourself
**[4:11]** and running this code.
**[4:12]** How the values of Q of SA change as was how the optimal return
**[4:18]** which you notice is the larger of these two numbers QSA.
**[4:23]** How that changes as well as how the optimal policy also changes.
**[4:29]** So I hope you go and play with the optional lab and change the reward
**[4:33]** function and change the discount factor gamma and try a different values.
**[4:38]** And see for yourself how the values of Q of SA change,
**[4:42]** how the optimal return from different states change and
**[4:45]** how the auto policy changes depending on these different values.
**[4:50]** And by doing so, I hope that will sharpen your intuition about how
**[4:55]** these different quantities are affected depending on the rewards and
**[4:59]** so on in reinforcement learning application.
**[5:03]** After you play to the lab, we then be ready to come back and
**[5:06]** talk about what's probably the single most important equation in reinforcement
**[5:10]** learning, which is something called the bellman equation.
**[5:14]** So I hope you have fun playing with the optional lab and
**[5:18]** after that let's come back to talk about bellman equations.
