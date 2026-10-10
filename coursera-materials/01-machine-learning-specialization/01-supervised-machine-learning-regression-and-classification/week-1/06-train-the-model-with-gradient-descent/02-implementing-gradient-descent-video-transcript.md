---
type: video-transcript
specialization: Machine Learning Specialization
course: "Supervised Machine Learning: Regression and Classification"
week: 1
section: Train the model with gradient descent
item_title: Implementing gradient descent
duration: 10 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/TXDBu/implementing-gradient-descent
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Implementing gradient descent — Transcript

**[0:03]** Let's take a look at how you can actually
**[0:06]** implement the gradient descent algorithm.
**[0:09]** Let me write down the gradient descent algorithm.
**[0:13]** Here it is. On each step,
**[0:16]** w, the parameter,
**[0:18]** is updated to the old value of w minus
**[0:22]** Alpha times this term d/dw
**[0:27]** of the cos function J of wb.
**[0:30]** What this expression is saying is,
**[0:32]** after your parameter w by taking the current value of
**[0:36]** w and adjusting it a small amount,
**[0:40]** which is this expression on the right,
**[0:43]** minus Alpha times this term over here.
**[0:48]** If you feel like there's a lot
**[0:51]** going on in this equation,
**[0:53]** it's okay, don't worry about it.
**[0:55]** We'll unpack it together.
**[0:57]** First, this equal notation here.
**[1:01]** Now, since I said we're assigning
**[1:03]** w a value using this equal sign,
**[1:06]** so in this context,
**[1:08]** this equal sign is the assignment operator.
**[1:11]** Specifically, in this context,
**[1:13]** if you write code that says a equals c,
**[1:17]** it means take the value c and store it in your computer,
**[1:21]** in the variable a.
**[1:23]** Or if you write a equals a plus 1,
**[1:26]** it means set the value of a to be equal to a plus 1,
**[1:29]** or increments the value of a by one.
**[1:33]** The assignment operator encoding is
**[1:36]** different than truth assertions in mathematics.
**[1:41]** Where if I write a equals c,
**[1:43]** I'm asserting, that is,
**[1:45]** I'm claiming that the values
**[1:47]** of a and c are equal to each other.
**[1:50]** Hopefully, I will never write a truth assertion a equals
**[1:53]** a plus 1 because that just can't possibly be true.
**[1:57]** In Python and in other programming languages,
**[2:01]** truth assertions are sometimes written as equals equals,
**[2:05]** so you may see oh,
**[2:06]** that says a equals equals c if you're
**[2:10]** testing whether a is equal to c. But in math notation,
**[2:14]** as we conventionally use it,
**[2:15]** like in these videos,
**[2:17]** the equal sign can be used for
**[2:19]** either assignments or for truth assertion.
**[2:23]** I try to make sure I was clear
**[2:25]** when I write an equal sign,
**[2:26]** whether we're assigning a value to a variable,
**[2:29]** or whether we're asserting the truth of
**[2:31]** the equality of two values.
**[2:34]** Now, this dive more deeply
**[2:37]** into what the symbols in this equation means.
**[2:39]** The symbol here is the Greek alphabet Alpha.
**[2:45]** In this equation, Alpha is also called the learning rate.
**[2:50]** The learning rate is usually a small positive number
**[2:54]** between 0 and 1 and it might be say, 0.01.
**[2:58]** What Alpha does is,
**[3:00]** it basically controls how
**[3:02]** big of a step you take downhill.
**[3:05]** If Alpha is very large,
**[3:08]** then that corresponds to
**[3:09]** a very aggressive gradient descent procedure
**[3:12]** where you're trying to take huge steps downhill.
**[3:15]** If Alpha is very small,
**[3:17]** then you'd be taking small baby steps downhill.
**[3:20]** We'll come back later to dive more deeply into
**[3:23]** how to choose a good learning rate Alpha.
**[3:26]** Finally, this term here,
**[3:29]** that's the derivative term of the cost function J.
**[3:33]** Let's not worry about the details
**[3:35]** of this derivative right now.
**[3:36]** But later on, you'll get to
**[3:38]** see more about the derivative term.
**[3:40]** But for now, you can think of
**[3:42]** this derivative term that I drew
**[3:44]** a magenta box around as telling you
**[3:46]** in which direction you want to take your baby step.
**[3:49]** In combination with the learning rate Alpha,
**[3:53]** it also determines the size
**[3:55]** of the steps you want to take downhill.
**[3:57]** Now, I do want to mention that
**[4:00]** derivatives come from calculus.
**[4:02]** Even if you aren't familiar with
**[4:04]** calculus, don't worry about it.
**[4:06]** Even without knowing any calculus,
**[4:09]** you'd be able to figure out all you need
**[4:10]** to know about this derivative term
**[4:12]** in this video and the next. One more thing.
**[4:16]** Remember your model has two parameters,
**[4:19]** not just w, but also b.
**[4:22]** You also have an assignment operations
**[4:25]** update the parameter b that looks very similar.
**[4:28]** b is assigned the old value of b minus
**[4:33]** the learning rate Alpha times
**[4:36]** this slightly different derivative term,
**[4:39]** d/db of J of wb.
**[4:42]** Remember in the graph of the surface plot
**[4:46]** where you're taking baby steps
**[4:48]** until you get to the bottom of the value,
**[4:50]** well, for the gradient descent algorithm,
**[4:53]** you're going to repeat
**[4:54]** these two update steps until the algorithm converges.
**[4:57]** By converges, I mean that you
**[5:00]** reach the point at a local minimum where
**[5:03]** the parameters w and b no longer
**[5:05]** change much with each additional step that you take.
**[5:09]** Now, there's one more subtle detail
**[5:13]** about how to correctly in semantic gradient descent,
**[5:16]** you're going to update two parameters, w and b.
**[5:20]** This update takes place for both parameters, w and b.
**[5:25]** One important detail is that for gradient descent,
**[5:30]** you want to simultaneously update w and b,
**[5:35]** meaning you want to update
**[5:37]** both parameters at the same time.
**[5:39]** What I mean by that, is that in this expression,
**[5:43]** you're going to update w from the old w to a new w,
**[5:48]** and you're also updating b from
**[5:50]** its oldest value to a new value of b.
**[5:54]** The way to implement this is to compute the right side,
**[5:58]** computing this thing for w and b,
**[6:02]** and simultaneously at the same time,
**[6:05]** update w and b to the new values.
**[6:10]** Let's take a look at what this means.
**[6:13]** Here's the correct way to implement
**[6:16]** gradient descent which does a simultaneous update.
**[6:19]** This sets a variable temp_w equal to that expression,
**[6:24]** which is w minus that term here.
**[6:27]** There's also a set in another variable temp_b to that,
**[6:31]** which is b minus that term.
**[6:33]** You compute both for hand sides, both updates,
**[6:36]** and store them into variables temp_w and temp_b.
**[6:40]** Then you copy the value of temp_w into w,
**[6:46]** and you also copy the value of temp_b into b.
**[6:51]** Now, one thing you may notice is that this value of
**[6:55]** w is from the for w gets updated.
**[7:00]** Here, I noticed that the pre-update w
**[7:03]** is where it goes into the derivative term over here.
**[7:07]** In contrast, here is
**[7:10]** an incorrect implementation of
**[7:12]** gradient descent that does not do a simultaneous update.
**[7:15]** In this incorrect implementation,
**[7:18]** we compute temp_w,
**[7:20]** same as before, so far that's okay.
**[7:23]** Now here's where things start to differ.
**[7:26]** We then update w with the value in
**[7:29]** temp_w before calculating the new value
**[7:33]** for the other parameter to be.
**[7:35]** Next, we calculate temp_b as b minus that term here,
**[7:40]** and finally, we update b with the value in temp_b.
**[7:45]** The difference between the right-hand side and
**[7:47]** the left-hand side implementations
**[7:49]** is that if you look over here,
**[7:51]** this w has already been updated to this new value,
**[7:55]** and this is updated w that actually
**[7:58]** goes into the cost function j of w, b.
**[8:02]** It means that this term here on the right is not the
**[8:05]** same as this term over here that you see on the left.
**[8:10]** That also means this temp_b term on
**[8:15]** the right is not quite the
**[8:16]** same as the temp b term on the left,
**[8:20]** and thus this updated value for
**[8:22]** b on the right is not the same
**[8:24]** as this updated value for variable b on the left.
**[8:29]** The way that gradient descent is implemented in code,
**[8:32]** it actually turns out to be more natural to implement
**[8:35]** it the correct way with simultaneous updates.
**[8:39]** When you hear someone talk about gradient descent,
**[8:42]** they always mean the gradient descents where you
**[8:44]** perform a simultaneous update of the parameters.
**[8:48]** If however, you were
**[8:50]** to implement non-simultaneous update,
**[8:53]** it turns out it will probably work more or less anyway.
**[8:57]** But doing it this way isn't
**[8:59]** really the correct way to implement it,
**[9:00]** is actually some other algorithm
**[9:02]** with different properties.
**[9:04]** I would advise you to just stick to
**[9:06]** the correct simultaneous update and
**[9:08]** not use this incorrect version on the right.
**[9:12]** That's gradient descent.
**[9:14]** In the next video,
**[9:16]** we'll go into details of
**[9:17]** the derivative term which you saw in this video,
**[9:20]** but that we didn't really talk about in detail.
**[9:22]** Derivatives are part of calculus,
**[9:25]** and again, if you're not familiar with
**[9:27]** calculus, don't worry about it.
**[9:29]** You don't need to know calculus at all in order to
**[9:31]** complete this course or this specialization,
**[9:34]** and you have all the information you need
**[9:36]** in order to implement gradient descent.
**[9:39]** Coming up in the next video,
**[9:41]** we'll go over derivatives together,
**[9:43]** and you come away with
**[9:45]** the intuition and knowledge you need to
**[9:47]** be able to implement and apply gradient descent yourself.
**[9:51]** I think that'll be an exciting thing
**[9:53]** for you to know how to implement.
**[9:55]** Let's go on to the next video to see how to do that.
