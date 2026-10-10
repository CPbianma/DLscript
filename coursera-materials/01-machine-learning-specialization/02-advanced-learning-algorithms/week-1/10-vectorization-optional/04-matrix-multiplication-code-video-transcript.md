---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 1
section: Vectorization(optional)
item_title: Matrix multiplication code
duration: 6 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/ysRAb/matrix-multiplication-code
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Matrix multiplication code — Transcript

**[0:00]** Without further ado, let's jump into
**[0:03]** the vectorize implementation of a neural network.
**[0:06]** We'll look at the code that you have seen in
**[0:08]** a earlier video, and hopefully,
**[0:11]** Matmul, that is that matrix multiplication calculation,
**[0:14]** will make more sense. Let's jump in.
**[0:16]** You saw previously how you can take
**[0:18]** the matrix A and compute
**[0:21]** A transpose times W resulting in this matrix here, Z.
**[0:27]** In code if this is the matrix A,
**[0:31]** this is a NumPy array with the
**[0:33]** elements corresponding to what I wrote on top,
**[0:36]** then A transpose, which I'm going to write as AT,
**[0:40]** is going to be this matrix here,
**[0:42]** with again the columns of A now laid out in rows instead.
**[0:49]** By the way, instead of setting up AT this way,
**[0:53]** another way to compute AT in NumPy,
**[0:56]** we will write AT equals A.T. That's
**[1:01]** the transpose function that takes
**[1:03]** the columns of a matrix and lays them on the side.
**[1:06]** In code, here's how you initialize
**[1:09]** the matrix W as another 2D NumPy array.
**[1:14]** Then to compute Z equals A transpose times W,
**[1:19]** you will write Z equals np.matmul,
**[1:24]** AT, W,
**[1:26]** and that will compute this matrix Z over here,
**[1:31]** giving you this result down here.
**[1:35]** By the way, if you read other's code,
**[1:38]** sometimes you see Z equals AT and then
**[1:41]** the @ W. This is
**[1:44]** an alternative way of calling the matmal function.
**[1:48]** Although I find using np.matmul to be clearer.
**[1:52]** The call you see in this class,
**[1:54]** we just use the matmal function like
**[1:56]** this rather than this @.
**[1:58]** Let's look at what a vectorized implementation
**[2:01]** of forward prop looks like.
**[2:03]** I'm going to set A transpose to be equal
**[2:07]** to the input feature values 217.
**[2:11]** These are just the usual input feature values,
**[2:14]** 200 degrees roasting coffee for 17 minutes.
**[2:18]** This is a one by two matrix.
**[2:21]** I'm going to take the parameters w_1,
**[2:25]** w_2, and w_3,
**[2:27]** and stack them in columns like this to form
**[2:30]** this matrix W. The values b_1,
**[2:35]** b_2, b_3, I'm going to put it
**[2:37]** into a one by three matrix,
**[2:39]** that is this matrix B as follows.
**[2:42]** Then it turns out that if you were to compute
**[2:46]** Z equals A transpose W plus B,
**[2:50]** that will result in
**[2:52]** these three numbers and that's computed by taking
**[2:57]** the input feature values and multiplying that by
**[3:01]** the first column and then adding B to get 165.
**[3:06]** Taking these feature values,
**[3:08]** dot-producting with the second column,
**[3:11]** that is a weight w_2 and adding b_2 to get negative 531.
**[3:16]** These feature values dot product with
**[3:19]** the weights w_3 plus b_3 to get 900.
**[3:24]** Feel free to pause the video if you
**[3:26]** wish to double-check these calculations.
**[3:28]** But this gives you is the values of z^1_1,
**[3:30]** Z^1_2, and Z^1_3.
**[3:36]** Then finally, if the function g applies
**[3:40]** the sigmoid function to
**[3:41]** these three numbers element-wise, that is,
**[3:44]** applies the sigmoid function to 165,
**[3:46]** to negative 531, and to 900,
**[3:49]** then you end up with A equals g
**[3:52]** of this matrix Z ends up being 1,0,1.
**[3:56]** It's 1,0,1 because sigmoid of
**[3:58]** 165 is so close to one that up
**[4:02]** to numerical round off is based to
**[4:03]** one and these are bases 0 and 1.
**[4:07]** Let's look at how you implement this in code.
**[4:10]** A transpose is equal to this,
**[4:13]** is this one by two array of 217.
**[4:16]** The matrix W is this two by three matrix,
**[4:20]** and B, this is one by three matrix.
**[4:24]** The way you can implement forward prop
**[4:27]** in a layer is dense input
**[4:30]** A transpose W b is equal to z
**[4:33]** equals matmul A transpose times W plus b.
**[4:38]** That just implements this line of code.
**[4:41]** Then a_out that is the output of
**[4:44]** this layer is equal to g,
**[4:48]** the activation function applied
**[4:50]** element-wise to this matrix Z.
**[4:54]** You return a_out,
**[4:56]** and that gives you this value.
**[4:58]** In case you're comparing this slide
**[5:01]** with the slide a few videos back,
**[5:03]** there was just one little difference,
**[5:05]** which was by convention,
**[5:07]** the way this is implemented in TensorFlow,
**[5:10]** rather than calling this variable A,T,
**[5:12]** we were calling it A_in,
**[5:14]** which is why this too is
**[5:16]** the correct implementation of the code.
**[5:19]** There is a convention in TensorFlow
**[5:22]** that individual examples are actually laid
**[5:26]** out in rows in the matrix X rather than in the matrix X
**[5:30]** transpose which is why
**[5:32]** the code implementation actually
**[5:33]** looks like this in TensorFlow.
**[5:35]** But this explains why with just a few lines of code you
**[5:39]** can implement forward prop in
**[5:41]** the neural network and moreover,
**[5:42]** get a huge bonus because
**[5:44]** modern computers are very good at implementing
**[5:47]** matrix multiplications such as matmul efficiently.
**[5:50]** That's the last video this week.
**[5:52]** Thanks for sticking with me all the way through
**[5:55]** the end of these optional videos.
**[5:57]** For the rest of this week,
**[5:59]** I hope you also take a look at
**[6:00]** the quizzes and the practice labs and
**[6:02]** also the optional labs to
**[6:04]** exercise this material even more deeply.
**[6:06]** You now know how to do inference
**[6:08]** and forward prop in a neural network,
**[6:10]** which I think is really cool, so congratulations.
**[6:13]** After you have gone through the quizzes and the labs,
**[6:16]** please also come back and in the next week,
**[6:19]** we'll look at how to actually train a neural network.
**[6:22]** I look forward to seeing you next week.
