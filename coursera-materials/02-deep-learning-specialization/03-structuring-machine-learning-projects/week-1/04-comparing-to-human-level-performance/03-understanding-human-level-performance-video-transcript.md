---
type: video-transcript
specialization: Deep Learning Specialization
course: Structuring Machine Learning Projects
week: 1
section: Comparing to Human-level Performance
item_title: Understanding Human-level Performance
duration: 11 min
source_url: https://www.coursera.org/learn/machine-learning-projects/lecture/XInVm/understanding-human-level-performance
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Understanding Human-level Performance — Transcript

**[0:00]** The term human-level performance is sometimes used
**[0:03]** casually in research articles.
**[0:05]** But let me show you how we can define it a bit more precisely.
**[0:09]** And in particular, use the definition of the phrase, human-level performance,
**[0:13]** that is most useful for helping you drive progress in your machine learning project.
**[0:19]** So remember from our last video that one of the uses of this phrase,
**[0:23]** human-level error, is that it gives us a way of estimating Bayes error.
**[0:28]** What is the best possible error any function could,
**[0:31]** either now or in the future, ever, ever achieve?
**[0:35]** So bearing that in mind, let's look at a medical image classification example.
**[0:40]** Let's say that you want to look at a radiology image like this,
**[0:43]** and make a diagnosis classification decision.
**[0:49]** And suppose that a typical human, untrained human,
**[0:52]** achieves 3% error on this task.
**[0:55]** A typical doctor, maybe a typical radiologist doctor, achieves 1% error.
**[1:02]** An experienced doctor does even better, 0.7% error.
**[1:06]** And a team of experienced doctors, that is if you get a team of experienced doctors
**[1:11]** and have them all look at the image and discuss and debate the image,
**[1:14]** together their consensus opinion achieves 0.5% error.
**[1:20]** So the question I want to pose to you is, how should you define human-level error?
**[1:25]** Is human-level error 3%, 1%, 0.7% or 0.5%?
**[1:31]** Feel free to pause this video to think about it if you wish.
**[1:34]** And to answer that question, I would urge you to bear in mind that one of the most
**[1:39]** useful ways to think of human error is as a proxy or an estimate for Bayes error.
**[1:45]** So please feel free to pause this video to think about it for a while if you wish.
**[1:50]** But here's how I would define human-level error.
**[1:55]** Which is if you want a proxy or an estimate for Bayes error,
**[1:59]** then given that a team of experienced doctors discussing and debating
**[2:03]** can achieve 0.5% error,
**[2:05]** we know that Bayes error is less than equal to 0.5%.
**[2:12]** So because some system, team of these doctors can achieve 0.5% error,
**[2:17]** so by definition, this directly, optimal error has got to be 0.5% or lower.
**[2:23]** We don't know how much better it is, maybe there's a even larger team
**[2:26]** of even more experienced doctors who could do even better,
**[2:29]** so maybe it's even a little bit better than 0.5%.
**[2:32]** But we know the optimal error cannot be higher than 0.5%.
**[2:36]** So what I would do in this setting is use 0.5% as our estimate for Bayes error.
**[2:43]** So I would define human-level performance as 0.5%.
**[2:48]** At least if you're hoping to use human-level error in the analysis of bias
**[2:52]** and variance as we saw in the last video.
**[2:56]** Now, for the purpose of publishing a research paper or for
**[2:59]** the purpose of deploying a system, maybe there's a different definition of
**[3:03]** human-level error that you can use which is so
**[3:06]** long as you surpass the performance of a typical doctor.
**[3:10]** That seems like maybe a very useful result if accomplished, and
**[3:13]** maybe surpassing a single radiologist, a single doctor's performance
**[3:18]** might mean the system is good enough to deploy in some context.
**[3:22]** So maybe the takeaway from this is to be clear about what your purpose is
**[3:26]** in defining the term human-level error.
**[3:28]** And if it is to show that you can surpass a single human and therefore argue for
**[3:34]** deploying your system in some context, maybe this is the appropriate definition.
**[3:39]** But if your goal is the proxy for Bayes error,
**[3:41]** then this is the appropriate definition.
**[3:44]** To see why this matters, let's look at an error analysis example.
**[3:51]** Let's say, for a medical imaging diagnosis example,
**[3:55]** that your training error is 5% and your dev error is 6%.
**[4:00]** And in the example from the previous slide, our human-level performance,
**[4:05]** and I'm going to think of this as proxy for Bayes error.
**[4:12]** Depending on whether you defined it as a typical doctor's performance or experienced doctor or team of doctors,
**[4:17]** you would have either 1% or 0.7% or 0.5% for this.
**[4:24]** And remember also our definitions from the previous video,
**[4:28]** that this gap between Bayes error or estimate of Bayes error and
**[4:32]** training error is calling that a measure of the avoidable bias.
**[4:36]** And this as a measure or an estimate of how much of a variance problem you have in
**[4:40]** your learning algorithm.
**[4:44]** So in this first example, whichever of these choices you make,
**[4:49]** the measure of avoidable bias will be something like 4%.
**[4:53]** It will be somewhere between I guess, 4%,
**[4:56]** if you take that to 4.5%, if you use 0.5%, whereas this is 1%.
**[5:06]** So in this example, I would say,
**[5:08]** it doesn't really matter which of the definitions of human-level error you use,
**[5:12]** whether you use the typical doctor's error or
**[5:15]** the single experienced doctor's error or the team of experienced doctor's error.
**[5:20]** Whether this is 4% or 4.5%, this is clearly bigger than the variance problem.
**[5:27]** And so in this case,
**[5:29]** you should focus on bias reduction techniques such as train a bigger network.
**[5:34]** Now let's look at a second example.
**[5:36]** Let's say your training error is 1% and your dev error is 5%.
**[5:42]** Then again it doesn't really matter, seems a bit
**[5:45]** academic whether the human-level performance is 1% or 0.7% or 0.5%.
**[5:49]** Because whichever of these definitions you use, your measure of avoidable bias
**[5:54]** will be, I guess somewhere between 0% if you use that, to 0.5%, right?
**[5:59]** That's the gap between the human-level performance and your training error,
**[6:03]** whereas this gap is 4%.
**[6:04]** So this 4% is going to be much bigger than the avoidable bias either way.
**[6:08]** And so they'll just suggest you should focus on variance reduction techniques
**[6:13]** such as regularization or getting a bigger training set.
**[6:16]** But where it really matters will be if your training error is 0.7%.
**[6:20]** So you're doing really well now, and your dev error is 0.8%.
**[6:26]** In this case, it really matters that you use your estimate for Bayes error as 0.5%.
**[6:36]** Because in this case, your measure of how much avoidable bias you have is 0.2%
**[6:41]** which is twice as big as your measure for your variance, which is just 0.1%.
**[6:48]** And so this suggests that maybe both the bias and variance are both problems but
**[6:51]** maybe the avoidable bias is a bit bigger of a problem.
**[6:54]** And in this example, 0.5% as we discussed on the previous slide was the best measure
**[7:00]** of Bayes error, because a team of human doctors could achieve that performance.
**[7:04]** If you use 0.7 as your proxy for Bayes error, you would have estimated
**[7:08]** avoidable bias as pretty much 0%, and you might have missed that.
**[7:13]** You actually should try to do better on your training set.
**[7:18]** So I hope this gives a sense also of why making progress in a machine learning
**[7:22]** problem gets harder as you achieve or as you approach human-level performance.
**[7:27]** In this example, once you've approached 0.7% error,
**[7:31]** unless you're very careful about estimating Bayes error,
**[7:35]** you might not know how far away you are from Bayes error.
**[7:38]** And therefore how much you should be trying to reduce aviodable bias.
**[7:42]** In fact, if all you knew was that a single typical doctor achieves 1% error,
**[7:47]** and it might be very difficult to know if you should be trying to fit your training set
**[7:52]** even better.
**[7:54]** And this problem arose only when you're doing very well on your problem already,
**[7:58]** only when you're doing 0.7%, 0.8%, really close to human-level performance.
**[8:04]** Whereas in the two examples on the left, when you are further away human-level
**[8:09]** performance, it was easier to target your focus on bias or variance.
**[8:13]** So this is maybe an illustration of why as your pro human-level performance is
**[8:17]** actually harder to tease out the bias and variance effects.
**[8:20]** And therefore why progress on your machine learning project just gets harder as
**[8:23]** you're doing really well.
**[8:25]** So just to summarize what we've talked about.
**[8:28]** If you're trying to understand bias and variance where
**[8:30]** you have an estimate of human-level error for a task that humans can do quite well,
**[8:35]** you can use human-level error as a proxy or as a approximation for Bayes error.
**[8:47]** And so the difference between your estimate of Bayes error tells you how
**[8:51]** much avoidable bias is a problem, how much avoidable bias there is.
**[8:56]** And the difference between training error and dev error,
**[8:59]** that tells you how much variance is a problem, whether your algorithm's able
**[9:04]** to generalize from the training set to the dev set.
**[9:07]** And the big difference between our discussion here and
**[9:10]** what we saw in an earlier course was that instead of comparing training error to 0%,
**[9:18]** And just calling that the estimate of the bias.
**[9:23]** In contrast, in this video we have a more nuanced analysis in which there is no
**[9:28]** particular expectation that you should get 0% error.
**[9:31]** Because sometimes Bayes error is non zero and sometimes it's just not possible for
**[9:36]** anything to do better than a certain threshold of error.
**[9:41]** And so in the earlier course, we were measuring training error,
**[9:46]** and seeing how much bigger training error was than zero.
**[9:49]** And just using that to try to understand how big our bias is.
**[9:53]** And that turns out to work just fine for problems where Bayes error is nearly 0%,
**[9:58]** such as recognizing cats.
**[10:00]** Humans are near perfect for that, so Bayes error is also near perfect for that.
**[10:04]** So that actually works okay when Bayes error is nearly zero.
**[10:07]** But for problems where the data is noisy, like speech recognition on very noisy audio,
**[10:11]** where it's just impossible sometimes to hear what was said and
**[10:14]** to get the correct transcription.
**[10:16]** For problems like that, having a better estimate for
**[10:19]** Bayes error can help you better estimate avoidable bias and variance.
**[10:22]** And therefore make better decisions on whether to focus on bias reduction tactics,
**[10:26]** or on variance reduction tactics.
**[10:30]** So to recap, having an estimate of human-level performance gives you
**[10:34]** an estimate of Bayes error.
**[10:36]** And this allows you to more quickly make decisions as to whether you should focus
**[10:40]** on trying to reduce a bias or trying to reduce the variance of your algorithm.
**[10:45]** And these techniques will tend to work well until you surpass human-level
**[10:50]** performance, whereupon you might no longer have a good estimate of Bayes error that
**[10:54]** still helps you make this decision really clearly.
**[10:58]** Now, one of the exciting developments in deep learning has been that for
**[11:01]** more and more tasks we're actually able to surpass human-level performance.
**[11:06]** In the next video,
**[11:07]** let's talk more about the process of surpassing human-level performance.
