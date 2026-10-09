---
type: video-transcript
specialization: Deep Learning Specialization
course: Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization
week: 3
section: Hyperparameter Tuning
item_title: Tuning Process
duration: 7 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/dknSn/tuning-process
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Tuning Process — Transcript

**[0:00]** Hi, and welcome back.
**[0:01]** You've seen by now that changing neural nets can
**[0:04]** involve setting a lot of different hyperparameters.
**[0:07]** Now, how do you go about finding a good setting for these hyperparameters?
**[0:11]** In this video, I want to share with you some guidelines,
**[0:13]** some tips for how to systematically organize your hyperparameter tuning process,
**[0:18]** which hopefully will make it more efficient for you to
**[0:20]** converge on a good setting of the hyperparameters.
**[0:23]** One of the painful things about training deepness
**[0:25]** is the sheer number of hyperparameters you have to deal with,
**[0:29]** ranging from the learning rate alpha to the momentum term beta, if using momentum,
**[0:35]** or the hyperparameters for the Adam Optimization Algorithm which are beta one,
**[0:41]** beta two, and epsilon.
**[0:44]** Maybe you have to pick the number of layers,
**[0:47]** maybe you have to pick the number of hidden units for the different layers,
**[0:50]** and maybe you want to use learning rate decay,
**[0:55]** so you don't just use a single learning rate alpha.
**[0:59]** And then of course,
**[1:01]** you might need to choose the mini-batch size.
**[1:06]** So it turns out, some of these hyperparameters are more important than others.
**[1:09]** The most learning applications I would say,
**[1:12]** alpha, the learning rate is the most important hyperparameter to tune.
**[1:16]** Other than alpha, a few other hyperparameters I tend to would maybe tune next,
**[1:21]** would be maybe the momentum term,
**[1:25]** say, 0.9 is a good default.
**[1:27]** I'd also tune the mini-batch size to make
**[1:30]** sure that the optimization algorithm is running efficiently.
**[1:34]** Often I also fiddle around with the hidden units.
**[1:36]** Of the ones I've circled in orange,
**[1:39]** these are really the three that I would consider second in importance to
**[1:43]** the learning rate alpha, and then third in
**[1:46]** importance after fiddling around with the others,
**[1:49]** the number of layers can sometimes make a huge difference,
**[1:51]** and so can learning rate decay.
**[1:55]** And then, when using the Adam algorithm I actually pretty much never tuned beta one,
**[1:58]** beta two, and epsilon.
**[2:00]** Pretty much I always use 0.9,
**[2:01]** 0.999 and tenth minus eight although you can try tuning those as well if you wish.
**[2:08]** But hopefully it does give you some rough sense of what hyperparameters
**[2:12]** might be more important than others, alpha,
**[2:16]** most important, for sure,
**[2:19]** followed maybe by the ones I've circle in orange,
**[2:22]** followed maybe by the ones I circled in purple.
**[2:25]** But this isn't a hard and fast rule and I think
**[2:27]** other deep learning practitioners may well
**[2:30]** disagree with me or have different intuitions on these.
**[2:33]** Now, if you're trying to tune some set of hyperparameters,
**[2:37]** how do you select a set of values to explore?
**[2:40]** In earlier generations of machine learning algorithms,
**[2:42]** if you had two hyperparameters,
**[2:44]** which I'm calling hyperparameter one and hyperparameter two here,
**[2:47]** it was common practice to sample the points in a grid like
**[2:53]** so, and systematically explore these values.
**[2:59]** Here I am placing down a five by five grid.
**[3:00]** In practice, it could be more or less than the five by five grid but you try out in
**[3:06]** this example all 25 points, and then pick whichever hyperparameter works best.
**[3:12]** And this practice works okay when the number of hyperparameters was relatively small.
**[3:18]** In deep learning, what we tend to do,
**[3:19]** and what I recommend you do instead,
**[3:21]** is choose the points at random.
**[3:23]** So go ahead and choose maybe of same number of points, right?
**[3:27]** 25 points, and then try out the hyperparameters on this randomly chosen set of points.
**[3:34]** And the reason you do that is that it's difficult to know in
**[3:38]** advance which hyperparameters are going to be the most important for your problem.
**[3:43]** And as you saw in the previous slide,
**[3:44]** some hyperparameters are actually much more important than others.
**[3:47]** So to take an example,
**[3:49]** let's say hyperparameter one turns out to be alpha, the learning rate.
**[3:53]** And to take an extreme example,
**[3:55]** let's say that hyperparameter two was that
**[3:58]** value epsilon that you have in the denominator of the Adam algorithm.
**[4:02]** So your choice of alpha matters a lot and your choice of epsilon hardly matters.
**[4:07]** So if you sample in the grid then you've really tried out
**[4:12]** five values of alpha
**[4:16]** and you might find that all of the different values
**[4:18]** of epsilon give you essentially the same answer.
**[4:21]** So you've now trained 25 models and only
**[4:24]** got into trial five values for the learning rate alpha,
**[4:27]** which I think is really important.
**[4:29]** Whereas in contrast, if you were to sample at random,
**[4:33]** then you will have tried out 25 distinct values of
**[4:37]** the learning rate alpha and therefore you be more
**[4:40]** likely to find a value that works really well.
**[4:43]** I've explained this example,
**[4:44]** using just two hyperparameters.
**[4:47]** In practice, you might be searching over many more hyperparameters than these,
**[4:50]** so if you have, say,
**[4:52]** three hyperparameters, I guess instead of searching over a square,
**[4:55]** you're searching over a cube where this third dimension is hyperparameter three and
**[5:00]** then by sampling within
**[5:03]** this three-dimensional cube you get to
**[5:05]** try out a lot more values of each of your three hyperparameters.
**[5:08]** And in practice you might be searching
**[5:11]** over even more hyperparameters than three and sometimes it's just hard to
**[5:14]** know in advance which ones turn out to be
**[5:17]** the really important hyperparameters for your application and sampling at random rather
**[5:22]** than in the grid shows that you are more richly
**[5:25]** exploring set of possible values
**[5:28]** for the most important hyperparameters, whatever they turn out to be.
**[5:31]** When you sample hyperparameters,
**[5:33]** another common practice is to use a coarse to fine sampling scheme.
**[5:37]** So let's say in this two-dimensional example that you sample these points,
**[5:42]** and maybe you found that this point work the best and
**[5:45]** maybe a few other points around it tended to work really well,
**[5:49]** then in the course of the final scheme what you might do is zoom in to
**[5:53]** a smaller region of the hyperparameters, and then sample more density within this space.
**[6:00]** Or maybe again at random,
**[6:02]** but to then focus more resources on searching within
**[6:06]** this blue square if you're suspecting that the best setting,
**[6:11]** the hyperparameters, may be in this region.
**[6:13]** So after doing a coarse sample of this entire square,
**[6:18]** that tells you to then focus on a smaller square.
**[6:22]** You can then sample more densely into smaller square.
**[6:26]** So this type of a coarse to fine search is also frequently used.
**[6:29]** And by trying out these different values of the hyperparameters you can then
**[6:33]** pick whatever value allows you to do best on your training set
**[6:37]** objective, or does best on your development set, or
**[6:41]** whatever you're trying to optimize in your hyperparameter search process.
**[6:46]** So I hope this gives you a way to more
**[6:48]** systematically organize your hyperparameter search process.
**[6:51]** The two key takeaways are,
**[6:53]** use random sampling and adequate search and
**[6:55]** optionally consider implementing a coarse to fine search process.
**[7:01]** But there's even more to hyperparameter search than this.
**[7:04]** Let's talk more in the next video about how to choose
**[7:07]** the right scale on which to sample your hyperparameters.
