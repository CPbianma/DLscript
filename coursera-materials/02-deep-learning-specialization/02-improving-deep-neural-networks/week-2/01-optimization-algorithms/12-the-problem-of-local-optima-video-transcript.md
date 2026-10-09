---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 2
section: Optimization Algorithms
item_title: The Problem of Local Optima
duration: 5 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/RFANA/the-problem-of-local-optima
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# The Problem of Local Optima — Transcript

**[0:00]** In the early days of deep learning,
**[0:01]** people used to worry a lot about the optimization algorithm
**[0:04]** getting stuck in bad local optima.
**[0:07]** But as this theory of deep learning has advanced,
**[0:09]** our understanding of local optima is also changing.
**[0:13]** Let me show you how we now think about local optima
**[0:16]** and problems in the optimization problem in deep learning.
**[0:21]** This was a picture people used to have in mind when they worried about local optima.
**[0:25]** Maybe you are trying to optimize some set of parameters,
**[0:28]** we call them W1 and W2,
**[0:30]** and the height in the surface is the cost function.
**[0:33]** In this picture, it looks like there are a lot of local optima in all those places.
**[0:38]** And it'd be easy for grading the sense,
**[0:41]** or one of the other algorithms to get stuck in a local
**[0:43]** optimum rather than find its way to a global optimum.
**[0:47]** It turns out that if you are plotting a figure like this in two dimensions,
**[0:51]** then it's easy to create plots like this with a lot of different local optima.
**[0:56]** And these very low dimensional plots used to guide their intuition.
**[1:00]** But this intuition isn't actually correct.
**[1:02]** It turns out if you create a neural network,
**[1:04]** most points of zero gradients are not local optima like points like this.
**[1:09]** Instead most points of zero gradient in a cost function are saddle points.
**[1:15]** So, that's a point where the zero gradient,
**[1:17]** again, just is maybe W1,
**[1:19]** W2, and the height is the value of the cost function J.
**[1:25]** But informally, a function of very high dimensional space,
**[1:28]** if the gradient is zero,
**[1:30]** then in each direction it can either be
**[1:32]** a convex light function or a concave light function.
**[1:36]** And if you are in, say,
**[1:38]** a 20,000 dimensional space,
**[1:40]** then for it to be a local optima,
**[1:42]** all 20,000 directions need to look like this.
**[1:45]** And so the chance of that happening is maybe very small,
**[1:49]** maybe two to the minus 20,000.
**[1:51]** Instead you're much more likely to get some directions where the curve bends up like so,
**[1:57]** as well as some directions where the curve function is bending
**[2:01]** down rather than have them all bend upwards.
**[2:04]** So that's why in very high-dimensional spaces you're
**[2:07]** actually much more likely to run into a saddle point like that shown on the right,
**[2:10]** then the local optimum.
**[2:13]** As for why the surface is called a saddle point,
**[2:16]** if you can picture,
**[2:17]** maybe this is a sort of saddle you put on a horse, right?
**[2:21]** Maybe this is a horse.
**[2:23]** This is a head of a horse,
**[2:24]** this is the eye of a horse.
**[2:28]** Well, not a good drawing of a horse but you get the idea.
**[2:33]** Then you, the rider,
**[2:34]** will sit here in the saddle.
**[2:38]** That's why this point here,
**[2:41]** where the derivative is zero,
**[2:43]** that point is called a saddle point.
**[2:47]** There's really the point on this saddle where you would sit, I guess,
**[2:50]** and that happens to have derivative zero.
**[2:53]** And so, one of the lessons we learned in history of
**[2:56]** deep learning is that a lot of our intuitions about low-dimensional spaces,
**[2:59]** like what you can plot on the left,
**[3:01]** they really don't transfer to
**[3:03]** the very high-dimensional spaces that any other algorithms are operating over.
**[3:07]** Because if you have 20,000 parameters,
**[3:10]** then J as your function over 20,000 dimensional vector,
**[3:14]** then you're much more likely to see saddle points than local optimum.
**[3:17]** If local optima aren't a problem,
**[3:20]** then what is a problem?
**[3:22]** It turns out that plateaus can really slow down learning and
**[3:26]** a plateau is a region where the derivative is close to zero for a long time.
**[3:31]** So if you're here,
**[3:33]** then gradient descents will move down the surface,
**[3:38]** and because the gradient is zero or near zero,
**[3:41]** the surface is quite flat.
**[3:42]** You can actually take a very long time, you know,
**[3:45]** to slowly find your way to maybe this point on the plateau.
**[3:51]** And then because of a random perturbation of left or right,
**[3:53]** maybe then finally I'm going to search pen colors for clarity.
**[3:57]** Your algorithm can then find its way off the plateau.
**[4:00]** Let it take this very long slope off before it's found its way
**[4:04]** here and they could get off this plateau.
**[4:09]** So the takeaways from this video are, first,
**[4:11]** you're actually pretty unlikely to get stuck in
**[4:13]** bad local optima so long as you're training a reasonably large neural network,
**[4:17]** save a lot of parameters,
**[4:18]** and the cost function J is defined over a relatively high dimensional space.
**[4:23]** But second, that plateaus are a problem and you can actually make learning pretty slow.
**[4:28]** And this is where algorithms like momentum or RmsProp or
**[4:31]** Adam can really help your learning algorithm as well.
**[4:35]** And these are scenarios where more sophisticated observation algorithms, such as Adam,
**[4:40]** can actually speed up the rate at which you
**[4:43]** could move down the plateau and then get off the plateau.
**[4:46]** So because your network is solving
**[4:49]** optimizations problems over such high dimensional spaces, to be honest,
**[4:53]** I don't think anyone has great intuitions about what these spaces really look like,
**[4:57]** and our understanding of them is still evolving.
**[4:59]** But I hope this gives you some better intuition about
**[5:02]** the challenges that the optimization algorithms may face.
**[5:06]** So that's congratulations on coming to the end of this week's content.
**[5:11]** Please take a look at this week's quiz as well as the exercise.
**[5:15]** I hope you enjoy practicing some of these ideas of this weeks
**[5:18]** exercise and I look forward to seeing you at the start of next week's videos.
