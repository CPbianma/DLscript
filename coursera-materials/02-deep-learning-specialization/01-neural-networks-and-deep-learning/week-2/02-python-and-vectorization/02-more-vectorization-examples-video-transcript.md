---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 2
section: Python and Vectorization
item_title: More Vectorization Examples
duration: 6 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/ZPlX9/more-vectorization-examples
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# More Vectorization Examples — Transcript

**[0:00]** In the previous video you saw a few examples of how vectorization,
**[0:04]** by using built in functions and by avoiding explicit for
**[0:08]** loops, allows you to speed up your code significantly.
**[0:11]** Let's look at a few more examples.
**[0:13]** The rule of thumb to keep in mind is, when you're programming your neural networks, or
**[0:17]** when you're programming just a regression,
**[0:20]** whenever possible avoid explicit for-loops.
**[0:22]** And it's not always possible to never use a for-loop, but when you can
**[0:27]** use a built in function or find some other way to compute whatever you need,
**[0:32]** you'll often go faster than if you have an explicit for-loop.
**[0:37]** Let's look at another example.
**[0:38]** If ever you want to compute a vector u as the product of the matrix A,
**[0:45]** and another vector v, then the definition of our matrix
**[0:50]** multiply is that your Ui is equal to sum over j,, Aij, Vj.
**[0:56]** That's how you define Ui.
**[0:58]** And so the non-vectorized implementation of this
**[1:03]** would be to set u equals NP.zeros, it would be n by 1.
**[1:09]** For i, and so on.
**[1:12]** For j, and so on..
**[1:16]** And then u[i] plus equals a[i][j] times v[j].
**[1:23]** So now, this is two for-loops, looping over both i and j.
**[1:26]** So, that's a non-vectorized version,
**[1:30]** the vectorized implementation which is to say u equals np dot (A,v).
**[1:37]** And the implementation on the right, the vectorized version,
**[1:40]** now eliminates two different for-loops, and it's going to be way faster.
**[1:45]** Let's go through one more example.
**[1:46]** Let's say you already have a vector, v, in memory and you
**[1:50]** want to apply the exponential operation on every element of this vector v.
**[1:55]** So you can put u equals the vector, that's e to the v1,
**[2:00]** e to the v2, and so on, down to e to the vn.
**[2:05]** So this would be a non-vectorized implementation,
**[2:09]** which is at first you initialize u to the vector of zeros.
**[2:13]** And then you have a for-loop that computes the elements one at a time.
**[2:18]** But it turns out that Python and NumPy have many built-in functions that allow
**[2:23]** you to compute these vectors with just a single call to a single function.
**[2:31]** So what I would do to implement this is import
**[2:36]** numpy as np, and then what you
**[2:41]** just call u = np.exp(v).
**[2:47]** And so, notice that, whereas previously you had that explicit for-loop,
**[2:52]** with just one line of code here, just v as an input vector u as an output vector,
**[2:56]** you've gotten rid of the explicit for-loop, and the implementation on
**[3:01]** the right will be much faster that the one needing an explicit for-loop.
**[3:06]** In fact, the NumPy library has many of the vector value functions.
**[3:10]** So np.log (v) will compute the element-wise log,
**[3:16]** np.abs computes the absolute value,
**[3:20]** np.maximum computes the element-wise maximum
**[3:25]** to take the max of every element of v with 0.
**[3:30]** v**2 just takes the element-wise square of each element of v.
**[3:36]** One over v takes the element-wise inverse, and so on.
**[3:42]** So, whenever you are tempted to write a for-loop take a look, and see if there's
**[3:47]** a way to call a NumPy built-in function to do it without that for-loop.
**[3:53]** So, let's take all of these learnings and
**[3:55]** apply it to our logistic regression gradient descent implementation,
**[3:59]** and see if we can at least get rid of one of the two for-loops we had.
**[4:03]** So here's our code for
**[4:04]** computing the derivatives for logistic regression, and we had two for-loops.
**[4:09]** One was this one up here, and the second one was this one.
**[4:12]** So in our example we had nx equals 2, but
**[4:15]** if you had more features than just 2 features then you'd
**[4:20]** need have a for-loop over dw1, dw2, dw3, and so on.
**[4:25]** So its as if there's actually a 4j equals 1, 2, and x.
**[4:31]** dWj gets updated.
**[4:37]** So we'd like to eliminate this second for-loop.
**[4:41]** That's what we'll do on this slide.
**[4:43]** So the way we'll do so is that instead of explicitly
**[4:49]** initializing dw1, dw2, and so on to zeros,
**[4:54]** we're going to get rid of this and instead make dw a vector.
**[5:00]** So we're going to set dw equals np.zeros, and
**[5:04]** let's make this a nx by 1, dimensional vector.
**[5:11]** Then, here, instead of this for
**[5:14]** loop over the individual components,
**[5:18]** we'll just use this vector value operation,
**[5:23]** dw plus equals xi times dz(i).
**[5:27]** And then finally, instead of this,
**[5:33]** we will just have dw divides equals m.
**[5:39]** So now we've gone from having two for-loops to just one for-loop.
**[5:42]** We still have this one for-loop that loops over the individual training examples.
**[5:49]** So I hope this video gave you a sense of vectorization.
**[5:52]** And by getting rid of one for-loop your code will already run faster.
**[5:56]** But it turns out we could do even better.
**[5:58]** So the next video will talk about how to vectorize logistic aggression even
**[6:02]** further.
**[6:03]** And you see a pretty surprising result, that without using any for-loops,
**[6:07]** without needing a for-loop over the training examples,
**[6:10]** you could write code to process the entire training sets.
**[6:14]** So, pretty much all at the same time.
**[6:17]** So, let's see that in the next video.
