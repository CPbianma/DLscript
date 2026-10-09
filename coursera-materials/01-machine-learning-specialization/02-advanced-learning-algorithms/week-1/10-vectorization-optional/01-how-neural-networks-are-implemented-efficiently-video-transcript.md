---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 1
section: Vectorization(optional)
item_title: How neural networks are implemented efficiently
duration: 4 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/qkJy8/how-neural-networks-are-implemented-efficiently
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# How neural networks are implemented efficiently — Transcript

**[0:00]** One of the reasons that deep learning researchers
**[0:04]** have been able to scale up neural networks,
**[0:07]** and thought really large neural networks
**[0:09]** over the last decade,
**[0:10]** is because neural networks can be vectorized.
**[0:13]** They can be implemented very
**[0:15]** efficiently using matrix multiplications.
**[0:18]** It turns out that
**[0:20]** parallel computing hardware, including GPUs,
**[0:23]** but also some CPU functions are very
**[0:26]** good at doing very large matrix multiplications.
**[0:29]** In this video, we'll take a look at how
**[0:32]** these vectorized implementations of neural networks work.
**[0:36]** Without these ideas, I don't think deep learning
**[0:38]** would be anywhere near a success and scale today.
**[0:42]** Here on the left is the code that you had seen
**[0:45]** previously of how you would implement forward prop,
**[0:50]** or forward propagation,
**[0:51]** in a single layer.
**[0:54]** X here is the input,
**[0:57]** W, the weights of the first, second,
**[1:01]** and third neurons, say,
**[1:03]** parameters B, and then this
**[1:05]** is the same code as which we saw before.
**[1:08]** This will output three numbers,
**[1:10]** say, like that.
**[1:11]** If you actually implement this computation,
**[1:14]** you get 1, 0, 1.
**[1:17]** It turns out you can develop
**[1:19]** a vectorized implementation of this function as follows.
**[1:25]** Set X to be equal to this.
**[1:29]** Notice the double square brackets.
**[1:31]** This is now a 2D array, like in TensorFlow.
**[1:35]** W is the same as before,
**[1:38]** and B, I'm now using B,
**[1:41]** is also a one by three 2D array.
**[1:47]** Then it turns out that all of these steps,
**[1:51]** this for loop inside,
**[1:53]** can be replaced with just a couple of lines of
**[1:56]** code, Z equals np.matmul.
**[2:00]** Matmul is how NumPy carries out matrix multiplication.
**[2:04]** Where now X and W are both matrices,
**[2:08]** and so you just multiply them together.
**[2:11]** It turns out that this for loop,
**[2:14]** all of these lines of code can be
**[2:16]** replaced with just a couple of lines of code,
**[2:18]** which gives a vectorized implementation of this function.
**[2:23]** You compute Z,
**[2:25]** which is now a matrix again,
**[2:27]** as numpy.matmul between A in and W,
**[2:32]** where here A in and W are both matrices,
**[2:36]** and matmul is how NumPy
**[2:38]** carries out a matrix multiplication.
**[2:41]** It multiplies two matrices together,
**[2:43]** and then adds the matrix B to it.
**[2:46]** Then A out is equal to the activation function g,
**[2:52]** that is the sigmoid function,
**[2:53]** applied element-wise to this matrix Z,
**[2:57]** and then you finally return A out.
**[3:00]** This is what the code looks like.
**[3:03]** Notice that in the vectorized implementation,
**[3:07]** all of these quantities, x,
**[3:09]** which is fed into the value of A in as well as W, B,
**[3:12]** as well as Z and A out,
**[3:15]** all of these are now 2D arrays.
**[3:17]** All of these are matrices.
**[3:19]** This turns out to be
**[3:22]** a very efficient implementation of
**[3:25]** one step of forward propagation
**[3:27]** through a dense layer in the neural network.
**[3:29]** This is code for
**[3:31]** a vectorized implementation of
**[3:33]** forward prop in a neural network.
**[3:35]** But what is this code
**[3:37]** doing and how does it actually work?
**[3:39]** What is this matmul actually doing?
**[3:42]** In the next two videos,
**[3:45]** both also optional,
**[3:46]** we'll go over matrix multiplication and how that works.
**[3:50]** If you're familiar with linear algebra,
**[3:53]** if you're familiar with vectors, matrices, transposes,
**[3:57]** and matrix multiplications,
**[3:59]** you can safely just quickly skim over
**[4:02]** these two videos and jump to the last video of this week.
**[4:06]** Then in the last video of this week, also optional,
**[4:09]** we'll dive into more detail to explain how
**[4:12]** matmul gives you this vectorized implementation.
**[4:15]** Let's go onto the next video,
**[4:18]** where we'll take a look at what matrix multiplication is.
