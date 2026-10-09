---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 1
section: Recurrent Neural Networks
item_title: Long Short Term Memory (LSTM)
duration: 10 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/KXoay/long-short-term-memory-lstm
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Long Short Term Memory (LSTM) — Transcript

**[0:00]** In the last video, you learn about the GRU, the Gated Recurring Unit and how
**[0:05]** that can allow you to learn very long range connections in a sequence.
**[0:09]** The other type of unit that allows you to do this very well is the LSTM or
**[0:13]** the long short term memory units.
**[0:15]** And this is even more powerful than the GRU, let's take a look.
**[0:20]** Here the equations from the previous video for the GRU and for
**[0:24]** the GRU we had a t = c t and two gates the update gate and the relevance gate.
**[0:30]** c(tilde) t, which is a candidate for replacing the memory cell.
**[0:35]** And then we use the gate, the update gate gamma Wu to decide whether or
**[0:39]** not to update c t  using c(tilde) t.
**[0:42]** The LSTM is an even slightly more powerful and more general version of the GRU and
**[0:50]** it's due to set hook writer and Jurgen Schmidt Huber.
**[0:55]** And this was a really seminal paper, there's a huge impact on sequence
**[0:59]** modeling, although I think this paper is one of the more difficult ones to read.
**[1:04]** It goes quite a lot into the theory of vanishing gradients.
**[1:08]** And so I think more people have learned about the details of LSTM through maybe
**[1:12]** other places than from this particular paper, even though I think this paper has
**[1:16]** had a wonderful impact on the deep learning community.
**[1:19]** But these are the equations that govern the LSTM, so
**[1:23]** the will continue to the memory cell c and the candidate value for
**[1:29]** updating it c(tilde) t  will be this.
**[1:32]** And so notice that for the LSTM,
**[1:37]** we will no longer have the case that a t is equal to c t.
**[1:45]** So this is what we use and so this is like the equation on the left except
**[1:50]** that with now more use a t there or a t-1, c t-1 and
**[1:54]** we are not using this
**[1:58]** gamma r this relevance. Although you can have a deviation of the LSTM and we put that
**[2:02]** back in but with a more common version of the LSTM doesn't bother with that.
**[2:08]** And then we will have an update gate same as before.
**[2:12]** So w update and I'm going to use a t-1 here,
**[2:17]** ct +bu and
**[2:22]** one new property of the LSTM is instead of having one update gate control
**[2:28]** both of these terms, we're going to have two separate terms.
**[2:32]** So instead of gamma u and 1- gamma u were going to have gamma u here
**[2:37]** and for gate k we should call gamma f.
**[2:42]** So this gate gamma f is going to be sigmoid of, pretty much what you'd expect.
**[2:50]** c t  plus
**[2:53]** bf, and then we're going to have a new output gate
**[2:58]** which is sigmoid of Wo and then again,
**[3:03]** pretty much what you'd expect plus bo.
**[3:10]** And then the update value to the memory cell will be c t equals
**[3:15]** gamma u then this asterisk in those element wise multiplication.
**[3:21]** There's a vector vector, element wise multiplication plus and
**[3:26]** instead of one minus gamma u were going to have a separate for
**[3:31]** gate gamma f times c t-1.
**[3:34]** So this gives the memory cell the option of keeping the old value c t-1 and
**[3:40]** then just adding to it this new value c(tilde) t.
**[3:44]** So use a separate update and forget gates right?
**[3:49]** So this stands on update.
**[3:52]** Forget and output gates and
**[3:55]** then finally instead of 80 equals c t.
**[4:01]** Is a t equal to the output gate element wise multiply with c t.
**[4:10]** So these are the equations that govern the LSTM.
**[4:14]** And you can tell it has three gates instead of two.
**[4:17]** So it's a bit more complicated and places against in slightly different places.
**[4:23]** So here again are the equations governing the behavior of the LSTM.
**[4:30]** Once again it's traditional to explain these things using pictures, so
**[4:34]** let me draw one here.
**[4:35]** And if these pictures are too complicated don't worry about it,
**[4:39]** I probably find the equations easier to understand than the picture but
**[4:43]** just show the picture here for the intuitions it conveys.
**[4:46]** The particular picture here was very much inspired by a blog post due to
**[4:50]** Chris Kohler titled Understanding LSTM networks.
**[4:54]** And the diagram drawn here is quite similar to one that he drew in his
**[4:57]** blog post.
**[4:58]** But the key things to take away from this picture or
**[5:01]** maybe that you use a t-1 and x t to compute all the gate values.
**[5:06]** So in this picture you have a t-1 and x t coming together to compute
**[5:11]** a forget gate to compute the update gates and the computer the output gate.
**[5:16]** And they also go through a tarnish to compute a c(tilde) t.
**[5:21]** And then these values are combined in these complicated ways with element wise multiplies and so on
**[5:26]** to get a c t from the previous c t -1.
**[5:32]** Now one element of this is interesting is if you hook up a bunch of these in parallel
**[5:36]** so that's one of them and you connect them, connect these temporarily.
**[5:41]** So there's the input x 1, then x 2, x 3.
**[5:45]** So you can take these units and just hook them up as follows where the
**[5:52]** output a for a period of time, 70 input at the next time set.
**[5:56]** And similarly for C and I've simplified the diagrams a little bit at the bottom.
**[6:02]** And one cool thing about this, you notice is that this is a line at the top that shows how
**[6:07]** so long as you said the forget and the update gates, appropriately,
**[6:12]** it is relatively easy for the LSTM to have some value C0 and
**[6:18]** have that be passed all the way to the right to have, maybe C3 equals C0.
**[6:23]** And this is why the LSTM as well as the GRU is very good at
**[6:27]** memorizing certain values.
**[6:30]** Even for a long time for certain real values stored in
**[6:34]** the memory cells even for many, many times steps.
**[6:40]** So that's it for the LSTM,
**[6:44]** as you can imagine, there are also a few variations on this that people use.
**[6:48]** Perhaps the most common one, is that instead of just having the gate values
**[6:53]** be dependent only on a t-1, xt.
**[6:57]** Sometimes people also sneak in there the value c t -1 as well.
**[7:05]** This is called a peephole connection.
**[7:09]** Not a great name maybe, but if you see peephole connection,
**[7:14]** what that means is that the gate values may depend not just on a t-1 but
**[7:19]** and on x t but also on the previous memory cell value.
**[7:23]** And the peephole connection can go into all three of these gates computations.
**[7:28]** So that's one common variation you see of LSTMs one technical
**[7:33]** detail is that these are say 100 dimensional vectors.
**[7:38]** If you have 100 dimensional hidden memory cell union.
**[7:41]** So is this and so say fifth element of
**[7:46]** c t-1 affects only the fifth element of the correspondent gates.
**[7:51]** So that relationship is 1 to 1 where not every element
**[7:55]** of the 100 dimensional c t-1 can affect all elements of the gates, but
**[7:59]** instead the first element of c t-1 affects the first element of the gates.
**[8:04]** Second element affects second elements and so on.
**[8:07]** But if you ever read the paper and see someone
**[8:09]** talk about the peephole connection, that's what they mean,
**[8:13]** that c t -1 is used to affect the gate value as well.
**[8:16]** So that's it for the LSTM, when should you use a GRU and when should you use an LSTM.
**[8:23]** There is a widespread consensus in this.
**[8:25]** And even though I presented GRUs first in the history of deep learning, LSTMs
**[8:30]** actually came much earlier and then GRUs were relatively recent invention that were
**[8:36]** maybe derived as partly a simplification of the more complicated LSTM model.
**[8:41]** Researchers have tried both of these models on many different problems and
**[8:45]** on different problems the different algorithms will win out.
**[8:47]** So there isn't a universally superior algorithm,
**[8:51]** which is why I want to show you both of them.
**[8:53]** But I feel like when I am using these,
**[8:56]** the advantage of the GRU is that it's a simpler model.
**[9:00]** And so it's actually easier to build a much bigger network only has two gates, so
**[9:05]** computation runs a bit faster so it scales the building, somewhat bigger models.
**[9:10]** But the LSTM is more powerful and
**[9:12]** more flexible since there's three gates instead of two.
**[9:15]** If you want to pick one to use,
**[9:17]** I think LSTM has been the historically more proven choice.
**[9:21]** So if you had to pick one, I think most people today will still use
**[9:25]** the LSTM as the default first thing to try.
**[9:28]** Although I think the last few years GRUs have been gaining a lot of momentum and
**[9:33]** I feel like more and
**[9:34]** more teams are also using GRUs because they're a bit simpler but often were,
**[9:38]** just as well and it might be easier to scale them to even bigger problems.
**[9:43]** So that's it for LSTMs with either GRUs or LSTMS, you'll be able to
**[9:48]** build new networks that can capture much longer range dependencies.
