---
type: video-transcript
specialization: Machine Learning Specialization
course: "Supervised Machine Learning: Regression and Classification"
week: 2
section: Multiple linear regression
item_title: Vectorization part 1
duration: 7 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/ismjc/vectorization-part-1
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Vectorization part 1 — Transcript

**[0:01]** In this video, you see
**[0:03]** a very useful idea called vectorization.
**[0:06]** When you're implementing a learning algorithm,
**[0:09]** using vectorization will both make your code
**[0:11]** shorter and also make it run much more efficiently.
**[0:15]** Learning how to write
**[0:17]** vectorized code will allow you to also
**[0:19]** take advantage of
**[0:20]** modern numerical linear algebra libraries,
**[0:23]** as well as maybe even GPU
**[0:25]** hardware that stands for graphics processing unit.
**[0:28]** This is hardware objectively designed
**[0:30]** to speed up computer graphics in your computer,
**[0:33]** but turns out can be used when you write vectorized code
**[0:35]** to also help you execute your code much more quickly.
**[0:38]** Let's look at a concrete example
**[0:40]** of what vectorization means.
**[0:42]** Here's an example with parameters w and b,
**[0:46]** where w is a vector with three numbers,
**[0:50]** and you also have a vector of features
**[0:53]** x with also three numbers.
**[0:56]** Here n is equal to 3.
**[0:59]** Notice that in linear algebra,
**[1:02]** the index or the counting starts from 1 and so
**[1:05]** the first value is subscripted w1 and x1.
**[1:10]** In Python code,
**[1:12]** you can define these variables w,
**[1:15]** b, and x using arrays like this.
**[1:18]** Here, I'm actually using
**[1:20]** a numerical linear algebra library
**[1:22]** in Python called NumPy,
**[1:24]** which is by far
**[1:25]** the most widely used numerical linear algebra library
**[1:28]** in Python and in machine learning.
**[1:30]** Because in Python,
**[1:32]** the indexing of arrays while
**[1:35]** counting in arrays starts from 0,
**[1:38]** you would access the first value of
**[1:41]** w using w square brackets 0.
**[1:44]** The second value using w square bracket 1,
**[1:48]** and the third and using w square bracket 2.
**[1:52]** The indexing here, it goes from 0,1 to
**[1:56]** 2 rather than 1, 2 to 3.
**[2:00]** Similarly, to access individual features of x,
**[2:04]** you will use x0,
**[2:06]** x1, and x2.
**[2:08]** Many programming languages including Python
**[2:11]** start counting from 0 rather than 1.
**[2:14]** Now, let's look at an implementation without
**[2:17]** vectorization for computing the model's prediction.
**[2:21]** In codes, it will look like this.
**[2:23]** You take each parameter
**[2:25]** w and multiply it by his associated feature.
**[2:30]** Now, you could write your code like this,
**[2:33]** but what if n isn't three but instead n is a 100 or a
**[2:37]** 100,000 is both inefficient for you
**[2:39]** the code and inefficient for your computer to compute.
**[2:43]** Here's another way. Without using
**[2:46]** vectorization but using a for loop.
**[2:49]** In math, you can use
**[2:52]** a summation operator to add all the products of w_j
**[2:56]** and x_j for j equals 1 through
**[2:59]** n. Then I'll cite the summation you add b at the end.
**[3:04]** To summation goes from j equals 1 up
**[3:08]** to and including n. For n equals 3,
**[3:12]** j therefore goes from 1, 2 to 3.
**[3:15]** In code, you can initialize after 0.
**[3:19]** Then for j in range from 0 to n,
**[3:23]** this actually makes j go from 0 to n minus 1.
**[3:28]** From 0, 1 to 2,
**[3:30]** you can then add to f the product of w_j times x_j.
**[3:36]** Finally, outside the for loop, you add b.
**[3:39]** Notice that in Python,
**[3:41]** the range 0 to n means that j goes from 0
**[3:45]** all the way to n minus 1 and does not include n itself.
**[3:49]** This is written range n in Python.
**[3:54]** But in this video, I added a 0
**[3:56]** here just to emphasize that it starts from 0.
**[3:59]** While this implementation is
**[4:02]** a bit better than the first one,
**[4:04]** this still doesn't use factorization,
**[4:06]** and isn't that efficient?
**[4:08]** Now, let's look at how you can
**[4:10]** do this using vectorization.
**[4:14]** This is the math expression of the function f,
**[4:17]** which is the dot product of w and x plus b,
**[4:22]** and now you can implement this
**[4:24]** with a single line of code by
**[4:26]** computing fp equals np dot dot,
**[4:30]** I said dot dot because the first dot is the period and
**[4:33]** the second dot is the function or the method called DOT.
**[4:38]** But is fp equals np dot dot w comma x and
**[4:44]** this implements the mathematical dot products
**[4:48]** between the vectors w and x.
**[4:51]** Then finally, you can add b to it at the end.
**[4:55]** This NumPy dot function is a vectorized implementation of
**[4:59]** the dot product operation between
**[5:01]** two vectors and especially when n is large,
**[5:04]** this will run much faster
**[5:06]** than the two previous code examples.
**[5:08]** I want to emphasize that vectorization
**[5:11]** actually has two distinct benefits.
**[5:13]** First, it makes code shorter,
**[5:15]** is now just one line of code. Isn't that cool?
**[5:18]** Second, it also results in your code running much faster
**[5:23]** than either of the two previous implementations
**[5:25]** that did not use vectorization.
**[5:28]** The reason that the vectorized implementation
**[5:32]** is much faster is behind the scenes.
**[5:35]** The NumPy dot function is
**[5:37]** able to use parallel hardware in
**[5:39]** your computer and this is true whether
**[5:41]** you're running this on a normal computer,
**[5:44]** that is on a normal computer CPU
**[5:46]** or if you are using a GPU,
**[5:48]** a graphics processor unit,
**[5:50]** that's often used to accelerate machine learning jobs.
**[5:54]** The ability of the NumPy dot function
**[5:56]** to use parallel hardware makes it much more
**[5:59]** efficient than the for loop or
**[6:01]** the sequential calculation that we saw previously.
**[6:06]** Now, this version is much more
**[6:09]** practical when n is large because you are
**[6:12]** not typing w0 times x0 plus w1 times x1
**[6:16]** plus lots of additional terms
**[6:19]** like you would have had for the previous version.
**[6:21]** But while this saves a lot on the typing,
**[6:25]** is still not that computationally
**[6:27]** efficient because it still doesn't use vectorization.
**[6:31]** To recap, vectorization makes your code shorter,
**[6:35]** so hopefully easier to write
**[6:37]** and easier for you or others to read,
**[6:39]** and it also makes it run much faster.
**[6:42]** But honest, this magic behind
**[6:44]** vectorization that makes this run so much faster.
**[6:47]** Let's take a look at what your computer is actually doing
**[6:50]** behind the scenes to make
**[6:51]** vectorized code run so much faster.
