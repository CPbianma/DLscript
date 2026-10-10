---
type: video-transcript
specialization: Machine Learning Specialization
course: "Supervised Machine Learning: Regression and Classification"
week: 3
section: The problem of overfitting
item_title: Regularized linear regression
duration: 9 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/WRULa/regularized-linear-regression
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Regularized linear regression — Transcript

**[0:00]** In this video, we'll figure out
**[0:02]** how to get gradient descent to
**[0:04]** work with regularized linear regression. Let's jump in.
**[0:08]** Here Is a cost function we've come up with in
**[0:10]** the last video for regularized linear regression.
**[0:14]** The first part is the usual squared error cost function,
**[0:18]** and now you have this additional regularization term,
**[0:21]** where Lambda is the regularization parameter,
**[0:24]** and you'd like to find parameters w and
**[0:28]** b that minimize the regularized cost function.
**[0:32]** Previously we were using
**[0:34]** gradient descent for the original cost function,
**[0:37]** just the first term before we
**[0:39]** added that second regularization term,
**[0:42]** and previously, we had
**[0:45]** the following gradient descent algorithm,
**[0:47]** which is that we repeatedly update the parameters w, j,
**[0:51]** and b for j equals 1 through n
**[0:54]** according to this formula
**[0:55]** and b is also updated similarly.
**[0:58]** Again, Alpha is
**[1:00]** a very small positive number called the learning rate.
**[1:03]** In fact, the updates for
**[1:05]** a regularized linear regression look exactly the same,
**[1:08]** except that now the cost,
**[1:10]** J, is defined a bit differently.
**[1:13]** Previously the derivative of J with respect
**[1:16]** to w_j was given by this expression over here,
**[1:20]** and the derivative respect to b was
**[1:23]** given by this expression over here.
**[1:26]** Now that we've added this additional regularization term,
**[1:30]** the only thing that changes is that the expression for
**[1:33]** the derivative with respect to
**[1:35]** w_j ends up with one additional term,
**[1:38]** this plus Lambda over m times w_j.
**[1:43]** And in particular for
**[1:45]** the new definition of the cost function j,
**[1:47]** these two expressions over here,
**[1:50]** these are the new derivatives of J with respect
**[1:53]** to w_j and the derivative of J with respect to b.
**[1:58]** Recall that we don't regularize b,
**[2:01]** so we're not trying to shrink B.
**[2:04]** That's why the updated B remains the same as before,
**[2:07]** whereas the updated w changes because
**[2:10]** the regularization term causes us to try to shrink w_j.
**[2:16]** Let's take these definitions for
**[2:18]** the derivatives and put them back into
**[2:21]** the expression on the left to write out
**[2:23]** the gradient descent algorithm
**[2:25]** for regularized linear regression.
**[2:28]** To implement gradient descent
**[2:31]** for regularized linear regression,
**[2:33]** this is what you would have your code do.
**[2:36]** Here is the update for w_j,
**[2:39]** for j equals 1 through n,
**[2:40]** and here's the update for b.
**[2:42]** As usual, please remember to carry out
**[2:45]** simultaneous updates for all of these parameters.
**[2:49]** Now, in order for you to get this algorithm to work,
**[2:53]** this is all you need to know.
**[2:55]** But what I like to do in
**[2:56]** the remainder of this video is to go over
**[2:58]** some optional material to convey
**[3:01]** a slightly deeper intuition about
**[3:02]** what this formula is actually doing,
**[3:05]** as well as chat briefly about how
**[3:07]** these derivatives are derived.
**[3:09]** The rest of this video is completely optional.
**[3:12]** It's completely okay if you skip the rest of this video,
**[3:16]** but if you have a strong interests
**[3:18]** in math, then stick with me.
**[3:19]** It is always nice to hang out with you here,
**[3:21]** and through these equations,
**[3:23]** perhaps you can build a deeper intuition
**[3:26]** about what the math and what
**[3:27]** the derivatives are doing as well.
**[3:29]** Let's take a look. Let's look at
**[3:32]** the update rule for w_j and rewrite it in another way.
**[3:37]** We're updating w_j as 1 times
**[3:42]** w_j minus Alpha times Lambda over m times w_j.
**[3:49]** I've moved the term from the end to the front here.
**[3:52]** Then minus Alpha times 1 over m,
**[3:57]** and then the rest of that term over there.
**[4:00]** We just rearranged the terms a little bit.
**[4:04]** If we simplify, then we're saying that w_j is updated
**[4:08]** as w_j times 1 minus Alpha times Lambda over m,
**[4:14]** minus Alpha times this other term over here.
**[4:19]** You might recognize the second term as
**[4:22]** the usual gradient descent update
**[4:25]** for unregularized linear regression.
**[4:27]** This is the update for
**[4:29]** linear regression before we had regularization,
**[4:32]** and this is the term we saw in Week 2 of this course.
**[4:37]** The only change we add
**[4:39]** regularization is that instead of w_j being set
**[4:42]** to be equal to w_j minus Alpha times
**[4:46]** this term is now
**[4:48]** w times this number minus the usual update.
**[4:52]** This is what we had in Week 1 of this course.
**[4:56]** What is this first term over here?
**[4:59]** Well, Alpha is a very small positive number, say 0.01.
**[5:05]** Lambda is usually a small number,
**[5:07]** say 1 or maybe 10.
**[5:10]** Let's say lambda is 1 for this example
**[5:13]** and m is the training set size, say 50.
**[5:17]** When you multiply Alpha Lambda over m,
**[5:22]** say 0.01 times 1 divided by 50,
**[5:27]** this term ends up being a small positive number
**[5:30]** , say 0.0002,
**[5:34]** and thus, 1 minus Alpha Lambda
**[5:37]** over m is going to be
**[5:38]** a number just slightly less than 1,
**[5:40]** in this case, 0.9998.
**[5:43]** The effect of this term is that
**[5:46]** on every single iteration of gradient descent,
**[5:49]** you're taking w_j and multiplying it by 0.9998,
**[5:54]** that is by some numbers slightly less than
**[5:56]** one and for carrying out the usual update.
**[5:59]** What regularization is doing on every single iteration
**[6:03]** is you're multiplying w
**[6:05]** by a number slightly less than 1,
**[6:07]** and that has effect of shrinking
**[6:09]** the value of w_j just a little bit.
**[6:13]** This gives us another view on why
**[6:15]** regularization has the effect of
**[6:17]** shrinking the parameters w_j
**[6:19]** a little bit on every iteration,
**[6:21]** and so that's how regularization works.
**[6:24]** If you're curious about how
**[6:26]** these derivative terms were computed,
**[6:29]** I've just one last optional slide that goes through
**[6:32]** just a little bit of
**[6:33]** a calculation of the derivative term.
**[6:35]** Again, this slide and the rest of
**[6:37]** this video are completely optional,
**[6:40]** meaning you won't need any of this to
**[6:41]** do the practice labs and the quizzes.
**[6:44]** Let's step through quickly to derivative calculation.
**[6:48]** The derivative of J with respect to w_j looks like this.
**[7:05]** Recall that f of x for linear regression is defined as
**[7:10]** w dot x plus b or w dot product x plus b.
**[7:16]** It turns out that by the rules of calculus,
**[7:19]** the derivatives look like this,
**[7:21]** is 1 over 2m times the sum i equals 1 through m of
**[7:29]** w dot x plus b minus y
**[7:33]** times 2x_j plus the derivative
**[7:37]** of the regularization term,
**[7:39]** which is Lambda over 2m times 2 w_j.
**[7:45]** Notice that the second term does not have
**[7:49]** the summation term from j equals 1 through n anymore.
**[7:53]** The 2's cancel out here and here,
**[7:56]** and also here and here.
**[7:59]** It simplifies to this expression over here.
**[8:07]** Finally, remember that wx plus b is f of x,
**[8:12]** and so you can rewrite it as this expression down here.
**[8:17]** This is why this expression is used to
**[8:20]** compute the gradient in regularized linear regression.
**[8:24]** You now know how to
**[8:26]** implement regularized linear regression.
**[8:29]** Using this, you really reduce overfitting when you
**[8:31]** have a lot of features and
**[8:33]** a relatively small training set.
**[8:35]** This should let you get linear regression to
**[8:37]** work much better on many problems.
**[8:40]** In the next video,
**[8:41]** we'll take this regularization idea and apply it to
**[8:44]** logistic regression to avoid
**[8:46]** overfitting for logistic regression as well.
**[8:49]** Let's take a look at that in the next video.
