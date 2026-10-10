---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 2
section: Back Propagation (Optional)
item_title: What is a derivative? (Optional)
duration: 23 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/i9Dqr/what-is-a-derivative-optional
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# What is a derivative? (Optional) — Transcript

**[0:01]** You've seen how in TensorFlow you can specify
**[0:05]** a neural network architecture to
**[0:07]** compute the output y as a function of the input x,
**[0:10]** and also specify a cost function,
**[0:13]** and TensorFlow will then
**[0:15]** automatically use back propagation to compute
**[0:18]** derivatives and use gradient descent
**[0:21]** or Adam to train the parameters of a neural network.
**[0:24]** The backpropagation algorithm, which computes
**[0:27]** derivatives of your cost function
**[0:29]** with respect to the parameters,
**[0:31]** is a key algorithm in neural network learning.
**[0:34]** But how does it actually work?
**[0:36]** In this and in the next few optional videos,
**[0:40]** we'll try to take a look at
**[0:41]** how backpropagation computes derivatives.
**[0:44]** These videos are completely optional and they do
**[0:47]** go just a little bit into calculus.
**[0:49]** If you're already familiar with
**[0:51]** calculus I hope you enjoy these videos,
**[0:53]** but if not, it's totally fine.
**[0:55]** We'll build up from the very basics
**[0:57]** of calculus to try to make sure you have
**[1:00]** all the intuition you need to
**[1:01]** understand how backpropagation works. Let's take a look.
**[1:05]** I'm going to use a simplified cost function,
**[1:09]** J of w equals w squared.
**[1:13]** The cost function is a function of
**[1:15]** the parameters w and say,
**[1:18]** b and for this simplified cost function
**[1:21]** let's just pretend J of w equals w squared.
**[1:25]** I'm going to ignore b for this example.
**[1:28]** Let's say the value of the parameter w is equal to 3.
**[1:33]** J of w will be equal to 9,
**[1:36]** w squared of 3 squared.
**[1:39]** Now if we were to increase w by a tiny amount,
**[1:46]** say Epsilon, which I'm going to set to 0.001.
**[1:52]** How does the value of J of w change?
**[1:57]** If we increase w by 0.001 then
**[2:01]** w becomes 3 plus 0.001, so it's 3.001.
**[2:07]** J of w,
**[2:08]** which is w squared,
**[2:10]** which we defined above,
**[2:11]** is now this 3.001 squared, which is 9.006001.
**[2:17]** What we see is that if w goes up by 0.001,
**[2:23]** I'm going to use this up arrow here to
**[2:26]** denote w goes up by 0.001,
**[2:29]** where 0.001 is this small value Epsilon.
**[2:34]** Then J of w roughly goes
**[2:38]** up by 6 times as much, 6 times 0.001.
**[2:43]** This isn't quite exactly.
**[2:46]** It actually goes up not to 9.006 but 9.006001.
**[2:51]** But it turns out that if
**[2:53]** Epsilon where infinitesimally small,
**[2:55]** and by infinitesimally small I mean very small.
**[2:59]** Epsilon is pretty small,
**[3:01]** but it's not infinitesimally small.
**[3:03]** If Epsilon was 0.00000,
**[3:05]** lots of zeros followed by one,
**[3:07]** then this becomes more and more accurate.
**[3:09]** In this example what we see is that
**[3:12]** if w goes up by Epsilon then
**[3:14]** J goes up roughly by 6 times Epsilon.
**[3:20]** In calculus what we would say is that
**[3:24]** the derivative of J of w with respect to w is equal to 6.
**[3:31]** All this means is if w goes up by
**[3:35]** a tiny little amount J of w goes up six times as much.
**[3:40]** What if Epsilon were to take on different value?
**[3:42]** What if Epsilon were 0.002.
**[3:45]** In this case w would be 3 plus 0.002,
**[3:51]** and w squared becomes 3.002 squared, which is 9.012004.
**[4:00]** In this case what we conclude is that if w goes up by
**[4:04]** 0.002 then J of w goes up by roughly 6 times 0.002.
**[4:13]** It goes up roughly to 9.012,
**[4:18]** and this 0.012 is roughly 6 times 0.002.
**[4:26]** That again, is a little bit off.
**[4:28]** This is extra 0.00004 here,
**[4:31]** because Epsilon is not quite infinitesimally small.
**[4:35]** Once again, we see this six to one ratio
**[4:40]** between how much w goes
**[4:42]** up versus how much J of w goes up.
**[4:45]** That's why the derivative of J of w
**[4:48]** with respect to w is equal to six.
**[4:51]** A small Epsilon is the more accurate this becomes.
**[4:55]** By the way, feel free to pause the video and try
**[4:58]** this calculation now yourself
**[5:00]** with other values of Epsilon.
**[5:02]** The key is that so long as Epsilon
**[5:04]** is pretty small the ratio by
**[5:07]** which J of w goes up versus the amount by
**[5:09]** which w goes up should be 6-1.
**[5:12]** Feel free to try it out yourself
**[5:14]** with other values of Epsilon,
**[5:15]** then check if this really holds true.
**[5:17]** This leads us to an informal
**[5:19]** definition of the derivative,
**[5:21]** which is that whenever w
**[5:23]** goes up by a tiny amount Epsilon that
**[5:26]** causes J of w to go up by k times Epsilon.
**[5:32]** In our example just now k was equal to six.
**[5:36]** Then we say that
**[5:37]** the derivative of J of w with respect to w is equal to k,
**[5:42]** which was equal to 6 in the example just now.
**[5:46]** You might remember when implementing
**[5:48]** gradient descent you will
**[5:50]** repeatedly use this rule to update the parameter w J,
**[5:56]** where as usual Alpha is the learning rate.
**[5:59]** What is gradient descent do?
**[6:03]** Notice that if the derivative is small,
**[6:06]** then this updates that will make
**[6:08]** a small update to the parameter W_j,
**[6:11]** whereas if this derivative term is large,
**[6:14]** this will result in a big change to the parameter W_j.
**[6:19]** This makes sense because this is
**[6:22]** essentially saying that if the derivative is small,
**[6:26]** this means that changing w
**[6:28]** doesn't make a big difference to the value
**[6:31]** of j and so let's
**[6:33]** not bother to make a huge change to W_j.
**[6:36]** But if the derivative is large,
**[6:38]** that means that even a tiny change
**[6:41]** the W_j can make a big difference in
**[6:44]** how much you can change or decrease
**[6:46]** the cost function j of w. In that case,
**[6:49]** let's make a bigger change to W_j,
**[6:52]** because doing so will actually make
**[6:54]** a big difference to how
**[6:56]** much we can reduce the cost function J.
**[6:58]** Let's take a look at a few more examples of derivatives.
**[7:04]** What you saw in the example just now
**[7:06]** was that if w equals 3,
**[7:08]** and j of w equals w squared equals 9,
**[7:12]** then if w goes up by Epsilon by 0.01,
**[7:16]** then j of w becomes j of 3.01 is now 9.006001.
**[7:26]** Or in other words,
**[7:28]** j has gone up by about 0.006,
**[7:31]** which is 6 times 0.001 or 6 times Epsilon,
**[7:37]** which is why the derivative
**[7:39]** of w with respect to W is equal to 6.
**[7:45]** Let's look at what the derivative will be
**[7:47]** for other values of w,
**[7:48]** take w equals 2.
**[7:51]** In this case, j of w is,
**[7:54]** w squared is now equal to 4,
**[7:56]** and if w goes up by 0.001,
**[7:59]** then J of w becomes j of 2.001,
**[8:03]** which is equal to this 4.004001 and
**[8:09]** so j of w has gone up from four to this value over here,
**[8:14]** which is roughly four times Epsilon bigger than four,
**[8:20]** which is why now the derivative is four.
**[8:24]** Because w going up by Epsilon
**[8:27]** has caused j of w to go up four times as much.
**[8:31]** Again, there's extra 0.001 is because it's not quite
**[8:34]** accurate because Epsilon is an infinitesimally small.
**[8:37]** Or let's look at another example.
**[8:40]** What if w were equal to negative 3?
**[8:43]** J of w which is w squared,
**[8:45]** is still equal to 9 because negative 3 squared is 9.
**[8:49]** If w was to go up by Epsilon again,
**[8:52]** then you now have w equals negative 2.999,
**[8:58]** so that's j of negative 2.999.
**[9:00]** The square of negative 2.999 is equal to this 8.994001,
**[9:05]** because w is negative 3 plus 0.001.
**[9:11]** Notice here, j of w has gone down by about 0.006,
**[9:18]** which is six times Epsilon.
**[9:22]** What we have in this example is that j starts off as 9,
**[9:28]** but it has now gone down.
**[9:30]** Notice this down arrow here [inaudible] arrow by
**[9:33]** 6 times Epsilon or
**[9:37]** equivalently it has gone up by negative 6 times Epsilon.
**[9:42]** That's why the derivative in this case is
**[9:45]** equal to negative 6.
**[9:48]** Because w going up by Epsilon causes j
**[9:53]** of w to go up by
**[9:55]** negative 6 times Epsilon when Epsilon is small.
**[9:58]** Another way to visualize this is
**[10:02]** to plot the function J of w,
**[10:06]** so that the horizontal axis is w and this is J of w,
**[10:10]** then when w is equal to 3,
**[10:12]** J of w is equal to 9.
**[10:15]** When it's negative 3 it's also equal to 9,
**[10:18]** and when it is 2,
**[10:20]** J of w is equal to 4.
**[10:22]** Let me make an observation that may
**[10:25]** be relevant if you've taken a calculus class before.
**[10:28]** But if you haven't, what I say in
**[10:30]** the next 60 seconds
**[10:33]** may not make sense, but don't worry about it.
**[10:34]** You will need to understand it to
**[10:36]** fully follow the rest of these videos.
**[10:38]** If you've taken a class in calculus at some point,
**[10:41]** you may recognize that the derivatives corresponds to
**[10:46]** the slope of a line that just
**[10:48]** touches the function J of w at this point,
**[10:51]** say where w equals 3.
**[10:54]** The slope of this line at this point,
**[10:57]** and the slope is this height over
**[10:59]** this width turns out to be equal to 6 when w equals 3,
**[11:03]** the slope of this line turns out to be
**[11:06]** 4 when w equals 2 and the slope of
**[11:08]** this line turns out to be negative
**[11:10]** 6 when w equals negative 3.
**[11:14]** It turns out in calculus,
**[11:15]** the slope of these lines
**[11:17]** correspond to the derivative of the function.
**[11:19]** But if you haven't taken a calculus class before and
**[11:22]** haven't seen this slope concept
**[11:25]** before, don't worry about it.
**[11:26]** Now, there's one last observation
**[11:29]** I want to make before moving on,
**[11:30]** which is that you see in all three of these examples,
**[11:35]** J of w is the same function,
**[11:37]** J of w is equal to w squared.
**[11:40]** But the derivative of J of w depends on w,
**[11:45]** when w is three,
**[11:46]** the derivative is six.
**[11:47]** When w is two,
**[11:48]** the derivative is four.
**[11:50]** When w is negative 3,
**[11:51]** the derivative is negative 6.
**[11:54]** It turns out that if you are familiar with calculus,
**[11:58]** and again, it's totally fine if you're not,
**[12:00]** calculus can allow us to calculate the derivative
**[12:05]** of J of w in respect to w as 2 times w. In a little bit,
**[12:10]** I'll show you how you can use Python to compute
**[12:14]** these derivatives yourself using
**[12:17]** a nifty Python package called SymPy.
**[12:21]** But because calculus tells us that
**[12:24]** the derivative of w squared J of w is 2w,
**[12:28]** that's why the derivative when w is three is 2 times
**[12:33]** 3 or when is two is 2 times 2,
**[12:40]** or when is negative 3 is 2 times negative 3 because
**[12:45]** this value of w times
**[12:48]** 2 turns out to give you the derivative.
**[12:51]** Let's go through just a few more
**[12:53]** examples before we wrap up.
**[12:55]** For these examples, I'm going to set w equals 2.
**[13:00]** You saw on the last slide,
**[13:02]** if J of w is w squared,
**[13:04]** then the derivative I said
**[13:07]** would be 2 times w, which was 4.
**[13:11]** If w goes up by 0.01,
**[13:14]** this being Epsilon,
**[13:15]** J of w becomes this so roughly J of
**[13:18]** w goes up by 4 times Epsilon.
**[13:21]** Let's look at a few other functions.
**[13:24]** What if J of w is equal to w cubed?
**[13:29]** In this case, w cubed,
**[13:31]** 2 cubed would be equal to 8,
**[13:33]** or what if J of w is just equal to w?
**[13:37]** Here, w will be equal to 2.
**[13:40]** Or what if J of w was 1 over w?
**[13:43]** In this case, 1 over w,
**[13:45]** 1 over 2 would be 1/2 or 0.5.
**[13:49]** What is the derivative of J of w with
**[13:52]** respect to w when the cost function J
**[13:56]** of w is either w cubed or w or 1 over w. Let me
**[14:02]** show you how you can compute these derivatives yourself
**[14:04]** using a library and package called SymPy.
**[14:09]** Let me first import SymPy.
**[14:13]** What I'm going to do is tell
**[14:16]** SymPy that I'm going to use J
**[14:18]** and w as symbols for computing derivatives.
**[14:24]** For our first example,
**[14:27]** we had the cost function J was equal to w squared.
**[14:32]** Notice how SymPy actually renders it in
**[14:35]** this nifty font here as well.
**[14:38]** If we were to use SymPy to take
**[14:40]** the derivative of J with respect to w,
**[14:43]** we should do as follows.
**[14:45]** You see that SymPy tells you this derivative is 2w.
**[14:48]** Let me actually choose a variable, dJ, dw,
**[14:53]** we set that to be equal to this,
**[14:54]** just type it again here. Print it out.
**[14:58]** There's 2w. If you want to
**[15:02]** plug in the value of w
**[15:04]** into this expression to evaluate it,
**[15:06]** you can do the derivative.subs w, 2.
**[15:10]** This means plug-in a value of w to
**[15:13]** be equal to 2 into this expression and evaluate it.
**[15:16]** That gives you the value of four,
**[15:18]** which is why when w equals to 2,
**[15:21]** we saw the derivative of J was equal to 4.
**[15:26]** Let's look at some other examples.
**[15:28]** What if J was w cubed?
**[15:32]** Then the derivative becomes 3 times w squared.
**[15:38]** It turns out from calculus,
**[15:39]** and this is what SymPy is calculating for us,
**[15:42]** if J is w cubed,
**[15:44]** then the derivative of J with respect to w is 3w squared.
**[15:49]** Depending on what w is,
**[15:51]** the value of the derivative changes as well.
**[15:55]** We can plug in if w equal to 2,
**[15:58]** you get 12 in this case.
**[16:00]** Or what if it was J equal to w?
**[16:05]** In this case, the derivative is just equal to 1.
**[16:08]** Or the final example we have
**[16:11]** was what if J equals 1 over w?
**[16:13]** In this case, the derivative turns out to be
**[16:17]** negative 1 over w squared.
**[16:20]** This is negative 1 over 4.
**[16:22]** What I'm going to do
**[16:24]** is take the derivatives we have worked out.
**[16:27]** Remember for w squared,
**[16:29]** it was 2w,
**[16:31]** for w cubed, it was 3w squared.
**[16:36]** For w is just 1 and
**[16:38]** 1 over w it's negative 1 over w squared.
**[16:42]** Let's copy this back to our other slide.
**[16:45]** What SymPy or really calculus showed
**[16:48]** us is if J of w is w cubed,
**[16:51]** the derivative is 3w squared,
**[16:53]** which is equal to 12 when w equals 2,
**[16:56]** when J of w equals w,
**[16:58]** the derivative is just equal to 1.
**[17:00]** When J of w is 1 over w is negative 1 over w squared,
**[17:03]** which is negative 1/4 when w equals 2.
**[17:08]** Let's start. We'll check if these expressions
**[17:10]** that we got from SymPy are correct.
**[17:13]** Let's try increasing w by Epsilon,
**[17:16]** in this case J of w. Feel free to
**[17:20]** pause the video and check this math
**[17:22]** on your own calculator if you want.
**[17:24]** But in this case, J of w to 0.001 cubed becomes this.
**[17:32]** So J has gone up from 8 to 8.012 roughly.
**[17:39]** It's gone up by roughly 12 times Epsilon.
**[17:43]** Thus the derivative is indeed 12.
**[17:46]** Or if J of w equals w,
**[17:50]** then if w increase by Epsilon, then J of w,
**[17:53]** which is just w, is now 2.001.
**[17:57]** So it's gone up by 0.01,
**[18:00]** which is exactly the value of Epsilon.
**[18:02]** So J of w has gone up by 1 times Epsilon.
**[18:05]** The derivative is indeed equal to 1.
**[18:09]** Notice that here, this is actually,
**[18:11]** exactly Epsilon even though
**[18:13]** Epsilon is infinitesimally small.
**[18:16]** On our last example,
**[18:18]** if J of w equals 1/w,
**[18:20]** if w goes up by Epsilon,
**[18:23]** then w is 1/2.001,
**[18:28]** then it turns out J of w is approximately
**[18:32]** 4.9975 with some extra digits that are truncated.
**[18:36]** But this turns out to be 0.5 minus 0.00025.
**[18:43]** J of w has started off at 0.5
**[18:47]** and it's gone down by 0.00025.
**[18:52]** This 0.00025, it is 0.25 times Epsilon.
**[18:59]** It's gone down by this amount or it's
**[19:02]** gone up by negative 0.25
**[19:05]** times Epsilon because negative
**[19:07]** 0.25 times Epsilon is equal to this sum over here.
**[19:11]** We see that if w goes up by Epsilon,
**[19:14]** J of w goes up by
**[19:16]** negative 1/4 or negative 0.25 times Epsilon,
**[19:21]** which is why the derivative in this case is negative 1/4.
**[19:26]** I hope that with these examples you have a sense of what
**[19:29]** the derivative with respect to w of J of w means.
**[19:35]** It just is if w goes up by Epsilon,
**[19:40]** how much does J of w goes up by
**[19:43]** some constant k times Epsilon.
**[19:46]** This constant k is the derivative.
**[19:49]** The value of k will depend both
**[19:51]** on what is the function J of w,
**[19:54]** as well as what is the value of
**[19:56]** w. Before we wrap up this video,
**[19:58]** I want to briefly touch on the notation used to
**[20:01]** write derivatives that you may see in other texts.
**[20:05]** Which is that if J of w is
**[20:08]** a function of a single variable, say w,
**[20:12]** then mathematicians will sometimes write the derivative
**[20:15]** as d/dw of J of w. Notice here
**[20:18]** this notation is using
**[20:20]** the lowercase letter d. Whereas in contrast,
**[20:25]** if J is a function of more than one variable,
**[20:30]** then mathematicians will sometimes use
**[20:33]** this squiggly alternative d
**[20:36]** to denote the derivative of J with
**[20:40]** respect to one of the parameters w_i.
**[20:43]** To my mind, this notation
**[20:45]** distinguishing between this regular letter
**[20:48]** d and this stylize calculus derivative symbol d,
**[20:53]** it makes little sense to me to
**[20:55]** make this distinction and this notation to
**[20:57]** my mind over complicates
**[20:59]** calculus and derive this notation.
**[21:02]** But for historical reasons,
**[21:06]** calculus text will use
**[21:08]** these two different notations depending on whether J
**[21:10]** is a function of a single variable
**[21:13]** or a function of multiple variables.
**[21:16]** But I think for practical purposes,
**[21:18]** this notational convention,
**[21:20]** it tends to just over-complicate things, I think,
**[21:23]** in a way that I don't think is actually necessary.
**[21:27]** For this class,
**[21:29]** I'm just going to use this notation everywhere,
**[21:33]** even when there's just a single variable.
**[21:36]** In fact, for most of our applications,
**[21:39]** the function J it
**[21:41]** is a function of more than one variable.
**[21:44]** So this other notation,
**[21:46]** which is sometimes called the
**[21:47]** partial derivative notation,
**[21:49]** this is actually the correct notation almost
**[21:52]** all the time because J
**[21:53]** usually has more than one variable.
**[21:55]** But I hope that using this notation
**[21:57]** throughout these lectures that
**[21:58]** simplifies the presentation and makes
**[22:01]** derivatives little bit easier to understand.
**[22:03]** In fact, this notation is the one you've
**[22:06]** been seeing in the videos leading up to now.
**[22:09]** For conciseness, instead of writing
**[22:11]** out this full expression here,
**[22:14]** sometimes you also see it shortened
**[22:16]** as derivative or partial derivative
**[22:19]** of J with respect to w_i or written like this.
**[22:23]** These are just simplified
**[22:27]** abbreviated forms of this expression over here.
**[22:31]** I hope that gives you a sense of what are derivatives.
**[22:35]** It's just if w goes up by a little bit,
**[22:37]** by Epsilon, how much does
**[22:39]** J of w change as a consequence.
**[22:42]** Next, let's take a look at how you can
**[22:45]** compute derivatives in a neural network.
**[22:48]** To do so, we need to take a look at something
**[22:51]** called a computation graph.
**[22:53]** Let's go take a look at that in the next video.
