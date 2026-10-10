---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 2
section: Python and Vectorization
item_title: Vectorizing Logistic Regression's Gradient Output
duration: 10 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/IgFnJ/vectorizing-logistic-regressions-gradient-output
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Vectorizing Logistic Regression's Gradient Output — Transcript

**[0:00]** In the previous video,
**[0:01]** you saw how you can use vectorization to compute their predictions.
**[0:05]** The lowercase a's for an entire training set all at the same time.
**[0:11]** In this video, you see how you can use vectorization to also
**[0:15]** perform the gradient computations for all M training samples.
**[0:19]** Again, all sort of at the same time.
**[0:21]** And then at the end of this video,
**[0:22]** we'll put it all together and show how you can derive
**[0:26]** a very efficient implementation of logistic regression.
**[0:29]** So, you may remember that for the gradient computation,
**[0:32]** what we did was we computed dz1 for the first example,
**[0:36]** which could be a1 minus y1 and then dz2 equals
**[0:43]** a2 minus y2 and so on.
**[0:52]** And so on for all M training examples.
**[0:56]** So, what we're going to do is define a new variable,
**[1:01]** dZ is going to be dz1, dz2, dzm.
**[1:08]** Again, all the D lowercase z variables stacked horizontally.
**[1:13]** So, this would be 1 by m matrix or alternatively a m dimensional row vector.
**[1:21]** Now recall that from the previous slide,
**[1:23]** we'd already figured out how to compute capital A which was this: a1 through
**[1:28]** am and we had defined capital Y as y1 through ym.
**[1:36]** Also you know, stacked horizontally.
**[1:39]** So, based on these definitions,
**[1:42]** maybe you can see for yourself that dz can be computed as
**[1:46]** just A minus Y because it's going to be equal to a1 - y1.
**[1:52]** So, the first element, a2 - y2,
**[1:55]** so in the second element and so on.
**[1:59]** And, so this first element a1 - y1 is exactly the definition of dz1.
**[2:06]** The second element is exactly the definition of dz2 and so on.
**[2:11]** So, with just one line of code,
**[2:13]** you can compute all of this at the same time.
**[2:20]** Now, in the previous implementation,
**[2:24]** we've gotten rid of one for loop already but we still had
**[2:27]** this second for loop over training examples.
**[2:31]** So we initialize dw to zero to a vector of zeroes.
**[2:35]** But then we still have to loop over 20 examples where we have
**[2:38]** dw plus equals x1 times dz1,
**[2:43]** for the first training example dw plus equals x2 dz2 and so on.
**[2:50]** So we do the M times and then dw divide equals by M and similarly for B, right?
**[2:56]** db was initialized as 0 and db plus equals dz1.
**[3:03]** db plus equals dz2 down to you know
**[3:09]** dz(m) and db divide equals M. So that's what we had in the previous implementation.
**[3:16]** We'd already got rid of one for loop.
**[3:18]** So, at least now dw is a vector and we went separately updating dw1,
**[3:25]** dw2 and so on.
**[3:26]** So, we got rid of that already but we still
**[3:29]** had the for loop over the M examples in the training set.
**[3:33]** So, let's take these operations and vectorize them.
**[3:36]** Here's what we can do, for
**[3:38]** the vectorized implementation of db, what it's doing is basically summing up,
**[3:42]** all of these dzs and then dividing by m. So,
**[3:47]** db is basically one over m,
**[3:51]** sum from I equals one through m of dzi and
**[3:56]** well all the dzs are in that row vector and so in Python,
**[4:03]** what you do is implement you know,
**[4:04]** 1 over a m times np.
**[4:08]** sum of dz.
**[4:12]** So, you just take this variable and call the np.
**[4:15]** sum function on it and that would give you db.
**[4:19]** How about dw? I'll just write
**[4:22]** out the correct equations who can verify is the right thing to do.
**[4:26]** DW turns out to be one over M,
**[4:28]** times the matrix X times dz transpose.
**[4:34]** And, so kind of see why that's the case.
**[4:37]** This is equal to one over m then the matrix X's,
**[4:41]** x1 through xm stacked up in columns like that and dz
**[4:48]** transpose is going to be dz1 down to dz(m) like so.
**[4:56]** And so, if you figure out what this matrix times this vector works out to be,
**[5:00]** it is turns out to be one over m times x1
**[5:05]** dz1 plus... plus xm dzm.
**[5:12]** And so, this is a n/1 vector and this is what you actually end up with,
**[5:21]** with dw because dw was taking these you know,
**[5:24]** xi dzi and adding them up and so that's what exactly
**[5:27]** this matrix vector multiplication is doing and so again,
**[5:32]** with one line of code you can compute dw.
**[5:35]** So, the vectorized implementation of the derivative calculations is just this,
**[5:40]** you use this line to implement db and use
**[5:44]** this line to implement dw and notice that without a for loop over the training set,
**[5:50]** you can now compute the updates you want to your parameters.
**[5:55]** So now, let's put all together into how you would actually implement logistic regression.
**[6:01]** So, this is our original,
**[6:02]** highly inefficient non vectorize implementation.
**[6:07]** So, the first thing we've done in the previous video was get rid of this volume, right?
**[6:11]** So, instead of looping over dw1,
**[6:14]** dw2 and so on,
**[6:15]** we have replaced this with a vector value dw which is dw+= xi,
**[6:23]** which is now a vector times dz(i).
**[6:28]** But now, we will see that we can also get rid of not
**[6:32]** just a for loop below but also get rid of this for loop.
**[6:36]** So, here is how you do it.
**[6:38]** So, using what we have from the previous slides,
**[6:42]** you would say, capitalZ,
**[6:46]** Z equal to w transpose X + B and the code you is write capital Z equals np.
**[6:57]** w transpose X + B and then a equals sigmoid of capital Z.
**[7:07]** So, you have now computed all of this and all of this for all the values of I.
**[7:12]** Next on the previous slide,
**[7:14]** we said you would compute dz equals A - Y.
**[7:21]** So, now you computed all of this for all the values of i.
**[7:24]** Then, finally dw equals 1/m x
**[7:31]** dz transpose and db equals 1/m of you know, np.
**[7:39]** sum dz.
**[7:43]** So, you've just done forward propagation and back propagation,
**[7:49]** really computing the predictions and computing the derivatives on
**[7:53]** all M training examples without using a for loop.
**[7:57]** And so the gradient descent update then would be you know W
**[8:00]** gets updated as w minus the learning rate times
**[8:04]** dw which was just computed above and B is update as B minus the learning rate times db.
**[8:12]** Sometimes is putting colons to that to denote that as is an assignment,
**[8:17]** but I guess I haven't been totally consistent with that notation.
**[8:21]** But with this, you have just implemented
**[8:25]** a single iteration of gradient descent for logistic regression.
**[8:29]** Now, I know I said that we should get rid of
**[8:32]** explicit for loops whenever you can but if you want to
**[8:35]** implement multiple iterations as
**[8:38]** a gradient descent then you still need a for loop over the number of iterations.
**[8:42]** So, if you want to have a thousand iterations of gradient descent,
**[8:47]** you might still need a for loop over the iteration number.
**[8:53]** There is an outermost for loop like that then I
**[8:55]** don't think there is any way to get rid of that for loop.
**[8:59]** But I do think it's incredibly cool that you can implement
**[9:02]** at least one iteration of gradient descent without needing to use a for loop.
**[9:07]** So, that's it you now have a highly vectorize and
**[9:09]** highly efficient implementation of gradient descent for logistic regression.
**[9:14]** There is just one more detail that I want to talk about in the next video,
**[9:18]** which is in our description here I briefly alluded to this technique called broadcasting.
**[9:24]** Broadcasting turns out to be a technique that Python and
**[9:28]** numpy allows you to use to make certain parts of your code also much more efficient.
**[9:32]** So, let's see some more details of broadcasting in the next video.
