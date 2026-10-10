---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 2
section: Python and Vectorization
item_title: A Note on Python/Numpy Vectors
duration: 7 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/87MUx/a-note-on-python-numpy-vectors
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# A Note on Python/Numpy Vectors — Transcript

**[0:00]** The ability of python to allow you to use broadcasting operations and
**[0:04]** more generally, the great flexibility of the python numpy program language is,
**[0:09]** I think, both a strength as well as a weakness of the programming language.
**[0:14]** I think it's a strength because they create expressivity of the language.
**[0:18]** A great flexibility of the language lets you get a lot done even with just a single
**[0:22]** line of code.
**[0:24]** But there's also weakness because with broadcasting and this great amount of
**[0:28]** flexibility, sometimes it's possible you can introduce very subtle bugs or
**[0:32]** very strange looking bugs, if you're not familiar with all of the intricacies of
**[0:36]** how broadcasting and how features like broadcasting work.
**[0:39]** For example, if you take a column vector and add it to a row vector, you would
**[0:44]** expect it to throw up a dimension mismatch or type error or something.
**[0:48]** But you might actually get back a matrix as a sum of a row vector and
**[0:52]** a column vector.
**[0:54]** So there is an internal logic to these strange effects of Python.
**[0:58]** But if you're not familiar with Python, I've seen some students have very strange,
**[1:03]** very hard to find bugs.
**[1:05]** So what I want to do in this video is share with you some couple tips and
**[1:09]** tricks that have been very useful for me to eliminate or
**[1:12]** simplify and eliminate all the strange looking bugs in my own code.
**[1:17]** And I hope that with these tips and tricks,
**[1:19]** you'll also be able to much more easily write bug-free, python and numpy code.
**[1:25]** To illustrate one of the less intuitive effects of Python-Numpy,
**[1:30]** especially how you construct vectors in Python-Numpy, let me do a quick demo.
**[1:34]** Let's set a = np.random.randn(5),
**[1:40]** so this creates five random Gaussian
**[1:45]** variables stored in array a.
**[1:49]** And so let's print(a) and now it turns out that
**[1:55]** the shape of a when you do this is this five color structure.
**[2:02]** And so this is called a rank 1 array in Python and
**[2:06]** it's neither a row vector nor a column vector.
**[2:09]** And this leads it to have some slightly non-intuitive effects.
**[2:12]** So for example, if I print a transpose, it ends up looking the same as a.
**[2:17]** So a and a transpose end up looking the same.
**[2:20]** And if I print the inner product between a and a transpose, you might think
**[2:25]** a times a transpose is maybe the outer product should give you matrix maybe.
**[2:30]** But if I do that, you instead get back a number.
**[2:34]** So what I would recommend is that when you're coding new networks,
**[2:39]** that you just not use data structures where the shape is 5, or n, rank 1 array.
**[2:46]** Instead, if you set a to be this, (5,1),
**[2:52]** then this commits a to be (5,1) column vector.
**[2:58]** And whereas previously, a and a transpose looked the same,
**[3:02]** it becomes now a transpose, now a transpose is a row vector.
**[3:06]** Notice one subtle difference.
**[3:08]** In this data structure, there are two square brackets when we print a transpose.
**[3:12]** Whereas previously, there was one square bracket.
**[3:14]** So that's the difference between this is really a 1 by
**[3:19]** 5 matrix versus one of these rank 1 arrays.
**[3:23]** And if you print, say, the product between a and a transpose,
**[3:28]** then this gives you the outer product of a vector, right?
**[3:32]** And so, the outer product of a vector gives you a matrix.
**[3:35]** So, let's look in greater detail at what we just saw here.
**[3:40]** The first command that we ran, just now, was this.
**[3:43]** And this created a data structure with
**[3:47]** a.shape was this funny thing (5,) so
**[3:52]** this is called a rank 1 array.
**[3:57]** And this is a very funny data structure.
**[3:58]** It doesn't behave consistently as either a row vector nor a column vector,
**[4:04]** which makes some of its effects nonintuitive.
**[4:06]** So what I'm going to recommend is that when you're doing your programing
**[4:10]** exercises, or in fact when you're implementing logistic regression or
**[4:14]** neural networks that you just do not use these rank 1 arrays.
**[4:21]** Instead, if every time you create an array,
**[4:24]** you commit to making it either a column vector, so
**[4:27]** this creates a (5,1) vector, or commit to making it a row vector,
**[4:32]** then the behavior of your vectors may be easier to understand.
**[4:36]** So in this case, a.shape is going to be equal to 5,1.
**[4:43]** And so this behaves a lot like a, but in fact, this is a column vector.
**[4:48]** And that's why you can think of this as (5,1) matrix, where it's a column vector.
**[4:53]** And here a.shape is going to be 1,5,
**[4:56]** and this behaves consistently as a row vector.
**[5:02]** So when you need a vector, I would say either use this or this, but
**[5:06]** not a rank 1 array.
**[5:07]** One more thing that I do a lot in my code is if I'm not entirely sure what's
**[5:12]** the dimension of one of my vectors, I'll often throw in an assertion statement
**[5:17]** like this, to make sure, in this case, that this is a (5,1) vector.
**[5:21]** So this is a column vector.
**[5:23]** These assertions are really inexpensive to execute, and
**[5:26]** they also help to serve as documentation for your code.
**[5:30]** So don't hesitate to throw in assertion statements like this whenever you
**[5:34]** feel like.
**[5:35]** And then finally, if for some reason you do end up with a rank 1 array,
**[5:39]** You can reshape this, a equals a.reshape
**[5:43]** into say a (5,1) array or a (1,5) array so
**[5:48]** that it behaves more consistently as either column vector or row vector.
**[5:53]** So I've sometimes seen students end up with very hard to track
**[5:57]** because those are the nonintuitive effects of rank 1 arrays.
**[6:01]** By eliminating rank 1 arrays in my old code, I think my code became simpler.
**[6:06]** And I did not actually find it restrictive in terms of things I could
**[6:09]** express in code.
**[6:10]** I just never used a rank 1 array.
**[6:12]** And so takeaways are to simplify your code, don't use rank 1 arrays.
**[6:17]** Always use either n by one matrices,
**[6:19]** basically column vectors, or one by n matrices, or basically row vectors.
**[6:24]** Feel free to toss a lot of insertion statements, so
**[6:26]** double-check the dimensions of your matrices and arrays.
**[6:29]** And also, don't be shy about calling the reshape operation to make sure that your
**[6:34]** matrices or your vectors are the dimension that you need it to be.
**[6:38]** So that,
**[6:39]** I hope that this set of suggestions helps you to eliminate a cause of bugs
**[6:44]** from Python code, and makes the problem exercise easier for you to complete.
