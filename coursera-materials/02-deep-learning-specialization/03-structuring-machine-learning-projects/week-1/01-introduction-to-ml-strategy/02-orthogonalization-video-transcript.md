---
type: video-transcript
specialization: Deep Learning Specialization
course: Structuring Machine Learning Projects
week: 1
section: Introduction to ML Strategy
item_title: Orthogonalization
duration: 11 min
source_url: https://www.coursera.org/learn/machine-learning-projects/lecture/FRvQe/orthogonalization
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Orthogonalization — Transcript

**[0:00]** One of the challenges with building machine learning systems is that there's
**[0:03]** so many things you could try, so many things you could change.
**[0:06]** Including, for example, so many hyperparameters you could tune.
**[0:10]** One of the things I've noticed is about the most effective machine learning people
**[0:14]** is they're very clear-eyed about what to tune
**[0:17]** in order to try to achieve one effect.
**[0:20]** This is a process we call orthogonalization.
**[0:22]** Let me tell you what I mean.
**[0:25]** Here's a picture of an old school television,
**[0:28]** with a lot of knobs that you could tune to adjust the picture in various ways.
**[0:35]** So for these old TV sets, maybe there was one knob to adjust how
**[0:39]** tall vertically your image is and another knob to adjust how wide it is.
**[0:45]** Maybe another knob to adjust how trapezoidal it is,
**[0:49]** another knob to adjust how much to move the picture left and right,
**[0:52]** another one to adjust how much the picture's rotated, and so on.
**[0:58]** And what TV designers had spent a lot of time doing was to build the circuitry,
**[1:03]** really often analog circuitry back then,
**[1:06]** to make sure each of the knobs had a relatively interpretable function.
**[1:11]** Such as one knob to tune this, one knob to tune this, one knob to tune this,
**[1:15]** and so on.
**[1:17]** In contrast, imagine if you had a knob that tunes 0.1 x how tall the image is,
**[1:24]** + 0.3 x how wide the image is,- 1.7 x how trapezoidal the image is,
**[1:32]** + 0.8 times the position of the image on the horizontal axis, and so on.
**[1:39]** If you tune this knob, then the height of the image, the width of the image,
**[1:42]** how trapezoidal it is, how much it shifts, it all changes all at the same time.
**[1:46]** If you have a knob like that, it'd be almost impossible to tune the TV so
**[1:51]** that the picture gets centered in the display area.
**[1:54]** So in this context, orthogonalization refers to that the TV designers
**[2:00]** had designed the knobs so that each knob kind of does only one thing.
**[2:06]** And this makes it much easier to tune the TV, so
**[2:09]** that the picture gets centered where you want it to be.
**[2:14]** Here's another example of orthogonalization.
**[2:17]** If you think about learning to drive a car, a car has three main controls,
**[2:22]** which are steering, the steering wheel decides how much you go left or
**[2:28]** right, acceleration, and braking.
**[2:31]** So these three controls, or really one control for steering and
**[2:35]** another two controls for your speed.
**[2:38]** It makes it relatively interpretable,
**[2:42]** what your different actions through different controls will do to your car.
**[2:46]** But now imagine if someone were to build a car so that there was a joystick,
**[2:51]** where one axis of the joystick controls 0.3 x your steering
**[2:56]** angle,- 0.8 x your speed.
**[3:00]** And you had a different control that controls 2
**[3:05]** x the steering angle, + 0.9 x the speed of your car.
**[3:12]** In theory, by tuning these two knobs,
**[3:15]** you could get your car to steer at the angle and at the speed you want.
**[3:19]** But it's much harder than if you had just one single control for
**[3:22]** controlling the steering angle, and a separate, distinct set of controls for
**[3:26]** controlling the speed.
**[3:28]** So the concept of orthogonalization refers to that,
**[3:31]** if you think of one dimension of what you want to do as controlling
**[3:35]** a steering angle, and another dimension as controlling your speed.
**[3:39]** Then you want one knob to just affect the steering angle as much as possible,
**[3:44]** and another knob, in the case of the car, is really acceleration and
**[3:49]** braking, that controls your speed.
**[3:51]** But if you had a control that mixes the two together,
**[3:54]** like a control like this one that affects both your steering angle and your speed,
**[3:59]** something that changes both at the same time,
**[4:01]** then it becomes much harder to set the car to the speed and angle you want.
**[4:06]** And by having orthogonal, orthogonal means at 90 degrees to each other.
**[4:11]** By having orthogonal controls that are ideally aligned with the things you
**[4:16]** actually want to control, it makes it much easier to tune the knobs you have to tune.
**[4:21]** To tune the steering wheel angle, and
**[4:23]** your accelerator, your braking, to get the car to do what you want.
**[4:28]** So how does this relate to machine learning?
**[4:32]** For a supervised learning system to do well, you usually need to
**[4:35]** tune the knobs of your system to make sure that four things hold true.
**[4:40]** First, is that you usually have to make sure that you're at least doing well
**[4:43]** on the training set.
**[4:45]** So performance on the training set needs to pass some acceptability assessment.
**[4:50]** For some applications,
**[4:52]** this might mean doing comparably to human level performance.
**[4:57]** But this will depend on your application, and
**[5:00]** we'll talk more about comparing to human level performance next week.
**[5:04]** But after doing well on the training sets,
**[5:07]** you then hope that this leads to also doing well on the dev set.
**[5:12]** And you then hope that this also does well on the test set.
**[5:16]** And finally, you hope that doing well on the test set on the cost
**[5:20]** function results in your system performing in the real world.
**[5:23]** So you hope that this resolves in happy cat
**[5:28]** picture app users, for example.
**[5:32]** So to relate back to the TV tuning example, if the picture of your TV was
**[5:37]** either too wide or too narrow, you wanted one knob to tune in order to adjust that.
**[5:43]** You don't want to have to carefully adjust five different knobs,
**[5:45]** which also affect different things.
**[5:47]** You want one knob to just affect the width of your TV image.
**[5:52]** So in a similar way, if your algorithm is not fitting the training set well on
**[5:57]** the cost function, you want one knob, yes, that's my attempt to draw a knob.
**[6:02]** Or maybe one specific set of knobs that you can use,
**[6:05]** to make sure you can tune your algorithm to make it fit well on the training set.
**[6:10]** So the knobs you use to tune this are, you might train a bigger network.
**[6:16]** Or you might switch to a better optimization algorithm,
**[6:20]** like the Adam optimization algorithm, and so
**[6:24]** on, into some other options we'll discuss later this week and next week.
**[6:28]** In contrast, if you find that the algorithm is not fitting the dev set well,
**[6:33]** then there's a separate set of knobs.
**[6:36]** Yes, that's my not very artistic rendering of another knob,
**[6:40]** you want to have a distinct set of knobs to try.
**[6:44]** So for example, if your algorithm is not doing well on the dev set, it's doing well
**[6:49]** on the training set but not on the dev set, then you have a set of knobs around
**[6:53]** regularization that you can use to try to make it satisfy the second criteria.
**[6:57]** So the analogy is, now that you've tuned the width of your TV set,
**[7:01]** if the height of the image isn't quite right,
**[7:04]** then you want a different knob in order to tune the height of the TV image.
**[7:08]** And you want to do this hopefully without affecting the width of your TV
**[7:13]** image too much.
**[7:14]** And getting a bigger training set would be another knob you could use,
**[7:20]** that helps your learning algorithm generalize better to the dev set.
**[7:26]** Now, having adjusted the width and height of your TV image, well,
**[7:30]** what if it doesn't meet the third criteria?
**[7:32]** What if you do well on the dev set but not on the test set?
**[7:36]** If that happens,
**[7:37]** then the knob you tune is, you probably want to get a bigger dev set.
**[7:42]** Because if it does well on the dev set but not the test set, it probably means you've
**[7:47]** overtuned to your dev set, and you need to go back and find a bigger dev set.
**[7:52]** And finally, if it does well on the test set, but it isn't delivering to you
**[7:57]** a happy cat picture app user, then what that means is that you want to go back and
**[8:04]** change either the dev set or the cost function.
**[8:13]** Because if doing well on the test set according to some cost function
**[8:18]** doesn't correspond to your algorithm doing what you need it to do in the real world,
**[8:21]** then it means that either your dev test set distribution isn't set correctly,
**[8:27]** or your cost function isn't measuring the right thing.
**[8:30]** I know I'm going over these examples quite quickly, but we'll go much more
**[8:34]** into detail on these specific knobs later this week and next week.
**[8:39]** So if you aren't following all the details right now, don't worry about it.
**[8:42]** But I want to give you a sense of this orthogonalization process,
**[8:46]** that you want to be very clear about which of these maybe four issues,
**[8:50]** the different things you could tune, are trying to address.
**[8:53]** And when I train a neural network, I tend not to use early stopping.
**[8:57]** It's not a bad technique, quite a lot of people do it.
**[9:00]** But I personally find early stopping difficult to think about.
**[9:04]** Because this is a knob that simultaneously affects how well you fit the training set,
**[9:09]** because if you stop early, you fit the training set less well.
**[9:13]** It also simultaneously is often done to improve your dev set performance.
**[9:18]** So this is one knob that is less orthogonalized,
**[9:21]** because it simultaneously affects two things.
**[9:25]** It's like a knob that simultaneously affects both the width and
**[9:28]** the height of your TV image.
**[9:30]** And it doesn't mean that it's a bad knob to use, you can use it if you want.
**[9:34]** But when you have more orthogonalized controls,
**[9:37]** such as these other ones that I'm writing down here,
**[9:40]** then it just makes the process of tuning your network much easier.
**[9:44]** So I hope that gives you a sense of what orthogonalization means.
**[9:47]** Just like when you look at the TV image, it's nice if you can say, my TV image
**[9:51]** is too wide, so I'm going to tune this knob, or it's too tall, so I'm going to
**[9:55]** tune that knob, or it's too trapezoidal, so I'm going to have to tune that knob.
**[9:59]** In machine learning, it's nice if you can look at your system and
**[10:01]** say, this piece of it is wrong.
**[10:03]** It does not do well on the training set, it does not do well on the dev set,
**[10:06]** it does not do well on the test set, or it's doing well on the test set but
**[10:08]** just not in the real world.
**[10:09]** But figure out exactly what's wrong, and then have exactly one knob, or
**[10:13]** a specific set of knobs that helps to just solve that problem
**[10:17]** that is limiting the performance of machine learning system.
**[10:20]** So what we're going to do this week and next week is go through how to diagnose
**[10:24]** what exactly is the bottleneck to your system's performance.
**[10:28]** As well as identify the specific set of knobs you could use to tune your system to
**[10:32]** improve that aspect of its performance.
**[10:34]** So let's start going more into the details of this process.
