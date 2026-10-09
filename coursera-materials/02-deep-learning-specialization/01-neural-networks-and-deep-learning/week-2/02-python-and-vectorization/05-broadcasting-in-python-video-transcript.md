---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 2
section: Python and Vectorization
item_title: Broadcasting in Python
duration: 11 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/uBuTv/broadcasting-in-python
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Broadcasting in Python — Transcript

**[0:00]** In the previous video, I mentioned that broadcasting
**[0:03]** is another technique that you can use to make your Python code run faster.
**[0:07]** In this video, let's delve into how broadcasting in Python actually works.
**[0:11]** Let's explore broadcasting with an example.
**[0:14]** In this matrix, I've shown the number of calories from carbohydrates,
**[0:18]** proteins, and fats in 100 grams of four different foods.
**[0:22]** So for example, a 100 grams of apples turns out,
**[0:25]** has 56 calories from carbs, and much less from proteins and fats.
**[0:29]** Whereas, in contrast, a 100 grams of beef has 104 calories from protein and
**[0:35]** 135 calories from fat.
**[0:37]** Now, let's say your goal is to calculate the percentage of calories
**[0:43]** from carbs, proteins and fats for each of the four foods.
**[0:48]** So, for example, if you look at this column and
**[0:52]** add up the numbers in that column you get that 100 grams of apple
**[0:57]** has 56 plus 1.2 plus 1.8 so that's 59 calories.
**[1:02]** And so as a percentage the percentage of
**[1:06]** calories from carbohydrates in an apple would
**[1:11]** be 56 over 59, that's about 94.9%.
**[1:16]** So most of the calories in an apple come from carbs, whereas in contrast,
**[1:22]** most of the calories of beef come from protein and fat and so on.
**[1:27]** So the calculation you want is really to sum up each of the four columns
**[1:33]** of this matrix to get the total number of calories in 100 grams of apples,
**[1:38]** beef, eggs, and potatoes.
**[1:40]** And then to divide throughout the matrix,
**[1:47]** so as to get the percentage of calories from carbs, proteins and
**[1:51]** fats for each of the four foods.
**[1:54]** So the question is, can you do this without an explicit for-loop?
**[2:01]** Let's take a look at how you could do that.
**[2:04]** What I'm going to do is show you how you can set,
**[2:08]** say this matrix equal to three by four matrix A.
**[2:12]** And then with one line of Python code we're going to sum down the columns.
**[2:18]** So we're going to get four numbers corresponding to the total number
**[2:22]** of calories in these four different types of foods,
**[2:25]** 100 grams of these four different types of foods.
**[2:28]** And I'm going to use a second line of Python code to divide each of
**[2:32]** the four columns by their corresponding sum.
**[2:35]** If that verbal description wasn't very clearly,
**[2:37]** hopefully it will be clearer in a second when we look in the Python code.
**[2:40]** So here we are in the Jupiter notebook.
**[2:42]** I've already written this first piece of code to prepopulate
**[2:46]** the matrix A with the numbers we had just now, so we'll hit shift enter and
**[2:49]** just run that, so there's the matrix A.
**[2:51]** And now here are the two lines of Python code.
**[2:55]** First, we're going to compute tau equals a, that sum.
**[2:59]** And x is equals 0 means to sum vertically.
**[3:02]** We'll say more about that in a little bit.
**[3:05]** And then print cal.
**[3:06]** So we'll sum vertically.
**[3:07]** Now 59 is the total number of calories in the apple, 239 was
**[3:13]** the total number of calories in the beef and the eggs and potato and so on.
**[3:19]** And then with a compute percentage
**[3:25]** equals A/cal.reshape 1,4.
**[3:30]** Actually we want percentages, so multiply by 100 here.
**[3:35]** And then let's print percentage.
**[3:40]** Let's run that.
**[3:41]** And so that command we've taken the matrix A and
**[3:46]** divided it by this one by four matrix.
**[3:50]** And this gives us the matrix of percentages.
**[3:52]** So as we worked out kind of by hand just now in the apple there
**[3:57]** was a first column 94.9% of the calories are from carbs.
**[4:02]** Let's go back to the slides.
**[4:04]** So just to repeat the two lines of code we had,
**[4:06]** this is what have written out in the Jupiter notebook.
**[4:09]** To add a bit of detail this parameter,
**[4:13]** (axis = 0), means that you want Python to sum vertically.
**[4:18]** So if this is axis 0 this means to sum vertically,
**[4:21]** where as the horizontal axis is axis 1.
**[4:24]** So be able to write axis 1 or sum horizontally instead of sum vertically.
**[4:28]** And then this command here,
**[4:30]** this is an example of Python broadcasting where you take a matrix A.
**[4:35]** So this is a three by four matrix and you divide it by a one by four matrix.
**[4:43]** And technically, after this first line of codes cal, the variable cal,
**[4:47]** is already a one by four matrix.
**[4:49]** So technically you don't need to call reshape here again, so
**[4:52]** that's actually a little bit redundant.
**[4:54]** But when I'm writing Python codes if I'm not entirely sure what matrix,
**[4:59]** whether the dimensions of a matrix I often would just call a reshape command just to
**[5:04]** make sure that it's the right column vector or the row vector or
**[5:07]** whatever you want it to be.
**[5:09]** The reshape command is a constant time.
**[5:11]** It's a order one operation that's very cheap to call.
**[5:15]** So don't be shy about using the reshape command to make sure that your matrices
**[5:18]** are the size you need it to be.
**[5:21]** Now, let's explain in greater detail how this type of operation works, right?
**[5:27]** We had a three by four matrix and we divided it by a one by four matrix.
**[5:33]** So, how can you divide a three by four matrix by a one by four matrix?
**[5:37]** Or by one by four vector?
**[5:40]** Let's go through a few more examples of broadcasting.
**[5:43]** If you take a 4 by 1 vector and add it to a number, what
**[5:47]** Python will do is take this number and auto-expand
**[5:53]** it into a four by one vector as well, as follows.
**[5:58]** And so the vector [1, 2, 3,
**[6:00]** 4] plus the number 100 ends up with that vector on the right.
**[6:04]** You're adding a 100 to every element, and in fact we use this form of
**[6:09]** broadcasting where that constant was the parameter b in an earlier video.
**[6:14]** And this type of broadcasting works with both column vectors and row vectors,
**[6:19]** and in fact we use a similar form of broadcasting earlier with the constant
**[6:24]** we're adding to a vector being the parameter b in logistic regression.
**[6:29]** Here's another example.
**[6:31]** Let's say you have a two by three matrix and
**[6:35]** you add it to this one by n matrix.
**[6:40]** So the general case would be if you
**[6:45]** have some (m,n) matrix here and
**[6:50]** you add it to a (1,n) matrix.
**[6:55]** What Python will do is copy the matrix m,
**[6:58]** times to turn this into m by n matrix, so instead of this one by
**[7:03]** three matrix it'll copy it twice in this example to turn it into this.
**[7:09]** Also, two by three matrix and we'll add these so
**[7:14]** you'll end up with the sum on the right, okay?
**[7:18]** So you taken, you added 100 to the first column,
**[7:21]** added 200 to second column, added 300 to the third column.
**[7:25]** And this is basically what we did on the previous slide,
**[7:28]** except that we use a division operation instead of an addition operation.
**[7:34]** So one last example, whether you have a (m,n) matrix and
**[7:40]** you add this to a (m,1) vector, (m,1) matrix.
**[7:47]** Then just copy this n times horizontally.
**[7:50]** So you end up with an (m,n) matrix.
**[7:53]** So as you can imagine you copy it horizontally three times.
**[7:56]** And you add those.
**[7:58]** So when you add them you end up with this.
**[8:01]** So we've added 100 to the first row and added 200 to the second row.
**[8:08]** Here's the more general principle of broadcasting in Python.
**[8:12]** If you have an (m,n) matrix and you add or
**[8:17]** subtract or multiply or divide with a (1,n) matrix,
**[8:24]** then this will copy it n times into an (m,n) matrix.
**[8:31]** And then apply the addition, subtraction, and
**[8:33]** multiplication of division element wise.
**[8:37]** If conversely, you were to take the (m,n) matrix and add, subtract, multiply,
**[8:42]** divide by an (m,1) matrix, then also this would copy it now n times.
**[8:49]** And turn that into an (m,n) matrix and then apply the operation element wise.
**[8:54]** Just one of the broadcasting, which is if you have an (m,1) matrix,
**[9:00]** so that's really a column vector like [1,2,3], and you add,
**[9:05]** subtract, multiply or divide by a row number.
**[9:08]** So maybe a (1,1) matrix.
**[9:11]** So such as that plus 100, then you end up copying
**[9:16]** this real number n times until you'll also get another (n,1) matrix.
**[9:23]** And then you perform the operation such as addition on this example element-wise.
**[9:29]** And something similar also works for row vectors.
**[9:38]** The fully general version of broadcasting can do even a little bit more than this.
**[9:43]** If you're interested you can read the documentation for
**[9:49]** NumPy, and look at broadcasting in that documentation.
**[9:52]** That gives an even slightly more general definition of broadcasting.
**[9:56]** But the ones on the slide are the main forms of broadcasting that you end up
**[10:00]** needing to use when you implement a neural network.
**[10:03]** Before we wrap up, just one last comment, which is for
**[10:06]** those of you that are used to programming in either MATLAB or
**[10:10]** Octave, if you've ever used the MATLAB or Octave function bsxfun
**[10:15]** in neural network programming bsxfun does something similar, not quite the same.
**[10:20]** But it is often used for similar purpose as what we use broadcasting in Python for.
**[10:25]** But this is really only for very advanced MATLAB and
**[10:28]** Octave users, if you've not heard of this, don't worry about it.
**[10:31]** You don't need to know it when you're coding up neural networks in Python.
**[10:35]** So, that was broadcasting in Python.
**[10:38]** I hope that when you do the programming homework that broadcasting will allow you
**[10:42]** to not only make a code run faster,
**[10:44]** but also help you get what you want done with fewer lines of code.
**[10:50]** Before you dive into the programming excercise, I want to share with you just
**[10:53]** one more set of ideas, which is that there's some tips and
**[10:56]** tricks that I've found reduces the number of bugs in my Python code and
**[11:00]** that I hope will help you too.
**[11:02]** So with that, let's talk about that in the next video.
