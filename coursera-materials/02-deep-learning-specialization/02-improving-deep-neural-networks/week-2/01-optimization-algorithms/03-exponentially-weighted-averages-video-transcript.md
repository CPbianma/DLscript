---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 2
section: Optimization Algorithms
item_title: Exponentially Weighted Averages
duration: 6 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/duStO/exponentially-weighted-averages
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Exponentially Weighted Averages — Transcript

**[0:00]** I want to show you a few optimization algorithms.
**[0:02]** They are faster than gradient descent.
**[0:04]** In order to understand those algorithms,
**[0:06]** you need to be able they use something called exponentially weighted averages.
**[0:11]** Also called exponentially weighted moving averages in statistics.
**[0:15]** Let's first talk about that,
**[0:17]** and then we'll use this to build up to more sophisticated optimization algorithms.
**[0:21]** So, even though I now live in the United States,
**[0:23]** I was born in London.
**[0:25]** So, for this example I got the daily temperature from London from last year.
**[0:31]** So, on January 1,
**[0:32]** temperature was 40 degrees Fahrenheit.
**[0:35]** Now, I know most of the world uses a Celsius system,
**[0:37]** but I guess I live in United States which uses Fahrenheit.
**[0:41]** So that's four degrees Celsius.
**[0:43]** And on January 2,
**[0:46]** it was nine degrees Celsius and so on.
**[0:48]** And then about halfway through the year,
**[0:50]** a year has 365 days so, that would be,
**[0:52]** sometime day number 180 will be sometime in late May, I guess.
**[0:56]** It was 60 degrees Fahrenheit which is 15 degrees Celsius, and so on.
**[1:00]** So, it start to get warmer, towards summer and it was colder in January.
**[1:05]** So, you plot the data you end up with this.
**[1:08]** Where day one being sometime in January, that you know,
**[1:12]** being the, beginning of summer,
**[1:13]** and that's the end of the year,
**[1:15]** kind of late December.
**[1:17]** So, this would be January, January 1,
**[1:20]** is the middle of the year approaching summer,
**[1:21]** and this would be the data from the end of the year.
**[1:24]** So, this data looks a little bit noisy and if you want to compute the trends,
**[1:29]** the local average or a moving average of the temperature,
**[1:35]** here's what you can do.
**[1:37]** Let's initialize V zero equals zero.
**[1:41]** And then, on every day,
**[1:43]** we're going to average it with a weight of 0.9 times whatever appears as value,
**[1:49]** plus 0.1 times that day temperature.
**[1:53]** So, theta one here would be the temperature from the first day.
**[1:57]** And on the second day, we're again going to take a weighted average.
**[2:01]** 0.9 times the previous value plus 0.1 times today's temperature and so on.
**[2:08]** Day two plus 0.1 times theta three and so on.
**[2:12]** And the more general formula is V on a given day is 0.9 times V from the previous day,
**[2:20]** plus 0.1 times the temperature of that day.
**[2:25]** So, if you compute this and plot it in red,
**[2:28]** this is what you get.
**[2:29]** You get a moving average of what's called an
**[2:32]** exponentially weighted average of the daily temperature.
**[2:36]** So, let's look at the equation we had from the previous slide,
**[2:39]** it was VT equals,
**[2:42]** previously we had 0.9.
**[2:44]** We'll now turn that to prime to beta,
**[2:46]** beta times VT minus one plus and it previously,
**[2:51]** was 0.1, I'm going to turn that into one minus beta times theta T,
**[2:56]** so, previously you had beta equals 0.9.
**[3:00]** It turns out that for reasons we are going to later,
**[3:03]** when you compute this you can think of VT as approximately averaging over,
**[3:13]** something like one over one minus beta, day's temperature.
**[3:21]** So, for example when beta goes 0.9 you could think of
**[3:26]** this as averaging over the last 10 days temperature.
**[3:32]** And that was the red line.
**[3:36]** Now, let's try something else.
**[3:37]** Let's set beta to be very close to one,
**[3:39]** let's say it's 0.98.
**[3:41]** Then, if you look at 1/1 minus 0.98,
**[3:46]** this is equal to 50.
**[3:48]** So, this is, you know, think of this as averaging over roughly,
**[3:51]** the last 50 days temperature.
**[3:54]** And if you plot that you get this green line.
**[3:58]** So, notice a couple of things with this very high value of beta.
**[4:01]** The plot you get is much smoother because you're now
**[4:04]** averaging over more days of temperature.
**[4:07]** So, the curve is just, you know,
**[4:08]** less wavy is now smoother,
**[4:10]** but on the flip side the curve has now shifted further to
**[4:14]** the right because you're now averaging over a much larger window of temperatures.
**[4:18]** And by averaging over a larger window,
**[4:21]** this formula, this exponentially weighted average formula.
**[4:24]** It adapts more slowly,
**[4:25]** when the temperature changes.
**[4:27]** So, there's just a bit more latency.
**[4:29]** And the reason for that is when Beta 0.98 then it's
**[4:33]** giving a lot of weight to the previous value and a much smaller weight just 0.02,
**[4:38]** to whatever you're seeing right now.
**[4:40]** So, when the temperature changes,
**[4:42]** when temperature goes up or down,
**[4:43]** there's exponentially weighted average.
**[4:45]** Just adapts more slowly when beta is so large.
**[4:48]** Now, let's try another value.
**[4:51]** If you set beta to another extreme,
**[4:53]** let's say it is 0.5,
**[4:54]** then this by the formula we have on the right.
**[4:58]** This is something like averaging over just two days temperature,
**[5:03]** and you plot that you get this yellow line.
**[5:06]** And by averaging only over two days temperature,
**[5:09]** you have a much, as if you're averaging over much shorter window.
**[5:12]** So, you're much more noisy,
**[5:13]** much more susceptible to outliers.
**[5:15]** But this adapts much more quickly to what the temperature changes.
**[5:19]** So, this formula is highly implemented, exponentially weighted average.
**[5:24]** Again, it's called an exponentially weighted,
**[5:26]** moving average in the statistics literature.
**[5:28]** We're going to call it exponentially weighted average for short and
**[5:32]** by varying this parameter or later we'll see
**[5:36]** such a hyper parameter if you're learning algorithm you can get
**[5:39]** slightly different effects and there will usually be
**[5:41]** some value in between that works best.
**[5:44]** That gives you the red curve which you know maybe looks like
**[5:46]** a beta average of the temperature than either the green or the yellow curve.
**[5:50]** You now know the basics of how to compute exponentially weighted averages.
**[5:54]** In the next video, let's get a bit more intuition about what it's doing.
