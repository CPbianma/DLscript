---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 1
section: Vectorization(optional)
item_title: Matrix multiplication rules
duration: 10 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/fKqUA/matrix-multiplication-rules
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# Matrix multiplication rules — Transcript

**[0:02]** So let's take a look at the general form of how you multiply two matrices together.
**[0:08]** And then in the last video after this one, we'll take this and
**[0:12]** apply it to the vectorized implementation of a neural network.
**[0:16]** Let's dive in.
**[0:17]** Here's the matrix A, which is a 2 by 3
**[0:21]** matrix because it has two rows and three columns.
**[0:26]** As before I encourage you to think of the columns of this
**[0:31]** matrix as three vectors, vectors a1, a2 and a3.
**[0:37]** And what we're going to do is take A transpose and
**[0:41]** multiply that with the matrix W.
**[0:44]** The first, what is A transpose?
**[0:46]** Well, A transpose is obtained by taking the first column of A and
**[0:50]** laying it on the side like this and then taking the second column of A and
**[0:55]** laying on his side like this.
**[0:57]** And then the third column of A and laying on the side like that.
**[1:00]** And so these rows are now A1 transpose,
**[1:05]** A2 transpose and A3 transpose.
**[1:08]** Next, here's the matrix W.
**[1:12]** I encourage you to think of W as factors w1,
**[1:16]** w2, w3, and w4 stacked together.
**[1:21]** As so let's look at how you then compute A transpose times W.
**[1:26]** Now, notice that I've also used slightly different shades of orange
**[1:31]** to denote the different columns of A, where the same shade corresponds
**[1:36]** to numbers that we think of as grouped together into a vector.
**[1:41]** And that same shade is used to indicate different roles of A transpose because
**[1:46]** the different roles of A transpose are A1 transpose, A2 transpose and A3 transpose.
**[1:51]** And in a similar way,
**[1:53]** I've used different shades to denote the different columns of W.
**[1:57]** Because the numbers are the same shade of blue,
**[2:01]** are the ones that are grouped together to form the vectors w1, w 2, or w3 or w4.
**[2:08]** Now, let's look at how you can compute A transpose times W.
**[2:14]** I'm going to draw vertical bows to the different shades of blue and
**[2:20]** horizontal bars with the different shades of orange to indicate
**[2:25]** which elements of Z that is A transpose W are influenced or
**[2:30]** affected by the different roles of A transpose and
**[2:34]** which are influenced or affected by the different columns of W.
**[2:40]** So for example, let's look at the first Column of W.
**[2:42]** So that's w1 as indicated by the lightest shade of blue here.
**[2:48]** So w1 will influence or will correspond to this
**[2:54]** first column of Z shown here by this lighter shade of blue.
**[3:00]** And the values of this second column of W that is w2 as indicated
**[3:06]** by this second lighter shade of blue will affect the values computed
**[3:11]** into second column of Z and so on for the third and fourth columns.
**[3:18]** Correspondingly, let's look at A transpose.
**[3:21]** A1 transpose is the first row of A transpose as indicated by
**[3:25]** the lightest shade of orange and A1 transpose will effect or
**[3:30]** influence or correspond to the values in the first row of Z.
**[3:35]** And A2 transpose will influence the second row of Z and
**[3:40]** A3 transports will influence or correspond to this third row of Z.
**[3:46]** So let's figure out how to compute the matrix Z,
**[3:50]** which is going to be a 3 by 4 matrix.
**[3:52]** So with 12 numbers altogether.
**[3:55]** Let's start off and figure out how to compute the number in the first row,
**[4:00]** in the first column of Z.
**[4:02]** So this upper left most element here because this is the first row and first
**[4:06]** column corresponding to the lighter shade of orange and the lighter shade of blue.
**[4:11]** The way you compute that is to grab the first row of a transpose and
**[4:16]** the first column of W and take their inner product or the product.
**[4:22]** And so this number is going to be (1,2)
**[4:27]** dot product with (3,4) which is (1 * 3) + (2 * 4) = 11.
**[4:34]** Let's look at the second example.
**[4:36]** How would you compute this element of Z.
**[4:42]** So this is in the third row, row 1, row 2, row 3.
**[4:45]** So this is in row 3 and the second column, column 1, column 2.
**[4:50]** So to compute the number in row 3, column 2 of Z,
**[4:55]** you would now grab row 3 of A transpose and
**[5:00]** column 2 of W and dot product those together.
**[5:05]** Notice that this corresponds to the darkest shade of orange and
**[5:09]** the second lightest shade of blue.
**[5:11]** And to compute this, this is (0.1 * 5) +(0.2 * 6),
**[5:18]** which is (0.5 + 1.2), which is equal to 1.7.
**[5:25]** So to compute the number in row 3, column 2 of Z,
**[5:29]** you grab the third row, row 3 of a transpose and column 2 of W.
**[5:34]** Let's look at one more example and let's see if you can figure this one out.
**[5:40]** This is row 2, column 3 of the matrix Z.
**[5:47]** Why don't you take a look and see if you can figure out which row and
**[5:51]** which column to grab the dot product together and
**[5:54]** therefore what is the number that will go in this element of this matrix.
**[5:59]** Hopefully you got that.
**[6:01]** You should be grabbing row 2 of A transpose and column 3 of W.
**[6:07]** And when you dot product that together you have A2
**[6:12]** transpose w3 is (-1 * 7) + (-2 * 8 ),
**[6:17]** which is (-7 + -16), which is equal to -23.
**[6:22]** And so that's how you compute this element of the matrix Z.
**[6:26]** And it turns out if you do this for every element of the matrix Z, then you can
**[6:31]** compute all of the numbers in this matrix which turns out to look like that.
**[6:36]** Feel free to pause the video if you want and picking the elements and double check
**[6:41]** that the formula we've been going through gives you the right value for Z.
**[6:46]** I just want to point out one last interesting requirement for
**[6:51]** multiplying matrices together, which is that X transpose
**[6:56]** here is a 3 by 2 matrix because it has 3 rows and 2 columns, and
**[7:02]** W here is a 2 by 4 matrix because it has 2 rows and 4 columns.
**[7:07]** One requirement in order to multiply two matrices
**[7:12]** together is that this number must match that number.
**[7:16]** And that's because you can only take dot products between vectors that
**[7:21]** are the same length.
**[7:22]** So you can take the dot product between a vector with two numbers.
**[7:27]** And that's because you can take the inner product between the vector of length
**[7:32]** 2 only with another vector of length 2.
**[7:35]** You can't take the inner product between vector of length 2 with a vector of
**[7:39]** length 3, for example.
**[7:41]** And that's why matrix multiplication is valid only if the number of
**[7:46]** columns of the first matrix, that is A transpose here is equal to the number
**[7:52]** of rolls of the second matrix, that is the number of rolls of W here.
**[7:57]** So that when you take dot products during this process,
**[8:00]** you're taking dot products of vectors of the same size.
**[8:04]** And then the other observation is that the output Z equals a transpose, W.
**[8:12]** The dimensions of Z is 3 by 4.
**[8:15]** And so the output of this multiplication will have the same
**[8:20]** number of rows as X transpose and the same number of columns as W.
**[8:26]** And so that too is another property of matrix multiplication.
**[8:31]** So that's matrix multiplication.
**[8:34]** All these videos are optional.
**[8:35]** So thank you for sticking with me through these.
**[8:38]** And if you're interested later in this week, there are also some purely optional
**[8:43]** quizzes to let you practice some more of these calculations yourself as well.
**[8:48]** Some of that, let's take what we've learned about matrix multiplication and
**[8:52]** applied back to the vectorized implementation of a Neural Network.
**[8:56]** I have to say the first time I understood the vectorized implementation,
**[9:00]** I thought that's actually really cool.
**[9:02]** I've been implementing Neural Networks for
**[9:04]** awhile myself without the vectorized implementation.
**[9:08]** And when I finally understood the vectorized implementation and
**[9:11]** implemented it that way for the first time,
**[9:14]** it ran blazingly much faster than anything I've ever done before.
**[9:18]** And I thought, wow, I wish I had figured this out earlier.
**[9:21]** The vectorized implementation, it is a little bit complicated,
**[9:25]** but it makes your networks run much faster.
**[9:28]** So let's take a look at that in the next video
