---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 4
section: Transformers
item_title: Transformer Network
duration: 14 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/Kf5Y3/transformer-network
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Transformer Network — Transcript

**[0:02]** You've learned about self-attention.
**[0:05]** You've learned about multi-headed attention.
**[0:07]** Let's put it all together to
**[0:09]** build the transformer network.
**[0:11]** In this video, you'll see how you
**[0:13]** can pair the attention mechanisms you
**[0:15]** saw in the previous videos
**[0:17]** to build the transformer architecture.
**[0:21]** Starting again with the sentence 'Jane
**[0:23]** visite L'Afrique en septembre'
**[0:26]** and its corresponding embedding.
**[0:28]** Let's walk through how you can
**[0:30]** translate the sentence from French to English.
**[0:33]** I've also added the start of
**[0:36]** sentence and end of sentence tokens here.
**[0:39]** Up until this point, for the sake of simplicity,
**[0:42]** I've only been talking about
**[0:44]** the embeddings for the words in the sentence,
**[0:46]** but in many sequence-to-sequence translation tasks,
**[0:51]** it will be useful to also add
**[0:53]** the start of sentence or the SOS and
**[0:56]** the end of sentence or
**[0:57]** the EOS tokens which I have in this example.
**[1:02]** The first step in the transformer is,
**[1:05]** these embeddings get fed into
**[1:08]** an encoder block which has a multi-head attention layer.
**[1:12]** This is exactly what you saw on the last slide,
**[1:16]** where you feed in the values Q,
**[1:21]** K and V computed from
**[1:26]** the embeddings and the weight matrices W. This layer then
**[1:30]** produces a matrix that can be passed into
**[1:33]** a feed-forward neural network which helps
**[1:36]** determine what interesting features
**[1:38]** there are in the sentence.
**[1:40]** In the transformer paper,
**[1:42]** this encoding block is repeated n
**[1:46]** times and a typical value for n is six.
**[1:53]** After maybe about six times through this block,
**[1:57]** we will then feed
**[2:00]** the output of the encoder into a decoder block.
**[2:03]** Let's start building the decoder block.
**[2:06]** The decoders block's job
**[2:09]** is to output the English translation.
**[2:12]** The first output will be the start of sentence token,
**[2:15]** which I've already written down here.
**[2:18]** At every step, the decoder block will
**[2:20]** input the first few words,
**[2:24]** whatever we've already generated of the translation.
**[2:27]** When we're just getting started,
**[2:29]** the only thing we know is that
**[2:32]** the translation will start with
**[2:34]** a start of sentence token.
**[2:37]** The start of sentence token gets fed in to
**[2:41]** this multi-head attention block and just this one token,
**[2:45]** the SOS token, start of sentence,
**[2:47]** is used to compute Q,
**[2:49]** K and V for this multi-head attention block.
**[2:53]** This first block's output is used to
**[2:58]** generate the Q matrix
**[3:02]** for the next multi-head attention block
**[3:04]** and the output of the encoder is used to generate
**[3:09]** K and V. Here's
**[3:13]** a second multi-head attention block with inputs Q,
**[3:17]** K and V as before.
**[3:20]** Why is it structured this way?
**[3:22]** Maybe here's one piece of intuition that could help.
**[3:25]** The input down here is
**[3:28]** what you've translated of the sentence so far.
**[3:31]** This will ask a query to say,
**[3:33]** "What of the start of sentence?".
**[3:36]** It will then pull context from K and V,
**[3:39]** which is translated from
**[3:40]** the French version of the sentence to
**[3:42]** then try to decide what is
**[3:44]** the next word in the sequence to generate.
**[3:46]** To finish the description of the decoded block,
**[3:50]** the multi-head attention block
**[3:52]** outputs the values which
**[3:54]** are fed to a feed forward neural network.
**[3:56]** This decoder block is also
**[3:58]** going to be repeated n times, maybe six times,
**[4:01]** where you take the output, feed it back to the input,
**[4:04]** and have this go through, say, half a dozen times.
**[4:08]** The job of this neural network is
**[4:11]** to predict the next word in the sentence.
**[4:13]** Hopefully, it will decide that the first word
**[4:16]** in the English translation is Jane.
**[4:19]** What we do is then feed Jane to the input as well.
**[4:26]** Now, the next query comes from SOS and Jane and it says,
**[4:31]** well, given Jane, what is the most appropriate next word?
**[4:36]** Let's find the right key and the right value,
**[4:39]** then lets us generate the most appropriate next word,
**[4:42]** which hopefully will generate visite.
**[4:46]** Then running this neural network again generates Africa.
**[4:51]** Then we feed Africa back into the input.
**[4:55]** Hopefully it then generates in and then September,
**[5:00]** and with this input,
**[5:01]** hopefully it generates the end of
**[5:03]** sentence token and then we're done.
**[5:06]** These encoder and decoder blocks,
**[5:08]** and how they're combined
**[5:09]** to perform a sequence to sequence
**[5:11]** translation tasks are the main ideas
**[5:13]** behind the transformer architecture.
**[5:15]** In this case, you saw how you can
**[5:18]** translate an input sentence into
**[5:20]** a sentence in another language
**[5:22]** to gain some intuition about how attention
**[5:25]** in neural networks can be combined
**[5:28]** to allow simultaneous computation.
**[5:31]** But beyond these main ideas,
**[5:33]** there are a few extra bells and whistles to transformers.
**[5:36]** Let me briefly step through these extra bells and
**[5:39]** whistles that makes
**[5:41]** the transformer network work even better.
**[5:44]** The first of these is positional encoding of the input.
**[5:49]** If you recall the self attention equations,
**[5:52]** there's nothing that indicates the position of a word.
**[5:56]** Is this word the first word in the sentence,
**[5:59]** in the middle, the last word in the sentence?
**[6:02]** But the position within a sentence can be
**[6:04]** extremely important to translation.
**[6:07]** The way you encode
**[6:08]** the position of elements in the input is that you
**[6:11]** use a combination of these sine and cosine equations.
**[6:17]** Let's say, for example,
**[6:19]** that your word embedding is a vector with four values.
**[6:24]** In this case, the dimension D of
**[6:28]** the word embedding is 4,
**[6:33]** so x^(1), x^(2),
**[6:36]** x^(3), let's say those are four dimensional vectors.
**[6:40]** In this example, we're going to then create
**[6:43]** a positional embedding vector of
**[6:45]** the same dimension, also four dimensional.
**[6:48]** I'm going to call this positional embedding p^(1),
**[6:54]** let's say for the position embedding
**[6:57]** of the first word Jane.
**[6:59]** In this equation below, pos,
**[7:03]** position denotes the numerical position of the word.
**[7:07]** For the word Jane,
**[7:09]** pos = 1,
**[7:15]** and i over here refers to
**[7:18]** the different dimensions of encoding.
**[7:21]** This first element corresponds to i = 0.
**[7:26]** This element i = 0,
**[7:28]** i =1, i = 1.
**[7:32]** These are the variables pos and i,
**[7:36]** they go into these equations down below.
**[7:40]** Where pos is the position of a word,
**[7:42]** i goes from 0 to 1,
**[7:46]** and d = 4,
**[7:49]** is the dimension of this vector.
**[7:51]** What the position encoding does with the sine and
**[7:55]** cosine is create a unique positional encoding vector.
**[7:59]** One of these vectors that is unique for each word,
**[8:03]** the vector p^(3) that encodes the position of l'Afrique,
**[8:10]** the third word will be a set of four values that'll be
**[8:14]** different than the four values used in
**[8:16]** code position of the first word of Jane.
**[8:20]** This is what the sine and cosine occurs look like.
**[8:25]** Is i = 0,
**[8:27]** i = 0,
**[8:28]** i = 1, i =1.
**[8:32]** Because you have these terms and
**[8:35]** denominator you end up with i =
**[8:38]** 0 will have some sinusoid curve that looks like this,
**[8:47]** and i =0 will be the matched cosine.
**[8:54]** 90 degrees out of face and i
**[8:57]** =1 will end up with a lower frequency sinusoid,
**[9:06]** and i =1 gives you a matched cosine curve.
**[9:14]** For T1, for position 1,
**[9:18]** you read off values at
**[9:20]** this position to fill in those four values there.
**[9:25]** Whereas for a different word at a different position,
**[9:28]** maybe this is now three on the horizontal axis,
**[9:31]** you read off a different set of values.
**[9:34]** Notice these first two values may be very
**[9:36]** similar because they're roughly at the same height.
**[9:38]** But by using these multiple sines and cosines,
**[9:42]** looking across all four values,
**[9:45]** P3 will be a different vector than P1.
**[9:49]** The positional encoding, P1j is added
**[9:54]** directly to X1 to the input this
**[9:58]** way so that each of the word vectors is also
**[10:02]** influenced or colored with
**[10:04]** where in the sentence the word appears.
**[10:07]** The output of the encoding block contains
**[10:11]** contextual semantic embedding
**[10:14]** and positional encoding information.
**[10:16]** The output of the embedding layer is then D,
**[10:20]** which in this case four
**[10:22]** by the maximum length of sequence, your model can take.
**[10:27]** The outputs of all these layers are also of this shape.
**[10:35]** In addition to adding
**[10:37]** these position encodings to the embeddings,
**[10:41]** you'd also pass them through
**[10:43]** the network with residual connections.
**[10:46]** These residual connections are similar to
**[10:48]** those you previously see in the resnet.
**[10:51]** Their purpose in this case is to pass along
**[10:54]** positional information through the entire architecture.
**[10:57]** In addition to positional encoding,
**[11:00]** the transformer network also uses
**[11:02]** a layer very similar to a batch norm.
**[11:06]** Their purpose in this case is to pass along
**[11:09]** positional information into position encoding.
**[11:12]** The transformer also uses a layer add norm that is
**[11:16]** very similar to the batch norm layer
**[11:18]** that you're already familiar with.
**[11:20]** For the purpose of this video,
**[11:22]** don't worry about the differences.
**[11:23]** Think of it as playing a role very
**[11:25]** similar to the batch norm.
**[11:27]** This helps speed up learning
**[11:29]** and this batch norm like layer,
**[11:32]** this add & norm layer is
**[11:34]** repeated throughout this architecture.
**[11:37]** Finally, for the output of the decoder block,
**[11:41]** there's actually also a linear and
**[11:43]** then a soft max layer to
**[11:45]** predict the next word one word at a time.
**[11:48]** In case you read the literature
**[11:50]** on the transformer network,
**[11:52]** you may also hear something called
**[11:55]** the mask multi-head attention,
**[11:58]** which I'm going to draw and over here.
**[12:00]** Mask multi-head attention is
**[12:02]** important only during the training process
**[12:05]** where you're using a dataset of correct
**[12:08]** French to English translations to train your transformer.
**[12:12]** Previously, we stepped through how
**[12:14]** the transformer performs prediction one word at the time,
**[12:18]** but how does it train?
**[12:20]** Let's say your dataset has a
**[12:22]** correct French to English translation.
**[12:25]** Jane visite l'Afrique on September,
**[12:27]** and Jane visits Africa in September.
**[12:29]** When training, you have access to
**[12:31]** the entire correct English translation,
**[12:34]** the correct output,
**[12:36]** and the correct input
**[12:39]** and because you have the full correct output,
**[12:43]** you don't actually have to generate
**[12:45]** the words one at a time during training.
**[12:48]** Instead, what masking does
**[12:50]** is it blocks out the last part of
**[12:52]** the sentence to mimic what
**[12:55]** the network will need to do
**[12:57]** at test time or during prediction.
**[12:59]** In other words, all that
**[13:00]** mask multi -head attention does is it
**[13:04]** repeatedly pretends
**[13:06]** that the network had perfectly translated,
**[13:10]** say the first few words and hides
**[13:14]** the remaining words to see if given
**[13:17]** a perfect first part of the translation,
**[13:21]** whether the new network can predict
**[13:24]** the next word in the sequence accurately.
**[13:26]** That's a summary of the transform architecture.
**[13:29]** Since the paper attention is all you need came out,
**[13:33]** there have been many other
**[13:35]** iterations of this model such as BERT
**[13:37]** or DistilBERT which
**[13:39]** you get to explore yourself this week.
**[13:41]** That was it. I know there was a lot of details,
**[13:45]** but now you have a good sense of
**[13:48]** all of the major building blocks
**[13:49]** of the transformer network.
**[13:51]** When you see this in this week's program exercise,
**[13:54]** playing around with the code there will help you to build
**[13:57]** even deeper intuition about
**[13:59]** how to make this work for your applications.
