---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 2
section: Optimization Algorithms
item_title: Understanding Exponentially Weighted Averages
duration: 10 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/Ud7t0/understanding-exponentially-weighted-averages
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Understanding Exponentially Weighted Averages — Transcript

**[0:00]** In the last video, we talked about exponentially weighted averages.
**[0:03]** This will turn out to be a key component of
**[0:06]** several optimization algorithms that you used to train your neural networks.
**[0:09]** So, in this video, I want to delve a little bit deeper
**[0:12]** into intuitions for what this algorithm is really doing.
**[0:15]** Recall that this is a key equation for implementing exponentially weighted averages.
**[0:21]** And so, if beta equals 0.9 you got the red line.
**[0:24]** If it was much closer to one,
**[0:26]** if it was 0.98, you get the green line.
**[0:29]** And it it's much smaller,
**[0:31]** maybe 0.5, you get the yellow line.
**[0:34]** Let's look a bit more than that to understand how
**[0:37]** this is computing averages of the daily temperature.
**[0:40]** So here's that equation again,
**[0:41]** and let's set beta equals 0.9 and write out a few equations that this corresponds to.
**[0:48]** So whereas, when you're implementing it you have T
**[0:50]** going from zero to one, to two to three,
**[0:54]** increasing values of T. To analyze it,
**[0:56]** I've written it with decreasing values of T. And this goes on.
**[1:00]** So let's take this first equation here,
**[1:03]** and understand what V100 really is.
**[1:06]** So V100 is going to be,
**[1:09]** let me reverse these two terms,
**[1:11]** it's going to be 0.1 times theta 100,
**[1:15]** plus 0.9 times whatever the value was on the previous day.
**[1:19]** Now, but what is V99?
**[1:21]** Well, we'll just plug it in from this equation.
**[1:25]** So this is just going to be 0.1 times theta 99,
**[1:30]** and again I've reversed these two terms,
**[1:33]** plus 0.9 times V98.
**[1:38]** But then what is V98?
**[1:39]** Well, you just get that from here.
**[1:41]** So you can just plug in here,
**[1:44]** 0.1 times theta 98,
**[1:47]** plus 0.9 times V97, and so on.
**[1:52]** And if you multiply all of these terms out,
**[1:54]** you can show that V100 is 0.1 times theta 100 plus.
**[2:00]** Now, let's look at coefficient on theta 99,
**[2:02]** it's going to be 0.1 times 0.9, times theta 99.
**[2:09]** Now, let's look at the coefficient on theta 98,
**[2:12]** there's a 0.1 here times 0.9, times 0.9.
**[2:16]** So if we expand out the Algebra,
**[2:18]** this become 0.1 times 0.9 squared, times theta 98.
**[2:26]** And, if you keep expanding this out,
**[2:28]** you find that this becomes 0.1 times 0.9 cubed,
**[2:32]** theta 97 plus 0.1,
**[2:34]** times 0.9 to the fourth,
**[2:37]** times theta 96, plus dot dot dot.
**[2:41]** So this is really a way to sum and that's a weighted average of theta 100,
**[2:47]** which is the current days temperature and we're looking for
**[2:49]** a perspective of V100 which you calculate on the 100th day of the year.
**[2:53]** But those are sum of your theta 100,
**[2:56]** theta 99, theta 98,
**[2:58]** theta 97, theta 96, and so on.
**[3:02]** So one way to draw this in pictures would be if,
**[3:05]** let's say we have some number of days of temperature.
**[3:08]** So this is theta and this is T. So theta 100 will be sum value,
**[3:14]** then theta 99 will be sum value,
**[3:17]** theta 98, so these are,
**[3:19]** so this is T equals 100,
**[3:21]** 99, 98, and so on,
**[3:23]** ratio of sum number of days of temperature.
**[3:26]** And what we have is then an exponentially decaying function.
**[3:31]** So starting from 0.1 to 0.9,
**[3:37]** times 0.1 to 0.9 squared,
**[3:41]** times 0.1, to and so on.
**[3:44]** So you have this exponentially decaying function.
**[3:47]** And the way you compute V100,
**[3:50]** is you take the element wise product between these two functions and sum it up.
**[3:55]** So you take this value,
**[3:56]** theta 100 times 0.1,
**[3:59]** times this value of theta 99 times 0.1 times 0.9,
**[4:05]** that's the second term and so on.
**[4:07]** So it's really taking the daily temperature,
**[4:10]** multiply with this exponentially decaying function, and then summing it up.
**[4:14]** And this becomes your V100.
**[4:17]** It turns out that,
**[4:19]** up to details that are for later.
**[4:21]** But all of these coefficients,
**[4:22]** add up to one or add up to very close to one,
**[4:27]** up to a detail called bias correction which we'll talk about in the next video.
**[4:31]** But because of that, this really is an exponentially weighted average.
**[4:35]** And finally, you might wonder,
**[4:37]** how many days temperature is this averaging over.
**[4:41]** Well, it turns out that 0.9 to the power of 10,
**[4:46]** is about 0.35 and this turns out to be about one over E,
**[4:52]** one of the base of natural algorithms.
**[4:54]** And, more generally, if you have one minus epsilon,
**[4:59]** so in this example,
**[5:00]** epsilon would be 0.1,
**[5:01]** so if this was 0.9, then one minus epsilon to the one over epsilon.
**[5:07]** This is about one over E,
**[5:08]** this about 0.34, 0.35.
**[5:12]** And so, in other words,
**[5:14]** it takes about 10 days for the height of this to
**[5:19]** decay to around 1/3 already one over E of the peak.
**[5:24]** So it's because of this,
**[5:25]** that when beta equals 0.9, we say that,
**[5:31]** this is as if you're computing
**[5:35]** an exponentially weighted average that focuses on just the last 10 days temperature.
**[5:40]** Because it's after 10 days that the weight decays
**[5:43]** to less than about a third of the weight of the current day.
**[5:48]** Whereas, in contrast, if beta was equal to 0.98,
**[5:53]** then, well, what do you need 0.98 to the power of in order for this to really small?
**[5:59]** Turns out that 0.98 to the power of 50 will be approximately
**[6:04]** equal to one over E. So the way to be pretty
**[6:06]** big will be bigger than one over E for the first 50 days,
**[6:09]** and then they'll decay quite rapidly over that.
**[6:11]** So intuitively, this is the hard and fast thing,
**[6:14]** you can think of this as averaging over about 50 days temperature.
**[6:18]** Because, in this example,
**[6:20]** to use the notation here on the left,
**[6:22]** it's as if epsilon is equal to 0.02,
**[6:25]** so one over epsilon is 50.
**[6:27]** And this, by the way, is how we got the formula,
**[6:30]** that we're averaging over one over one minus beta or so days.
**[6:35]** Right here, epsilon replace a row of 1 minus beta.
**[6:39]** It tells you, up to some constant roughly how
**[6:42]** many days temperature you should think of this as averaging over.
**[6:45]** But this is just a rule of thumb for how to think about it,
**[6:48]** and it isn't a formal mathematical statement.
**[6:51]** Finally, let's talk about how you actually implement this.
**[6:54]** Recall that we start over V0 initialized as zero,
**[6:57]** then compute V one on the first day,
**[6:59]** V2, and so on.
**[7:01]** Now, to explain the algorithm,
**[7:02]** it was useful to write down V0,
**[7:05]** V1, V2, and so on as distinct variables.
**[7:09]** But if you're implementing this in practice,
**[7:11]** this is what you do: you initialize V to be called to zero,
**[7:15]** and then on day one,
**[7:17]** you would set V equals beta,
**[7:21]** times V, plus one minus beta, times theta one.
**[7:25]** And then on the next day, you add update V,
**[7:27]** to be called to beta V,
**[7:31]** plus 1 minus beta,
**[7:33]** theta 2, and so on.
**[7:35]** And some of it uses notation V subscript theta to denote
**[7:41]** that V is computing this exponentially weighted average of the parameter theta.
**[7:47]** So just to say this again but for a new format,
**[7:49]** you set V theta equals zero,
**[7:52]** and then, repeatedly, have one each day,
**[7:55]** you would get next theta T, and then set to V,
**[8:02]** theta gets updated as beta,
**[8:05]** times the old value of V theta,
**[8:07]** plus one minus beta,
**[8:08]** times the current value of V theta.
**[8:12]** So one of the advantages of this exponentially weighted average formula,
**[8:15]** is that it takes very little memory.
**[8:17]** You just need to keep just one row number in computer memory,
**[8:21]** and you keep on overwriting it with this formula based on the latest values that you got.
**[8:26]** And it's really this reason, the efficiency,
**[8:29]** it just takes up one line of code basically and just
**[8:33]** storage and memory for
**[8:34]** a single row number to compute this exponentially weighted average.
**[8:38]** It's really not the best way,
**[8:40]** not the most accurate way to compute an average.
**[8:42]** If you were to compute a moving window,
**[8:44]** where you explicitly sum over the last 10 days,
**[8:47]** the last 50 days temperature and just divide by 10 or divide by 50,
**[8:51]** that usually gives you a better estimate.
**[8:53]** But the disadvantage of that,
**[8:55]** of explicitly keeping all the temperatures around and
**[8:57]** sum of the last 10 days is it requires more memory,
**[9:00]** and it's just more complicated to implement and is computationally more expensive.
**[9:03]** So for things, we'll see some examples on the next few videos,
**[9:07]** where you need to compute averages of a lot of variables.
**[9:12]** This is a very efficient way to do so both from computation
**[9:15]** and memory efficiency point of view which is why it's used in a lot of machine learning.
**[9:19]** Not to mention that there's just one line of code which is, maybe, another advantage.
**[9:24]** So, now, you know how to implement exponentially weighted averages.
**[9:28]** There's one more technical detail that's worth for you knowing
**[9:30]** about called bias correction.
**[9:32]** Let's see that in the next video, and then after that,
**[9:35]** you will use this to build
**[9:37]** a better optimization algorithm than the straight forward create
