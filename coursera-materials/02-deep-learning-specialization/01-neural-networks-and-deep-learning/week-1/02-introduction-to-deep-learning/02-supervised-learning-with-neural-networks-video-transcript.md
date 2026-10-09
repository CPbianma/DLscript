---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 1
section: Introduction to Deep Learning
item_title: Supervised Learning with Neural Networks
duration: 8 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/2c38r/supervised-learning-with-neural-networks
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Supervised Learning with Neural Networks — Transcript

**[0:03]** There's been a lot of hype about neural networks.
**[0:05]** And perhaps some of that hype is justified, given how well they're working.
**[0:10]** But it turns out that so
**[0:11]** far, almost all the economic value created by neural networks has been through
**[0:15]** one type of machine learning, called supervised learning.
**[0:18]** Let's see what that means, and let's go over some examples.
**[0:22]** In supervised learning, you have some input x, and
**[0:26]** you want to learn a function mapping to some output y.
**[0:30]** So for example, just now we saw the housing price prediction application where
**[0:34]** you input some features of a home and try to output or estimate the price y.
**[0:40]** Here are some other examples that neural networks have been applied to very
**[0:45]** effectively.
**[0:46]** Possibly the single most lucrative application of deep learning today is
**[0:51]** online advertising, maybe not the most inspiring, but certainly very lucrative,
**[0:56]** in which, by inputting information about an ad to the website it's thinking
**[1:02]** of showing you, and some information about the user, neural networks have
**[1:07]** gotten very good at predicting whether or not you click on an ad.
**[1:10]** And by showing you and
**[1:11]** showing users the ads that you are most likely to click on, this has been
**[1:15]** an incredibly lucrative application of neural networks at multiple companies.
**[1:20]** Because the ability to show you ads that you're more likely to
**[1:24]** click on has a direct impact on the bottom
**[1:26]** line of some of the very large online advertising companies.
**[1:30]** Computer vision has also made huge strides in the last several years,
**[1:35]** mostly due to deep learning.
**[1:37]** So you might input an image and want to output an index,
**[1:41]** say from 1 to 1,000 trying to tell you if this picture,
**[1:45]** it might be any one of, say a 1000 different images.
**[1:47]** So, you might us that for photo tagging.
**[1:50]** I think the recent progress in speech recognition has also been very exciting,
**[1:54]** where you can now input an audio clip to a neural network, and
**[1:57]** have it output a text transcript.
**[2:00]** Machine translation has also made huge strides thanks to deep learning where now
**[2:05]** you can have a neural network input an English sentence and directly output say,
**[2:09]** a Chinese sentence.
**[2:11]** And in autonomous driving, you might input an image, say a picture of what's in
**[2:15]** front of your car as well as some information from a radar, and
**[2:20]** based on that, maybe a neural network can be trained to tell you the position
**[2:25]** of the other cars on the road.
**[2:26]** So this becomes a key component in autonomous driving systems.
**[2:30]** So a lot of the value creation through neural networks has been through cleverly
**[2:35]** selecting what should be x and what should be y for
**[2:39]** your particular problem, and then fitting this supervised learning component into
**[2:45]** often a bigger system such as an autonomous vehicle.
**[2:48]** It turns out that slightly different types of neural networks are useful for
**[2:52]** different applications.
**[2:54]** For example, in the real estate application that we saw in the previous
**[3:00]** video, we use a universally standard neural network architecture, right?
**[3:04]** Maybe for real estate and online advertising might be a relatively
**[3:08]** standard neural network, like the one that we saw.
**[3:13]** For image applications we'll often use convolutional neural networks,
**[3:19]** often abbreviated CNN.
**[3:21]** And for sequence data.
**[3:24]** So for example, audio has a temporal component, right?
**[3:27]** Audio is played out over time, so audio is most naturally represented
**[3:32]** as a one-dimensional time series or as a one-dimensional temporal sequence.
**[3:38]** And so for sequence data, you often use an RNN,
**[3:42]** a recurrent neural network.
**[3:45]** Language, English and Chinese, the alphabets or the words come one at a time.
**[3:50]** So language is also most naturally represented as sequence data.
**[3:54]** And so more complex versions of RNNs are often used for these applications.
**[4:00]** And then, for more complex applications, like autonomous driving, where you have an
**[4:04]** image, that might suggest more of a CNN, convolution neural network, structure and
**[4:09]** radar info which is something quite different.
**[4:12]** You might end up with a more custom, or
**[4:15]** some more complex, hybrid neural network architecture.
**[4:20]** So, just to be a bit more concrete about what are the standard CNN and
**[4:25]** RNN architectures.
**[4:27]** So in the literature you might have seen pictures like this.
**[4:32]** So that's a standard neural net.
**[4:34]** You might have seen pictures like this.
**[4:36]** Well this is an example of a Convolutional Neural Network, and we'll see in
**[4:41]** a later course exactly what this picture means and how can you implement this.
**[4:45]** But convolutional networks are often used for image data.
**[4:51]** And you might also have seen pictures like this.
**[4:54]** And you'll learn how to implement this in a later course.
**[4:57]** Recurrent neural networks are very good for
**[5:00]** this type of one-dimensional sequence data that has maybe a temporal component.
**[5:06]** You might also have heard about applications of machine learning
**[5:10]** to both Structured Data and Unstructured Data.
**[5:14]** Here's what the terms mean.
**[5:14]** Structured Data means basically databases of data.
**[5:19]** So, for example, in housing price prediction, you might have a database or
**[5:25]** the column that tells you the size and the number of bedrooms.
**[5:28]** So, this is structured data, or in predicting whether or not a user will
**[5:33]** click on an ad, you might have information about the user, such as the age,
**[5:37]** some information about the ad, and then labels why that you're trying to predict.
**[5:41]** So that's structured data, meaning that each of the features,
**[5:46]** such as size of the house, the number of bedrooms, or
**[5:49]** the age of a user, has a very well defined meaning.
**[5:54]** In contrast, unstructured data refers to things like audio, raw audio,
**[6:00]** or images where you might want to recognize what's in the image or text.
**[6:05]** Here the features might be the pixel values in an image or
**[6:09]** the individual words in a piece of text.
**[6:12]** Historically, it has been much harder for
**[6:14]** computers to make sense of unstructured data compared to structured data.
**[6:19]** And in fact the human race has evolved to be very good at understanding
**[6:24]** audio cues as well as images.
**[6:26]** And then text was a more recent invention, but
**[6:28]** people are just really good at interpreting unstructured data.
**[6:31]** And so one of the most exciting things about the rise of neural networks is that,
**[6:36]** thanks to deep learning, thanks to neural networks, computers are now much better
**[6:41]** at interpreting unstructured data as well compared to just a few years ago.
**[6:46]** And this creates opportunities for many new exciting applications that use
**[6:51]** speech recognition, image recognition, natural language processing on text,
**[6:56]** much more than was possible even just two or three years ago.
**[7:00]** I think because people have a natural empathy to understanding unstructured
**[7:03]** data, you might hear about neural network successes on unstructured data
**[7:08]** more in the media because it's just cool when the neural network recognizes a cat.
**[7:13]** We all like that, and we all know what that means.
**[7:15]** But it turns out that a lot of short term economic value that neural
**[7:19]** networks are creating has also been on structured data,
**[7:24]** such as much better advertising systems, much better profit recommendations, and
**[7:28]** just a much better ability to process the giant databases that
**[7:33]** many companies have to make accurate predictions from them.
**[7:37]** So in this course, a lot of the techniques we'll go over will apply
**[7:41]** to both structured data and to unstructured data.
**[7:44]** For the purposes of explaining the algorithms,
**[7:46]** we will draw a little bit more on examples that use unstructured data.
**[7:52]** But as you think through applications of neural networks within your own team I
**[7:56]** hope you find both uses for them in both structured and unstructured data.
**[8:02]** So neural networks have transformed supervised learning and
**[8:06]** are creating tremendous economic value.
**[8:09]** It turns out though, that the basic technical ideas behind neural networks
**[8:12]** have mostly been around, sometimes for many decades.
**[8:16]** So why is it, then, that they're only just now taking off and working so well?
**[8:20]** In the next video, we'll talk about why it's only quite recently
**[8:24]** that neural networks have become this incredibly powerful tool that you can use.
