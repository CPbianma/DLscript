---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 3
section: State-action value function
item_title: State-action value function definition
duration: 11 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/FEU97/state-action-value-function-definition
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# State-action value function definition — Transcript

**[0:01]** when we start to develop reinforcement learning hours later this week,
**[0:05]** you see that there's a key quantity that reinforcement learning algorithm will try to
**[0:10]** compute and that's called the state action value function.
**[0:13]** Let's take a look at what this function is.
**[0:16]** The state action value function is a function typically
**[0:20]** denoted by the letter uppercase Q.
**[0:23]** And it's a function of a state you might be in as well as
**[0:28]** the action you might choose to take in that state and Q of s,a.
**[0:34]** Will give a number that equals the return.
**[0:38]** If you start in that state.
**[0:41]** S and take the action A just once and after taking
**[0:45]** action A once you then behave optimally after that.
**[0:50]** So after that you take whatever actions will result in the highest possible
**[0:55]** return.
**[0:55]** Now you might be thinking there's something a little bit strange about this
**[0:59]** definition because how do we know what is the optimal behavior?
**[1:03]** And if we knew what the optimal behavior, if we already knew what's the best action to
**[1:07]** take in every state, why do we still need to compute Q of SA.
**[1:11]** Because we already have the optimal policy.
**[1:13]** So I do want to acknowledge that there's something a little bit strange about this
**[1:17]** definition.
**[1:17]** There's almost something a little bit circular about this definition, but
**[1:22]** rest assured When we look at specific reinforcement learning algorithms later will
**[1:26]** resolve this slightly circular definition and will come up with a way to compute
**[1:31]** the Q function even before we've come up with the optimal policy.
**[1:35]** But you see that in a later video.
**[1:37]** So don't worry about this for now.
**[1:39]** Let's look at an example we saw previously that this is a pretty
**[1:44]** good policy Go left from stage 2, 3 and four and go right from State five.
**[1:50]** It turns out that this is actually the optimal policy for
**[1:55]** the mars rover application When the discount factor gamma is 0.5, so Q of S.
**[2:01]** A will be equal to the total return If you start from say that
**[2:06]** take the action A and then behave optimally after that.
**[2:12]** Meaning take actions according to this policy.
**[2:15]** Shown over here, let's figure out what Q of s,a.
**[2:18]** Is for a few different states.
**[2:21]** Let's look at say Q of state too.
**[2:26]** And what if we take the action to go right well if you're in state two and
**[2:31]** you go right then you end up at state three And
**[2:34]** then after that you behave optimally you're going to go left from ST three and
**[2:40]** then go left from state to and then eventually you get the reward of 100.
**[2:45]** In this case, the rewards you get would be zero from state to zero
**[2:51]** when you get to stay three zero when you get back to state two and
**[2:56]** then 100 when you finally get to the terminal state one and
**[3:01]** so the return will be zero plus 0.5 times that plus 0.5
**[3:06]** squared times ac plus 0.5 cubed times 100.
**[3:10]** And this turns out to be 12.5 And so
**[3:14]** Q of ST two of going right as equal to 12.5.
**[3:19]** Note that this passes, no judgment on whether going right is a good idea or not.
**[3:24]** It's actually not that good an idea from state two to go right, but
**[3:28]** it just faithfully reports out the return if you take action A and
**[3:32]** then behave optimally afterwards.
**[3:34]** Here's another example.
**[3:36]** If you're in state to and you were to go left, then the sequence
**[3:41]** of rewards you get will be zero when you're in state two followed by 100.
**[3:47]** And so the return is zero plus 0.5 times 100
**[3:52]** that's equal to 50 in order to write down The values of Q(s,a).
**[3:59]** In this diagram, I'm going to write 12.5 here on the right
**[4:05]** to denote that this is Q of state two going to the right.
**[4:10]** And then when I write a little 50 here on the left to denote
**[4:14]** that this is Q of state two and going to the left just to take one more
**[4:19]** example What if we're in state four and we decide to go left.
**[4:24]** Well if you're in state four you go left,
**[4:27]** you get rewards zero and then you take action left here.
**[4:31]** So zero gain, take action left here, zero and then 100.
**[4:35]** So Q of four Left results in rewards zero because the first action is left and
**[4:43]** then because we followed the optimal policy afterwards You can reward 00 100.
**[4:51]** And so the return is zero plus 00.5 times that.
**[4:55]** Plus 4.5 squared times that plus 0.5 cubed times that.
**[4:59]** Which is therefore equal to 12.5.
**[5:03]** So Q4 left is 12.5.
**[5:06]** I'm going to write this here as 12.5.
**[5:10]** And it turns out if you were to carry out this exercise for all of the other
**[5:15]** states and all of the other actions, you end up with this being the Q of s,a.
**[5:21]** For different states and different actions And then finally at the Terminal State.
**[5:26]** Well it doesn't matter what you do, you just get that terminal reward 100 or 40.
**[5:32]** So just write down those terminal awards over here.
**[5:35]** So this is Q of s,a.
**[5:37]** For every state state one through six and for the two actions,
**[5:42]** action left and action right.
**[5:44]** Because the state action value function is almost always denoted by the letter Q.
**[5:51]** This is also often called the Q function.
**[5:55]** So the terms Q.
**[5:56]** Function and state action value function are used interchangeably and
**[6:01]** it tells you what are your returns or really what is the value?
**[6:05]** How good is it?
**[6:06]** Just take action A and state S and then behave optimally after that.
**[6:11]** Now it turns out that once you can compute the Q function this will
**[6:16]** give you a way to pick actions as well.
**[6:19]** Here's the policy and return.
**[6:21]** And here are the values Q of s,a.
**[6:24]** From the previous slide.
**[6:26]** You notice one interesting thing when you look at the different states which
**[6:32]** is that if you take state two taking the action left results in a,q.
**[6:37]** Value or state action value of 50 which is actually the best possible return you can
**[6:42]** get from that state.
**[6:43]** In state three two of s,a.
**[6:45]** for the action left also gives you that higher return
**[6:50]** in state four the action left gives you the return you want.
**[6:55]** And in state five is actually the action going to the right that
**[6:59]** gives you that higher return of 20.
**[7:02]** So it turns out that the best possible return from any state S.
**[7:08]** Is the largest value of Q of s,a
**[7:11]** A maximizing over A.
**[7:13]** Just to make sure this is clear what I'm saying is that in say state for
**[7:19]** There is Q of state four left which is 12.5 And q.
**[7:24]** of state four right, Which turns out to be 10.
**[7:29]** And the larger of these two values which is 12.5 Is
**[7:33]** the best possible return from that state four.
**[7:37]** In other words the highest return you can hope to get from State four is 12.5.
**[7:41]** And it's actually the larger of these two numbers 12.5 and 10.
**[7:45]** And moreover, if you want your Mars Rover to enjoy a return of 12.5
**[7:52]** rather than say 10 then the action you should take is the action A.
**[7:58]** That gives you the larger value of Q of s,a.
**[8:01]** So the best possible action status is the action A.
**[8:05]** That actually maximizes Q, of s,a.
**[8:10]** So this might give you a hint for why computing Q, of s,a.
**[8:16]** Is an important part of the reinforcement learning algorithm that will build later.
**[8:22]** Namely if you have a way of computing Q of s,a.
**[8:25]** For every state and for every action then when you're in
**[8:29]** some state s all you have to do is look at the different actions A.
**[8:34]** And pick the action A.
**[8:36]** That maximizes Q of s,a.
**[8:38]** And so pi of s.
**[8:39]** S can just pick the action A.
**[8:42]** That gives the largest value of Q of s,a.
**[8:44]** And that will turn out to be a good action.
**[8:47]** In fact it turned out to be the optimal action.
**[8:50]** Another intuition about why this makes sense is Qof s,a.
**[8:54]** Is returned if you start in the state S and take the action A.
**[8:58]** And then behave optimally after that.
**[9:00]** So in order to earn the biggest possible return,
**[9:04]** what you really want is to take the action A.
**[9:07]** That results in the biggest total return.
**[9:12]** That's why if only we have a way of computing Q f s,a.
**[9:15]** For every state taking the action A that maximizes return under
**[9:20]** these circumstances seems like it's the best action to take in that state.
**[9:24]** Although this isn't something you need to know for this
**[9:27]** course, I want to mention also that if you look online or look at the reinforcement
**[9:32]** learning literature, sometimes you also see this Q function written as Q.
**[9:38]** Star instead of Q.
**[9:40]** And this Q function is sometimes also called the optimal Q function.
**[9:45]** These terms just refer to the Q function exactly as we've defined it.
**[9:50]** So if you look at the reinforcement learning literature and read about Q.
**[9:53]** Star or the Q function,
**[9:54]** that just means the state action value function that we've been talking about.
**[9:59]** But for the purposes of this course you don't need to worry about this.
**[10:02]** So to summarize if you can compute Q of s,a.
**[10:07]** For every state and every action,
**[10:10]** then that gives us a good way to compute the optimal policy pi of S.
**[10:15]** So that's the state action value function or the Q function.
**[10:20]** We'll talk later about how to come up with an algorithm to compute them despite
**[10:24]** the slightly circular aspect of the definition of the Q function.
**[10:28]** But first let's take a look at the next video at some specific examples of what
**[10:33]** these values Q of s,a.
**[10:34]** Actually look like
