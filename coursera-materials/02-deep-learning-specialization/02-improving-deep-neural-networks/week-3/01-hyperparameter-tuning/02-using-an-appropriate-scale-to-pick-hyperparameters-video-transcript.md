---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 3
section: Hyperparameter Tuning
item_title: Using an Appropriate Scale to pick Hyperparameters
duration: 9 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/3rdqN/using-an-appropriate-scale-to-pick-hyperparameters
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Using an Appropriate Scale to pick Hyperparameters — Transcript

**[0:00]** In the last video, you saw how sampling at random, over the range of hyperparameters,
**[0:05]** can allow you to search over the space of hyperparameters more efficiently.
**[0:09]** But it turns out that sampling at random doesn't mean sampling uniformly at random,
**[0:14]** over the range of valid values.
**[0:16]** Instead, it's important to pick the appropriate scale
**[0:20]** on which to explore the hyperparameters.
**[0:22]** In this video, I want to show you how to do that.
**[0:25]** Let's say that you're trying to choose the number of hidden units, n[l], for
**[0:30]** a given layer l.
**[0:31]** And let's say that you think a good range of values is somewhere from 50 to 100.
**[0:36]** In that case, if you look at the number line from 50 to 100,
**[0:41]** maybe picking some number values at random within this number line.
**[0:46]** There's a pretty visible way to search for this particular hyperparameter.
**[0:50]** Or if you're trying to decide on the number of layers in your neural network,
**[0:54]** we're calling that capital L.
**[0:56]** Maybe you think the total number of layers should be somewhere between 2 to 4.
**[1:02]** Then sampling uniformly at random, along 2, 3 and 4, might be reasonable.
**[1:08]** Or even using a grid search, where you explicitly evaluate the values 2, 3 and
**[1:12]** 4 might be reasonable.
**[1:15]** So these were a couple examples where sampling uniformly at random over
**[1:19]** the range you're contemplating; might be a reasonable thing to do.
**[1:23]** But this is not true for all hyperparameters.
**[1:26]** Let's look at another example.
**[1:28]** Say your searching for the hyperparameter alpha, the learning rate.
**[1:33]** And let's say that you suspect 0.0001 might be on the low end,
**[1:38]** or maybe it could be as high as 1.
**[1:42]** Now if you draw the number line from 0.0001 to 1,
**[1:48]** and sample values uniformly at random over this number line.
**[1:55]** Well about 90% of the values you sample would be between 0.1 and 1.
**[2:02]** So you're using 90% of the resources to search between 0.1 and 1, and
**[2:06]** only 10% of the resources to search between 0.0001 and 0.1.
**[2:12]** So that doesn't seem right.
**[2:14]** Instead, it seems more reasonable to search for hyperparameters on a log scale.
**[2:19]** Where instead of using a linear scale, you'd have 0.0001 here,
**[2:25]** and then 0.001, 0.01, 0.1, and then 1.
**[2:30]** And you instead sample uniformly, at random, on this type of logarithmic scale.
**[2:37]** Now you have more resources dedicated to searching between 0.0001 and
**[2:44]** 0.001, and between 0.001 and 0.01, and so on.
**[2:50]** So in Python, the way you implement this,
**[2:55]** is let r = -4 * np.random.rand().
**[3:00]** And then a randomly chosen value of alpha, would be alpha = 10 to the power of r.
**[3:08]** So after this first line, r will be a random number between -4 and 0.
**[3:15]** And so alpha here will be between 10 to the -4 and 10 to the 0.
**[3:20]** So 10 to the -4 is this left thing, this 10 to the -4.
**[3:25]** And 1 is 10 to the 0.
**[3:28]** In a more general case,
**[3:30]** if you're trying to sample between 10 to the a, to 10 to the b, on the log scale.
**[3:35]** And in this example, this is 10 to the a.
**[3:40]** And you can figure out what a is by taking the log base 10 of 0.0001,
**[3:45]** which is going to tell you a is -4.
**[3:49]** And this value on the right, this is 10 to the b.
**[3:51]** And you can figure out what b is,
**[3:52]** by taking log base 10 of 1, which tells you b is equal to 0.
**[3:58]** So what you do, is then sample r uniformly, at random, between a and b.
**[4:04]** So in this case, r would be between -4 and 0.
**[4:06]** And you can set alpha,
**[4:08]** on your randomly sampled hyperparameter value, as 10 to the r, okay?
**[4:14]** So just to recap, to sample on the log scale, you take the low value,
**[4:18]** take logs to figure out what is a.
**[4:20]** Take the high value, take a log to figure out what is b.
**[4:23]** So now you're trying to sample, from 10 to the a to the b, on a log scale.
**[4:28]** So you set r uniformly, at random, between a and b.
**[4:32]** And then you set the hyperparameter to be 10 to the r.
**[4:35]** So that's how you implement sampling on this logarithmic scale.
**[4:40]** Finally, one other tricky case is sampling the hyperparameter beta,
**[4:46]** used for computing exponentially weighted averages.
**[4:49]** So let's say you suspect that beta should be somewhere between 0.9 to 0.999.
**[4:55]** Maybe this is the range of values you want to search over.
**[4:59]** So remember, that when computing exponentially weighted averages,
**[5:03]** using 0.9 is like averaging over the last 10 values.
**[5:09]** kind of like taking the average of 10 days temperature,
**[5:12]** whereas using 0.999 is like averaging over the last 1,000 values.
**[5:18]** So similar to what we saw on the last slide, if you want to search between 0.9
**[5:23]** and 0.999, it doesn't make sense to sample on the linear scale, right?
**[5:28]** Uniformly, at random, between 0.9 and 0.999.
**[5:31]** So the best way to think about this,
**[5:33]** is that we want to explore the range of values for 1 minus beta,
**[5:38]** which is going to now range from 0.1 to 0.001.
**[5:43]** And so we'll sample the between beta,
**[5:47]** taking values from 0.1, to maybe 0.1, to 0.001.
**[5:53]** So using the method we have figured out on the previous slide,
**[5:57]** this is 10 to the -1, this is 10 to the -3.
**[6:01]** Notice on the previous slide, we had the small value on the left, and
**[6:05]** the large value on the right, but here we have reversed.
**[6:08]** We have the large value on the left, and the small value on the right.
**[6:12]** So what you do, is you sample r uniformly, at random, from -3 to -1.
**[6:19]** And you set 1- beta = 10 to the r, and so beta = 1- 10 to the r.
**[6:25]** And this becomes your randomly sampled value of your hyperparameter,
**[6:29]** chosen on the appropriate scale.
**[6:31]** And hopefully this makes sense, in that this way,
**[6:35]** you spend as much resources exploring the range 0.9 to 0.99,
**[6:39]** as you would exploring 0.99 to 0.999.
**[6:43]** So if you want to study more formal mathematical justification for why we're
**[6:47]** doing this, right, why is it such a bad idea to sample in a linear scale?
**[6:51]** It is that, when beta is close to 1, the sensitivity
**[6:57]** of the results you get changes, even with very small changes to beta.
**[7:02]** So if beta goes from 0.9 to 0.9005,
**[7:10]** it's no big deal, this is hardly any change in your results.
**[7:15]** But if beta goes from 0.999 to 0.9995,
**[7:19]** this will have a huge impact on exactly what your algorithm is doing, right?
**[7:26]** In both of these cases, it's averaging over roughly 10 values.
**[7:30]** But here it's gone from an exponentially weighted average over about
**[7:35]** the last 1,000 examples, to now, the last 2,000 examples.
**[7:40]** And it's because that formula we have, 1 / 1- beta,
**[7:44]** this is very sensitive to small changes in beta, when beta is close to 1.
**[7:49]** So what this whole sampling process does,
**[7:52]** is it causes you to sample more densely in the region of when beta is close to 1.
**[7:59]** Or, alternatively, when 1- beta is close to 0.
**[8:03]** So that you can be more efficient in terms of how you distribute the samples,
**[8:07]** to explore the space of possible outcomes more efficiently.
**[8:11]** So I hope this helps you select the right scale on which to
**[8:14]** sample the hyperparameters.
**[8:15]** In case you don't end up making the right scaling decision on some hyperparameter
**[8:20]** choice, don't worry to much about it.
**[8:23]** Even if you sample on the uniform scale, where sum of the scale would
**[8:26]** have been superior, you might still get okay results.
**[8:30]** Especially if you use a coarse to fine search, so that in later iterations,
**[8:33]** you focus in more on the most useful range of hyperparameter values to sample.
**[8:38]** I hope this helps you in your hyperparameter search.
**[8:40]** In the next video, I also want to share with you some thoughts of how to organize
**[8:44]** your hyperparameter search process.
**[8:46]** That I hope will make your workflow a bit more efficient.
