---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 3
section: State-action value function
item_title: Bellman Equation
duration: 13 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/3Wpee/bellman-equation
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Bellman Equation — Transcript

**[0:01]** Let me summarize where we are.
**[0:03]** If you can compute
**[0:05]** the state action value function Q of S,
**[0:08]** A, then it gives you a way to
**[0:10]** pick a good action from every scene.
**[0:12]** Just pick the action A,
**[0:14]** that gives you the largest value of Q of S,A.
**[0:17]** The question is, how do you compute
**[0:19]** these values Q of S,A?
**[0:21]** In reinforcement learning, there's a key equation called
**[0:25]** the Bellman equation that will help us to
**[0:27]** compute the state action value function.
**[0:30]** Let's take a look at what is this equation.
**[0:33]** As a reminder, this is the definition of Q of S, A.
**[0:38]** It's return if we start in state S,
**[0:40]** take the action a once and they
**[0:41]** behave optimally after that.
**[0:43]** In order to describe the Bellman equation,
**[0:45]** I'm going to use the following notation.
**[0:48]** I'm going to use S to denote the current state.
**[0:51]** Next, I'm going to use R of S
**[0:54]** to denote the rewards of the current state.
**[0:58]** For our little MDP example,
**[1:02]** we will have that r of one State1 is 100.
**[1:06]** The reward of State 2 is 0, and so on.
**[1:09]** The reward of State 6 is 40.
**[1:12]** I'm going to use
**[1:14]** the alphabet A to denote the current action,
**[1:18]** the action that you take in
**[1:19]** the state S. After you take the action a,
**[1:23]** you get to some new state.
**[1:25]** For example, if you're in State
**[1:27]** 4 and you take the action left,
**[1:29]** then you get to State 3.
**[1:32]** I'm going to use S prime to denote
**[1:35]** the state you get to after taking that action a
**[1:38]** from the current state S.
**[1:40]** I'm also going to use A prime to
**[1:42]** denote the action that you might take in state S prime,
**[1:48]** the new state you got to.
**[1:49]** The notation convention, by the way,
**[1:51]** is that S,A correspond to the current state and action.
**[1:55]** When we add the prime,
**[1:57]** that's the next state,
**[1:58]** then the next action.
**[2:00]** The Bellman equation is the following.
**[2:02]** It says that Q of S,A,
**[2:06]** that is the return under this set of
**[2:10]** assumptions that's equal to r of S,
**[2:15]** says reward you get for being in that state plus
**[2:19]** the discount factor Gamma times
**[2:23]** max over all possible actions,
**[2:25]** a prime of q of S prime,
**[2:29]** the new state you just got to,
**[2:31]** and then a prime.
**[2:34]** There's a lot going on in this equation.
**[2:36]** Let's first take a look at some examples.
**[2:39]** We'll come back to see why
**[2:40]** this equation might make sense.
**[2:42]** Let's look at an example.
**[2:44]** Let's look at Q of State 2 and action.
**[2:49]** Apply Bellman Equation to
**[2:51]** this to see what value it gives us.
**[2:54]** If the current state is state
**[2:58]** two and that the action is to go right,
**[3:01]** then the next day you get to,
**[3:03]** after going write S prime would be the State 3.
**[3:07]** The Bellman equation says Q of 2,
**[3:10]** right is R of S. This R State 2,
**[3:16]** which is just the rewards
**[3:18]** zero plus the discount factor Gamma,
**[3:22]** which we set to 0.5 in this example,
**[3:25]** times max of the Q values in state S prime in State 3.
**[3:34]** This is going to be the max of 25 and 6.25,
**[3:40]** since this is max over a prime of
**[3:42]** q of S prime comma a prime.
**[3:45]** This is taking the larger of 25 or
**[3:50]** 6.25 because those are the two choices for State 3.
**[3:55]** This turns out to be equal to zero plus 0.5 times 25,
**[4:01]** which is equal to 12.5,
**[4:04]** which fortunately is Q of two and then the action right.
**[4:09]** Let's look at just one more example.
**[4:11]** Let me take the State 4 and see what
**[4:15]** is Q of State 4 if you decide to go left.
**[4:19]** In this case, the current state is
**[4:21]** four current action is to go left.
**[4:24]** The next state, if you can start from four going left.
**[4:27]** You end up also at State 3.
**[4:30]** Let us prime this three again, the Bellman Equation,
**[4:33]** we'll say this is equal to R of S. Our State four,
**[4:38]** which is zero plus 0.5 the discount factor
**[4:42]** Gamma of max over a prime of q of S prime.
**[4:47]** That is the State 3 again, comma a prime.
**[4:51]** Once again, the Q values for State 3 are 25 and
**[4:55]** 6.25 and the larger of these is 25.
**[4:59]** This works out to be R(4) is 0 plus 0.5 times 25,
**[5:07]** which is again equal to 12.5.
**[5:10]** That's why q of four with the action
**[5:13]** left is also equal to 12.5,
**[5:17]** just one note, if you're in a terminal state,
**[5:20]** then Bellman Equation simplifies to q of SA equals to
**[5:25]** r of S because there's
**[5:26]** no state S prime and so that second term would go away.
**[5:31]** Which is why Q
**[5:32]** of S,A in the terminal states is just 100,
**[5:35]** 100 or 40 40.
**[5:37]** If you wish feel free to pause
**[5:38]** the video and apply the Bellman Equation to
**[5:41]** any other state action in
**[5:43]** this MDP and check for yourself if this math works out.
**[5:47]** Just to recap, this is how we had define Q of S,A.
**[5:54]** We saw earlier that the best possible return from
**[5:57]** any state S is max over a Q of S,A.
**[6:01]** In fact, just to rename SNA,
**[6:05]** it turns out that the best possible return
**[6:07]** from a state S prime,
**[6:09]** is max over S prime of a prime.
**[6:13]** I didn't really do anything other than rename S,
**[6:17]** S prime and a to a prime.
**[6:18]** But this will make some of
**[6:19]** the intuitions a little bit easier later.
**[6:22]** But for any state S prime,
**[6:23]** like State 3, the best possible return from, say,
**[6:27]** State 3 is the max over
**[6:28]** all possible actions of Q of S prime a prime.
**[6:32]** Here again is the Bellman equation.
**[6:36]** The intuition that this captures is if you're starting
**[6:41]** from state s and you're going to take
**[6:43]** action a and then act optimally after that,
**[6:46]** then you're going to see
**[6:48]** some sequence of rewards over time.
**[6:51]** In particular, the return will
**[6:53]** be computed from the reward at the first step,
**[6:57]** plus Gamma times reward at the second step
**[7:01]** plus Gamma squared times reward at
**[7:03]** the third step, and so on.
**[7:06]** Plus dot, dot, dot until you get to the terminal state.
**[7:08]** What Bellman equation says is this sequence of rewards,
**[7:14]** what the discount factor is,
**[7:15]** can be broken down into two components.
**[7:18]** First, this R of s,
**[7:21]** that's the reward you get right away.
**[7:25]** In the reinforcement learning literature,
**[7:27]** this is sometimes also called the immediate reward,
**[7:30]** but that's what R_1 is.
**[7:32]** It's the reward you get for starting out in some state
**[7:36]** s. The second term then is the following;
**[7:39]** after you start in state s and take action a,
**[7:43]** you get to some new state s prime.
**[7:47]** The definition of Q of s,
**[7:48]** a assumes we're going to behave optimally after that.
**[7:52]** After we get to s prime,
**[7:54]** we are going to behave optimally and get
**[7:56]** the best possible return from the state s prime.
**[8:00]** What this is, max of a prime of Q of s prime a prime,
**[8:05]** this is the return from behaving optimally,
**[8:09]** starting from the state s prime.
**[8:13]** That's exactly what we had written up here,
**[8:17]** is the best possible return
**[8:19]** for when you start from state s prime.
**[8:21]** Another way of phrasing this is
**[8:24]** this total return down here is also equal to R_1 plus,
**[8:30]** and then we're going to factor out Gamma in the map,
**[8:33]** is Gamma times R_2 plus,
**[8:36]** and instead of Gamma squared is just Gamma times
**[8:40]** R_3 plus Gamma squared times R_4 plus dot dot dot.
**[8:45]** Notice that if you were starting from state s prime,
**[8:49]** the sequence of rewards you get will be R_2,
**[8:53]** R_3, then R_4, and so on.
**[8:56]** That's why this expression here,
**[9:00]** that's the total return
**[9:03]** if you were to start from state s prime.
**[9:06]** If you were to behave optimally,
**[9:09]** then this expression should be
**[9:11]** the best possible return for starting from state s prime,
**[9:15]** which is why this sequence of
**[9:18]** discount rewards equals that max of
**[9:22]** a prime of Q of s prime a prime and there were also
**[9:25]** leftover with this extra discount factor Gamma there,
**[9:29]** which is why Q of s,
**[9:31]** a is also equal to this expression over here.
**[9:35]** In case you think this is quite complicated and
**[9:38]** you aren't following all the details,
**[9:40]** don't worry about it.
**[9:41]** So long as you apply this equation,
**[9:44]** you will manage to get the right results.
**[9:46]** But the high level intuition I hope you take away is that
**[9:50]** the total return you get
**[9:52]** in the reinforcement learning problem has two parts.
**[9:56]** The first part is this reward that you get right away,
**[10:01]** and then the second part is
**[10:03]** Gamma times the return
**[10:06]** you get starting from the next state s prime.
**[10:09]** As these two components together,
**[10:12]** R of s plus Gamma times the return from the next state,
**[10:16]** that is equal to the total return from the
**[10:19]** current state s. That
**[10:21]** is the essence of the Bellman equation.
**[10:24]** Just to relate this back to our earlier example,
**[10:27]** Q of 4, left.
**[10:30]** That's the total return for starting
**[10:32]** State 4 and going left.
**[10:34]** If you were to go left in State
**[10:38]** 4 the rewards you get are 0 in State 4,
**[10:41]** 0 in State 3,
**[10:42]** 0 in State 2, and then 100,
**[10:45]** which is why the total return is this;
**[10:47]** 0.5 squared plus 0.5 cubed, which was 12.5.
**[10:52]** What Bellman equation is saying is
**[10:54]** that we can break this up into two pieces.
**[10:56]** There is this zero,
**[10:58]** which is R of the state four,
**[11:00]** and then plus 0.5 times this other sequence,
**[11:07]** 0 plus 0.50 plus 0.5 squared times 100.
**[11:14]** But if you look at what this sequence is,
**[11:17]** this is really the optimal return from
**[11:19]** the next state s prime that you got to
**[11:22]** after taking the action left from state four.
**[11:25]** That's why this is equal to the reward 4 plus
**[11:29]** 0.5 times the optimal return from State 3.
**[11:34]** Because if you were to start from State 3,
**[11:36]** the rewards you get would be zero
**[11:38]** followed by zero followed by 100,
**[11:41]** so this is optimal return from
**[11:44]** State 3 and that's why this is
**[11:47]** just R of 4 plus 0.5 max over
**[11:51]** a prime Q of State 3, a prime.
**[11:55]** I know the Bellman equation,
**[11:57]** this is somewhat complicated equation breaking down
**[11:59]** your total returns into
**[12:01]** the reward you're getting right away.
**[12:03]** The immediate reward plus
**[12:04]** Gamma times the returns from the next state s prime.
**[12:08]** If it makes sense to you,
**[12:10]** but not fully, it's okay. Don't worry about it.
**[12:13]** You can still apply Bellman's equations
**[12:15]** to get a reinforcement learning algorithm
**[12:17]** to work correctly,
**[12:19]** but I hope that at least the high level intuition
**[12:21]** of why breaking
**[12:23]** down the rewards into what you get right
**[12:24]** away plus what you get in the future.
**[12:27]** I hope that makes sense.
**[12:29]** Before moving on to
**[12:30]** develop a reinforcement learning algorithm,
**[12:33]** we have coming up next an optional video on
**[12:36]** Stochastic Markov decision processes or
**[12:39]** on reinforcement learning applications where the actions,
**[12:42]** if you take, can have a slightly random effect.
**[12:46]** Take look at the optional video if you wish.
**[12:48]** Then after that, we'll start to
**[12:50]** develop a reinforcement learning algorithm.
