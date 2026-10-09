---
type: video-transcript
specialization: Deep Learning Specialization
course: Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization
week: 3
section: Hyperparameter Tuning
item_title: Hyperparameters Tuning in Practice: Pandas vs. Caviar
duration: 7 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/DHNcc/hyperparameters-tuning-in-practice-pandas-vs-caviar
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Hyperparameters Tuning in Practice: Pandas vs. Caviar — Transcript

**[0:00]** You have now heard a lot about how to search for good hyperparameters.
**[0:04]** Before wrapping up our discussion on hyperparameter search,
**[0:08]** I want to share with you just a couple of final tips and tricks for
**[0:11]** how to organize your hyperparameter search process.
**[0:14]** Deep learning today is applied to many different application areas and
**[0:19]** that intuitions about hyperparameter settings from one application area may or
**[0:24]** may not transfer to a different one.
**[0:26]** There is a lot of cross-fertilization among different applications' domains,
**[0:30]** so for example, I've seen ideas developed in the computer vision community,
**[0:35]** such as Confonets or ResNets, which we'll talk about in a later course,
**[0:40]** successfully applied to speech.
**[0:42]** I've seen ideas that were first developed in speech successfully applied in NLP,
**[0:46]** and so on.
**[0:47]** So one nice development in deep learning is that people from different application
**[0:52]** domains do read increasingly research papers from other application domains to
**[0:56]** look for inspiration for cross-fertilization.
**[1:00]** In terms of your settings for
**[1:01]** the hyperparameters, though, I've seen that intuitions do get stale.
**[1:06]** So even if you work on just one problem, say logistics, you might have found a good
**[1:10]** setting for the hyperparameters and kept on developing your algorithm,
**[1:15]** or maybe seen your data gradually change over the course of several months,
**[1:20]** or maybe just upgraded servers in your data center.
**[1:25]** And because of those changes,
**[1:26]** the best setting of your hyperparameters can get stale.
**[1:29]** So I recommend maybe just retesting or
**[1:32]** reevaluating your hyperparameters at least once every several months
**[1:35]** to make sure that you're still happy with the values you have.
**[1:39]** Finally, in terms of how people go about searching for
**[1:42]** hyperparameters, I see maybe two major schools of thought, or
**[1:46]** maybe two major different ways in which people go about it.
**[1:50]** One way is if you babysit one model.
**[1:52]** And usually you do this if you have maybe a huge data set but not a lot of
**[1:57]** computational resources, not a lot of CPUs and GPUs, so you can basically afford
**[2:01]** to train only one model or a very small number of models at a time.
**[2:05]** In that case you might gradually babysit that model even as it's training.
**[2:11]** So, for example, on Day 0 you might initialize your parameter as random and
**[2:15]** then start training.
**[2:16]** And you gradually watch your learning curve, maybe the cost function J or
**[2:21]** your dataset error or something else, gradually decrease over the first day.
**[2:27]** Then at the end of day one, you might say, gee, looks it's learning quite well,
**[2:31]** I'm going to try increasing the learning rate a little bit and see how it does.
**[2:35]** And then maybe it does better.
**[2:37]** And then that's your Day 2 performance.
**[2:38]** And after two days you say, okay, it's still doing quite well.
**[2:42]** Maybe I'll fill the momentum term a bit or decrease the learning variable a bit now,
**[2:46]** and then you're now into Day 3.
**[2:47]** And every day you kind of look at it and try nudging up and down your parameters.
**[2:52]** And maybe on one day you found your learning rate was too big.
**[2:55]** So you might go back to the previous day's model, and so on.
**[2:58]** But you're kind of babysitting the model one day at a time even as it's training
**[3:03]** over a course of many days or over the course of several different weeks.
**[3:08]** So that's one approach, and people that babysit one model,
**[3:12]** that is watching performance and patiently nudging the learning rate up or down.
**[3:17]** But that's usually what happens if you don't have enough computational
**[3:21]** capacity to train a lot of models at the same time.
**[3:24]** The other approach would be if you train many models in parallel.
**[3:28]** So you might have some setting of the hyperparameters and
**[3:32]** just let it run by itself ,either for a day or even for multiple days,
**[3:36]** and then you get some learning curve like that; and
**[3:38]** this could be a plot of the cost function J or cost of your training error or
**[3:42]** cost of your dataset error, but some metric in your tracking.
**[3:45]** And then at the same time you might start up a different model with a different
**[3:48]** setting of the hyperparameters.
**[3:50]** And so, your second model might generate a different learning curve,
**[3:54]** maybe one that looks like that.
**[3:55]** I will say that one looks better.
**[3:57]** And at the same time, you might train a third model,
**[3:59]** which might generate a learning curve that looks like that, and another one that,
**[4:03]** maybe this one diverges so it looks like that, and so on.
**[4:06]** Or you might train many different models in parallel,
**[4:10]** where these orange lines are different models, right, and so
**[4:13]** this way you can try a lot of different hyperparameter settings and
**[4:16]** then just maybe quickly at the end pick the one that works best.
**[4:21]** Looks like in this example it was, maybe this curve that look best.
**[4:25]** So to make an analogy,
**[4:27]** I'm going to call the approach on the left the panda approach.
**[4:30]** When pandas have children, they have very few children,
**[4:33]** usually one child at a time, and
**[4:35]** then they really put a lot of effort into making sure that the baby panda survives.
**[4:40]** So that's really babysitting.
**[4:41]** One model or one baby panda.
**[4:44]** Whereas the approach on the right is more like what fish do.
**[4:48]** I'm going to call this the caviar strategy.
**[4:50]** There's some fish that lay over 100 million eggs in one mating season.
**[4:55]** But the way fish reproduce is they lay a lot of eggs and
**[4:58]** don't pay too much attention to any one of them but
**[5:01]** just see that hopefully one of them, or maybe a bunch of them, will do well.
**[5:05]** So I guess, this is really the difference between how mammals
**[5:10]** reproduce versus how fish and a lot of reptiles reproduce.
**[5:15]** But I'm going to call it the panda approach versus the caviar approach,
**[5:17]** since that's more fun and memorable.
**[5:20]** So the way to choose between these two approaches is really a function
**[5:23]** of how much computational resources you have.
**[5:26]** If you have enough computers to train a lot of models in parallel,
**[5:31]** then by all means take the caviar approach and
**[5:34]** try a lot of different hyperparameters and see what works.
**[5:37]** But in some application domains, I see this in some online advertising settings
**[5:42]** as well as in some computer vision applications, where there's just so
**[5:45]** much data and the models you want to train are so
**[5:48]** big that it's difficult to train a lot of models at the same time.
**[5:53]** It's really application dependent of course, but
**[5:55]** I've seen those communities use the panda approach a little bit more,
**[6:00]** where you are kind of babying a single model along and
**[6:03]** nudging the parameters up and down and trying to make this one model work.
**[6:08]** Although, of course, even the panda approach, having trained one model and
**[6:12]** then seen it work or not work, maybe in the second week or the third week,
**[6:15]** maybe I should initialize a different model and then baby that one along
**[6:19]** just like even pandas, I guess, can have multiple children in their lifetime,
**[6:23]** even if they have only one, or a very small number of children, at any one time.
**[6:28]** So hopefully this gives you a good sense of how to go about the hyperparameter
**[6:32]** search process.
**[6:34]** Now, it turns out that there's one other technique that can
**[6:37]** make your neural network much more robust to the choice of hyperparameters.
**[6:41]** It doesn't work for all neural networks, but when it does, it can
**[6:44]** make the hyperparameter search much easier and also make training go much faster.
**[6:48]** Let's talk about this technique in the next video.
