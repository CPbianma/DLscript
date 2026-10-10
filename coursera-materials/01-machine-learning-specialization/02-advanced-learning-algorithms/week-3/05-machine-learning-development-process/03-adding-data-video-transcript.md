---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 3
section: Machine learning development process
item_title: Adding data
duration: 14 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/AHAJy/adding-data
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# Adding data — Transcript

**[0:02]** In this video, I'd like to share with you some tips for
**[0:05]** adding data or collecting more data or sometimes even creating more data for
**[0:10]** your machine learning application.
**[0:12]** Just a heads up that this in the next few videos will seem a little bit like a grab
**[0:17]** bag of different techniques.
**[0:18]** And I apologize if it seems a little bit grab baggy and
**[0:21]** that's because machine learning applications are different.
**[0:25]** Machine learning is applied to so many different problems and for
**[0:28]** some humans are great at creating labels.
**[0:31]** And for some you can get more data and for some you can't.
**[0:34]** And that's why different applications actually sometimes call for
**[0:38]** slightly different techniques.
**[0:40]** But I hope in this in the next few videos to share with you some of the techniques
**[0:44]** that are found to be most useful for different applications,
**[0:47]** although not every one of them will apply for every single application.
**[0:50]** But I hope many of them would be useful for
**[0:52]** many of the applications that you'll be working on as well.
**[0:56]** But let's take a look at some tips for how to add data for your application.
**[1:01]** When training machine learning algorithms,
**[1:03]** it feels like always we wish we had even more data almost all the time.
**[1:08]** And so sometimes it's tempting to let's just get more data of everything.
**[1:14]** But, trying to get more data of all types can be slow and expensive.
**[1:20]** Instead, an alternative way of adding data might be to focus on adding
**[1:26]** more data of the types where analysis has indicated it might help.
**[1:31]** In the previous slide we saw if error analysis reviewed that
**[1:35]** pharma spam was a large problem, then you may decide to have a more
**[1:40]** targeted effort not to get more data everything under the sun but
**[1:45]** to stay focused on getting more examples of pharma spam
**[1:50]** And with a more modest cost this could let you add just the emails you
**[1:55]** need to hope you're learning and get smarter on recognizing pharma spam.
**[2:01]** And so one example of how you might do this is,
**[2:05]** if you have a lot of unlabeled email data, say emails sitting around and
**[2:10]** no one has bothered to label yet as spam or non-spam
**[2:14]** You may able to ask your labors to quickly skim through the unlabeled data and
**[2:20]** find more examples specifically a pharma related spam.
**[2:25]** And this could boost your learning algorithm performance much more than just
**[2:30]** trying to add more data of all sorts of emails.
**[2:34]** But the more general pattern I hope you take away from this is,
**[2:37]** if you have some ways to add more data of everything that's okay.
**[2:41]** Nothing wrong with that.
**[2:43]** But if error analysis has indicated that there are certain subsets
**[2:48]** of the data that the algorithm is doing particularly poorly on.
**[2:52]** And that you want to improve performance on,
**[2:55]** then getting more data of just the types where you wanted to do better.
**[2:59]** Be it more examples of pharmaceutical spam or
**[3:02]** more examples of phishing spam or something else.
**[3:04]** That could be a more efficient way to add just a little bit of data but
**[3:08]** boost your algorithms performance by quite a lot.
**[3:11]** Beyond getting your hands on brand new training examples xy.
**[3:16]** There's another technique that's widely used especially for images and
**[3:22]** audio data that can increase your training set size significantly.
**[3:27]** This technique is called data augmentation.
**[3:30]** And what we're going to do is take an existing training example to create a new
**[3:34]** training example.
**[3:35]** For example if you're trying to recognize the letters from A to Z for
**[3:39]** an OCR optical character recognition problem.
**[3:43]** So not just the digits 0-9 but also the letters from A to Z.
**[3:47]** Given an image like this, you might decide to create
**[3:52]** a new training example by rotating the image a bit.
**[3:57]** Or by enlarging the image a bit or by shrinking a little bit or
**[4:03]** by changing the contrast of the image.
**[4:07]** And these are examples of distortions to the image that don't change
**[4:12]** the fact that this is still the letter A
**[4:16]** And for some letters but not others you can also take the mirror image
**[4:20]** of the letter and it still looks like the letter A.
**[4:24]** But this only applies to some letters but
**[4:28]** these would be ways of taking a training example X, Y.
**[4:33]** And applying a distortion or transformation to the input X
**[4:38]** ,in order to come up with another example that has the same label.
**[4:44]** And by doing this you're telling the algorithm that the letter A rotated a bit
**[4:48]** or enlarged a bit or shrunk a little bit it is still the letter A.
**[4:53]** And creating additional examples like this holds the learning algorithm,
**[4:57]** do a better job learning how to recognize the letter A.
**[5:01]** For a more advanced example of data augmentation.
**[5:05]** You can also take the letter A and place a grid on top of it.
**[5:09]** And by introducing random warping of this grid, you can take the letter A.
**[5:16]** And introduce warpings of the leather A to create a much richer library of
**[5:20]** examples of the letter A.
**[5:23]** And this process of distorting these examples then has turned one image
**[5:28]** of one example into here training examples that you can feed to
**[5:32]** the learning algorithm to hope it learn more robustly.
**[5:36]** What is the letter A.
**[5:37]** This idea of data augmentation also works for speech recognition.
**[5:42]** Let's say for a voice search application,
**[5:45]** you have an original audio clip that sounds like this.
**[5:49]** >> What is today's weather.
**[5:51]** >> One way you can apply data augmentation to speech
**[5:55]** data would be to take noisy background audio like this.
**[6:00]** For example, this is what the sound of a crowd sounds like.
**[6:08]** And it turns out that if you take these two audio clips,
**[6:12]** the first one and the crowd noise and you add them together,
**[6:16]** then you end up with an audio clip that sounds like this.
**[6:20]** >> What is today's weather.
**[6:22]** >> And you just created an audio clip that sounds like someone saying what's
**[6:27]** the weather today.
**[6:28]** But they're saying it around the noisy crowd in the background.
**[6:32]** Or in fact if you were to take a different background noise,
**[6:36]** say someone in the car, this is what background noise of a car sounds like.
**[6:44]** And you want to add the original audio clip to the car noise, then you get this.
**[6:50]** >> What is today's weather.
**[6:52]** >> And it sounds like the original audio clip, but
**[6:56]** as if the speaker was saying it from a car.
**[6:59]** And the more advanced data augmentation step would be if you make the original
**[7:03]** audio sound like you're recording it on a bad cell phone connection like this.
**[7:10]** And so we've seen how you can take one audio clip and turn it into three training
**[7:15]** examples here, one with crowd background noise, one with car background noise and
**[7:20]** one as if it was recorded on a bad cell phone connection.
**[7:23]** And the times I worked on speech recognition systems,
**[7:26]** this was actually a really critical technique for increasing artificially
**[7:31]** the size of the training data I had to build a more accurate speech recognizer.
**[7:36]** One tip for data augmentation is that the changes or
**[7:39]** the distortions you make to the data,
**[7:42]** should be representative of the types of noise or distortions in the test set.
**[7:48]** So for example, if you take the letter a and warp it like this, this still looks
**[7:53]** like examples of letters you might see out there that you would like to recognize.
**[7:58]** Or for audio adding background noise or bad cellphone connection
**[8:03]** if that's representative of what you expect to hear in the test set,
**[8:08]** then this will be helpful ways to carry out data augmentation on your audio data.
**[8:14]** In contrast is usually not that helpful at purely random meaningless noise to data.
**[8:21]** For example,, you have taken the letter A and
**[8:24]** I've added per pixel noise where if Xi is the intensity or
**[8:28]** the brightness of pixel i, if I were to just add noise to each pixel,
**[8:33]** they end up with images that look like this.
**[8:37]** But if to the extent that this isn't that representative of what you see in
**[8:41]** the test set because you don't often get images like this in the test
**[8:44]** set is actually going to be less helpful.
**[8:47]** So one way to think about data augmentation is how can you modify or
**[8:52]** warp or distort or make more noise in your data.
**[8:55]** But in a way so
**[8:56]** that what you get is still quite similar to what you have in your test set,
**[9:01]** because that's what the learning algorithm will ultimately end up doing well on.
**[9:07]** Now, whereas data augmentation takes an existing training example and
**[9:11]** modifies it to create another training example.
**[9:15]** There's one of the techniques which is data synthesis in which you make up brand
**[9:19]** new examples from scratch.
**[9:21]** Not by modifying an existing example but by creating brand new examples.
**[9:27]** So take the example of photo OCR.
**[9:30]** Photo OCR or photo optical character recognition refers to
**[9:35]** the problem of looking at an image like this and
**[9:38]** automatically having a computer read the text that appears in this image.
**[9:43]** So there's a lot of text in this image.
**[9:46]** How can you train an OCR algorithm to read text from an image like this?
**[9:52]** Well, when you look closely at what the letters in this image looks like they
**[9:57]** actually look like this.
**[9:59]** So this is real data from a photo OCR task.
**[10:02]** And one key step with the photo OCR task is to be able to look at the little image
**[10:07]** like this, and recognize the letter at the middle.
**[10:10]** So this has T in the middle, this has the letter L in the middle,
**[10:15]** this has the letter C in the middle and so on.
**[10:19]** So one way to create artificial data for this task is if you go
**[10:24]** to your computer's text editor, you find that it has a lot
**[10:29]** of different fonts and what you can do is take these fonts and
**[10:34]** basically type of random text in your text editor.
**[10:39]** And screenshotted using different colors and different contrasts and
**[10:44]** very different fonts and you get synthetic data like that on the right.
**[10:50]** The images on the left were real data from real pictures taken out in the world.
**[10:55]** The images on the right are synthetically generated using fonts on the computer,,
**[11:00]** and it actually looks pretty realistic.
**[11:03]** So with synthetic data generation like this you can generate a very
**[11:08]** large number of images or examples for your photo OCR task.
**[11:14]** It can be a lot of work to write the code to generate realistic looking
**[11:18]** synthetic data for a given application.
**[11:20]** But when you spend the time to do so,
**[11:23]** it can sometimes help you generate a very large amount of data for
**[11:27]** your application and give you a huge boost to your algorithm's performance.
**[11:33]** Synthetic data generation has been used most probably for
**[11:37]** computer vision tasks and less for other applications.
**[11:41]** Not that much for audio tasks as well.
**[11:44]** All the techniques you've seen in this video related to
**[11:48]** finding ways to engineer the data used by your system.
**[11:52]** In the way that machine learning has developed over the last several decades,
**[11:56]** many decades.
**[11:57]** Most machine learning researchers attention was on the conventional model
**[12:02]** centric approach and here's what I mean.
**[12:06]** A machine learning system or an AI system includes both code to implement your
**[12:10]** album or your model, as well as the data that you train the algorithm model.
**[12:15]** and over the last few decades, most researchers doing machine learning
**[12:20]** research would download the data set and hold the data fixed while they focus on
**[12:24]** improving the code or the algorithm or the model.
**[12:29]** Thanks to that paradigm of machine learning research.
**[12:32]** I find that today the algorithm we have access to such as linear regression,
**[12:37]** logistic regression, neural networks, also decision trees we should see next week.
**[12:43]** There are algorithms that already very good and
**[12:46]** will work well for many applications.
**[12:49]** And so sometimes it can be more fruitful to spend more of your
**[12:54]** time taking a data centric approach in which you
**[12:58]** focus on engineering the data used by your algorithm.
**[13:02]** And this can be anything from collecting more data just on pharmaceutical spam.
**[13:08]** If that's what error analysis told you to do.
**[13:11]** To using data augmentation to generate more images or more audio or
**[13:15]** using data synthesis to just create more training examples.
**[13:19]** And sometimes that focus on the data can be an efficient way to help your learning
**[13:24]** algorithm improve its performance.
**[13:26]** So I hope that this video gives you a set of tools to be efficient and
**[13:31]** effective in how you add more data to get your learning algorithm to work better.
**[13:38]** Now there are also some applications where you just don't have that much data and
**[13:42]** it's really hard to get more data.
**[13:44]** It turns out that there's a technique called transfer learning which could apply
**[13:49]** in that setting to give your learning algorithm performance a huge boost.
**[13:53]** And the key idea is to take data from a totally different barely related tasks.
**[13:59]** But using a neural network there's sometimes ways to use that data from
**[14:03]** a very different tasks to get your algorithm to do better on your
**[14:07]** application.
**[14:08]** Doesn't apply to everything, but when it does it can be very powerful.
**[14:12]** Let's take a look in the next video and how transfer learning works.
