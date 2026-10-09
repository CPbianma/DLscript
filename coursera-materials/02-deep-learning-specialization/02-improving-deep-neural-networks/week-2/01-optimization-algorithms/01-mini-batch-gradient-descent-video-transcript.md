---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 2
section: Optimization Algorithms
item_title: Mini-batch Gradient Descent
duration: 11 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/qcogH/mini-batch-gradient-descent
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Mini-batch Gradient Descent — Transcript

**[0:00]** Hello, and welcome back.
**[0:01]** In this week, you learn about optimization algorithms
**[0:04]** that will enable you to train your neural network much faster.
**[0:08]** You've heard me say before that applying machine learning is a highly empirical process,
**[0:12]** is a highly iterative process.
**[0:14]** In which you just had to train a lot of models to find one that works really well.
**[0:18]** So, it really helps to really train models quickly.
**[0:21]** One thing that makes it more difficult is that
**[0:23]** Deep Learning tends to work best in the regime of big data.
**[0:26]** We are able to train neural networks on a huge data set
**[0:29]** and training on a large data set is just slow.
**[0:33]** So, what you find is that having fast optimization algorithms,
**[0:36]** having good optimization algorithms can really
**[0:39]** speed up the efficiency of you and your team.
**[0:41]** So, let's get started by talking about mini-batch gradient descent.
**[0:45]** You've learned previously that vectorization allows
**[0:48]** you to efficiently compute on all m examples,
**[0:51]** that allows you to process your whole training set without an explicit For loop.
**[0:56]** That's why we would take our training examples and stack them
**[1:00]** into these huge matrix capsule Xs.
**[1:04]** X1, X2, X3, and then eventually it goes up to XM training samples.
**[1:12]** And similarly for Y this is Y1 and Y2,
**[1:15]** Y3 and so on up to YM.
**[1:22]** So, the dimension of X was an X by M and this was 1 by M. Vectorization allows
**[1:30]** you to process all M examples relatively
**[1:33]** quickly if M is very large then it can still be slow.
**[1:37]** For example what if M was 5 million or 50 million or even bigger.
**[1:44]** With the implementation of gradient descent on your whole training set,
**[1:48]** what you have to do is,
**[1:49]** you have to process your entire training set
**[1:51]** before you take one little step of gradient descent.
**[1:54]** And then you have to process your entire training sets of
**[1:56]** five million training samples again before
**[1:58]** you take another little step of gradient descent.
**[2:00]** So, it turns out that you can get a faster algorithm if you let gradient descent
**[2:04]** start to make some progress even before you finish processing your entire,
**[2:10]** your giant training sets of 5 million examples.
**[2:14]** In particular, here's what you can do.
**[2:16]** Let's say that you split up your training set into smaller,
**[2:19]** little baby training sets and these baby training sets are called mini-batches.
**[2:27]** And let's say each of your baby training sets have just 1,000 examples each.
**[2:35]** So, you take X1 through X1,000 and you call that your first little baby training set,
**[2:42]** also call the mini-batch.
**[2:43]** And then you take home the next 1,000 examples.
**[2:47]** X1,001 through X2,000 and the next X1,000 examples and come next one and so on.
**[2:56]** I'm going to introduce a new notation. I'm going to call
**[2:59]** this X superscript with curly braces,
**[3:03]** 1 and I am going to call this,
**[3:06]** X superscript with curly braces, 2.
**[3:11]** Now, if you have 5 million training samples total
**[3:15]** and each of these little mini batches has a thousand examples,
**[3:18]** that means you have 5,000 of these because you know, 5,000 times 1,000 equals 5 million.
**[3:24]** Altogether you would have 5,000 of these mini batches.
**[3:31]** So it ends with X superscript curly braces
**[3:33]** 5,000 and then similarly you do the same thing for Y.
**[3:37]** You would also split up your training data for Y accordingly.
**[3:41]** So, call that Y1 then this is Y1,001 through Y2,000.
**[3:50]** This is called, Y2 and so on until you have Y5,000.
**[4:00]** Now, mini batch number T is going to be comprised of XT,
**[4:08]** and YT. And
**[4:12]** that is a thousand training samples with the corresponding input output pairs.
**[4:18]** Before moving on, just to make sure my notation is clear,
**[4:22]** we have previously used superscript round brackets I to index in the training set so X I,
**[4:27]** is the I-th training sample.
**[4:29]** We use superscript, square brackets
**[4:31]** L to index into the different layers of the neural network.
**[4:34]** So, ZL comes from the Z value,
**[4:39]** for the L layer of the neural network and here we are introducing
**[4:42]** the curly brackets T to index into different mini batches.
**[4:48]** So, you have XT, YT. And to check your understanding of these,
**[4:53]** what is the dimension of XT and YT?
**[5:01]** Well, X is an X by M. So,
**[5:04]** if X1 is a thousand training examples or the X values for a thousand examples,
**[5:10]** then this dimension should be Nx by 1,000 and X2 should also be Nx by 1,000 and so on.
**[5:19]** So, all of these should have dimension MX by 1,000 and
**[5:22]** these should have dimension 1 by 1,000.
**[5:29]** To explain the name of this algorithm,
**[5:34]** batch gradient descent, refers to
**[5:37]** the gradient descent algorithm we have been talking about previously.
**[5:40]** Where you process your entire training set all at the same time.
**[5:43]** And the name comes from viewing that as
**[5:46]** processing your entire batch of training samples all at the same time.
**[5:49]** I know it's not a great name but that's just what it's called.
**[5:53]** Mini-batch gradient descent in contrast,
**[5:55]** refers to algorithm which we'll talk about on the next slide
**[5:58]** and which you process is single mini batch XT,
**[6:02]** YT at the same time rather than processing your entire training set XY the same time.
**[6:09]** So, let's see how mini-batch gradient descent works.
**[6:12]** To run mini-batch gradient descent on your training sets you run for T equals
**[6:17]** 1 to 5,000 because we had 5,000 mini batches as high as 1,000 each.
**[6:24]** What are you going to do inside the For loop is basically implement one step of
**[6:29]** gradient descent using XT comma YT.
**[6:38]** It is as if you had a training set of size 1,000 examples and it
**[6:48]** was as if you were to implement the algorithm you are
**[6:51]** already familiar with, but just on this little training set
**[6:54]** size of M equals 1,000. Rather than having an explicit For loop over all 1,000 examples,
**[7:00]** you would use vectorization to process all 1,000 examples sort of all at the same time.
**[7:06]** Let us write this out. First,
**[7:08]** you implement forward prop on the inputs.
**[7:15]** So just on XT. And you do that by implementing Z1 equals W1.
**[7:24]** Previously, we would just have X there, right?
**[7:27]** But now you are processing the entire training set,
**[7:30]** you are just processing the first mini-batch so that it
**[7:32]** becomes XT when you're processing mini-batch
**[7:36]** T. Then you will have A1 equals G1 of Z1,
**[7:45]** a capital Z since this is actually
**[7:48]** a vectorized implementation and so on until you end up with AL,
**[7:57]** as I guess GL of ZL, and then this is your prediction.
**[8:03]** And you notice that here you should use a vectorized implementation.
**[8:09]** It's just that this vectorized implementation processes
**[8:14]** 1,000 examples at a time rather than 5 million examples.
**[8:18]** Next you compute the cost function J which I'm going to write as
**[8:25]** one over 1,000 since here 1,000 is the size of your little training set.
**[8:32]** Sum from I equals one through L of really the loss of
**[8:38]** Y^I YI. And this notation, for clarity,
**[8:45]** refers to examples from the mini batch XT YT.
**[8:53]** And if you're using regularization,
**[8:55]** you can also have this regularization term.
**[8:59]** Move it to the denominator times sum of L,
**[9:03]** Frobenius norm of the weight matrix squared.
**[9:07]** Because this is really the cost on just one mini-batch,
**[9:12]** I'm going to index as cost J with a superscript T in curly braces.
**[9:18]** You notice that everything we are doing is exactly the same as when
**[9:23]** we were previously implementing gradient descent except that instead of doing it on XY,
**[9:29]** you're not doing it on XT YT.
**[9:31]** Next, you implement back prop to
**[9:36]** compute gradients with respect to JT,
**[9:44]** you are still using only XT YT and then you update the weights W,
**[9:54]** really WL, gets updated as WL
**[9:59]** minus alpha D WL and similarly for B.
**[10:08]** This is one pass through your training set using mini-batch gradient descent.
**[10:17]** The code I have written down here is also called doing one epoch of training and
**[10:25]** epoch is a word that means a single pass through the training set.
**[10:34]** Whereas with batch gradient descent,
**[10:38]** a single pass through the training set allows you to take only one gradient descent step.
**[10:44]** With mini-batch gradient descent, a single pass through the training set,
**[10:48]** that is one epoch, allows you to take 5,000 gradient descent steps.
**[10:52]** Now of course you want to take
**[10:55]** multiple passes through the training set which you usually want to,
**[10:58]** you might want another for loop for another while loop out there.
**[11:02]** So you keep taking passes through the training set
**[11:05]** until hopefully you converge or at least approximately converged.
**[11:08]** When you have a large training set,
**[11:10]** mini-batch gradient descent runs much faster than batch gradient descent and
**[11:15]** that's pretty much what everyone in Deep Learning
**[11:17]** will use when you're training on a large data set.
**[11:20]** In the next video, let's delve deeper into mini-batch gradient descent so
**[11:24]** you can get a better understanding of what it is doing and why it works so well.
