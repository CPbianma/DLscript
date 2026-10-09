---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 3
section: Various Sequence To Sequence Architectures
item_title: Basic Models
duration: 6 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/HyEui/basic-models
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Basic Models — Transcript

**[0:03]** In this week, you'll hear
**[0:05]** about sequence to sequence models,
**[0:07]** which are useful for everything from
**[0:09]** machine translation to speech recognition.
**[0:11]** Let's start with the basic models,
**[0:13]** and then later this week, you'll hear about beam search,
**[0:16]** the attention model, and we will wrap up the discussion
**[0:19]** of models for audio data like speech.
**[0:21]** Let's get started. Let's say you want to input
**[0:26]** a French sentence like Jane visite I'Afrique Septembre,
**[0:31]** and you want to translate it to the English sentence,
**[0:34]** Jane is visiting Africa in September.
**[0:36]** As usual, let's use x1 through x,
**[0:40]** in this case 5 to represent
**[0:42]** the words and the input sequence,
**[0:44]** and we'll use y1 through y6 to
**[0:47]** represent the words in the output sequence.
**[0:51]** How can you train a neural network to input
**[0:54]** the sequence x and output the sequence y?
**[0:58]** Well, here's something you could do.
**[1:00]** The ideas I'm about to present are mainly from
**[1:04]** these two papers due to Ilya Sutskever, Vinyals Oriol, and V. Le. Quoc  and
**[1:10]** that one by
**[1:11]** Kyunghyun Cho, Bart van Merriënboer, Caglar Gulcehre, Dzmitry Bahdanau, Fethi Bougares, Holger Schwenk, and Yoshua Bengio.
**[1:22]** First, let's have a network which we're going to call
**[1:25]** the encoder network be built as
**[1:29]** a RNN and this could be a
**[1:31]** Gru or LSTM feeding the input French words
**[1:36]** one word at a time.
**[1:37]** After ingesting the input sequence the RNN
**[1:42]** then outputs a vector that represents the input sentence.
**[1:48]** After that, you can build a decoded network,
**[1:51]** which you might draw here.
**[1:53]** Which takes as input
**[1:55]** the encoding output by
**[1:57]** the encoding network shown in black on the left,
**[2:00]** and then can be trained to output
**[2:03]** the translation one word at a time.
**[2:10]** Eventually, it helps us say the end of
**[2:15]** sequence and the sentence token
**[2:17]** upon which the decoder stops, and as usual,
**[2:21]** we could take the generator tokens
**[2:23]** and feed them to the next
**[2:26]** so if they just stay in the sequence they were doing
**[2:29]** before when synthesizing text using the language model.
**[2:32]** One of the most remarkable recent results
**[2:35]** in deep learning is that this model works.
**[2:38]** Given enough pairs of French and English sentences,
**[2:42]** if you train a model to input
**[2:45]** a French sentence and
**[2:46]** output the corresponding English translation,
**[2:49]** this will actually work decently well.
**[2:52]** This model simply uses an encoding network whose job it
**[2:56]** is to find an encoding of the input French sentence,
**[3:00]** and then use a decoding network to then
**[3:03]** generate the corresponding English translation.
**[3:07]** An architecture very similar to
**[3:09]** this also works for image captioning.
**[3:13]** Given an image like the one shown here,
**[3:16]** maybe you wanted to be captions
**[3:18]** automatically as a cat sitting on a chair.
**[3:21]** How do you train in your network to
**[3:23]** input an image and output
**[3:26]** a caption like that phrase up there?
**[3:30]** Here's what you can do.
**[3:33]** From the earlier course on the ConvNets,
**[3:35]** you've seen and how you can input
**[3:37]** an image into a convolutional network,
**[3:40]** may maybe a pre-trained AlexNet,
**[3:43]** and have that learn and encoding
**[3:45]** a learner to the features of the input image.
**[3:48]** This is actually the AlexNet architecture,
**[3:52]** and if we get rid of this final softmax unit,
**[3:56]** the pre-trained AlexNet can give you a
**[3:59]** 4,096-dimensional feature vector of
**[4:02]** which to represent this picture of a cat.
**[4:05]** This pre-trained network can
**[4:08]** be the encoded network for the image and you
**[4:11]** now have a 4,096-dimensional
**[4:14]** vector that represents the image.
**[4:17]** You can then take this and feed it to
**[4:20]** an RNN whose job it is to
**[4:24]** generate the caption one word at a time.
**[4:29]** Similar to what we saw with machine translation,
**[4:34]** translating from French the English,
**[4:36]** you can now input
**[4:38]** a feature vector describing the inputs and then
**[4:42]** have it generate an output set of words,
**[4:49]** one word at a time.
**[4:50]** This actually works pretty well for image captioning,
**[4:54]** especially if the caption you want to
**[4:56]** generate is not too long.
**[4:58]** As far as I know, this type
**[5:02]** of model was first proposed by
**[5:04]** Jin Hwan Mau Wei Xu Yong Chung Wang, Xiao Hong and Alan Yo. although it turns
**[5:10]** out there are multiple groups coming up with
**[5:12]** very similar models independently
**[5:14]** and at about the same time.
**[5:18]** Two of the groups that had done
**[5:20]** very similar work at
**[5:22]** about the same time and I think independently of
**[5:24]** Junhua Mao, Wei Xu, Yi Yang, Jiang Wang, Zhiheng Huang, Alan L. Yuille as well as Adrej Karpathy and Fei-Fei Li.
**[5:32]** You've now seen how
**[5:35]** a basic sequence to sequence model works.
**[5:37]** How basic image to sequence,
**[5:39]** or image captioning model works.
**[5:41]** But there are some differences between
**[5:43]** how you'll run a model like this,
**[5:45]** the generally the sequence compared to how you were
**[5:49]** synthesizing novel text using a language model.
**[5:52]** One of the key differences is you don't want
**[5:55]** to randomly choose in translation.
**[5:57]** You may be want the most likely translation
**[6:00]** or you don't want to randomly choose in caption,
**[6:02]** maybe not, but you might want
**[6:03]** the best caption and most likely caption.
**[6:06]** Let's see in the next video how
**[6:08]** you go about generating that.
