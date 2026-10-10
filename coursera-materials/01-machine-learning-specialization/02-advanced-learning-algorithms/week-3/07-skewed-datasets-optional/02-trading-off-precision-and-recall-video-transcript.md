---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 3
section: Skewed datasets (optional)
item_title: Trading off precision and recall
duration: 12 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/42TEG/trading-off-precision-and-recall
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# Trading off precision and recall — Transcript

**[0:00]** In the ideal case,
**[0:02]** we like for learning algorithms that have
**[0:04]** high precision and high recall.
**[0:06]** High precision would mean that if
**[0:08]** a diagnosis of patients have that rare disease,
**[0:11]** probably the patient does
**[0:12]** have it and it's an accurate diagnosis.
**[0:15]** High recall means that if
**[0:16]** there's a patient with that rare disease,
**[0:18]** probably the algorithm will correctly
**[0:21]** identify that they do have that disease.
**[0:24]** But it turns out that in practice there's often
**[0:26]** a trade-off between precision and recall.
**[0:29]** In this video, we'll take a look at that trade-off
**[0:32]** and how you can pick a good point along that trade-off.
**[0:35]** Here are the definitions from
**[0:38]** the last video on precision
**[0:39]** and recall, I'll just write them here.
**[0:41]** Well, you recall precision
**[0:43]** is the number of true positives
**[0:45]** divided by the total number that was predicted positive,
**[0:48]** and recall is the number of true positives divided by
**[0:51]** the total actual number of positives.
**[0:55]** If you're using logistic regression to make predictions,
**[1:00]** then the logistic regression model
**[1:02]** will output numbers between 0 and 1.
**[1:05]** We would typically threshold the output
**[1:09]** of logistic regression at 0.5 and
**[1:12]** predict 1 if f of x is greater than equal to
**[1:15]** 0.5 and predict 0 if it's less than 0.5.
**[1:20]** But suppose we want to predict that y is equal to 1.
**[1:24]** That is, the rare disease is
**[1:26]** present only if we're very confident.
**[1:29]** If our philosophy is,
**[1:30]** whenever we predict that the patient has a disease,
**[1:33]** we may have to send them for
**[1:35]** possibly invasive and expensive treatment.
**[1:39]** If the consequences of the disease aren't that bad,
**[1:43]** even if left not treated aggressively,
**[1:45]** then we may want to predict y equals
**[1:47]** 1 only if we're very confident.
**[1:50]** In that case, we may choose to set
**[1:53]** a higher threshold where we will
**[1:55]** predict y is 1 only if f of x
**[1:58]** is greater than or equal to 0.7,
**[2:01]** so this is saying we'll predict y equals 1
**[2:03]** only we're at least 70 percent sure,
**[2:06]** rather than just 50 percent sure and so
**[2:09]** this number also becomes 0.7.
**[2:12]** Notice that these two numbers have
**[2:14]** to be the same because it's just depending
**[2:16]** on whether it's greater than or equal to or
**[2:19]** less than this number that you predict 1 or 0.
**[2:23]** By raising this threshold,
**[2:25]** you predict y equals 1 only if
**[2:27]** you're pretty confident and what that
**[2:30]** means is that precision will
**[2:32]** increase because whenever you predict one,
**[2:36]** you're more likely to be right so
**[2:39]** raising the thresholds will result in higher precision,
**[2:43]** but it also results in
**[2:45]** lower recall because we're now predicting one
**[2:49]** less often and so of
**[2:51]** the total number of patients with the disease,
**[2:55]** we're going to correctly diagnose fewer of them.
**[2:59]** By raising this threshold to 0.7,
**[3:01]** you end up with higher precision, but lower recall.
**[3:08]** In fact, if you want to predict y
**[3:10]** equals 1 only if you are very confident,
**[3:13]** you can even raise this higher to 0.9 and that results
**[3:18]** in an even higher precision
**[3:20]** and so whenever you predict the patient has the disease,
**[3:22]** you're probably right and this
**[3:24]** will give you a very high precision.
**[3:25]** The recall will go even further down.
**[3:28]** On the flip side,
**[3:30]** suppose we want to avoid missing
**[3:33]** too many cases of the rare disease,
**[3:35]** so if what we want is when in doubt,
**[3:40]** predict y equals 1,
**[3:42]** this might be the case where
**[3:44]** if treatment is not too invasive or
**[3:47]** painful or expensive but leaving
**[3:50]** a disease untreated has
**[3:51]** much worse consequences for the patient.
**[3:53]** In that case, you might say,
**[3:55]** when in doubt in the interests of
**[3:57]** safety let's just predict that they have
**[3:59]** it and consider them for treatment
**[4:02]** because untreated cases could be quite bad.
**[4:05]** If for your application,
**[4:06]** that is the better way to make decisions,
**[4:09]** then you would take this threshold instead lower it,
**[4:12]** say, set it to 0.3.
**[4:15]** In that case, you predict one so long
**[4:18]** as you think there's maybe a 30 percent chance or
**[4:21]** better of the disease being present and you
**[4:24]** predict zero only if you're pretty
**[4:26]** sure that the disease is absent.
**[4:28]** As you can imagine,
**[4:30]** the impact on precision and recall will be
**[4:33]** opposite to what you saw up here,
**[4:37]** and lowering this threshold will result in
**[4:41]** lower precision because we're now looser,
**[4:45]** we're more willing to predict one even if we aren't sure
**[4:48]** but to result in higher recall,
**[4:53]** because of all the patients that do have that disease,
**[4:56]** we're probably going to correctly identify more of them.
**[4:59]** More generally, we have the flexibility to predict
**[5:04]** one only if f is
**[5:06]** above some threshold and by choosing this threshold,
**[5:09]** we can make different trade-offs
**[5:11]** between precision and recall.
**[5:13]** It turns out that for most learning algorithms,
**[5:17]** there is a trade-off between precision and recall.
**[5:20]** Precision and recall both go between zero and
**[5:23]** one and if you were to set a very high threshold,
**[5:28]** say a threshold of 0.99,
**[5:31]** then you enter with very high precision,
**[5:33]** but lower recall and
**[5:36]** as you reduce the value of this threshold,
**[5:38]** you then end up with a curve that
**[5:42]** trades off precision and recall until eventually,
**[5:45]** if you have a very low threshold,
**[5:47]** so the threshold equals 0.01,
**[5:49]** then you end up with
**[5:51]** very low precision but relatively high recall.
**[5:55]** Sometimes by plotting this curve,
**[5:57]** you can then try to pick a threshold
**[5:59]** which corresponds to picking a point on this curve.
**[6:02]** The balances, the cost of
**[6:04]** false positives and false negatives or the balances,
**[6:08]** the benefits of high precision and high recall.
**[6:11]** Plotting precision and recall for different values of
**[6:14]** the threshold allows you to pick a point that you want.
**[6:19]** Notice that picking the threshold is not something you
**[6:25]** can really do with
**[6:27]** cross-validation because it's up
**[6:30]** to you to specify the best points.
**[6:32]** For many applications, manually picking the threshold to
**[6:36]** trade-off precision and recall
**[6:38]** will be what you end up doing.
**[6:40]** It turns out that if you want to automatically
**[6:43]** trade-off precision and recall
**[6:45]** rather than have to do so yourself,
**[6:47]** there is another metric called
**[6:49]** the F1 score that is sometimes used to
**[6:53]** automatically combine precision recall to help
**[6:56]** you pick the best value
**[6:58]** or the best trade-off between the two.
**[7:00]** One challenge with precision recall is you're now
**[7:03]** evaluating your algorithms using two different metrics,
**[7:07]** so if you've trained
**[7:08]** three different algorithms and
**[7:11]** the precision-recall numbers look like this,
**[7:13]** is not that obvious how to pick which algorithm to use.
**[7:17]** If there was an algorithm that's
**[7:19]** better on precision and better on recall,
**[7:22]** then you probably want to go with that one.
**[7:23]** But in this example,
**[7:25]** Algorithm 2 has the highest precision,
**[7:28]** but Algorithm 3 has the highest recall,
**[7:31]** and Algorithm 1 trades off the two in-between,
**[7:34]** and so no one algorithm is obviously the best choice.
**[7:39]** In order to help you decide which algorithm to pick,
**[7:44]** it may be useful to find a way to
**[7:46]** combine precision and recall into a single score,
**[7:50]** so you can just look at which algorithm
**[7:52]** has the highest score and maybe go with that one.
**[7:56]** One way you could combine precision and
**[7:59]** recall is to take the average,
**[8:01]** this turns out not to be a good way,
**[8:03]** so I don't really recommend this.
**[8:05]** But if we were to take the average,
**[8:07]** you get 0.45,
**[8:08]** 0.4, and 0.5.
**[8:11]** But it turns out that
**[8:12]** computing the average and picking the algorithm with
**[8:14]** the highest average between
**[8:16]** precision and recall doesn't work
**[8:18]** that well because this algorithm has very low precision,
**[8:22]** and in fact, this corresponds
**[8:24]** maybe to an algorithm that actually does
**[8:27]** print y equals 1
**[8:29]** and diagnosis all patients as having the disease,
**[8:33]** that's why recall is
**[8:34]** perfect but the precision is really low.
**[8:37]** Algorithm 3 is actually not
**[8:38]** a particularly useful algorithm,
**[8:41]** even though the average between precision
**[8:43]** and recall is quite high.
**[8:46]** Let's not use the average between precision and recall.
**[8:51]** Instead, the most common way of combining
**[8:54]** precision recall is a compute
**[8:56]** something called the F1 score,
**[8:59]** and the F1 score is a way of
**[9:01]** combining P and R precision and
**[9:03]** recall but that gives
**[9:04]** more emphasis to whichever of these values is lower.
**[9:08]** Because it turns out if an algorithm has
**[9:10]** very low precision or
**[9:11]** very low recall is pretty not that useful.
**[9:14]** The F1 score is a way of computing an average
**[9:18]** of sorts that pays more attention to whichever is lower.
**[9:23]** The formula for computing F1 score is this,
**[9:28]** you're going to compute one over P and one over R,
**[9:32]** and average them,
**[9:33]** and then take the inverse of that.
**[9:36]** Rather than averaging P and R precision recall
**[9:40]** we're going to average one over P and one over R,
**[9:43]** and then take one over that.
**[9:46]** If you simplify this equation it can
**[9:48]** also be computed as follows.
**[9:50]** But by averaging one over P and one over R this gives
**[9:53]** a much greater emphasis to if either P
**[9:56]** or R turns out to be very small.
**[9:59]** If you were to compute
**[10:00]** the F1 score for these three algorithms,
**[10:02]** you'll find that the F1 score for Algorithm 1 is 0.444,
**[10:08]** and for the second algorithm is 0.175.
**[10:11]** You notice that 0.175 is
**[10:13]** much closer to the lower value than
**[10:15]** the higher value and for the third algorithm is 0.0392.
**[10:22]** F1 score gives away to
**[10:26]** trade-off precision and recall, and in this case,
**[10:28]** it will tell us that maybe
**[10:30]** the first algorithm is
**[10:31]** better than the second or the third algorithms.
**[10:34]** By the way, in math,
**[10:36]** this equation is also called
**[10:39]** the harmonic mean of P and R,
**[10:42]** and the harmonic mean is a way of taking
**[10:45]** an average that emphasizes the smaller values more.
**[10:48]** But for the purposes of this class,
**[10:49]** you don't need to worry about
**[10:50]** that terminology of the harmonic mean.
**[10:53]** Congratulations on getting to
**[10:54]** the last video of this week and thank you
**[10:56]** also for sticking with me through
**[10:58]** these two optional videos.
**[11:00]** In this week, you've learned a lot of practical tips,
**[11:04]** practical advice for how to
**[11:05]** build a machine learning system,
**[11:07]** and by applying these ideas,
**[11:09]** I think you'd be very effective at
**[11:11]** building machine learning algorithms.
**[11:14]** Next week, we'll come back to talk about
**[11:17]** another very powerful machine learning algorithm.
**[11:21]** In fact, of the advanced techniques that why
**[11:23]** we use in many commercial production settings,
**[11:26]** I think at the top of the list would be
**[11:28]** neural networks and decision trees.
**[11:31]** Next week we'll talk about decision trees,
**[11:33]** which I think will be another
**[11:35]** very powerful technique that
**[11:37]** you're going to use to
**[11:38]** build many successful applications as well.
**[11:40]** I look forward to seeing you next week.
