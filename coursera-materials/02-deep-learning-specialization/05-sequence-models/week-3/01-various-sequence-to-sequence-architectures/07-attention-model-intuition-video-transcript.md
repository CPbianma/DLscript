---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 3
section: Various Sequence To Sequence Architectures
item_title: Attention Model Intuition
duration: 10 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/RDXpX/attention-model-intuition
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Attention Model Intuition — Transcript

**[0:00]** For most of this week,
**[0:01]** you've been using a Encoder-Decoder architecture for machine translation.
**[0:07]** Where one RNN reads in a sentence and then different one outputs a sentence.
**[0:11]** There's a modification to this called the Attention Model,
**[0:15]** that makes all this work much better.
**[0:18]** The attention algorithm, the attention idea has
**[0:21]** been one of the most influential ideas in deep learning.
**[0:23]** Let's take a look at how that works.
**[0:26]** Get a very long French sentence like this.
**[0:29]** What we are asking this green encoder neural network to do is,
**[0:33]** to read in the whole sentence and then memorize
**[0:36]** the whole sentences and store it in the activations conveyed here.
**[0:40]** Then for the purple network,
**[0:42]** the decoder network till then
**[0:44]** generate the English translation.
**[0:47]** Jane went to Africa last September and enjoyed the culture and met many wonderful people;
**[0:50]** she came back raving about how wonderful her trip was,
**[0:52]** and is tempting me to go too.
**[0:53]** Now, the way a human translator
**[0:56]** would translate this sentence is not to first read
**[1:00]** the whole French sentence and then memorize
**[1:02]** the whole thing and then regurgitate an English sentence from scratch.
**[1:06]** Instead, what the human translator would do is read the first part of it,
**[1:11]** maybe generate part of the translation.
**[1:14]** Look at the second part, generate a few more words,
**[1:17]** look at a few more words,
**[1:18]** generate a few more words and so on.
**[1:20]** You kind of work part by part through the sentence,
**[1:23]** because it's just really difficult to memorize the whole long sentence like that.
**[1:29]** What you see for the Encoder-Decoder architecture above is that,
**[1:34]** it works quite well for short sentences,
**[1:37]** so we might achieve a relatively high Bleu score,
**[1:40]** but for very long sentences,
**[1:43]** maybe longer than 30 or 40 words,
**[1:45]** the performance comes down.
**[1:47]** The Bleu score might look like this as the sentence that varies
**[1:51]** and short sentences are just hard to translate,
**[1:56]** hard to get all the words, right?
**[1:59]** Long sentences, it doesn't do well on because it's just difficult to
**[2:03]** get in your network to memorize a super long sentence.
**[2:07]** In this and the next video,
**[2:08]** you'll see the Attention Model which translates maybe a bit more like humans might,
**[2:14]** looking at part of the sentence at a time and with an Attention Model,
**[2:19]** machine translation systems performance can look like this,
**[2:22]** because by working one part of the sentence at a time,
**[2:26]** you don't see this huge dip which is
**[2:29]** really measuring the ability of a neural network to memorize
**[2:32]** a long sentence which maybe isn't what we most badly need a neural network to do.
**[2:38]** In this video, I want to just give you some intuition about
**[2:43]** how attention works and then we'll flesh out the details in the next video.
**[2:49]** The Attention Model was due to Dimitri, Bahdanau, Camcrun Cho,
**[2:56]** Yoshua Bengio and even though it was obviously developed for machine translation,
**[3:00]** it spread to many other application areas as well.
**[3:03]** This is really a very influential,
**[3:06]** I think very seminal paper in the deep learning literature.
**[3:10]** Let's illustrate this with a short sentence,
**[3:14]** even though these ideas were maybe developed more for long sentences,
**[3:18]** but it'll be easier to illustrate these ideas with a simpler example.
**[3:22]** We have our usual sentence,
**[3:24]** Jane visite l'Afrique en Septembre.
**[3:26]** Let's say that we use a RNN,
**[3:30]** and in this case, I'm going to use a bidirectional RNN,
**[3:34]** in order to compute some set of
**[3:37]** features for each of the input words and you have to understand it,
**[3:42]** bidirectional RNN with outputs Y1 to Y3
**[3:46]** and so on up to Y5 but we're not doing a word for word translation,
**[3:51]** let me get rid of the Y's on top.
**[3:54]** But using a bidirectional RNN,
**[3:56]** what we've done is for each other words,
**[3:59]** really for each of the five positions into sentence,
**[4:02]** you can compute a very rich set of features about
**[4:06]** the words in the sentence and maybe surrounding words in every position.
**[4:12]** Now, let's go ahead and generate the English translation.
**[4:17]** We're going to use another RNN to generate the English translations.
**[4:21]** Here's my RNN note as usual and instead of using A to denote the activation,
**[4:29]** in order to avoid confusion with the activations down here,
**[4:32]** I'm just going to use a different notation,
**[4:34]** I'm going to use S to denote the hidden state in this RNN up here,
**[4:39]** so instead of writing A1 I'm going to right S1 and so
**[4:45]** we hope in this model that the first word it generates will be Jane,
**[4:50]** to generate Jane visits Africa in September.
**[4:54]** Now, the question is,
**[4:57]** when you're trying to generate this first word,
**[4:59]** this output, what part of the input French sentence should you be looking at?
**[5:05]** Seems like you should be looking primarily at this first word,
**[5:07]** maybe a few other words close by,
**[5:11]** but you don't need to be looking way at the end of the sentence.
**[5:15]** What the Attention Model would be computing is a set of
**[5:18]** attention weights and we're going to use Alpha one, one
**[5:25]** to denote when you're generating the first words,
**[5:29]** how much should you be paying attention to this first piece of information here.
**[5:36]** And then we'll also come up with a second that's called Attention Weight,
**[5:41]** Alpha one, two which tells us what we're trying to compute the first work of Jane,
**[5:46]** how much attention we're
**[5:51]** paying to this second word from the inputs and so on and the Alpha one, three and so on,
**[5:57]** and together this will tell us what is
**[6:02]** exactly the context from denoter C that we should be paying attention to,
**[6:08]** and that is input to this RNN unit to then try to generate the first words.
**[6:14]** That's one step of the RNN,
**[6:16]** we will flesh out all these details in the next video.
**[6:19]** For the second step of this RNN,
**[6:23]** we're going to have
**[6:25]** a new hidden state S two and we're going to have a new set of the attention weights.
**[6:31]** We're going to have Alpha two, one to tell us when we generate in the second word.
**[6:38]** I guess this will be visits maybe that being the ground trip label.
**[6:42]** How much should we paying attention to the first word in the french input and also,
**[6:47]** Alpha two, two and so on.
**[6:50]** How much should we paying attention the word visite,
**[6:53]** how much should we pay attention to l'Afrique and so on.
**[6:55]** And of course, the first word we generate in Jane is also an input to this,
**[7:01]** and then we have some context that we're paying attention to and the second step,
**[7:05]** there's also an input and that together will generate the second word and
**[7:09]** that leads us to the third step, S three,
**[7:14]** where this is an input and we have some new context C that
**[7:19]** depends on the various Alpha three for the different time sets,
**[7:24]** that tells us how much should we be paying attention to
**[7:27]** the different words from the input French sentence and so on.
**[7:32]** So, some things I haven't specified yet,
**[7:35]** but that will go further into detail in the next video of this,
**[7:38]** how exactly this context defines and the goal of the context is
**[7:43]** for the third word is really should capture that
**[7:46]** maybe we should be looking around this part of the sentence.
**[7:50]** The formula you use to do that will defer to
**[7:55]** the next video as well as how do you compute these attention weights.
**[8:01]** And you see in the next video that Alpha three T,
**[8:05]** which is, when you're trying to generate the third word,
**[8:07]** I guess this would be the Africa, just getting the right output.
**[8:11]** The amounts that this RNN step
**[8:16]** should be paying attention to the French word that time T,
**[8:21]** that depends on the activations of the bidirectional RNN at time T,
**[8:27]** I guess it depends on the fourth activations and the,
**[8:32]** backward activations at time T and it will depend on the state from the previous steps,
**[8:37]** it will depend on S two, and these things together will influence,
**[8:39]** how much you pay attention to a specific word in the input French sentence.
**[8:47]** But we'll flesh out all these details in the next video.
**[8:49]** But the key intuition to take away is that
**[8:52]** this way the RNN marches forward generating one word at a time,
**[8:58]** until eventually it generates maybe the EOS and at every step,
**[9:04]** there are these attention weighs.
**[9:06]** Alpha T.T. Prime that tells it,
**[9:09]** when you're trying to generate the T, English word,
**[9:11]** how much should you be paying attention to the T prime French words.
**[9:16]** And this allows it on every time step to look only maybe
**[9:20]** within a local window of the French sentence to pay attention to,
**[9:24]** when generating a specific English word.
**[9:28]** I hope this video conveys some intuition
**[9:31]** about Attention Model and that we now have a rough sense of,
**[9:34]** maybe how the algorithm works.
**[9:36]** Let's go to the next video to flesh out the details of the Attention Model.
