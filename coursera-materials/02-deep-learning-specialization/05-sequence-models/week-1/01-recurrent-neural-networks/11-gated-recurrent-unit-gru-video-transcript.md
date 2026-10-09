---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 1
section: Recurrent Neural Networks
item_title: Gated Recurrent Unit (GRU)
duration: 17 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/agZiL/gated-recurrent-unit-gru
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Gated Recurrent Unit (GRU) — Transcript

**[0:00]** You've seen how a basic RNN works.
**[0:03]** In this video, you learn about the gated recurrent unit,
**[0:06]** which has a modification to the RNN hidden layer
**[0:09]** that makes it much better at
**[0:11]** capturing long-range connections and helps
**[0:13]** a lot with the vanishing gradient problems.
**[0:16]** Let's take a look. You've already seen the formula
**[0:19]** for computing the activations at time t of an RNN.
**[0:23]** It's the activation function applied to the parameter W_a
**[0:27]** times the activations for
**[0:29]** a previous time sediment the current
**[0:31]** input and then plus the bias.
**[0:33]** I'm going to draw this as a picture.
**[0:36]** The RNN units I'm going to draw as a picture,
**[0:39]** drawn as a box which inputs a of t minus 1,
**[0:47]** deactivation for the last timestep and also inputs x^t,
**[0:52]** and these two go together,
**[0:56]** and after some weights
**[0:58]** and after this type of linear calculation,
**[1:01]** if g is a tanh activation function,
**[1:05]** then after the tanh,
**[1:07]** it computes the output of activation, a.
**[1:12]** The output activation a^t might also be parsed to
**[1:18]** say a softmax unit or something that could then
**[1:22]** be used to outputs y hat ^t.
**[1:26]** This is maybe a visualization of the RNN unit of
**[1:31]** the hidden layer of the RNN in terms of a picture.
**[1:35]** I want to show you this picture
**[1:37]** because we're going to use a similar picture to
**[1:38]** explain the GRU or the gated recurrent unit.
**[1:42]** A lot of ideas of GRUs were due
**[1:44]** to these two papers respectively
**[1:47]** by Junyoung Chung, Caglar, Gulcehre,
**[1:50]** KyungHyun Cho, and Yoshua Bengio.
**[1:54]** Sometime is going to refer to this sentence,
**[1:56]** which we'd seen in the last video,
**[1:57]** to motivate that given a sentence like this,
**[2:00]** you might need to remember the cat was
**[2:02]** singular to make sure you understand
**[2:04]** why that was rather than
**[2:06]** were as of the cat was for the cats were full.
**[2:11]** As we read in this sentence from left to right,
**[2:15]** the GRU unit is going to have a new variable called C,
**[2:19]** which stands for cell, for memory cell.
**[2:23]** What the memory cell do is
**[2:25]** it will provide a bit of memory.
**[2:27]** Remember, for example,
**[2:29]** whether cat was singular or plural,
**[2:32]** so that when it gets much further into the sentence,
**[2:34]** it can still work on
**[2:36]** the consideration whether the subject
**[2:38]** of the sentence was singular or plural.
**[2:40]** At time t, the memory cell will have some value c of
**[2:44]** t. What we'll see is that the GRU unit will
**[2:49]** actually output an activation value a of t that's
**[2:52]** equal to c of t. For now I wanted to
**[2:56]** use different symbols c and
**[2:57]** a to denote the memory cell value and
**[3:00]** the output activation value
**[3:02]** even though they're the same and I'm using
**[3:04]** this notation because when we talked about
**[3:06]** LSTMs a little bit later,
**[3:09]** these will be two different values.
**[3:10]** But for now, for the GRU c of t
**[3:13]** is equal to the output activation a of
**[3:16]** t. These are the equations that
**[3:19]** govern the computations of a GRU unit.
**[3:23]** At every time step,
**[3:25]** we're going to consider an overwriting
**[3:27]** the memory cell with a value c tilde of t. This
**[3:31]** going to be a candidate for replacing c of
**[3:34]** t. We're going to compute
**[3:36]** this using an activation function,
**[3:38]** tanh of w_c,
**[3:42]** and so that's the parameter matrix w_c
**[3:45]** and we'll pass it as parameter matrix.
**[3:49]** The previous value of
**[3:50]** the memory cell, the activation value,
**[3:53]** as well as the current input
**[3:56]** value x^t and then plus a bias.
**[3:59]** C tilde of t is going to be
**[4:00]** a candidate for replacing c^t.
**[4:03]** Then the key, really the important idea of the GRU,
**[4:09]** it will be that we'll have a gate.
**[4:12]** The gate I'm going to call Gamma_u.
**[4:15]** This is the capital Greek alphabet, Gamma_u,
**[4:19]** and u stands for update gate.
**[4:24]** This would be a value between 0 and 1.
**[4:28]** To develop your intuition about how GRUs work,
**[4:31]** think of Gamma_u this gate value as being always 0 or 1.
**[4:36]** Although in practice, your computer with
**[4:39]** a sigmoid function applied to this.
**[4:43]** Remember that the sigmoid function looks like this,
**[4:47]** as value is always between 0 and 1.
**[4:51]** For most of the possible ranges of the input,
**[4:54]** the sigmoid function is either very,
**[4:55]** very close to 0 or very,
**[4:57]** very close to 1.
**[4:58]** For intuition, think of Gamma as
**[5:00]** being either 0 or 1 most of the time.
**[5:07]** I chose the alphabet Gamma for this
**[5:10]** because if you look at a gated fence,
**[5:13]** it looks a bit like this, I guess.
**[5:15]** Then there are a lot of Gammas in this fence.
**[5:19]** That's why your Gamma_u we're going to
**[5:21]** use to denote the gate.
**[5:23]** Also Greek alphabet G,
**[5:25]** like G for gate, so G for Gamma and G for gate.
**[5:29]** Then next the key part of the GRU is this equation,
**[5:35]** which is that we have come up
**[5:38]** with a candidate where we're thinking of
**[5:40]** updating C using c tilde
**[5:44]** and then the gate will decide
**[5:45]** whether or not we actually update it.
**[5:48]** The way to think about it is maybe this memory cell C
**[5:53]** is going to be set to either zero or one
**[5:56]** depending on whether the word you're conserving,
**[5:59]** really the subject of the sentence is singular or plural.
**[6:03]** Because it's singular, let's say that we
**[6:05]** set this to one and if it was plural,
**[6:08]** maybe we'll set this as a zero and then the GRU unit will
**[6:12]** memorize the value of the C^t all the way until here,
**[6:18]** where this is still equal to one and
**[6:21]** so that tells it was singular so use the choice was.
**[6:25]** The job of the gate, of gamma u,
**[6:28]** is to decide when do you update this value.
**[6:32]** In particular, when you see the phrase the cat,
**[6:34]** you know that you're talking about a new concept,
**[6:37]** the subject of the sentence cat.
**[6:38]** That would be a good time to update this bit and then
**[6:41]** maybe when you're done using it the cat was full,
**[6:45]** then you know I don't need to memorize
**[6:47]** anymore I can just forget that.
**[6:50]** The specific equation we'll use
**[6:52]** for the GRU is the following;
**[6:55]** which is that the actual value of C^t would be
**[6:58]** equal to this gate times
**[7:02]** the candidate value plus one minus
**[7:07]** the gate times the old value C^t minus one.
**[7:15]** Notice that if the gate,
**[7:18]** if this update value of z equal to one,
**[7:21]** then is saying set the new value of C^t
**[7:24]** equal to this candidate value so that's like over here,
**[7:27]** set the gate equal to one
**[7:29]** so go ahead and update that bit.
**[7:31]** Then for all of these values in the middle,
**[7:34]** you should have the gate equal
**[7:36]** zero so do the same, don't update it,
**[7:40]** just hang on to the old value because
**[7:43]** if gamma u is equal to zero,
**[7:45]** then this would be zero and
**[7:47]** this will be one and so it's just setting
**[7:49]** C^t equal to the old value
**[7:52]** even as you scan the sentence from left to right.
**[7:54]** When the gate is equal to
**[7:56]** zero as saying, don't update it,
**[7:58]** just hang on to the value and don't forget what it's
**[8:01]** value was and so that way,
**[8:03]** even when you get all the way down here,
**[8:05]** hopefully you've just been setting
**[8:07]** C^t equal C^t minus one
**[8:09]** all along and still memorizes the cat was singular.
**[8:13]** Let me also draw a picture to denote the GRU unit.
**[8:19]** By the way, when you look in
**[8:21]** online blog posts and textbooks and tutorials,
**[8:24]** these types of pictures are quite popular for explaining
**[8:27]** GRUs as well as we'll see later LSTM units.
**[8:31]** I personally find the equations easier to understand in
**[8:34]** the pictures so if the picture
**[8:35]** doesn't make sense don't worry about it,
**[8:37]** but I'll just draw it in case it helps some of you.
**[8:41]** The GRU unit inputs
**[8:44]** C^t minus one for the previous time step
**[8:46]** and this happens to be equal to
**[8:48]** 80 minus one so it takes us as input.
**[8:51]** Then it also takes this input X^t.
**[8:55]** Then these two things get combined
**[8:59]** together and with
**[9:01]** some appropriate waiting and some tonnage.
**[9:04]** This gives you c tilde t,
**[9:07]** which is a candidate for replacing C^t and then we have
**[9:11]** a different set of parameters and
**[9:12]** through a sigmoid activation function,
**[9:14]** this gives you gamma u,
**[9:16]** which is the update gate and then finally,
**[9:19]** all of these things combined
**[9:21]** together through another operation.
**[9:23]** I won't write out the formula but
**[9:25]** this box here which are shaded in purple,
**[9:27]** represents this equation which we had down there.
**[9:31]** That's what this purple operation represents
**[9:35]** and it takes as input the gate value,
**[9:39]** the candidate new value,
**[9:41]** that's the gate value again,
**[9:43]** and the old value for C^t it takes as input this,
**[9:46]** this and this, and together they
**[9:49]** generate the new value for the memory cell.
**[9:53]** That's C^t equals a.
**[9:56]** If you wish, you could also use this impulses through
**[9:59]** a soft-max or something to make
**[10:02]** some prediction for Y^t so that is the GRU units.
**[10:09]** These are slightly simplified version of it.
**[10:11]** What is remarkably good at is through the gate
**[10:14]** deciding that when you're
**[10:17]** scanning the sentence from left to right,
**[10:18]** say that that's a good time to update
**[10:20]** one to the memory cell and enter,
**[10:22]** not change it,
**[10:23]** until you get to the point where you really needed to use
**[10:26]** this memory cell that you
**[10:28]** had set even much earlier in the sentence.
**[10:31]** Now, because the gate is quite
**[10:36]** easy to set to zero so long as
**[10:39]** this quantity is a large negative value,
**[10:41]** then up to numerical round-off,
**[10:43]** the update gate will be essentially zero,
**[10:46]** very close to zero.
**[10:48]** When that's the case,
**[10:49]** then this update equation and sub
**[10:51]** setting C^t equals C^t minus one and so
**[10:56]** this is very good at maintaining the value for the cell
**[10:59]** and because gamma can be so close to zero,
**[11:04]** can be 0.000001 or even smaller than that.
**[11:10]** it doesn't suffer from much of
**[11:11]** a vanishing gradient problem because
**[11:13]** in say gamma so close to zero
**[11:15]** that this becomes essentially C^t equals C^t minus
**[11:19]** one and the value of C^t is maintained pretty much
**[11:23]** exactly even across many times that.
**[11:27]** This can help significantly
**[11:29]** with the vanishing gradient problem
**[11:30]** and therefore allowing your network to
**[11:32]** learn even very long-range dependencies,
**[11:35]** such as the cat and was are related
**[11:38]** even if they are separated by
**[11:39]** a lot of words in the middle.
**[11:41]** Now, I just want to talk over
**[11:43]** some more details of how you implement this.
**[11:46]** In the equations have written,
**[11:50]** C^t can be a vector.
**[11:53]** If you have 100-dimensional hidden activation value,
**[11:57]** then C^t can be 100-dimensional Zai,
**[12:00]** and so C^t would also be the same dimension and
**[12:04]** Gamma would also be
**[12:06]** the same dimension as
**[12:08]** the other things I'm drawing in boxes.
**[12:10]** In that case, these asterisks
**[12:12]** are actually element-wise multiplication.
**[12:16]** Here, if the gates
**[12:20]** is 100-dimensional vector, what it is,
**[12:22]** is really 100-dimensional vector of bits,
**[12:27]** the value is mostly 0 and 1,
**[12:30]** that tells you of this 100-dimensional memory cell,
**[12:33]** which are the bits you want to update.
**[12:36]** Of course in practice,
**[12:37]** Gamma won't be exactly`0 and 1,
**[12:39]** sometimes I'll say values in the middle as well.
**[12:42]** There is convenient for intuition to
**[12:43]** think of it as mostly taking
**[12:45]** on values that are pretty much exactly 0,
**[12:48]** or pretty much exactly 1.
**[12:50]** What these element-wise multiplications do is it
**[12:54]** just tells you GRU
**[13:02]** which are the dimensions of
**[13:04]** your memory cell vector to update at every time step.
**[13:07]** You can choose to keep some bits
**[13:09]** constant while updating other bits.
**[13:11]** For example, maybe you'll use one-bit to
**[13:13]** remember the singular or plural cat,
**[13:17]** and maybe you'll use some other bits
**[13:19]** to realize that you're talking about food.
**[13:21]** Because we talked about eating and talk about foods,
**[13:25]** then you'd expect to
**[13:26]** talk about whether the cat is full later.
**[13:28]** You can use different bits and change
**[13:30]** only a subset of the bits at every point in time.
**[13:32]** You now understand the most important ideas that a GRU.
**[13:36]** What I presented on this slide is actually
**[13:38]** a slightly simplified GRU unit.
**[13:42]** Let me describe the full GRU unit.
**[13:45]** To do that, let me copy the three main equations.
**[13:50]** This one, this one,
**[13:53]** and this one to the next slide.
**[13:55]** Here they are. For the full GRU units,
**[14:00]** I'm sure they'll make one change to this,
**[14:01]** which is for the first equation which was calculating
**[14:04]** the candidate new value for the memory cell,
**[14:08]** I'm going to add just one term.
**[14:09]** They pushed that a little bit to the right,
**[14:11]** and I'm going to add one more gate.
**[14:14]** This is another gate
**[14:17]** Gamma r. You can think of r as standing for relevance.
**[14:22]** This gate Gamma r tells you how relevant is C^t
**[14:26]** minus 1 to computing the next candidate for C^t.
**[14:32]** This gate Gamma r is computed pretty
**[14:36]** much as you expect with a new parameter matrix w _r,
**[14:40]** and then the same things as input x_t plus b_r.
**[14:47]** As you can imagine, there are
**[14:49]** multiple ways to design these types of neural networks,
**[14:52]** and why do we have Gamma r?
**[14:54]** Why not use a simpler version from the previous slides?
**[14:59]** It turns out that over many years,
**[15:01]** researchers have experimented with
**[15:02]** many different possible versions of how
**[15:05]** to design these units
**[15:07]** to try to have longer range connections.
**[15:09]** To try to have
**[15:11]** model long-range effects and
**[15:13]** also address vanishing gradient problems.
**[15:15]** The GRU is one of
**[15:17]** the most commonly used versions that researchers
**[15:20]** have converged to and then found as
**[15:21]** robust and useful for many different problems.
**[15:24]** If you wish, you could try to invent
**[15:26]** a new versions of these units if you want,
**[15:28]** but the GRU is a standard one,
**[15:31]** is just commonly used.
**[15:32]** Although you can imagine that
**[15:33]** researchers have tried other versions
**[15:36]** that are similar but not exactly the
**[15:37]** same as what I'm writing down here as well.
**[15:41]** The other common version is called an LSTM,
**[15:45]** which stands for Long, Short-term Memory,
**[15:47]** which we'll talk about in the next video.
**[15:49]** But GRUs and LSTMs are
**[15:51]** two specific instantiations of
**[15:54]** this set of ideas that are most commonly used.
**[15:57]** Just one note on notation.
**[15:59]** I tried to define
**[16:00]** a consistent notation to
**[16:02]** make these ideas easier to understand.
**[16:04]** If you look at the academic literature,
**[16:13]** sometimes you'll see people use an alternative notation,
**[16:16]** there would be H tilde there, U,
**[16:18]** R and H to refer to these quantities as well.
**[16:21]** They try to use a more consistent notation between GRUs
**[16:25]** and LSTMs as well as using a more consistent notation,
**[16:28]** Gamma to refer to the gains
**[16:30]** to hopefully make these ideas easier to understand.
**[16:33]** That's it for the GRU,
**[16:36]** for the Gated Recurrent Unit.
**[16:37]** This is one of the ideas in RNNs
**[16:39]** that has enabled them to become much
**[16:41]** better at capturing very long-range dependencies
**[16:44]** as made RNNs much more effective.
**[16:47]** Next, as I briefly mentioned,
**[16:49]** the other most commonly used
**[16:50]** deviation of this class of ideas is
**[16:52]** something called the LSTM
**[16:54]** unit or the Long, Short-term Memory unit.
**[16:56]** Let's take a look at that in the next video.
