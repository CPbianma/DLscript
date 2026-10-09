---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 3
section: Bias and variance
item_title: Establishing a baseline level of performance
duration: 9 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/acyFT/establishing-a-baseline-level-of-performance
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# Establishing a baseline level of performance — Transcript

**[0:00]** Let's look at some concrete numbers for
**[0:04]** what J-train and JCV might be,
**[0:06]** and see how you can judge if
**[0:08]** a learning algorithm has high bias or high variance.
**[0:11]** For the examples in this video,
**[0:14]** I'm going to use as a running example the application of
**[0:17]** speech recognition which is
**[0:19]** something I've worked on multiple times over the years.
**[0:21]** Let's take a look. A lot of users doing
**[0:24]** web search on a mobile phone will use
**[0:27]** speech recognition rather than type on
**[0:30]** the tiny keyboards on our phones because
**[0:32]** speaking to a phone is often faster than typing.
**[0:36]** Typical audio that's a web search engine
**[0:39]** we get would be like this,
**[0:42]** "What is today's weather?"
**[0:44]** Or like this,
**[0:45]** "Coffee shops near me."
**[0:46]** It's the job of the speech
**[0:48]** recognition algorithms to output
**[0:49]** the transcripts whether it's
**[0:51]** today's weather or coffee shops near me.
**[0:53]** Now, if you were to train
**[0:56]** a speech recognition system
**[0:58]** and measure the training error,
**[1:00]** and the training error means what's
**[1:02]** the percentage of audio clips in
**[1:05]** your training set that the algorithm does
**[1:07]** not transcribe correctly in its entirety.
**[1:10]** Let's say the training error for
**[1:12]** this data-set is 10.8 percent meaning
**[1:15]** that it transcribes it perfectly
**[1:18]** for 89.2 percent of your training set,
**[1:22]** but makes some mistake in
**[1:23]** 10.8 percent of your training set.
**[1:26]** If you were to also measure
**[1:28]** your speech recognition algorithm's performance
**[1:30]** on a separate cross-validation set,
**[1:33]** let's say it gets 14.8 percent error.
**[1:37]** If you were to look at
**[1:40]** these numbers it looks like
**[1:41]** the training error is really high,
**[1:43]** it got 10 percent wrong,
**[1:45]** and then the cross-validation error is higher but getting
**[1:48]** 10 percent of even your training set
**[1:50]** wrong that seems pretty high.
**[1:52]** It seems like that 10 percent error would lead you to
**[1:55]** conclude it has high bias
**[1:57]** because it's not doing well on your training set,
**[1:59]** but it turns out that when analyzing
**[2:01]** speech recognition it's useful to also
**[2:04]** measure one other thing which is what is
**[2:07]** the human level of performance?
**[2:10]** In other words, how well can even humans
**[2:13]** transcribe speech accurately from these audio clips?
**[2:16]** Concretely, let's say that you measure
**[2:19]** how well fluent speakers can
**[2:22]** transcribe audio clips and you find
**[2:25]** that human level performance achieves 10.6 percent error.
**[2:29]** Why is human level error so high?
**[2:33]** It turns out that for web search,
**[2:36]** there are a lot of audio clips that sound like this,
**[2:39]** "I'm going to navigate to [inaudible]."
**[2:43]** There's a lot of noisy audio where
**[2:45]** really no one can accurately
**[2:47]** transcribe what was said
**[2:49]** because of the noise in the audio.
**[2:51]** If even a human makes 10.6 percent error,
**[2:55]** then it seems difficult to
**[2:58]** expect a learning algorithm to do much better.
**[3:00]** In order to judge if the training error is high,
**[3:04]** it turns out to be more useful to see if
**[3:07]** the training error is much
**[3:09]** higher than a human level of performance,
**[3:12]** and in this example it does
**[3:14]** just 0.2 percent worse than humans.
**[3:16]** Given that humans are actually really good at
**[3:18]** recognizing speech I think if I
**[3:20]** can build a speech recognition system that achieves
**[3:22]** 10.6 percent error matching
**[3:24]** human performance I'd be pretty happy,
**[3:26]** so it's just doing a little bit worse than humans.
**[3:29]** But in contrast, the gap or the difference
**[3:32]** between JCV and J-train is much larger.
**[3:36]** There's actually a four percent gap there,
**[3:39]** whereas previously we had said maybe
**[3:42]** 10.8 percent error means this is high bias.
**[3:46]** When we benchmark it to human level performance,
**[3:49]** we see that the algorithm is actually
**[3:51]** doing quite well on the training set,
**[3:53]** but the bigger problem is
**[3:55]** the cross-validation error is much
**[3:57]** higher than the training error which
**[4:00]** is why I would conclude that
**[4:01]** this algorithm actually has more
**[4:03]** of a variance problem than a bias problem.
**[4:07]** It turns out when judging
**[4:10]** if the training error is high is
**[4:13]** often useful to establish
**[4:16]** a baseline level of performance,
**[4:18]** and by baseline level of performance I
**[4:20]** mean what is the level of
**[4:22]** error you can reasonably hope your
**[4:24]** learning algorithm to eventually get to.
**[4:27]** One common way to establish
**[4:30]** a baseline level of performance is to measure how well
**[4:33]** humans can do on this task because
**[4:36]** humans are really good at understanding speech data,
**[4:39]** or processing images or understanding texts.
**[4:41]** Human level performance is often
**[4:43]** a good benchmark when you are using unstructured data,
**[4:48]** such as: audio,
**[4:49]** images, or texts.
**[4:50]** Another way to estimate
**[4:53]** a baseline level of performance is
**[4:55]** if there's some competing algorithm,
**[4:56]** maybe a previous implementation
**[4:59]** that someone else has implemented or even
**[5:01]** a competitor's algorithm to establish
**[5:03]** a baseline level of performance if you can measure that,
**[5:07]** or sometimes you might guess based on prior experience.
**[5:13]** If you have access to
**[5:14]** this baseline level of performance that is,
**[5:17]** what is the level of
**[5:18]** error you can reasonably hope to get to or
**[5:20]** what is the desired level of
**[5:22]** performance that you want your algorithm to get to?
**[5:24]** Then when judging if
**[5:27]** an algorithm has high bias or variance,
**[5:29]** you would look at the baseline level of performance,
**[5:32]** and the training error,
**[5:34]** and the cross-validation error.
**[5:35]** The two key quantities to measure are
**[5:38]** then: what is the difference
**[5:40]** between training error and
**[5:43]** the baseline level that you hope to get to.
**[5:45]** This is 0.2,
**[5:47]** and if this is large then
**[5:49]** you would say you have a high bias problem.
**[5:52]** You will then also look at
**[5:54]** this gap between your training error
**[5:57]** and your cross-validation error,
**[5:58]** and if this is high then you
**[6:00]** will conclude you have a high variance problem.
**[6:03]** That's why in this example we
**[6:05]** concluded we have a high variance problem,
**[6:08]** whereas let's look at the second example.
**[6:11]** If the baseline level of performance;
**[6:14]** that is human level performance, and training error,
**[6:16]** and cross validation error look like this,
**[6:19]** then this first gap
**[6:21]** is 4.4 percent and so there's actually a big gap.
**[6:25]** The training error is much higher
**[6:27]** than what humans can do and what we hope to
**[6:29]** get to whereas the cross-validation error
**[6:32]** is just a little bit bigger than the training error.
**[6:34]** If your training error and
**[6:36]** cross validation error look like this,
**[6:38]** I will say this algorithm has high bias.
**[6:42]** By looking at these numbers,
**[6:44]** training error and cross validation error,
**[6:46]** you can get a sense intuitively or informally of
**[6:50]** the degree to which your algorithm
**[6:52]** has a high bias or high variance problem.
**[6:55]** Just to summarize, this gap between
**[6:58]** these first two numbers gives you
**[7:01]** a sense of whether you have a high bias problem,
**[7:04]** and the gap between these two numbers gives you
**[7:07]** a sense of whether you have a high variance problem.
**[7:11]** Sometimes the baseline level of
**[7:12]** performance could be zero percent.
**[7:14]** If your goal is to achieve
**[7:15]** perfect performance than the baseline level
**[7:17]** of performance it could be zero percent,
**[7:19]** but for some applications like
**[7:21]** the speech recognition application where some audio
**[7:24]** is just noisy then the baseline level of
**[7:26]** a performance could be much higher than zero.
**[7:28]** The method described on this slide will
**[7:30]** give you a better read in
**[7:32]** terms of whether your algorithm
**[7:33]** suffers from bias or variance.
**[7:36]** By the way, it is possible for
**[7:38]** your algorithms to have high bias and high variance.
**[7:41]** Concretely, if you get numbers like these,
**[7:45]** then the gap between
**[7:47]** the baseline and the training error is large.
**[7:50]** That would be a 4.4 percent,
**[7:52]** and the gap between
**[7:55]** training error and cross validation error is also large.
**[7:57]** This is 4.7 percent.
**[7:59]** If it looks like this you will conclude that
**[8:01]** your algorithm has high bias and high variance,
**[8:04]** although hopefully this won't happen
**[8:06]** that often for your learning applications.
**[8:08]** To summarize, we've seen
**[8:11]** that looking at whether your training error is
**[8:12]** large is a way to tell if your algorithm has high bias,
**[8:16]** but on applications where the data is
**[8:19]** sometimes just noisy and is infeasible or
**[8:22]** unrealistic to ever expect to get
**[8:24]** a zero error then it's useful to
**[8:26]** establish this baseline level of performance.
**[8:29]** Rather than just asking is my training error a lot,
**[8:32]** you can ask is my training error
**[8:34]** large relative to what I hope I can get to eventually,
**[8:37]** such as, is my training
**[8:39]** large relative to what humans can do on the task?
**[8:42]** That gives you a more accurate read on how far away
**[8:45]** you are in terms of
**[8:46]** your training error from where you hope to get to.
**[8:49]** Then similarly, looking at
**[8:51]** whether your cross-validation error
**[8:52]** is much larger than your training error,
**[8:55]** gives you a sense of whether or not
**[8:57]** your algorithm may have a high variance problem as well.
**[9:00]** In practice, this is how I often
**[9:02]** will look at these numbers to judge
**[9:04]** if my learning algorithm has
**[9:05]** a high bias or high variance problem.
**[9:08]** Now, to further hone
**[9:09]** our intuition about how a learning algorithm is doing,
**[9:12]** there's one other thing that I found
**[9:15]** useful to think about which is the learning curve.
**[9:18]** Let's take a look at what that means in the next video.
