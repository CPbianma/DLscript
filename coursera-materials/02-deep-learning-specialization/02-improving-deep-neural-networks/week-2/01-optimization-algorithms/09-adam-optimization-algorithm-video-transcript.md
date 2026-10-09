---
type: video-transcript
specialization: Deep Learning Specialization
course: Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization
week: 2
section: Optimization Algorithms
item_title: Adam Optimization Algorithm
duration: 7 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/w9VCZ/adam-optimization-algorithm
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Adam Optimization Algorithm — Transcript

**[0:00]** During the history of deep learning,
**[0:02]** many researchers
**[0:03]** including some very well-known researchers,
**[0:05]** sometimes proposed optimization algorithms
**[0:07]** and show they work well in a few problems.
**[0:09]** But those optimization algorithms
**[0:11]** subsequently were shown not to really
**[0:13]** generalize that well to
**[0:15]** the wide range of neural
**[0:16]** networks you might want to train.
**[0:17]** Over time, I think
**[0:19]** the deep learning community actually developed
**[0:21]** some amount of skepticism
**[0:23]** about new optimization algorithms.
**[0:25]** A lot of people felt that
**[0:27]** gradient descent with momentum really works well,
**[0:29]** was difficult to propose things that work much better.
**[0:33]** RMSprop and the Adam optimization algorithm,
**[0:36]** which we'll talk about in this video,
**[0:37]** is one of those rare algorithms that has really stood up,
**[0:41]** and has been shown to work well across
**[0:44]** a wide range of deep learning architectures.
**[0:46]** This one of the algorithms that I wouldn't
**[0:48]** hesitate to recommend you try,
**[0:50]** because many people have tried it and seeing
**[0:52]** it work well on many problems.
**[0:54]** The Adam optimization algorithm is
**[0:56]** basically taking momentum and RMSprop,
**[0:59]** and putting them together.
**[1:01]** Let's see how that works.
**[1:02]** To implement Adam, you initialize V_dw equals 0,
**[1:07]** S_dw equals 0, and similarly V_db, S_db equals 0.
**[1:15]** Then on iteration t,
**[1:20]** you would compute the derivatives,
**[1:22]** compute dw, db using current mini-batch.
**[1:29]** Usually, you do this with mini-batch gradient descent,
**[1:33]** and then you do
**[1:35]** the momentum exponentially weighted average.
**[1:38]** V_dw equals Beta, but now I'm going to call
**[1:42]** this Beta_1 to distinguish it from the hyperparameter,
**[1:46]** Beta_2 we'll use for the RMSprop portion of this.
**[1:52]** This is exactly what we had when we're implementing
**[1:58]** momentum except they have now called
**[2:00]** the hyperparameter Beta _1 instead of Beta,
**[2:04]** and similarly you have V_db as follows,
**[2:10]** plus 1 minus Beta_1 times db,
**[2:14]** and then you do the RMSprop,
**[2:17]** like update as well.
**[2:18]** Now you have a different hyperparameter,
**[2:20]** Beta_2, plus 1, minus Beta_2 dw squared.
**[2:26]** Again, the squaring there,
**[2:28]** is element-wise squaring of your derivatives, dw.
**[2:33]** Then S_db is equal to this,
**[2:37]** plus 1 minus Beta_2, times db.
**[2:43]** This is the momentum-like update
**[2:48]** with hyperparameter Beta_1,
**[2:49]** and this is the RMSprop-like update
**[2:53]** with hyperparameter Beta_2.
**[2:55]** In the typical implementation of Adam,
**[2:58]** you do implement bias correction.
**[3:01]** You're going to have V corrected,
**[3:04]** corrected means after bias correction, dw equals V_dw,
**[3:08]** divided by 1 minus Beta_1 ^t,
**[3:14]** if you've done t elevations, and similarly,
**[3:17]** V_db corrected equals V_db divided by 1 minus Beta_1^t,
**[3:24]** and then similarly you implement
**[3:26]** this bias correction on S as well, so there's S_dw,
**[3:32]** divided by 1 minus Beta_2^t,
**[3:36]** and S_ db corrected equals
**[3:41]** S_db divided by 1 minus Beta_2^t.
**[3:48]** Finally, you perform the update.
**[3:50]** W gets updated as W minus Alpha times.
**[3:55]** If we're just implementing momentum,
**[3:57]** you'd use V_dw, or maybe V_dw corrected.
**[4:03]** But now we add in the RMSprop portion of this,
**[4:06]** so we're also going to divide by
**[4:08]** square root of S_dw corrected,
**[4:11]** plus Epsilon, and similarly,
**[4:14]** b gets updated as a similar formula.
**[4:17]** V_db corrected divided by
**[4:22]** square root S corrected, db plus Epsilon.
**[4:28]** These algorithm combines the effect of
**[4:32]** gradient descent with momentum
**[4:34]** together with gradient descent with RMSprop.
**[4:37]** This is commonly used
**[4:39]** learning algorithm that's proven to be very
**[4:41]** effective for many different neural networks
**[4:44]** of a very wide variety of architectures.
**[4:46]** This algorithm has a number of hyperparameters.
**[4:49]** The learning rate hyperparameter
**[4:51]** Alpha is still important,
**[4:54]** and usually needs to be tuned,
**[4:57]** so you just have to try
**[4:59]** a range of values and see what works.
**[5:02]** We did a default choice for Beta _1 is 0.9,
**[5:06]** so this is the weighted average of dw.
**[5:10]** This is the momentum-like term.
**[5:12]** The hyperparameter for Beta_2,
**[5:15]** the authors of the Adam paper inventors
**[5:17]** the Adam algorithm recommend 0.999.
**[5:20]** Again, this is computing
**[5:22]** the moving weighted average of dw
**[5:24]** squared as was db squared.
**[5:26]** The choice of Epsilon doesn't matter very much,
**[5:30]** but the authors of the Adam paper recommend a 10^minus 8,
**[5:34]** but this parameter, you really don't need to set it,
**[5:39]** and it doesn't affect performance much at all.
**[5:42]** But when implementing Adam,
**[5:44]** what people usually do is just use a default values
**[5:47]** of Beta_1 and Beta _2, as was Epsilon.
**[5:49]** I don't think anyone ever really tuned Epsilon,
**[5:52]** and then try a range of
**[5:54]** values of Alpha to see what works best.
**[5:56]** You can also tune Beta_1 and Beta_2,
**[5:58]** but is not done that often
**[6:00]** among the practitioners I know.
**[6:02]** Where does the term Adam come from?
**[6:06]** Adam stands for adaptive moment estimation,
**[6:14]** so Beta_1 is computing the mean of the derivatives.
**[6:18]** This is called the first moment,
**[6:19]** and Beta_2 is used to
**[6:21]** compute exponentially weighted average of the squares,
**[6:24]** and that's called the second moment.
**[6:25]** That gives rise to the name adaptive moment estimation.
**[6:29]** But everyone just calls it
**[6:30]** the Adam optimization algorithm.
**[6:32]** By the way, one of
**[6:33]** my long-term friends and
**[6:35]** collaborators is called Adam Coates.
**[6:37]** Far as I know, this algorithm
**[6:39]** doesn't have anything to do with him,
**[6:40]** except for the fact that I think he uses it sometimes,
**[6:43]** but sometimes I get asked that question.
**[6:45]** Just in case you're wondering.
**[6:47]** That's it for the Adam optimization algorithm.
**[6:50]** With it, I think you really train
**[6:52]** your neural networks much more quickly.
**[6:54]** But before we wrap up for this week,
**[6:55]** let's keep talking about hyperparameter tuning,
**[6:58]** as well as gain some more intuitions about what
**[7:01]** the optimization problem for neural networks looks like.
**[7:04]** In the next video, we'll talk about learning rate decay.
