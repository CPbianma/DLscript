---
type: video-transcript
specialization: Machine Learning Specialization
course: "Supervised Machine Learning: Regression and Classification"
week: 2
section: Multiple linear regression
item_title: Vectorization part 2
duration: 7 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/p2Nqv/vectorization-part-2
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Vectorization part 2 — Transcript

**[0:01]** I remember when I first learned about vectorization,
**[0:05]** I spent many hours on my computer
**[0:07]** taking an unvectorized version
**[0:09]** of an algorithm running it,
**[0:10]** see how long it run, and then running
**[0:12]** a vectorized version of the code
**[0:14]** and seeing how much faster that run,
**[0:16]** and I just spent hours playing with that.
**[0:18]** And it frankly blew my mind that
**[0:20]** the same algorithm vectorized would run so much faster.
**[0:23]** It felt almost like a magic trick to me.
**[0:26]** In this video, let's figure
**[0:28]** out how this magic trick really works.
**[0:30]** Let's take a deeper look at how
**[0:32]** a vectorized implementation may
**[0:34]** work on your computer behind the scenes.
**[0:36]** Let's look at this for loop.
**[0:38]** The for loop like this runs without vectorization.
**[0:42]** If j ranges from 0 to say 15,
**[0:47]** this piece of code performs
**[0:49]** operations one after another.
**[0:51]** On the first timestamp which I'm going to write as t0.
**[0:56]** It first operates on the values at index 0.
**[1:01]** At the next time-step,
**[1:03]** it calculates values corresponding to index
**[1:06]** 1 and so on until the 15th step,
**[1:09]** where it computes that.
**[1:12]** In other words, it calculates
**[1:14]** these computations one step at a time,
**[1:17]** one step after another.
**[1:19]** In contrast, this function in NumPy is
**[1:24]** implemented in the computer hardware with vectorization.
**[1:28]** The computer can get all values of the vectors w and x,
**[1:33]** and in a single-step,
**[1:35]** it multiplies each pair of w and
**[1:38]** x with each other all at the same time in parallel.
**[1:41]** Then after that, the computer takes these 16 numbers and
**[1:45]** uses specialized hardware to
**[1:47]** add them altogether very efficiently,
**[1:50]** rather than needing to carry out distinct additions
**[1:53]** one after another to add up these 16 numbers.
**[1:57]** This means that codes with vectorization can perform
**[2:01]** calculations in much less time
**[2:03]** than codes without vectorization.
**[2:06]** This matters more when you're running algorithms on
**[2:09]** large data sets or trying to train large models,
**[2:12]** which is often the case with machine learning.
**[2:15]** That's why being able to vectorize implementations
**[2:19]** of learning algorithms,
**[2:20]** has been a key step to getting
**[2:22]** learning algorithms to run efficiently,
**[2:24]** and therefore scale well to large datasets that
**[2:28]** many modern machine learning algorithms
**[2:30]** now have to operate on.
**[2:31]** Now, let's take a look at
**[2:33]** a concrete example of how this helps with
**[2:36]** implementing multiple linear regression
**[2:39]** and this linear regression with multiple input features.
**[2:42]** Say you have a problem with
**[2:45]** 16 features and 16 parameters,
**[2:48]** w1 through w16,
**[2:51]** in addition to the parameter b.
**[2:54]** You calculate it 16 derivative terms
**[2:58]** for these 16 weights and codes,
**[3:01]** maybe you store the values of w and d in two np.arrays,
**[3:05]** with d storing the values of the derivatives.
**[3:10]** For this example, I'm
**[3:12]** just going to ignore the parameter b.
**[3:14]** Now, you want to compute an update
**[3:17]** for each of these 16 parameters.
**[3:20]** W_j is updated to w_j minus the learning rate,
**[3:24]** say 0.1, times d_j,
**[3:29]** for j from 1 through 16.
**[3:33]** Encodes without vectorization,
**[3:36]** you would be doing something like this.
**[3:39]** Update w1 to be w1 minus
**[3:42]** the learning rate 0.1 times d1, next,
**[3:45]** update w2 similarly,
**[3:48]** and so on through w16,
**[3:52]** updated as w16 minus 0.1 times d16.
**[3:57]** Encodes without vectorization, you can use a
**[4:01]** for loop like this for j in range 016,
**[4:05]** that again goes from 0-15,
**[4:08]** said w_j equals w_j minus 0.1 times d_j.
**[4:13]** In contrast, with factorization,
**[4:17]** you can imagine the computer's
**[4:19]** parallel processing hardware like this.
**[4:21]** It takes all 16 values in
**[4:23]** the vector w and subtracts in parallel,
**[4:27]** 0.1 times all 16 values in the vector d,
**[4:32]** and assign all 16 calculations
**[4:36]** back to w all at the same time and all in one step.
**[4:39]** In code, you can implement this as follows,
**[4:44]** w is assigned to w minus 0.1 times d. Behind the scenes,
**[4:51]** the computer takes these NumPy arrays, w and d,
**[4:54]** and uses parallel processing hardware to
**[4:57]** carry out all 16 computations efficiently.
**[5:00]** Using a vectorized implementation,
**[5:02]** you should get a much more efficient implementation
**[5:05]** of linear regression.
**[5:07]** Maybe the speed difference won't be huge
**[5:09]** if you have 16 features,
**[5:11]** but if you have thousands of
**[5:13]** features and perhaps very large training sets,
**[5:16]** this type of vectorized implementation will make
**[5:18]** a huge difference in
**[5:19]** the running time of your learning algorithm.
**[5:21]** It could be the difference between codes
**[5:23]** finishing in one or two minutes,
**[5:25]** versus taking many hours to do the same thing.
**[5:29]** In the optional lab that follows this video,
**[5:32]** you see an introduction to one of
**[5:34]** the most used Python libraries and Machine Learning,
**[5:36]** which we've already touched on in
**[5:38]** this video called NumPy.
**[5:40]** You see how they create vectors encode and
**[5:43]** these vectors or lists of
**[5:45]** numbers are called NumPy arrays,
**[5:48]** and you also see how to take the dot product of
**[5:51]** two vectors using a NumPy function called dot.
**[5:56]** You also get to see
**[5:58]** how vectorized code such as using the dot function,
**[6:01]** can run much faster than a for-loop.
**[6:03]** In fact, you'd get to time this code yourself,
**[6:06]** and hopefully see it run much faster.
**[6:09]** This optional lab introduces
**[6:11]** a fair amount of new NumPy syntax,
**[6:13]** so when you read through the optional lab,
**[6:16]** please still feel like you have to
**[6:18]** understand all the code right away,
**[6:20]** but you can save this notebook and use it as a reference
**[6:23]** to look at when you're working with
**[6:25]** data stored in NumPy arrays.
**[6:27]** Congrats on finishing this video on vectorization.
**[6:31]** You've learned one of the most
**[6:32]** important and useful techniques
**[6:34]** in implementing machine learning algorithms.
**[6:36]** In the next video,
**[6:38]** we'll put the math of
**[6:39]** multiple linear regression together with vectorization,
**[6:43]** so that you will influence gradient descent for
**[6:46]** multiple linear regression with vectorization.
**[6:49]** Let's go on to the next video.
