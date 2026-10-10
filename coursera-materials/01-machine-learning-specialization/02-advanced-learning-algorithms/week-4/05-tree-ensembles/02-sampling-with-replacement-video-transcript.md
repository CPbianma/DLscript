---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 4
section: Tree ensembles
item_title: Sampling with replacement
duration: 4 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/zZ6pa/sampling-with-replacement
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Sampling with replacement — Transcript

**[0:01]** In order to build a tree ensemble,
**[0:05]** we're going to need a technique
**[0:06]** called sampling with replacement.
**[0:08]** Let's take a look at what that means.
**[0:10]** In order to illustrate
**[0:12]** how sampling with replacement works,
**[0:14]** I'm going to show you a demonstration of sampling with
**[0:18]** replacement using four tokens that are colored red,
**[0:21]** yellow, green, and blue.
**[0:23]** I actually have here with me four tokens of colors,
**[0:28]** red, yellow, green, and blue.
**[0:29]** I'm going to demonstrate
**[0:31]** what sampling with replacement using them look like.
**[0:34]** Here's a black velvet bag, empty.
**[0:38]** I'm going to take this example of four tokens,
**[0:42]** and drop them in.
**[0:43]** I'm going to sample four times
**[0:45]** with replacement out of this bag.
**[0:47]** What that means, I'm going to shake it up,
**[0:49]** and can't see when I'm picking,
**[0:51]** pick out one token, turns out to be green.
**[0:54]** The term with replacement means that if
**[0:57]** I take out the next token, I'm going to take this,
**[1:00]** and put it back in, and shake it up again,
**[1:02]** and then take on another one, yellow.
**[1:05]** Replace it. That's a little replacement part.
**[1:08]** Then go again, blue replace it again,
**[1:12]** and then pick on one more, which is blue again.
**[1:16]** That sequence of tokens I got
**[1:18]** was green, yellow, blue, blue.
**[1:20]** Notice that I got blue twice,
**[1:22]** and didn't get red even a single time.
**[1:24]** If you were to repeat this sampling with
**[1:27]** replacement procedure multiple times,
**[1:29]** if you were to do it again,
**[1:31]** you might get red,
**[1:33]** yellow, red, green, or green,
**[1:35]** green, blue, red.
**[1:37]** Or you might also get red, blue, yellow, green.
**[1:43]** Notice that the with replacement part of this is critical
**[1:48]** because if I were
**[1:49]** not replacing a token every time I sample,
**[1:52]** then if I were to pour four tokens from my bag of four,
**[1:56]** I will always just get the same four tokens.
**[1:58]** That's why replacing a
**[2:00]** token after I pull it out each time,
**[2:02]** is important to make sure I don't
**[2:04]** just get the same four tokens every single time.
**[2:07]** The way that sampling with replacement
**[2:10]** applies to building an ensemble of trees is as follows.
**[2:15]** We are going to construct
**[2:16]** multiple random training sets
**[2:19]** that are all slightly different
**[2:21]** from our original training set.
**[2:23]** In particular, we're going to take
**[2:24]** our 10 examples of cats and dogs.
**[2:27]** We're going to put the 10 training examples
**[2:30]** in a theoretical bag.
**[2:32]** Please don't actually put a real cat or dog in a bag.
**[2:36]** That sounds inhumane, but you can take
**[2:39]** a training example and put it
**[2:40]** in a theoretical bag if you want.
**[2:42]** I'm using this theoretical bag,
**[2:44]** we're going to create
**[2:46]** a new random training set of
**[2:49]** 10 examples of the exact same size
**[2:51]** as the original data set.
**[2:53]** The way we'll do so is we're reaching and
**[2:56]** pick out one random training example.
**[2:58]** Let's say we get this training example.
**[3:01]** Then we put it back into the bag,
**[3:03]** and then again randomly pick
**[3:06]** out one training example and so you get that.
**[3:09]** You pick again and again and again.
**[3:14]** Notice now this fifth training example
**[3:16]** is identical to the second one that we had out there.
**[3:19]** But that's fine. You keep going and keep going,
**[3:22]** and we get another repeats the example,
**[3:24]** and so on and so forth.
**[3:26]** Until eventually you end up with 10 training examples,
**[3:29]** some of which are repeats.
**[3:31]** You notice also that this training set does not
**[3:34]** contain all 10 of
**[3:36]** the original training examples, but that's okay.
**[3:38]** That is part of the sampling with replacement procedure.
**[3:41]** The process of sampling with replacement,
**[3:43]** lets you construct a new training set
**[3:46]** that's a little bit similar to,
**[3:48]** but also pretty different
**[3:49]** from your original training set.
**[3:51]** It turns out that this would be
**[3:53]** the key building block for building an ensemble of trees.
**[3:56]** Let's take a look in the next video
**[3:58]** and how you could do that.
