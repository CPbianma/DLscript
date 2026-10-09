---
type: video-transcript
specialization: Deep Learning Specialization
course: Structuring Machine Learning Projects
week: 1
section: Comparing to Human-level Performance
item_title: Surpassing Human-level Performance
duration: 6 min
source_url: https://www.coursera.org/learn/machine-learning-projects/lecture/LiV7n/surpassing-human-level-performance
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Surpassing Human-level Performance — Transcript

**[0:00]** A lot of teams often find it exciting to surpass
**[0:03]** human-level performance on the specific recreational classification task.
**[0:07]** Let's talk over some of the things you see if you try to accomplish this yourself.
**[0:12]** We've discussed before how machine learning progress gets
**[0:15]** harder as you approach or even surpass human-level performance.
**[0:19]** Let's talk over one more example of why that's the case.
**[0:23]** Let's say you have a problem where a team of humans discussing and
**[0:26]** debating achieves 0.5% error,
**[0:30]** a single human 1% error,
**[0:32]** and you have an algorithm of 0.6% training error and 0.8% dev error.
**[0:38]** So in this case,
**[0:40]** what is the avoidable bias?
**[0:46]** So this one is relatively easier to answer,
**[0:50]** 0.5% is your estimate of Baye's error,
**[0:53]** so your avoidable bias is,
**[0:54]** you're not going to use this 1% number as reference,
**[0:57]** you can use this difference,
**[0:58]** so maybe you estimate your avoidable bias is at least 0.1% and your variance as 0.2%.
**[1:06]** So there's maybe more to do to reduce your variance than your avoidable bias perhaps.
**[1:13]** But now let's take a harder example, let's say,
**[1:16]** a team of humans and single human performance, the same as before,
**[1:20]** but your algorithm gets 0.3% training error,
**[1:24]** and 0.4% dev error.
**[1:28]** Now, what is the avoidable bias?
**[1:31]** It's now actually much harder to answer that.
**[1:34]** Is the fact that your training error,
**[1:36]** 0.3%, does this mean you've over-fitted by 0.2%,
**[1:41]** or is Baye's error, actually 0.1%,
**[1:44]** or maybe is Baye's error 0.2%,
**[1:46]** or maybe Baye's error is 0.3%?
**[1:49]** You don't really know,
**[1:51]** but based on the information given in this example,
**[1:56]** you actually don't have enough information
**[2:01]** to tell if you should focus on reducing bias or reducing variance in your algorithm.
**[2:05]** So that slows down the efficiency where you should make progress.
**[2:10]** Moreover, if your error is already better than
**[2:15]** even a team of humans looking at and discussing and debating the right label,
**[2:20]** for an example, then it's just also harder to rely on human intuition to
**[2:25]** tell your algorithm what are ways that your algorithm could
**[2:27]** still improve the performance?
**[2:30]** So in this example,
**[2:32]** once you've surpassed this 0.5% threshold,
**[2:35]** your options, your ways of making progress on
**[2:38]** the machine learning problem are just less clear.
**[2:43]** It doesn't mean you can't make progress,
**[2:45]** you might still be able to make significant progress,
**[2:48]** but some of the tools you have for
**[2:51]** pointing you in a clear direction just don't work as well.
**[2:55]** Now, there are many problems where machine learning
**[2:58]** significantly surpasses human-level performance.
**[3:02]** For example, I think,
**[3:03]** online advertising, estimating how likely someone is to click on that.
**[3:08]** Probably, learning algorithms do that much better today than any human could,
**[3:12]** or making product recommendations,
**[3:14]** recommending movies or books to you.
**[3:17]** I think that web sites today can do that much
**[3:20]** better than maybe even your closest friends can.
**[3:23]** All logistics predicting how long will take you to drive from A to B,
**[3:26]** or predicting how long to take a delivery vehicle to drive from A to B,
**[3:30]** or trying to predict whether someone will repay a loan,
**[3:34]** and therefore, whether or not you should approve a loan offer.
**[3:39]** All of these are problems where I think today machine
**[3:42]** learning far surpasses a single human's performance.
**[3:46]** Notice something about these four examples.
**[3:49]** All four of these examples are actually learning from structured data,
**[3:53]** where you might have a database of what ads users have clicked on,
**[3:58]** database of products you've bought before,
**[4:00]** databases of how long it takes to get from A to B,
**[4:03]** database of previous loan applications and their outcomes.
**[4:07]** And these are not natural perception problems,
**[4:11]** so these are not computer vision,
**[4:14]** or speech recognition, or natural language processing tasks.
**[4:18]** Humans tend to be very good in natural perception task.
**[4:23]** So it is possible,
**[4:25]** but it's just a bit harder for computers to
**[4:27]** surpass human-level performance on natural perception tasks.
**[4:31]** And finally, all of these are problems where there are
**[4:34]** teams that have access to huge amounts of data.
**[4:38]** So for example, the best systems for all four of these applications have probably
**[4:43]** looked at far more data of that application than any human could possibly look at.
**[4:49]** And so, that's also made it relatively
**[4:51]** easy for a computer to surpass human-level performance.
**[4:56]** Now, the fact that there's so much data that computer could examine,
**[4:59]** so it can better find statistical patterns than even the human mind.
**[5:04]** Other than these problems,
**[5:06]** today there are speech recognition systems that can surpass human-level performance.
**[5:12]** And there are also some computer vision,
**[5:15]** some image recognition tasks,
**[5:17]** where computers have surpassed human-level performance.
**[5:21]** But because humans are very good at these natural perception tasks,
**[5:25]** I think it was harder for computers to get there.
**[5:28]** And then there are some medical tasks,
**[5:30]** for example, reading ECGs or diagnosing skin cancer,
**[5:34]** or certain narrow radiology task,
**[5:37]** where computers are getting really good and
**[5:40]** maybe surpassing a single human-level's performance.
**[5:44]** And I guess one of the exciting things about
**[5:46]** recent advances in deep learning is that even for
**[5:48]** these tasks we can now surpass human-level performance in some cases,
**[5:53]** but it has been a bit harder because humans
**[5:56]** tend to be very good at these natural perception tasks.
**[6:00]** So surpassing human-level performance is often not easy,
**[6:04]** but given enough data there've been lots of deep learning systems
**[6:08]** have surpassed human-level performance on a single supervisory problem.
**[6:12]** So that makes sense for an application you're working on.
**[6:15]** I hope that maybe someday you manage to get
**[6:17]** your deep learning system to also surpass human-level performance.
