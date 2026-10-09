---
type: video-transcript
specialization: Deep Learning Specialization
course: Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization
week: 2
section: Optimization Algorithms
item_title: Bias Correction in Exponentially Weighted Averages
duration: 4 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/XjuhD/bias-correction-in-exponentially-weighted-averages
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Bias Correction in Exponentially Weighted Averages — Transcript

**[0:00]** You've learned how to implement
**[0:01]** exponentially weighted averages.
**[0:03]** There's one technical detail called bias correction that
**[0:06]** can make your computation of
**[0:08]** these averages more accurate.
**[0:10]** Let's see how that works.
**[0:11]** In the previous video,
**[0:12]** you saw this figure for Beta equals 0.9,
**[0:15]** this figure for a Beta equals 0.98.
**[0:19]** But it turns out that if you
**[0:20]** implement the formula as written here,
**[0:23]** you won't actually get
**[0:25]** the green curve when Beta equals 0.98,
**[0:29]** you actually get the purple curve here.
**[0:32]** You notice that the purple curve starts off really low.
**[0:36]** Let's see how to fix that.
**[0:38]** When implementing a moving average,
**[0:40]** you initialize it with V_0 equals 0,
**[0:42]** and then V_1 is equal to 0.98 V_0 plus 0.02 Theta 1.
**[0:50]** But V_0 is equal to 0,
**[0:52]** so that term just goes away.
**[0:53]** So V_1 is just 0.02 times Theta 1.
**[0:57]** That's why if the first day's temperature is,
**[1:01]** say, 40 degrees Fahrenheit,
**[1:03]** then V_1 will be 0.02 times 40,
**[1:07]** which is 0.8, so you get a much lower value down here.
**[1:11]** That's not a very good estimate
**[1:12]** of the first day's temperature.
**[1:14]** V_2 will be 0.98 times V_1 plus 0.02 times Theta 2.
**[1:21]** If you plug in V_1,
**[1:23]** which is this down here,
**[1:26]** and multiply it out,
**[1:27]** then you find that V_2 is actually equal to
**[1:30]** 0.98 times 0.02 times Theta 1 plus
**[1:35]** 0.02 times Theta 2 and that's
**[1:38]** 0.0196 Theta 1 plus 0.02 Theta 2.
**[1:46]** Assuming Theta 1 and Theta 2 are positive numbers.
**[1:49]** When you compute this,
**[1:51]** V_2 will be much less than Theta 1 or Theta 2,
**[1:54]** so V_2 isn't a very good estimate
**[1:56]** of the first two days temperature of the year.
**[1:59]** It turns out that there's a way to
**[2:01]** modify this estimate that makes it much better,
**[2:03]** that makes it more accurate,
**[2:04]** especially during this initial phase of your estimate.
**[2:08]** Instead of taking V_t, take V_t divided
**[2:12]** by 1 minus Beta to the power of t,
**[2:16]** where t is the current day that you're on.
**[2:19]** Let's take a concrete example.
**[2:21]** When t is equal to 2,
**[2:22]** 1 minus Beta to the power of t is 1 minus 0.98 squared.
**[2:31]** It turns out that is 0.0396.
**[2:37]** Your estimate of the temperature on day 2
**[2:41]** becomes V_2 divided by 0.0396,
**[2:46]** and this is going to be 0.0196
**[2:50]** times Theta 1 plus 0.02 Theta 2.
**[2:53]** You notice that these two things
**[2:55]** act as denominator, 0.0396.
**[2:59]** This becomes a weighted average of Theta 1 and
**[3:02]** Theta 2 and this removes this bias.
**[3:05]** You notice that as t becomes large,
**[3:08]** Beta to the t will approach 0,
**[3:13]** which is why when t is large enough,
**[3:14]** the bias correction makes almost no difference.
**[3:17]** This is why when t is large,
**[3:18]** the purple line and the green line pretty much overlap.
**[3:22]** But during this initial phase of learning,
**[3:24]** when you're still warming up your estimates,
**[3:28]** bias correction can help you
**[3:29]** obtain a better estimate of the temperature.
**[3:31]** This is bias correction that helps you
**[3:33]** go from the purple line to the green line.
**[3:36]** In machine learning, for most implementations
**[3:39]** of the exponentially weighted average,
**[3:41]** people don't often bother to implement
**[3:44]** bias corrections because most people would
**[3:46]** rather just weigh that initial period
**[3:48]** and have a slightly more biased
**[3:49]** assessment and then go from there.
**[3:51]** But we are concerned about
**[3:52]** the bias during this initial phase,
**[3:54]** while your exponentially weighted moving average
**[3:56]** is warming up,
**[3:58]** then bias correction can help
**[4:00]** you get a better estimate early on.
**[4:02]** With that, you now know how to
**[4:04]** implement exponentially weighted moving averages.
**[4:07]** Let's go on and use this to build
**[4:09]** some better optimization algorithms.
