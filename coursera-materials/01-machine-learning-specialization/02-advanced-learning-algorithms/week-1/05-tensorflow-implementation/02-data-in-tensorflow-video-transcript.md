---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 1
section: TensorFlow implementation
item_title: Data in TensorFlow
duration: 11 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/eTL7B/data-in-tensorflow
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# Data in TensorFlow — Transcript

**[0:02]** In this video, I want to step through with you how data is represented in NumPy and
**[0:07]** in TensorFlow.
**[0:09]** So that as you're implementing new neural networks,
**[0:12]** you can have a consistent framework to think about how to represent your data.
**[0:18]** One of the unfortunate things about the way things are done in code today is that
**[0:22]** many, many years ago NumPy was first created and became a standard library for
**[0:27]** linear algebra and Python.
**[0:29]** And then much later the Google brain team, the team that I had started and
**[0:34]** once led created TensorFlow.
**[0:36]** And so unfortunately there are some inconsistencies between how data is
**[0:40]** represented in NumPy and in TensorFlow.
**[0:43]** So it's good to be aware of these conventions so that you can implement
**[0:47]** correct code and hopefully get things running in your neural networks.
**[0:52]** Let's start by taking a look at how TensorFlow represents data.
**[0:56]** Let's see you have a data set like this from the coffee example.
**[1:01]** I mentioned that you would write x as follows.
**[1:05]** So why do you have this double square bracket here?
**[1:10]** Let's take a look at how NumPy stores vectors and matrices.
**[1:16]** In case you think matrices and
**[1:18]** vectors are complicated mathematical concepts don't worry about it.
**[1:23]** We'll go through a few concrete examples and you'll be able to do everything
**[1:28]** you need to do with matrices and vectors in order to implement your networks.
**[1:33]** Let's start with an example of a matrix.
**[1:36]** Here is a matrix with 2 rows and 3 columns.
**[1:43]** Notice that there are one,
**[1:46]** two rows and 1, 2, 3 columns.
**[1:51]** So we call this a 2 x 3 matrix.
**[1:55]** And so the convention is the dimension of the matrix is
**[2:00]** written as the number of rows by the number of columns.
**[2:05]** So in code to store this matrix, this 2 x 3 matrix,
**[2:10]** you just write x = np.array of these numbers like these.
**[2:17]** Where you notice that the square bracket tells you that 1,
**[2:22]** 2, 3 is the first row of this matrix and 4, 5,
**[2:27]** 6 is the second row of this matrix.
**[2:31]** And then this open square bracket groups the first and the second row together.
**[2:38]** So this sets x to be this to the array of numbers.
**[2:43]** So matrix is just a 2D array of numbers.
**[2:48]** Let's look at one more example, here I've written out another matrix.
**[2:54]** How many roles and how many columns does this have?
**[2:56]** Well, you can count this as one, two,
**[3:00]** three, four rows and it has one, two columns.
**[3:05]** So this is a number of rows by the number of columns matrix, so it's a 4 x 2 matrix.
**[3:12]** And so to store this in code, you will write x equals np.array and
**[3:18]** then this syntax over here to store these four rows of matrix in the variable x.
**[3:25]** So this creates a 2D array of these eight numbers.
**[3:29]** Matrices can have different dimensions.
**[3:32]** You saw an example of an 2 x 3 matrix and the 4 x 2 matrix.
**[3:38]** A matrix can also be other dimensions like 1 x 2 or 2 x 1.
**[3:44]** And we'll see examples of these on the next slide.
**[3:49]** So what we did previously when setting x to be input feature vectors,
**[3:55]** was set x to be equal to np.array with two square brackets, 200, 17.
**[4:02]** And what that does is this creates a 1 x 2 matrix,
**[4:08]** that is just one row and two columns.
**[4:12]** Let's look at a different example,
**[4:16]** if you were to define x to be np.array but now written like this,
**[4:23]** this creates a 2 x 1 matrix that has two rows and one column.
**[4:30]** Because the first row is just the number 200 and
**[4:34]** the second row, is just the number 17.
**[4:38]** And so this has the same numbers but in a 2 x 1 instead of a 1 x 2 matrix.
**[4:44]** Enough this example on top is also called a row vector,
**[4:48]** is a vector that is just a single row.
**[4:52]** And this example is also called a column
**[4:55]** vector because this vector that just has a single column.
**[4:59]** And the difference between using double square brackets like this
**[5:05]** versus a single square bracket like this, is that whereas the two
**[5:10]** examples on top of 2D arrays where one of the dimensions happens to be 1.
**[5:17]** This example results in a 1D vector.
**[5:22]** So this is just a 1D array that has no rows or columns,
**[5:26]** although by convention we may right x as a column like this.
**[5:32]** So on a contrast this with what we had previously done in the first course,
**[5:38]** which was to write x like this with a single square bracket.
**[5:43]** And that resulted in what's called in Python,
**[5:46]** a 1D vector instead of a 2D matrix.
**[5:49]** And this technically is not 1 x 2 or 2 x 1, is just a linear array with no rows or
**[5:56]** no columns, but it's just a list of numbers.
**[6:00]** So whereas in course one when we're working with linear regression and
**[6:05]** logistic regression, we use these 1D vectors to represent the input features x.
**[6:11]** With TensorFlow the convention is to use matrices to represent the data.
**[6:16]** And why is there this switching conventions?
**[6:18]** Well it turns out that TensorFlow was designed to handle very large datasets and
**[6:24]** by representing the data in matrices instead of 1D arrays,
**[6:28]** it lets TensorFlow be a bit more computationally efficient internally.
**[6:34]** So going back to our original example for the first training, example in
**[6:39]** this dataset with features 200°C in 17 minutes, we were represented like this.
**[6:45]** And so this is actually a 1 x 2 matrix that happens to have one row and
**[6:52]** two columns to store the numbers 217.
**[6:57]** And in case this seems like a lot of details and really complicated
**[7:01]** conventions, don't worry about it all of this will become clearer.
**[7:06]** And you get to see the concrete implementations of the code yourself in
**[7:11]** the optional labs and in the practice labs.
**[7:14]** Going back to the code for carrying out for propagation or
**[7:18]** influence in the neural network.
**[7:20]** When you compute a1 equals layer 1 applied to x, what is a1?
**[7:26]** Well, a1 is actually going to be because the three numbers,
**[7:31]** is actually going to be a 1 x 3 matrix.
**[7:35]** And if you print out a1 you will get something like this
**[7:40]** is tf.tensor 0.2, 0.7, 0.3 as a shape of 1 x 3,
**[7:45]** 1, 3 refers to that this is a 1 x 3 matrix.
**[7:50]** And this is TensorFlow's way of saying that this is a floating point number
**[7:54]** meaning that it's a number that can have a decimal point represented using
**[7:59]** 32 bits of memory in your computer, that's where the float 32 is.
**[8:04]** And what is the tensor?
**[8:05]** A tensor here is a data type that the TensorFlow team had created in order to
**[8:10]** store and carry out computations on matrices efficiently.
**[8:15]** So whenever you see tensor just think of that matrix on these few slides.
**[8:20]** Technically a tensor is a little bit more general than the matrix but for
**[8:25]** the purposes of this course,
**[8:27]** think of tensor as just a way of representing matrices.
**[8:31]** So remember I said at the start of this video that there's the TensorFlow way of
**[8:35]** representing the matrix and the NumPy way of representing matrix.
**[8:39]** This is an artifact of the history of how NumPy and
**[8:43]** TensorFlow were created and unfortunately there are two ways of
**[8:48]** representing a matrix that have been baked into these systems.
**[8:53]** And in fact if you want to take a1 which is a tensor and
**[8:57]** want to convert it back to NumPy array, you can do so with this function a1.numpy.
**[9:04]** And it will take the same data and return it in the form of a NumPy array
**[9:09]** rather than in the form of a TensorFlow array or TensorFlow matrix.
**[9:14]** Now let's take a look at what the activations output the second layer would
**[9:18]** look like.
**[9:19]** Here's the code that we had from before,
**[9:22]** layer 2 is a dense layer with one unit and sigmoid activation and
**[9:26]** a2 is computed by taking layer 2 and applying it to a1 so what is a2?
**[9:31]** A2, maybe a number like 0.8 and
**[9:35]** technically this is a 1 x 1 matrix is a 2D array with one row and
**[9:42]** one column and so it's equal to this number 0.8.
**[9:48]** And if you print out a2, you see that it is a TensorFlow
**[9:53]** tensor with just one element one number 0.8 and it is a 1 x 1 matrix.
**[10:00]** And again it is a float32,
**[10:02]** decimal points number taking up 32 bits in computer memory.
**[10:08]** Once again you can convert from a tensorflow tensor to
**[10:13]** a NumPy matrix using a2.numpy and
**[10:16]** that will turn this back into a NumPy array that looks like this.
**[10:22]** So that hopefully gives you a sense of how data is represented in TensorFlow and
**[10:27]** in NumPy.
**[10:28]** I'm used to loading data and manipulating data in NumPy, but when you pass a NumPy
**[10:34]** array into TensorFlow, TensorFlow likes to convert it to its own internal format.
**[10:39]** The tensor and then operate efficiently using tensors.
**[10:43]** And when you read the data back out you can keep it as a tensor or
**[10:47]** convert it back to a NumPy array.
**[10:50]** I think it's a bit unfortunate that the history of how these library evolved has
**[10:55]** let us have to do this extra conversion work when
**[10:58]** actually the two libraries can work quite well together.
**[11:02]** But when you convert back and forth, whether you're using a NumPy array or
**[11:06]** a tensor, it's just something to be aware of when you're writing code.
**[11:11]** Next let's take what we've learned and
**[11:13]** put it together to actually build a neural network.
**[11:16]** Let's go see that in the next video.
