---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 4
section: Transformers
item_title: Multi-Head Attention
duration: 8 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/jsV2q/multi-head-attention
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Multi-Head Attention — Transcript

**[0:03]** Let's jump in and learn about the multi head attention mechanism.
**[0:07]** The notation gets a little bit complicated, but
**[0:10]** the thing to keep in mind is basically just a big for-loop over the self
**[0:14]** attention mechanism that you learned about in the last video.
**[0:18]** Let's take a look each time you calculate self attention for
**[0:23]** a sequence is called a head.
**[0:26]** And thus the name multi head attention refers to if you do what you saw in
**[0:31]** the last video, but a bunch of times let's walk through how this works.
**[0:36]** Remember that you got the vectors Q K and
**[0:40]** V for each of the input terms by multiplying
**[0:45]** them by a few matrices, W Q W K and W V.
**[0:50]** With multi head attention, you take that same set of query key and
**[0:54]** value vectors as inputs.
**[0:56]** So the q, k, v values written down here and calculate multiple self attentions.
**[1:03]** So the first of these, you multiply the k,
**[1:08]** q, v matrices with weight matrices,
**[1:12]** w one q, w one k and w one v.
**[1:16]** And so these three values give you a new set of query key and
**[1:22]** value vectors for the first words.
**[1:26]** And you do the same thing for each of the other words.
**[1:31]** For the sake of intuition, you might find it useful to think of w one q,
**[1:38]** w one k and w one v as being learned to help ask and
**[1:42]** answer the question, what's happening there?
**[1:47]** And so this is just more or less the self attention
**[1:51]** example that we walked through earlier in the previous video.
**[1:55]** After finishing you may think, we have w q, w one q, w one k,
**[2:01]** w one v, I learn to help you ask and answer the question, what's happening?
**[2:07]** And so with this computation, the word visite gives the best answer to
**[2:12]** what's happening, which is why I've highlighted with this blue
**[2:17]** arrow over here to represent that the inner product between the key for
**[2:22]** l'Afrique has the highest value with the query for visite,
**[2:26]** which is the first of the questions we'll get to ask.
**[2:30]** So this is how you get the representation for l'Afrique and
**[2:34]** you do the same for Jane, visite and the other words en septembre.
**[2:39]** So you end up with five vectors to represent the five words in the sequence.
**[2:43]** So this is a computation you carry out for
**[2:46]** the first of the several heads you use in multi head attention.
**[2:52]** And so you would step through exactly the same calculation that we had just now for
**[2:57]** l'Afrique and for the other words and end up with the same attention values,
**[3:02]** a one through a five that we had in the previous video.
**[3:06]** But now we're going to do this not once but a handful of times.
**[3:11]** So that rather than having one head, we may now have eight heads,
**[3:15]** which just means performing this whole calculation maybe eight times.
**[3:21]** And so so far, we've computed this quantity of attention with the first
**[3:27]** head indicated by the subsequent one in these matrices.
**[3:33]** And the attention equation is just this,
**[3:36]** which you had previously seen in the last video as well.
**[3:40]** Now, let's do this computation with the second head.
**[3:43]** The second head will have a new set of matrices.
**[3:47]** I'm going to write WQ two, WK two and
**[3:51]** WV two that allows this mechanism to ask and
**[3:56]** answer a second question.
**[4:00]** So the first question was what's happening?
**[4:03]** Maybe the second question is when is something happening?
**[4:09]** And so instead of having W one here in the general case,
**[4:13]** we will have here Wi and I've now stacked up the second head
**[4:17]** behind the first one was the second one shown in red.
**[4:22]** So you repeat a computation that's exactly the same as the first one but
**[4:27]** with this new set of matrices instead.
**[4:30]** And you end up with in this case maybe the inner product between the september
**[4:36]** key and the l'Afrique query will have the highest inner product.
**[4:41]** So I'm going to highlight this red arrow to indicate that the value for september
**[4:48]** will play a large role in this second part of the representation for l'Afrique.
**[4:55]** Maybe the third question we now want to ask
**[4:59]** as represented by W Q three, W K three and
**[5:04]** WV three is who, who has something to do with Africa?
**[5:10]** And in this case when you do this computation the third time,
**[5:15]** maybe the inner product between Jane's key vector and
**[5:20]** the l'Afrique query vector will be highest and
**[5:23]** self highlighted this black arrow here.
**[5:27]** So that Jane's value will have the greatest weight
**[5:31]** in this representation which I've now stacked on at the back.
**[5:36]** In the literature,
**[5:37]** the number of heads is usually represented by the lower case letter H.
**[5:42]** And so H is equal to the number of heads.
**[5:46]** And you can think of each of these heads as a different feature.
**[5:50]** And when you pass these features to a new network you can calculate a very rich
**[5:55]** representation of the sentence.
**[5:57]** Calculating these computations for the three heads or the eight heads or
**[6:02]** whatever the number, the concatenation of these three values or
**[6:07]** A values is used to compute the output of the multi headed attention.
**[6:12]** And so the final value is the concatenation of all of these H heads.
**[6:22]** And then finally multiplied by a matrix W.
**[6:27]** Now one more detail that's worth keeping in mind is that in the description
**[6:32]** of multi head attention, I described computing these different values for
**[6:38]** the different heads as if you would do them in a big for-loop.
**[6:42]** And conceptually it's okay to think of it like that.
**[6:46]** But in practice you can actually compute these different heads' values in
**[6:51]** parallel because no one has value depends on the value of any other head.
**[6:55]** So in terms of how this is implemented,
**[6:58]** you can actually compute all the heads in parallel instead of sequentially.
**[7:03]** And then concatenate them multiply by W zero.
**[7:06]** And there's your multi headed attention.
**[7:10]** Now, there's a lot going on on the slide.
**[7:12]** Thanks for sticking with me all the way to the end of this video.
**[7:17]** In the next video, I'm going to use a simplified icon.
**[7:21]** We're going to use this little diagram here to denote
**[7:26]** this multi head computation.
**[7:29]** So it takes as input matrices Q, K and V.
**[7:32]** So these values down here and outputs this value up here.
**[7:38]** So in the next video, when we put this into the full transformer network,
**[7:44]** I'm going to use this little picture to denote all of
**[7:49]** these computations denoted on the slide.
**[7:53]** So, congratulations.
**[7:54]** In the last video you learned about self attention.
**[7:57]** And by doing that multiple times, you now understand the multi head attention
**[8:02]** mechanism, which lets you ask multiple questions for every single word and
**[8:07]** learn a much richer, much better representation for every word.
**[8:12]** Let's now put all this together to build the transformer network.
**[8:15]** Let's go to the next video to see that.
