---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 3
section: Speech Recognition - Audio Data
item_title: Trigger Word Detection
duration: 5 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/Li4ts/trigger-word-detection
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Trigger Word Detection — Transcript

**[0:00]** You've now learned so much about deep learning and
**[0:03]** sequence models that we can actually describe a trigger word system
**[0:07]** quite simply just on one slide, as you see in this video.
**[0:11]** But with the rise of speech recognition, that there have been more and
**[0:14]** more devices you can wake up with your voice and
**[0:17]** those are sometimes called trigger word detection systems.
**[0:20]** So let's see how you can build a trigger word system.
**[0:23]** Examples of trigger word systems include the Amazon Echo,
**[0:27]** which is woken up with the word Alexa,
**[0:29]** the Baidu DuerOS powered devices woken up with the phrase xiaodunihao,
**[0:34]** Apple Siri working up with hey, Siri, and Google Home woken up with okay, Google.
**[0:40]** So it's thanks to trigger word detection that if you have, say,
**[0:44]** an Amazon Echo in your living room, you can walk in your living room and
**[0:48]** just say, Alexa, what time is it?
**[0:50]** And have it wake up or be triggered by the word Alexa and answer your voice query.
**[0:56]** So if you can build a trigger word detection system, maybe you can make your
**[1:00]** computer do something by telling it, computer, activate.
**[1:04]** One of my friends also worked on turning on and
**[1:08]** off a particular lamp using a trigger word kind of as a fun project.
**[1:13]** But what I want to show you is how you can build a trigger word detection system.
**[1:18]** The literature on trigger detection algorithm is still evolving so there isn't
**[1:22]** wide consensus yet on what's the best algorithm for trigger word detection.
**[1:26]** So I'm just going to show you one example of an algorithm you can use.
**[1:30]** Now, you've seen RNNs like this and what we really do is take an audio clip,
**[1:35]** maybe compute spectrogram features.
**[1:38]** And that generates features, x1, x2, x3 audio features, x1, x2,
**[1:42]** x3 that you pass through an RNN.
**[1:45]** And so all that remains to be done is to define the target labels.
**[1:50]** Y
**[1:51]** So if this point in the audio clip is when someone just finished saying
**[1:56]** the trigger word, such as Alexa or xiaodunihao or hey, Siri, or okay,
**[2:01]** Google, then in the training sets, you can set the target labels to be 0 for
**[2:07]** everything before that point and right after that to set the target label of 1.
**[2:13]** And then if a little bit later on, the trigger word was said again and
**[2:19]** the trigger word was said at this point,
**[2:22]** then you can again set the target label to be 1 right after that.
**[2:28]** Now, this type of labelling scheme for an RNN could work.
**[2:34]** Actually, this will actually work reasonably well.
**[2:37]** One slight disadvantage of this is it creates a very imbalanced
**[2:41]** training set to have a lot more 0s than 1s.
**[2:45]** So one other thing you could do, this is a little bit of a hack, but
**[2:49]** could make the model a little bit easier to train is instead of setting only
**[2:54]** a single time step output 1, you can actually make it output a few 1s for
**[2:59]** several times or for a fixed period of time before reverting back to 0.
**[3:04]** So and that slightly evens out the ratio of 1s to 0s,
**[3:12]** but this is a little bit of a hack.
**[3:17]** But if this is when in the audio clipper the trigger word is said,
**[3:22]** then right after that, you can set the target label to 1, and
**[3:26]** if this is the trigger word said again,
**[3:29]** then right after that is when you want the RNN to output 1.
**[3:35]** So you get to play more of this as well in the programming exercise.
**[3:40]** But I think you should feel quite proud of yourself that you've learned enough about
**[3:45]** deep learning that it just takes one picture and
**[3:47]** one slide to describe something as complicated as trigger word detection.
**[3:53]** And based on this,
**[3:54]** I hope you'll be able to implement something that works and allows you to
**[3:59]** detect trigger words when you see more of this in the program exercise.
**[4:04]** In this course on sequence models, you learned about our RNNs,
**[4:08]** including both GRUs and LSTMs, and then in the second week,
**[4:12]** you learned a lot about word embeddings and how to learn representations of words.
**[4:17]** And then in this week, you learned about the attention model
**[4:22]** as well as how to use it to process audio data.
**[4:26]** And I hope you have fun implementing all of these ideas in this week's
**[4:30]** program exercise.
