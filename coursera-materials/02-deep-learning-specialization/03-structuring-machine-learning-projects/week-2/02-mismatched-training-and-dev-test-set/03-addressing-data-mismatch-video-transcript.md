---
type: video-transcript
specialization: Deep Learning Specialization
course: Structuring Machine Learning Projects
week: 2
section: Mismatched Training and Dev/Test Set
item_title: Addressing Data Mismatch
duration: 10 min
source_url: https://www.coursera.org/learn/machine-learning-projects/lecture/biLiy/addressing-data-mismatch
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Addressing Data Mismatch — Transcript

**[0:00]** If your training set comes from a different distribution,
**[0:02]** than your dev and test set,
**[0:04]** and if error analysis shows you that you have a data mismatch problem, what can you do?
**[0:09]** There aren't completely systematic solutions to this,
**[0:13]** but let's look at some things you could try.
**[0:15]** If I find that I have a large data mismatch problem,
**[0:19]** what I usually do is carry out manual error analysis and try to
**[0:23]** understand the differences between the training set and the dev/test sets.
**[0:31]** To avoid overfitting the test set,
**[0:34]** technically for error analysis,
**[0:35]** you should manually only look at a dev set and not at a test set.
**[0:40]** But as a concrete example,
**[0:42]** if you're building the speech-activated rear-view mirror application,
**[0:47]** you might look or, I guess if it's speech,
**[0:50]** listen to examples in your dev set to try
**[0:53]** to figure out how your dev set is different than your training set.
**[0:56]** So, for example, you might find
**[0:58]** that a lot of dev set examples are very noisy and there's a lot of car noise.
**[1:03]** And this is one way that your dev set differs from your training set.
**[1:08]** And maybe you find other categories of errors.
**[1:11]** For example, in the speech-activated rear-view mirror in your car,
**[1:17]** you might find that it's often mis-recognizing
**[1:20]** street numbers because there are
**[1:22]** a lot more navigational queries which will have street addresses.
**[1:25]** So, getting street numbers right is really important.
**[1:28]** When you have insight into the nature of the dev set errors,
**[1:31]** or you have insight into how the dev
**[1:33]** set may be different or harder than your training set,
**[1:37]** what you can do is then try to find ways to make the training data more similar.
**[1:41]** Or, alternatively, try to collect more data similar to your dev and test sets.
**[1:47]** So, for example, if you find that car noise in the background is a major source of error,
**[1:53]** one thing you could do is simulate noisy in-car data.
**[2:00]** So a little bit more about how to do this on the next slide.
**[2:03]** Or you find that you're having a hard time recognizing street numbers,
**[2:06]** maybe you can go and deliberately try to get more data of
**[2:10]** people speaking out numbers and add that to your training set.
**[2:15]** Now, I realize that this slide is giving a rough guideline for things you could try.
**[2:20]** This isn't a systematic process and,
**[2:23]** I guess, it's no guarantee that you get the insights you need to make progress.
**[2:27]** But I have found that this manual insight,
**[2:32]** together we're trying to make the data more similar on the dimensions that
**[2:35]** matter that this often helps on a lot of the problems.
**[2:39]** So, if your goal is to make the training data more similar to your dev set,
**[2:46]** what are some things you can do?
**[2:48]** One of the techniques you can use is
**[2:50]** artificial data synthesis and let's discuss
**[2:52]** that in the context of addressing the car noise problem.
**[2:56]** So, to build a speech recognition system,
**[2:59]** maybe you don't have a lot of audio that was actually
**[3:01]** recorded inside the car with the background noise of a car,
**[3:05]** background noise of a highway, and so on.
**[3:07]** But, it turns out, there's a way to synthesize it.
**[3:09]** So, let's say that you've recorded
**[3:11]** a large amount of clean audio without this car background noise.
**[3:15]** So, here's an example of a clip you might have in your training set. >>The quick brown fox jumps over the lazy dog.
**[3:21]** By the way, this sentence is used a lot in AI for
**[3:26]** testing because this is a short sentence that contains every alphabet from A to Z,
**[3:30]** so you see this sentence a lot.
**[3:32]** But, given that recording of "the quick brown fox jumps over the lazy dog," you
**[3:36]** can then also get a recording of car noise like this. >>[car noise]
**[3:46]** So, that's what the inside of a car sounds like,
**[3:49]** if you're driving in silence.
**[3:50]** And if you take these two audio clips and add them together,
**[3:53]** you can then synthesize what
**[3:55]** saying "the quick brown fox jumps over the lazy dog" would sound like,
**[3:58]** if you were saying that in a noisy car. So, it sounds like this. >>The quick brown fox jumps over the lazy dog [car noise]
**[4:06]** So, this is a relatively simple audio synthesis example.
**[4:10]** In practice, you might synthesize other audio effects like
**[4:14]** reverberation which is the sound of
**[4:16]** your voice bouncing off the walls of the car and so on.
**[4:19]** But through artificial data synthesis,
**[4:22]** you might be able to quickly create more data that sounds like it
**[4:26]** was recorded inside the car without needing to go out there and collect tons of data,
**[4:32]** maybe thousands or tens of thousands of hours of
**[4:34]** data in a car that's actually driving along.
**[4:37]** So, if your error analysis shows you that you should try to
**[4:41]** make your data sound more like it was recorded inside the car,
**[4:45]** then this could be a reasonable process for
**[4:47]** synthesizing that type of data to give you a learning algorithm.
**[4:51]** Now, there is one note of caution I
**[4:54]** want to sound on artificial data synthesis which is that,
**[4:57]** let's say, you have 10,000 hours of data that was recorded against a quiet background.
**[5:04]** And, let's say, that you have just one hour of car noise.
**[5:11]** So, one thing you could try is take this one hour
**[5:14]** of car noise and repeat it 10,000 times in
**[5:17]** order to add to this 10,000 hours of data recorded against a quiet background.
**[5:24]** If you do that, the audio will sound perfectly fine to the human ear,
**[5:29]** but there is a chance,
**[5:30]** there is a risk that your learning algorithm will over fit to the one hour of car noise.
**[5:38]** And, in particular, if this is the set of
**[5:44]** all audio that you could record in the car or,
**[5:52]** maybe the sets of all car noise backgrounds you can imagine,
**[5:56]** if you have just one hour of car noise background,
**[5:59]** you might be simulating just a very small subset of this space.
**[6:03]** You might be just synthesizing from a very small subset of this space.
**[6:09]** And to the human ear,
**[6:10]** all this audio sounds just fine because one hour of car noise
**[6:13]** sounds just like any other hour of car noise to the human ear.
**[6:18]** But, it's possible that you're synthesizing data from a very small subset of this space,
**[6:23]** and the neural network might be
**[6:25]** overfitting to the one hour of car noise that you may have.
**[6:30]** I don't know if it will be practically feasible to
**[6:33]** inexpensively collect 10,000 hours of car noise so that
**[6:37]** you don't need to repeat the same one hour of
**[6:39]** car noise over and over but you have 10,000 unique hours
**[6:42]** of car noise to add to 10,000 hours of unique audio recording against a clean background.
**[6:48]** But it's possible, no guarantees.
**[6:50]** But it is possible that using 10,000 hours of unique car noise rather than just one hour,
**[6:56]** that could result in better performance for your learning algorithm.
**[7:01]** And the challenge with artificial data synthesis is to the human ear,
**[7:05]** as far as your ears can tell,
**[7:07]** these 10,000 hours all sound the same as this one hour,
**[7:10]** so you might end up creating this
**[7:13]** very impoverished synthesized data set from
**[7:16]** a much smaller subset of the space without actually realizing it.
**[7:19]** Here's another example of artificial data synthesis.
**[7:23]** Let's say you're building a self driving car and so you want to really detect
**[7:26]** vehicles like this and put a bounding box around it let's say.
**[7:31]** So, one idea that a lot of people have discussed is, well,
**[7:34]** why should you use computer graphics to simulate tons of images of cars?
**[7:39]** And, in fact, here are a couple of pictures of
**[7:41]** cars that were generated using computer graphics.
**[7:44]** And I think these graphics effects are actually pretty good and I can
**[7:46]** imagine that by synthesizing pictures like these,
**[7:50]** you could train a pretty good computer vision system for detecting cars.
**[7:54]** Unfortunately, the picture that I
**[7:56]** drew on the previous slide again applies in this setting.
**[8:00]** Maybe this is the set of all cars and,
**[8:05]** if you synthesize just a very small subset of these cars,
**[8:10]** then to the human eye,
**[8:12]** maybe the synthesized images look fine.
**[8:15]** But you might overfit to this small subset you're synthesizing.
**[8:18]** In particular, one idea that a lot of people have independently raised is,
**[8:23]** once you find a video game with good computer graphics of cars and just
**[8:26]** grab images from them and get a huge data set of pictures of cars,
**[8:31]** it turns out that if you look at a video game,
**[8:33]** if the video game has just 20 unique cars in the video game,
**[8:38]** then the video game looks fine
**[8:39]** because you're driving around in the video game and you see
**[8:42]** these 20 other cars and it looks like a pretty realistic simulation.
**[8:47]** But the world has a lot more than 20 unique designs of cars,
**[8:51]** and if your entire synthesized training set has only 20 distinct cars,
**[8:56]** then your neural network will probably overfit to these 20 cars.
**[9:00]** And it's difficult for a person to easily tell that,
**[9:03]** even though these images look realistic,
**[9:06]** you're really covering such a tiny subset of the sets of all possible cars.
**[9:11]** So, to summarize, if you think you have a data mismatch problem,
**[9:15]** I recommend you do error analysis,
**[9:17]** or look at the training set,
**[9:18]** or look at the dev set to try this figure out,
**[9:20]** to try to gain insight into how these two distributions of data might differ.
**[9:24]** And then see if you can find some ways to get
**[9:26]** more training data that looks a bit more like your dev set.
**[9:30]** One of the ways we talked about is artificial data synthesis.
**[9:33]** And artificial data synthesis does work.
**[9:35]** In speech recognition, I've seen artificial data synthesis significantly
**[9:39]** boost the performance of what were already very good speech recognition system.
**[9:43]** So, it can work very well.
**[9:45]** But, if you're using artificial data synthesis,
**[9:47]** just be cautious and bear in mind whether or not you might be accidentally
**[9:51]** simulating data only from a tiny subset of the space of all possible examples.
**[9:57]** So, that's it for how to deal with data mismatch.
**[10:01]** Next, I like to share with you some thoughts
**[10:04]** on how to learn from multiple types of data at the same time.
