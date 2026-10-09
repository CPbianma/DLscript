---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 1
section: Vectorization(optional)
item_title: Matrix multiplication
duration: 9 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/YUhR0/matrix-multiplication
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Matrix multiplication — Transcript

**[0:01]** You know that a matrix is
**[0:04]** just a block or 2D array of numbers.
**[0:07]** What does it mean to multiply
**[0:09]** two matrices? Let's take a look.
**[0:12]** In order to build up to multiplying matrices,
**[0:15]** let's start by looking at
**[0:18]** how we take dot products between vectors.
**[0:21]** Let's use the example of taking
**[0:23]** the dot product between this vector 1,
**[0:26]** 2 and this vector 3, 4.
**[0:29]** If z is the dot product between these two vectors,
**[0:33]** then you compute z by
**[0:35]** multiplying the first element by the first element here,
**[0:38]** it's 1 times 3, plus
**[0:40]** the second element times
**[0:42]** the second element plus 2 times 4,
**[0:44]** and so that's just 3 plus 8,
**[0:47]** which is equal to 11.
**[0:49]** In the more general case,
**[0:52]** if z is the dot product between a vector a and vector w,
**[0:58]** then you compute z by
**[1:00]** multiplying the first element together and
**[1:02]** then the second elements together and the third and so
**[1:04]** on and then adding up all of these products.
**[1:06]** That's the vector, vector dot product.
**[1:10]** It turns out there's
**[1:11]** another equivalent way of writing a dot product,
**[1:15]** which has given a vector a,
**[1:18]** that is, 1, 2 written as a column.
**[1:21]** You can turn this into a row.
**[1:24]** That is, you can turn it from what's
**[1:26]** called a column vector to
**[1:28]** a row vector by taking the transpose of a.
**[1:33]** The transpose of the vector a means you take
**[1:37]** this vector and lay its elements on the side like this.
**[1:42]** It turns out that if you multiply a transpose,
**[1:48]** this is a row vector,
**[1:49]** or you can think of this as a one-by-two matrix with w,
**[1:54]** which you can now think of as a two-by-one matrix.
**[1:59]** Then z equals a transpose times w and this is the same as
**[2:05]** taking the dot product between a and w. To recap,
**[2:12]** z equals the dot product between a and w
**[2:15]** is the same as z equals a transpose,
**[2:19]** that is a laid on the side,
**[2:21]** multiplied by w and
**[2:25]** this will be useful for
**[2:26]** understanding matrix multiplication.
**[2:29]** That these are just two ways of writing
**[2:31]** the exact same computation to arrive at z.
**[2:35]** Now let's look at vector matrix multiplication,
**[2:39]** which is when you take a vector and you
**[2:41]** multiply a vector by a matrix.
**[2:44]** Here again is the vector a 1,
**[2:47]** 2 and a transpose is a laid on the side,
**[2:52]** so rather than this think of this as
**[2:54]** a two-by-one matrix it becomes a one-by-two matrix.
**[2:59]** Let me now create
**[3:02]** a two-by-two matrix w with these four elements,
**[3:05]** 3, 4, 5, 6.
**[3:07]** If you want to compute Z as
**[3:11]** a transpose times w. Let's see how you go about doing so.
**[3:19]** It turns out that Z is going to be a one-by-two matrix,
**[3:28]** and to compute the first value of Z we're
**[3:30]** going to take a transpose, 1,
**[3:33]** 2 here, and multiply that by the first column of w,
**[3:38]** that's 3, 4.
**[3:41]** To compute the first element of Z,
**[3:44]** you end up with 1 times 3 plus 2 times 4,
**[3:49]** which we saw earlier is equal to 11,
**[3:52]** and so the first element of Z is 11.
**[3:55]** Let's figure out what's the second element of Z.
**[3:59]** It turns out you just repeat this process,
**[4:02]** but now multiplying a transpose by
**[4:04]** the second column of w. To do that computation,
**[4:09]** you have 1 times 5 plus 2 times 6,
**[4:15]** which is equal to 5 plus 12, which is 17.
**[4:19]** That's equal to 17.
**[4:22]** Z is equal to this one-by-two matrix, 11 and 17.
**[4:29]** Now, just one last thing,
**[4:32]** and then that'll take us to the end of this video,
**[4:34]** which is how to take
**[4:36]** vector matrix multiplication and generalize
**[4:38]** it to matrix matrix multiplication.
**[4:42]** I have a matrix A with these four elements,
**[4:46]** the first column is 1,
**[4:47]** 2 and the second column is negative 1,
**[4:49]** negative 2 and I want to know how to compute
**[4:54]** a transpose times w. Unlike the previous slide,
**[5:00]** A now is a matrix rather than just the vector or
**[5:03]** the matrix is just a set of
**[5:05]** different vectors stacked together in columns.
**[5:09]** First let's figure out what is A transpose.
**[5:12]** In order to compute A transpose,
**[5:15]** we're going to take the columns of A and
**[5:17]** similar to what happened when you transpose a vector,
**[5:21]** we're going to take the columns
**[5:22]** and lay them on the side,
**[5:23]** one column at a time.
**[5:25]** The first column 1,
**[5:27]** 2 becomes the first row 1,
**[5:29]** 2, let's just laid on side,
**[5:31]** and this second column, negative 1,
**[5:34]** negative 2 becomes laid on the side negative 1,
**[5:38]** negative 2 like this.
**[5:39]** The way you transpose a matrix is you take
**[5:41]** the columns and you just lay the columns on the side,
**[5:44]** one column at a time,
**[5:46]** you end up with this being A transpose.
**[5:49]** Next we have this matrix W,
**[5:53]** which going to write as 3,4, 5,6.
**[5:56]** There's a column 3, 4 and the column 5, 6.
**[6:00]** One way I encourage you to think of matrices.
**[6:03]** At least there's useful for
**[6:05]** neural network implementations is if you see a matrix,
**[6:09]** think of the columns of
**[6:11]** the matrix and if you see the transpose of a matrix,
**[6:15]** think of the rows of that matrix as being grouped
**[6:17]** together as illustrated here,
**[6:19]** with A and A transpose as well as W. Now,
**[6:24]** let me show you how to multiply A transpose and
**[6:28]** W. In order to carry out
**[6:31]** this computation let me call the columns of A,
**[6:36]** a_1 and a_2 and that means that a_1 transpose,
**[6:42]** this the first row of A transpose,
**[6:44]** and a_2 transpose is the second row of A transpose.
**[6:49]** Then same as before,
**[6:51]** let me call the columns of W to be w_1 and w_2.
**[6:57]** It turns out that to compute A transpose W,
**[7:02]** the first thing we need to do is let's
**[7:04]** just ignore the second row of
**[7:08]** A and let's just pay attention to
**[7:10]** the first row of A and let's take this row 1,
**[7:14]** 2 that is a_1 transpose and multiply that with
**[7:17]** W. You already know
**[7:20]** how to do that from the previous slide.
**[7:23]** The first element is 1,
**[7:25]** 2, inner product or dot product we've 3, 4.
**[7:28]** That ends up with 3 times 1 plus 2 times 4, which is 11.
**[7:32]** Then the second element is 1,
**[7:36]** 2 A transpose,
**[7:38]** inner product we've 5, 6.
**[7:40]** There's 5 times 1 plus 6 times 2,
**[7:43]** which is 5 plus 12, which is 17.
**[7:46]** That gives you the first row of Z
**[7:49]** equals A transpose W. All we've done is
**[7:53]** take a_1 transpose and multiply
**[7:56]** that by W. That's
**[7:57]** exactly what we did on the previous slide.
**[8:00]** Next, let's forget a_1 for now,
**[8:04]** and let's just look at a_2 and take
**[8:07]** a_2 transpose and multiply that by W. Now we
**[8:12]** have a_2 transpose times W. To
**[8:16]** compute that first we take negative 1 and
**[8:18]** negative 2 and dot product that with 3, 4.
**[8:21]** That's negative 1 times 3 plus negative
**[8:25]** 2 times 4 and that turns out to be negative 11.
**[8:30]** Then we have to compute
**[8:32]** a_2 transpose times the second column,
**[8:36]** and has negative 1 times 5 plus negative 2 times 6,
**[8:39]** and that turns out to be negative 17.
**[8:43]** You end up with A transpose times W is equal
**[8:46]** to this two-by-two matrix over here.
**[8:50]** Let's talk about the general form
**[8:54]** of matrix matrix multiplication.
**[8:57]** This was an example of how you
**[8:59]** multiply a vector with a matrix,
**[9:02]** or a matrix with
**[9:03]** a matrix is a lot of dot products between
**[9:06]** vectors but ordered in
**[9:07]** a certain way to construct the elements of the upper Z,
**[9:11]** one element at a time.
**[9:13]** I know this was a lot,
**[9:14]** but in the next video,
**[9:16]** let's look at the general form of how
**[9:18]** a matrix matrix multiplication is
**[9:21]** defined and I hope that will make all this clear as well.
**[9:25]** Let's go on to the next video.
