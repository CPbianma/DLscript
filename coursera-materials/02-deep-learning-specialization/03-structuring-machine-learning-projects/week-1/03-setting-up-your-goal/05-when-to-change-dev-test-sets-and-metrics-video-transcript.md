---
type: video-transcript
specialization: Deep Learning Specialization
course: Structuring Machine Learning Projects
week: 1
section: Setting Up your Goal
item_title: When to Change Dev/Test Sets and Metrics?
duration: 11 min
source_url: https://www.coursera.org/learn/machine-learning-projects/lecture/Ux3wB/when-to-change-dev-test-sets-and-metrics
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# When to Change Dev/Test Sets and Metrics? — Transcript

**[0:00]** You've seen how set to have a dev set and evaluation metric
**[0:03]** is like placing a target somewhere for your team to aim at.
**[0:07]** But sometimes partway through a project you might
**[0:09]** realize you put your target in the wrong place.
**[0:12]** In that case you should move your target.
**[0:14]** Let's take a look at an example.
**[0:16]** Let's say you build a cat classifier to try to find lots of pictures of cats to show to
**[0:21]** your cat loving users and the metric that you decided to use is classification error.
**[0:26]** So algorithms A and B have, respectively,
**[0:29]** 3% error and 5% error,
**[0:32]** so it seems like Algorithm A is doing better.
**[0:34]** But let's say you try out these algorithms, you look at these algorithms and Algorithm A,
**[0:38]** for some reason, is letting through a lot of the pornographic images.
**[0:43]** So if you shift Algorithm A the users would
**[0:46]** see more cat images because you'll see 3 percent error and identify cats,
**[0:51]** but it also shows the users
**[0:53]** some pornographic images which is totally unacceptable both for your company,
**[0:57]** as well as for your users.
**[0:59]** In contrast, Algorithm B has 5 percent error so this
**[1:03]** classifies fewer images but it doesn't have pornographic images.
**[1:08]** So from your company's point of view,
**[1:10]** as well as from a user acceptance point of view,
**[1:13]** Algorithm B is actually a much better algorithm
**[1:15]** because it's not letting through any pornographic images.
**[1:19]** So, what has happened in this example is that Algorithm A
**[1:22]** is doing better on your evaluation metric.
**[1:25]** It's getting 3 percent error but it is actually a worse algorithm.
**[1:29]** So, in this case, the evaluation metric plus
**[1:33]** the dev set prefers Algorithm A because they're saying, look,
**[1:38]** Algorithm A has lower error which is the metric you're using but you and
**[1:43]** your users prefer Algorithm B because it's not letting through pornographic images.
**[1:51]** So when this happens,
**[1:52]** when your evaluation metric is no longer
**[1:55]** correctly rank ordering preferences between algorithms,
**[1:59]** in this case is mispredicting that Algorithm A is a better algorithm,
**[2:04]** then that's a sign that you should change
**[2:05]** your evaluation metric or perhaps your development set or test set.
**[2:13]** So, in this case the misclassification error metric
**[2:16]** that you're using can be written as follows: this one over m,
**[2:20]** a number of examples in your development set,
**[2:23]** of sum from i equals 1 to mdev,
**[2:30]** number of examples in this development set of indicator of whether or not the prediction
**[2:37]** of example i in your development set is not equal to the actual label i,
**[2:44]** where they use this notation to denote their predictive value.
**[2:50]** Right. So these are zero.
**[2:51]** And this indicates a function notation,
**[2:54]** counts up the number of examples on which this thing inside is true.
**[3:00]** So this formula just counts up the number of misclassified examples.
**[3:06]** The problem with this evaluation metric is that they treat
**[3:09]** pornographic and non-pornographic images equally
**[3:13]** but you really want your classifier to not mislabel pornographic images,
**[3:18]** like maybe you recognize a pornographic image as a cat image and
**[3:21]** therefore show it to unsuspecting user,
**[3:24]** therefore very unhappy with unexpectedly seeing porn.
**[3:31]** One way to change this evaluation metric would be if you add a weight term here,
**[3:38]** we call this w(i) where w(i) is going to be equal to 1 if x(i) is
**[3:48]** non-porn and maybe 10 or
**[3:53]** maybe even large number like a 100 if x(i) is porn.
**[4:00]** So this way you're giving a much larger weight
**[4:05]** to examples that are pornographic so that the error term goes up
**[4:09]** much more if the algorithm makes a mistake on classifying
**[4:12]** a pornographic image as a cat image.
**[4:16]** In this example you giving
**[4:19]** 10 times bigger weight to classify pornographic images correctly.
**[4:25]** If you want this normalization constant,
**[4:27]** technically this becomes sum over i of w(i),
**[4:31]** so then this error would still be between zero and one.
**[4:35]** The details of this weighting aren't important and to actually implement this weighting,
**[4:40]** you need to actually go through your dev and test sets,
**[4:43]** so label the pornographic images
**[4:47]** in your dev and test sets so you can implement this weighting function.
**[4:50]** But the high level of take away is,
**[4:53]** if you find that your evaluation metric is not giving
**[4:56]** the correct rank order preference for what is actually a better algorithm,
**[5:01]** then there's a time to think about defining a new evaluation metric.
**[5:06]** And this is just one possible way that you could define an evaluation metric.
**[5:12]** The goal of the evaluation metric is to accurately tell you,
**[5:15]** given two classifiers, which one is better for your application.
**[5:20]** For the purpose of this video,
**[5:21]** don't worry too much about the details of how we define a new error metric,
**[5:25]** the point is that if you're not satisfied with your old error metric
**[5:29]** then don't keep coasting with an error metric you're unsatisfied with,
**[5:33]** instead try to define a new one that you think better captures
**[5:36]** your preferences in terms of what's actually a better algorithm.
**[5:39]** One thing you might notice is that so far we've only talked about
**[5:42]** how to define a metric to evaluate classifiers.
**[5:46]** That is, we've defined an evaluation metric that helps us
**[5:50]** better rank order classifiers when
**[5:53]** they are performing at varying levels in terms of streaming out porn.
**[5:57]** And this is actually an example of an orthogonalization where
**[6:01]** I think you should take a machine learning problem and break it into distinct steps.
**[6:05]** So, one knob, or one step is to figure out how to define a metric that captures what you want to do,
**[6:14]** and I would worry separately about how to actually do well on this metric.
**[6:21]** So think of the machine learning task as two distinct steps.
**[6:26]** To use the target analogy,
**[6:28]** the first step is to place the target.
**[6:32]** So define where you want to aim and then as a completely separate step,
**[6:37]** this is one knob you can tune which is how do you
**[6:40]** place the target as a completely separate problem.
**[6:44]** Think of it as a separate knob to tune in terms of how to do well at this algorithm,
**[6:48]** how to aim accurately or how to shoot at the target.
**[6:58]** Defining the metric is step one and you do something else for step two.
**[7:06]** In terms of shooting at the target,
**[7:08]** maybe your learning algorithm is optimizing some cost function that looks like this,
**[7:11]** where you are minimizing some of losses on your training set.
**[7:21]** One thing you could do is to also modify
**[7:25]** this in order to incorporate these weights
**[7:28]** and maybe end up changing this normalization constant as well.
**[7:31]** So it is just 1 over a sum of w(i).
**[7:34]** Again, the details of how you define J aren't important,
**[7:36]** but the point was with the philosophy of orthogonalization think of placing the target as
**[7:42]** one step and aiming and shooting at a target as a distinct step which you do separately.
**[7:48]** In other words I encourage you to think of,
**[7:49]** defining the metric as one step and only after you define a metric,
**[7:55]** figure out how to do well on that metric which might be
**[7:57]** changing the cost function J that your neural network is optimizing.
**[8:00]** Before going on, let's look at just one more example.
**[8:03]** Let's say that your two cat classifiers A and B have, respectively,
**[8:08]** 3 percent error and 5 percent error as evaluated on your dev set.
**[8:13]** Or maybe even on your test set which are images downloaded off the internet,
**[8:17]** so high quality well framed images.
**[8:19]** But maybe when you deploy your algorithm product,
**[8:21]** you find that algorithm B actually looks like it's performing better,
**[8:24]** even though it's doing better on your dev set.
**[8:27]** And you find that you've been training off
**[8:30]** very nice high quality images downloaded off
**[8:33]** the Internet but when you deploy those on the mobile app,
**[8:36]** users are uploading all sorts of pictures, they're much less framed,
**[8:39]** you haven't only covered the cat, the cats have funny facial expressions,
**[8:42]** maybe images are much blurrier,
**[8:44]** and when you test out your algorithms you find that Algorithm B is actually doing better.
**[8:51]** So this would be another example of your metric and dev test sets falling down.
**[8:58]** The problem is that you're evaluating on
**[9:01]** the dev and test set as very nice, high resolution,
**[9:04]** well-framed images but what your users
**[9:06]** really care about is you have them doing well on images they are uploading,
**[9:09]** which are maybe less professional shots and blurrier and less well framed.
**[9:15]** So the guideline is,
**[9:17]** if doing well on your metric and
**[9:20]** your current dev sets or dev and test sets' distribution,
**[9:23]** if that does not correspond to doing well on the application you actually care about,
**[9:27]** then change your metric and/or your dev test set.
**[9:32]** In other words, if we discover that your dev test set has these very high quality images
**[9:38]** but evaluating on this dev test set
**[9:41]** is not predictive of how well your app actually performs,
**[9:45]** because your app needs to deal with lower quality images,
**[9:47]** then that's a good time to change your dev test
**[9:51]** set so that your data better reflects the type of data you actually need to do well on.
**[9:56]** But the overall guideline is if your current metric and data you are
**[10:00]** evaluating on doesn't correspond to doing well on what you actually care about,
**[10:04]** then change your metric and/or your dev/test set to
**[10:07]** better capture what you need your algorithm to actually do well on.
**[10:11]** Having an evaluation metric and the dev set allows you to
**[10:14]** much more quickly make decisions about is Algorithm A or Algorithm B better.
**[10:18]** It really speeds up how quickly you or your team can iterate.
**[10:22]** So my recommendation is,
**[10:24]** even if you can't define the perfect evaluation metric and dev set,
**[10:28]** just set something up quickly and use that to drive the speed of your team iterating.
**[10:32]** And if later down the line you find out that it wasn't a good one,
**[10:36]** you have better idea, change it at that time, it's perfectly okay.
**[10:39]** But what I recommend against for the most teams is
**[10:42]** to run for too long without any evaluation metric and
**[10:45]** dev set up because that can slow down
**[10:48]** the efficiency of what your team can iterate and improve your algorithm.
**[10:52]** So that's it on when to change your evaluation metric and/or dev and test sets.
**[10:58]** I hope that these guidelines help you set up your whole team to have
**[11:02]** a well-defined target that you can iterate efficiently toward improving performance.
