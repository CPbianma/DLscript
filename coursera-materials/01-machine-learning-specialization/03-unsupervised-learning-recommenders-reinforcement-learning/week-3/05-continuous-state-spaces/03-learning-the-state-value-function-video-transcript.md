---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 3
section: Continuous state spaces
item_title: Learning the state-value function
duration: 17 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/EH7Zf/learning-the-state-value-function
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Learning the state-value function — Transcript

**[0:00]** Let's see how we can use reinforcement learning to
**[0:04]** control the lunar lander or for other reinforcement learning problems.
**[0:09]** The key idea is that we're going to train a neural network to compute or to
**[0:15]** approximate the state action value function Q of SA,
**[0:20]** and that in turn will let us pick good actions.
**[0:23]** Let's see how this works.
**[0:24]** The heart of the learning algorithm is we're going to train
**[0:28]** a neural network that inputs the current state and
**[0:31]** the current action and computes or approximates Q of SA.
**[0:38]** In particular, for the lunar lander,
**[0:41]** we're going to take the state S and any action A and put them together.
**[0:47]** Concretely, the state was that list of eight numbers that we saw previously.
**[0:52]** You'd have x, y, x dot,
**[0:56]** y dot, theta, theta dot,
**[0:59]** and then LR for whether the lakes are grounded.
**[1:02]** That's a list of eight numbers to describe the state.
**[1:05]** Then finally, we have four possible actions,
**[1:08]** nothing left main or main engine and right.
**[1:12]** We can encode any of those four actions using a one-hot feature vector.
**[1:18]** If action were the first action,
**[1:21]** we may encode it using 1, 0, 0, 0.
**[1:25]** Or if it was the second action to find the left cluster,
**[1:29]** we may encode it as 0, 1, 0, 0.
**[1:33]** This list of 12 numbers,
**[1:36]** eight numbers for the state,
**[1:38]** and then four numbers,
**[1:39]** a one-hot encoding of the action is the inputs we'll have to the neural network.
**[1:44]** I'm going to call this x.
**[1:47]** We'll then take these 12 numbers and feed them to a neural network with,
**[1:52]** say, 64 units in the first hidden layer,
**[1:55]** 64 units in the second hidden layer,
**[1:57]** and then a single output in the output layer.
**[2:00]** The job of the neural network is to output Q of SA,
**[2:05]** the state action value function for the lunar lander given the input S and A.
**[2:11]** Because we'll be using neural network training algorithms in a little bit,
**[2:16]** I'm also going to refer to this value Q of SA as
**[2:20]** the target value y that we're training the neural network to approximate.
**[2:25]** Notice that I did say reinforcement learning is different from supervised learning.
**[2:30]** But what we're going to do is not input a state and have it output an action.
**[2:35]** What we're going to do is input a state action pair and have it try to output Q of SA,
**[2:41]** and using a neural network inside
**[2:44]** the reinforcement learning algorithm this way will turn out to work pretty well.
**[2:48]** We'll see the details in a little bit.
**[2:51]** So don't worry about it if it doesn't make sense yet.
**[2:54]** But if you can train a neural network with appropriate choices of parameters in
**[2:59]** the hidden layers and in the output layer to give you a good estimates of Q of SA,
**[3:05]** then whenever your lunar lander is in some state S,
**[3:10]** you can then use the neural network to compute Q of SA for all four actions.
**[3:16]** You can compute Q of S nothing,
**[3:19]** Q of S left, Q of S main, Q of S right.
**[3:22]** Then finally, whichever of these has the highest value,
**[3:26]** you would pick the corresponding action A.
**[3:29]** So for example, if out of these four values,
**[3:33]** Q of S main is largest,
**[3:36]** then you would decide to gunfire the main engine of the lunar lander.
**[3:40]** So the question becomes,
**[3:42]** how do you train a neural network to output Q of SA?
**[3:48]** It turns out the approach will be to use Bellman's equations to create
**[3:52]** a training set with lots of examples X and Y,
**[3:56]** and then we'll use supervised learning exactly as you learned
**[4:00]** in the second course when we talked about neural networks,
**[4:04]** to learn using supervised learning a mapping from X to Y,
**[4:08]** that is a mapping from the state action pair to this target value Q of SA.
**[4:15]** But how do you get a training set with values for
**[4:19]** X and Y that you can then train a neural network on?
**[4:23]** Let's take a look. So here's the Bellman equation,
**[4:27]** Q of SA equals R of S plus gamma max of A prime Q of S prime A prime.
**[4:32]** So the right-hand side is what you want Q of SA to be equal to.
**[4:38]** So I'm going to call this value on the right-hand side Y,
**[4:42]** and the input to the neural network is a state and an action,
**[4:47]** so I'm going to call that X.
**[4:50]** The job of a neural network is to input X,
**[4:53]** that is input a state action pair,
**[4:55]** and try to accurately predict what will be the value on the right.
**[5:00]** So in supervised learning,
**[5:02]** we were training a neural network to learn a function F,
**[5:06]** which depends on a bunch of parameters W and B,
**[5:10]** the parameters of the various layers of the neural network,
**[5:13]** and it was a job of the neural network to input X,
**[5:18]** and hopefully output something close to the target value Y.
**[5:25]** So the question is,
**[5:26]** how can we come up with a training set with
**[5:29]** values X and Y for a neural network to learn from?
**[5:35]** Here's what we're going to do.
**[5:37]** We're going to use the lunar lander,
**[5:39]** and just try taking different actions in it.
**[5:42]** If we don't have a good policy yet,
**[5:45]** we'll take actions randomly,
**[5:46]** fire the left thruster,
**[5:48]** fire the right thruster,
**[5:50]** fire the main engine, do nothing.
**[5:52]** By just trying out different things in the lunar lander simulator,
**[5:58]** we'll observe a lot of examples of when we're in some state,
**[6:02]** and we took some action,
**[6:04]** maybe a good action,
**[6:05]** maybe a terrible action, either way.
**[6:07]** Then we got some rewards R of S for being in that state,
**[6:12]** and as a result of our action,
**[6:14]** we got to some new state S prime.
**[6:17]** As you take different actions in the lunar lander,
**[6:21]** you see these S, A,
**[6:23]** R of S, S prime,
**[6:24]** and we call them tuples in Python codes many times.
**[6:27]** For example, maybe one time you're in some state S,
**[6:31]** and just to give this an index,
**[6:33]** I'm going to call this S1,
**[6:34]** and you happen to take some action A1,
**[6:37]** this could be nothing, left main thruster or right,
**[6:40]** as a result of which you got some reward,
**[6:44]** and you wound up at some state S prime 1.
**[6:48]** Maybe a different time, you're in some other state S2,
**[6:51]** you took some other action,
**[6:53]** could be a good action, could be a bad action,
**[6:55]** could be any of the four actions,
**[6:56]** and you got the reward,
**[6:59]** and then you wound up with S prime 2,
**[7:02]** and so on, multiple times.
**[7:04]** Maybe you've done this 10,000 times,
**[7:06]** or even more than 10,000 times.
**[7:08]** You would have to save the way with not just S1,
**[7:12]** A1, and so on,
**[7:14]** but up to S10,000, A10,000.
**[7:16]** It turns out that each of these lists of four elements,
**[7:20]** each of these tuples will be enough to create
**[7:24]** a single training example, X1, Y1.
**[7:28]** In particular, here's how you do it.
**[7:31]** There are four elements in this first tuple.
**[7:34]** The first two will be used to compute X1,
**[7:38]** and the second two would be used to compute Y1.
**[7:42]** In particular, X1 is just going to be S1,
**[7:48]** A1 put together, S1 would be eight numbers,
**[7:53]** the state of the lunar lander,
**[7:55]** A1 would be four numbers,
**[7:57]** the one-hot encoding of whatever action this was,
**[8:00]** and Y1 would be computed using
**[8:02]** the right-hand side of the Bellman equation.
**[8:05]** In particular, the Bellman equation says,
**[8:08]** when you input S1, A1,
**[8:11]** you want Q of S1, A1 to be this right-hand side,
**[8:16]** to be equal to R of S1 plus
**[8:20]** Gamma max over A prime of Q of S1 prime A prime.
**[8:27]** Notice that these two elements of the tuple on the right,
**[8:32]** give you enough information to compute this.
**[8:34]** You know what is R of S1,
**[8:37]** that's the reward you've saved away here,
**[8:39]** plus the discount factor Gamma times max over
**[8:43]** all actions A prime of Q of S prime 1,
**[8:47]** that's the state you got to in this example,
**[8:49]** and then take the max over all possible actions A prime.
**[8:53]** I'm going to call this Y1,
**[8:56]** and when you compute this,
**[8:59]** this will be some number like 12.5,
**[9:02]** or 17, or 0.5, or some other number,
**[9:06]** and we'll save that number here as Y1,
**[9:10]** so that this pair X1,
**[9:12]** Y1 becomes the first trading example
**[9:15]** in this little dataset we're computing.
**[9:17]** Now, you may be wondering, wait,
**[9:20]** where does Q of S prime A prime,
**[9:23]** or Q of S prime 1 A prime come from?
**[9:27]** Well, initially, we don't know what is the Q function,
**[9:31]** but it turns out that when you don't know what is the Q function,
**[9:34]** you can start off with taking
**[9:35]** a totally random guess for what is the Q function,
**[9:38]** and we'll see on the next slide that the algorithm will work nonetheless.
**[9:43]** But in every step,
**[9:44]** Q here is just going to be some guess that will get better over time,
**[9:49]** it turns out, of what is the actual Q function.
**[9:52]** Let's look at the second example.
**[9:53]** If you had a second experience where you're in state S2,
**[9:57]** took action A2, got that reward,
**[9:59]** and then got to that state,
**[10:01]** then we would create a second training example in this dataset,
**[10:04]** X2, where the input is now S2, A2.
**[10:10]** So the first two elements go to computing the input X,
**[10:14]** and then Y2 will be equal to R of S2 plus gamma,
**[10:21]** max of A prime,
**[10:23]** Q of S prime 2 A prime,
**[10:27]** and whatever this number is,
**[10:29]** Y2, we put this over here in our small but growing training set,
**[10:35]** and so on and so forth,
**[10:37]** until maybe you end up with 10,000 training examples
**[10:42]** with these X, Y pairs.
**[10:46]** What we'll see later is that we'll actually take this training set,
**[10:51]** where the Xs are inputs with 12 features,
**[10:55]** and the Ys are just numbers,
**[10:57]** and we'll train a neural network with, say,
**[11:00]** the mean squared error loss to try to predict Y as a function of the input X.
**[11:08]** What I describe here is just one piece of the learning algorithm we'll use.
**[11:13]** Let's put it all together on the next slide and see
**[11:16]** how it all comes together into a single algorithm.
**[11:19]** Let's take a look at what the full algorithm for learning the Q function is like.
**[11:25]** First, we're going to take our neural network and
**[11:28]** initialize all the parameters of the neural network randomly.
**[11:32]** Initially, we have no idea what is the Q function,
**[11:35]** so let's just pick totally random values of the weights,
**[11:38]** and we'll pretend that this neural network is
**[11:41]** our initial random guess for the Q function.
**[11:44]** This is a little bit like when you are training
**[11:47]** linear regression and you initialize all the parameters randomly,
**[11:51]** and then use gradient descent to improve the parameters.
**[11:54]** Initializing randomly for now is fine.
**[11:57]** What's important is whether the algorithm can
**[11:59]** slowly improve the parameters to get to a better estimate.
**[12:03]** Next, we will repeatedly do the following.
**[12:06]** We will take actions in the lunar lander.
**[12:09]** Slide around randomly, take some good actions,
**[12:12]** take some bad actions, it's okay either way.
**[12:14]** But you get lots of these tuples of when it was in some state,
**[12:19]** you took some action A, got a reward R of S,
**[12:21]** and you got to some state S prime.
**[12:23]** What we will do is store the 10,000 most recent examples of these tuples.
**[12:30]** As you run this algorithm,
**[12:32]** you will see many,
**[12:34]** many steps in the lunar lander,
**[12:36]** maybe hundreds of thousands of steps.
**[12:38]** But to make sure we don't end up using excessive computer memory,
**[12:43]** common practice is to just remember the 10,000 most
**[12:47]** recent such tuples that we saw taking actions in the MDP.
**[12:51]** This technique of storing the most recent examples
**[12:56]** only is sometimes called the replay buffer in a reinforcement learning algorithm.
**[13:02]** For now, we're just flying the lunar lander randomly,
**[13:06]** sometimes crashing, sometimes not,
**[13:08]** and getting these tuples as experience for our learning algorithm.
**[13:13]** Occasionally then, we will train the neural network.
**[13:17]** In order to train the neural network, here's what we'll do.
**[13:21]** We'll look at these 10,000 most recent tuples we had saved,
**[13:24]** and create a training set of 10,000 examples.
**[13:30]** Training set needs lots of pairs of X and Y.
**[13:34]** For our training examples,
**[13:36]** X will be the SA from this part of the tuple,
**[13:41]** so it'll be a list of 12 numbers.
**[13:43]** The eight numbers for the state,
**[13:45]** and the four numbers for the one-hot encoding of the action,
**[13:48]** and the target value that we want a neural network to try to predict,
**[13:53]** will be Y equals R of S plus gamma,
**[13:56]** max of A prime,
**[13:57]** Q of S prime A prime.
**[13:59]** How do we get this value of Q?
**[14:01]** Well, initially, is this neural network that we had randomly initialized.
**[14:06]** So it may not be a very good guess,
**[14:07]** but it's a guess.
**[14:09]** After creating these 10,000 training examples,
**[14:12]** we'll have training examples X1,
**[14:14]** Y1 through X 10,000,
**[14:18]** Y 10,000, and so we'll train a neural network,
**[14:24]** and I'm going to call the new neural network Q new,
**[14:27]** such that Q new of SA learns to approximate Y.
**[14:33]** So this is exactly training that neural network to output
**[14:37]** F with parameters W and B to input X,
**[14:41]** to try to approximate the target value Y.
**[14:45]** Now, this neural network should be a slightly better estimates
**[14:50]** of what the Q function or the state action value function should be.
**[14:54]** So what we'll do is we're going to take Q and set it to this new neural network.
**[15:00]** that we had just learned.
**[15:02]** Many of the ideas in this algorithm are due to Min et al.
**[15:07]** And it turns out that if you run this algorithm where
**[15:11]** you start with a really random guess of the Q function,
**[15:15]** then use Bellman's equations to
**[15:17]** repeatedly try to improve the estimates of the Q function.
**[15:21]** Then by doing this over and over,
**[15:23]** taking lots of actions,
**[15:24]** training a model that will improve your guess for the Q function.
**[15:28]** And so for the next model you train,
**[15:31]** you now have a slightly better estimate of what is the Q function.
**[15:35]** And then the next model you train will be even better.
**[15:38]** And when you update Q equals Q new,
**[15:40]** then for the next time you train a model,
**[15:42]** Q of S prime A prime will be an even better estimate.
**[15:46]** And so as you run this algorithm on every iteration,
**[15:50]** Q of S prime A prime hopefully becomes
**[15:52]** an even better estimate of the Q function.
**[15:56]** So that when you run the algorithm long enough,
**[15:58]** this will actually become a pretty good estimate of the true value of Q of S A.
**[16:05]** So that you can then use this to pick hopefully good actions for the MDP.
**[16:10]** The algorithm you just saw is sometimes called the DQN algorithm,
**[16:15]** which stands for Deep Q Network.
**[16:17]** Because you are using deep learning and your network
**[16:20]** to train a model to learn the Q function.
**[16:24]** So hence DQN or Deep Q Network.
**[16:27]** DQ using a neural network.
**[16:29]** And if you use the algorithm as I described it,
**[16:32]** it will kind of work okay on the lunar lander.
**[16:36]** Maybe it'll take a long time to converge,
**[16:38]** maybe it won't land perfectly,
**[16:39]** but it'll sort of work.
**[16:41]** But it turns out that with a couple of refinements to the algorithm,
**[16:44]** it can work much better.
**[16:46]** So in the next few videos,
**[16:47]** let's take a look at some refinements to the algorithm that you just saw.
