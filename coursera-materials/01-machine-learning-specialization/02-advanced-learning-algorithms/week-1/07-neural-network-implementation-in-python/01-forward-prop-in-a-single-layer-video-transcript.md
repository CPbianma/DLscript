---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 1
section: Neural network implementation in Python
item_title: Forward prop in a single layer
duration: 5 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/AJc5g/forward-prop-in-a-single-layer
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# Forward prop in a single layer — Transcript

**[0:02]** if you had to implement forward propagation yourself from scratch in
**[0:06]** python, how would you go about doing so, in addition to gaining intuition
**[0:11]** about what's really going on in libraries like TensorFlow and PyTorch.
**[0:15]** If ever some day you decide you want to build something even
**[0:18]** better than TensorFlow and PyTorch, maybe now you have a better idea home,
**[0:23]** I don't really recommend doing this for most people.
**[0:26]** But maybe someday, someone will come up with an even better framework than
**[0:30]** TensorFlow and PyTorch and whoever does that may end up having to implement
**[0:34]** these things from scratch themselves.
**[0:36]** So let's take a look,
**[0:38]** on this slide I'm going to go through quite a bit of code and
**[0:42]** you see all this code again later in the optional lab as was in the practice lab.
**[0:48]** So don't worry about having to take notes on every line of code or
**[0:51]** memorize every line of code.
**[0:53]** You see this code written down in the Jupiter notebook in the lab and
**[0:57]** the goal of this video is to just show you the code to make sure you can
**[1:02]** understand what it's doing.
**[1:04]** So that when you go to the optional lab and the practice lab and see the code
**[1:08]** there, you know what to do so don't worry about taking detailed notes on every line.
**[1:12]** If you can read through the code on this slide and understand what it's doing,
**[1:16]** that's all you need.
**[1:18]** So let's take a look at how you implement forward prop in a single layer,
**[1:23]** we're going to continue using the coffee roasting model shown here.
**[1:29]** And let's look at how you would take an input feature vector x,
**[1:33]** and implement forward prop to get this output a2.
**[1:37]** In this python implementation,
**[1:40]** I'm going to use 1D arrays to represent all of these vectors and
**[1:45]** parameters, which is why there's only a single square bracket here.
**[1:50]** This is a 1D array in python rather than a 2D matrix,
**[1:54]** which is what we had when we had double square brackets.
**[1:59]** So the first value you need to compute is,
**[2:02]** a super strip square bracket 1 subscript 1, which is the first
**[2:07]** activation value of a1 and that's g of this expression over here.
**[2:13]** So I'm going to use the convention on this slide that at a term like w2,
**[2:20]** 1, I'm going to represent as a variable w2 and then subscript 1.
**[2:26]** This underscore one denotes subscript one, denotes subscript one so
**[2:30]** w2 means w superscript 2 in square brackets and then subscript 1.
**[2:36]** So, to compute a1_1, we have parameters w1_1 and
**[2:43]** b1_1, which are say 1_2 and -1.
**[2:49]** You would then compute z1_1 as the dot product
**[2:54]** between that parameter w1_1 and the input x,
**[2:59]** and added to b1_1 and then finally a1_1 is equal to g,
**[3:06]** the sigmoid function applied to z1_1.
**[3:11]** Next let's go on to compute a1_2, which again by the convention
**[3:17]** I described here is going to be a1_2, written like that.
**[3:21]** So similar as what we did on the left,
**[3:25]** w1_2 is two parameters -3, 4, b1_2 is the term,
**[3:30]** b 1, 2 over there, so you compute z as this term in the middle and
**[3:36]** then apply the sigmoid function and then you end up with a 1_2,
**[3:42]** and finally you do the same thing to compute a1_3.
**[3:48]** Now, you've computed these three values, a1_1,
**[3:52]** a1_2, and a1_3, and we like to take these three numbers and
**[3:57]** group them together into an array to give you a1 up here,
**[4:02]** which is the output of the first layer.
**[4:05]** And so you do that by grouping them together using a np array as follows, so
**[4:11]** now you've computed a_1, let's implement the second layer as well.
**[4:17]** So you compute, the output a2, so a2 is computed using
**[4:21]** this expression and so we would have parameters w2_1 and
**[4:27]** b2_1 corresponding to these parameters.
**[4:31]** And then you would compute z as the dot product between w2_1 and a1,
**[4:37]** and add b2_1 and then apply the sigmoid function to get a2_1 and
**[4:42]** that's it, that's how you implement forward prop using just python and np.
**[4:48]** Now, there are a lot of expressions in this page of code that you just saw,
**[4:52]** let's in the next video look at how you can simplify this to implement
**[4:56]** forward prop for a more general neural network, rather than hard coding it for
**[5:01]** every single neuron like we just did.
**[5:04]** So let's go see that in the next video.
