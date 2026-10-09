---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 2
section: Python and Vectorization
item_title: Vectorization
duration: 8 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/NYnog/vectorization
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Vectorization — Transcript

**[0:00]** Welcome back. Vectorization is basically
**[0:03]** the art of getting rid of explicit for loops in your code.
**[0:07]** In the deep learning era, especially in deep learning in practice,
**[0:11]** you often find yourself training on relatively large data sets,
**[0:15]** because that's when deep learning algorithms tend to shine.
**[0:18]** And so, it's important that your code very quickly because otherwise,
**[0:22]** if it's training a big data set,
**[0:24]** your code might take a long time to run then you just find
**[0:27]** yourself waiting a very long time to get the result.
**[0:30]** So in the deep learning era,
**[0:32]** I think the ability to perform vectorization has become a key skill.
**[0:37]** Let's start with an example.
**[0:40]** So, what is Vectorization?
**[0:42]** In logistic regression you need to compute Z equals W transpose X plus B,
**[0:48]** where W was this column vector and X is also this vector.
**[0:55]** Maybe they are very large vectors if you have a lot of features.
**[0:58]** So, W and X were both these R and no R, NX dimensional vectors.
**[1:07]** So, to compute W transpose X,
**[1:10]** if you had a non-vectorized implementation,
**[1:15]** you would do something like Z equals zero.
**[1:18]** And then for I in range of X.
**[1:24]** So, for I equals 1, 2 NX,
**[1:27]** Z plus equals W I times XI.
**[1:34]** And then maybe you do Z plus equal B at the end.
**[1:37]** So, that's a non-vectorized implementation.
**[1:39]** Then you find that that's going to be really slow.
**[1:43]** In contrast, a vectorized implementation would just compute W transpose X directly.
**[1:48]** In Python or a numpy,
**[1:52]** the command you use for that is Z equals np.W,
**[2:01]** X, so this computes W transpose X.
**[2:06]** And you can also just add B to that directly.
**[2:09]** And you find that this is much faster.
**[2:12]** Let's actually illustrate this with a little demo.
**[2:17]** So, here's my Jupiter notebook in which I'm going to write some Python code.
**[2:21]** So, first, let me import the numpy library to import.
**[2:28]** Send P. And so, for example,
**[2:30]** I can create A as an array as follows.
**[2:36]** Let's say print A.
**[2:39]** Now, having written this chunk of code,
**[2:41]** if I hit shift enter,
**[2:43]** then it executes the code.
**[2:44]** So, it created the array A and it prints it out.
**[2:47]** Now, let's do the Vectorization demo.
**[2:50]** I'm going to import the time libraries,
**[2:51]** since we use that,
**[2:53]** in order to time how long different operations take.
**[2:56]** Can they create an array A?
**[2:59]** Those random thought round.
**[3:02]** This creates a million dimensional array with random values.
**[3:10]** b = np.random.rand.
**[3:13]** Another million dimensional array.
**[3:16]** And, now, tic=time.time, so this measure the current time,
**[3:20]** c = np.dot (a, b).
**[3:26]** toc = time.time.
**[3:28]** And this print,
**[3:31]** it is the vectorized version.
**[3:34]** It's a vectorize version.
**[3:37]** And so, let's print out.
**[3:41]** Let's see the last time,
**[3:45]** so there's toc - tic x 1000,
**[3:48]** so that we can express this in milliseconds.
**[3:52]** So, ms is milliseconds.
**[3:54]** I'm going to hit Shift Enter.
**[3:56]** So, that code took about three milliseconds or this time 1.5,
**[4:01]** maybe about 1.5 or 3.5 milliseconds at a time.
**[4:06]** It varies a little bit as I run it,
**[4:08]** but looks like maybe on average it's taking like 1.5 milliseconds,
**[4:12]** maybe two milliseconds as I run this.
**[4:15]** All right.
**[4:16]** Let's keep adding to this block of code.
**[4:19]** That's not implementing non-vectorize version.
**[4:22]** Let's see, c = 0,
**[4:24]** then tic = time.time.
**[4:27]** Now, let's implement a for loop.
**[4:29]** For I in range of 1 million,
**[4:35]** I'll pick out the number of zeros right.
**[4:38]** C += (a,i) x (b,
**[4:43]** i), and then toc = time.time.
**[4:50]** Finally, print more than explicit full loop.
**[4:57]** The time it takes is this 1000 x toc - tic + "ms"
**[5:15]** to know that we're doing this in milliseconds.
**[5:17]** Let's do one more thing.
**[5:19]** Let's just print out the value of C we
**[5:22]** compute it to make sure that it's the same value in both cases.
**[5:27]** I'm going to hit shift enter to run this and check that out.
**[5:35]** In both cases, the vectorize version
**[5:38]** and the non-vectorize version computed the same values,
**[5:41]** as you know, 2.50 to 6.99, so on.
**[5:45]** The vectorize version took 1.5 milliseconds.
**[5:48]** The explicit for loop and non-vectorize version took about 400, almost 500 milliseconds.
**[5:57]** The non-vectorize version took something like 300
**[6:01]** times longer than the vectorize version.
**[6:05]** With this example you see that if only you remember to vectorize your code,
**[6:11]** your code actually runs over 300 times faster.
**[6:15]** Let's just run it again.
**[6:16]** Just run it again.
**[6:18]** Yeah. Vectorize version 1.5 milliseconds seconds and the for loop.
**[6:22]** So 481 milliseconds, again,
**[6:25]** about 300 times slower to do the explicit for loop.
**[6:29]** If the engine x slows down,
**[6:30]** it's the difference between your code taking maybe one minute to
**[6:33]** run versus taking say five hours to run.
**[6:37]** And when you are implementing deep learning algorithms,
**[6:41]** you can really get a result back faster.
**[6:43]** It will be much faster if you vectorize your code.
**[6:46]** Some of you might have heard that a lot of
**[6:49]** scaleable deep learning implementations are done on a GPU or a graphics processing unit.
**[6:54]** But all the demos I did just now in the Jupiter notebook where actually on the CPU.
**[6:59]** And it turns out that both GPU and CPU have parallelization instructions.
**[7:04]** They're sometimes called SIMD instructions.
**[7:07]** This stands for a single instruction multiple data.
**[7:11]** But what this basically means is that,
**[7:13]** if you use built-in functions such as this
**[7:16]** np.function or other functions that don't require you explicitly implementing a for loop.
**[7:23]** It enables Phyton Pi to take
**[7:28]** much better advantage of parallelism to do your computations much faster.
**[7:33]** And this is true both computations on CPUs and computations on GPUs.
**[7:38]** It's just that GPUs are remarkably good at
**[7:41]** these SIMD calculations but CPU is actually also not too bad at that.
**[7:44]** Maybe just not as good as GPUs.
**[7:47]** You're seeing how vectorization can significantly speed up your code.
**[7:51]** The rule of thumb to remember is whenever possible,
**[7:54]** avoid using explicit for loops.
**[7:57]** Let's go onto the next video to see some more examples of
**[7:59]** vectorization and also start to vectorize logistic regression.
