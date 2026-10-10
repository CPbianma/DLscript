---
type: video-transcript
specialization: Deep Learning Specialization
course: Structuring Machine Learning Projects
week: 2
section: Error Analysis
item_title: Carrying Out Error Analysis
duration: 11 min
source_url: https://www.coursera.org/learn/machine-learning-projects/lecture/GwViP/carrying-out-error-analysis
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Carrying Out Error Analysis — Transcript

**[0:00]** Hello, and welcome back.
**[0:02]** If you're trying to get a learning algorithm to do a task that humans can do.
**[0:06]** And if your learning algorithm is not yet at the performance of a human.
**[0:10]** Then manually examining mistakes that your algorithm is making,
**[0:13]** can give you insights into what to do next.
**[0:16]** This process is called error analysis.
**[0:19]** Let's start with an example.
**[0:20]** Let's say you're working on your cat classifier, and you've achieved 90% accuracy,
**[0:24]** or equivalently 10% error, on your dev set.
**[0:29]** And let's say this is much worse than you're hoping to do.
**[0:32]** Maybe one of your teammates looks at some of the examples that the algorithm is
**[0:36]** misclassifying, and notices that it is miscategorizing some dogs as cats.
**[0:42]** And if you look at these two dogs, maybe they look a little bit like a cat,
**[0:46]** at least at first glance.
**[0:47]** So maybe your teammate comes to you with a proposal for
**[0:51]** how to make the algorithm do better, specifically on dogs, right?
**[0:56]** You can imagine building a focus effort, maybe to collect more dog pictures, or
**[1:01]** maybe to design features specific to dogs, or something.
**[1:04]** In order to make your cat classifier do better on dogs, so
**[1:07]** it stops misrecognizing these dogs as cats.
**[1:11]** So the question is, should you go ahead and
**[1:13]** start a project focused on the dog problem?
**[1:19]** There could be several months of works you could do in order to make your algorithm
**[1:23]** make fewer mistakes on dog pictures.
**[1:27]** So is that worth your effort?
**[1:29]** Well, rather than spending a few months doing this,
**[1:32]** only to risk finding out at the end that it wasn't that helpful.
**[1:36]** Here's an error analysis procedure that can let you very quickly tell whether or not
**[1:40]** this could be worth your effort.
**[1:43]** Here's what I recommend you do.
**[1:45]** First, get about, say 100 mislabeled dev set examples, then examine them manually.
**[1:51]** Just count them up one at a time, to see how many of these mislabeled
**[1:56]** examples in your dev set are actually pictures of dogs.
**[1:59]** Now, suppose that it turns out
**[2:02]** that 5% of your 100 mislabeled dev set examples are pictures of dogs.
**[2:07]** So, that is, if 5 out of 100 of these mislabeled
**[2:12]** dev set examples are dogs, what this means is that of the 100 examples.
**[2:18]** Of a typical set of 100 examples you're getting wrong, even if you completely solve the dog problem,
**[2:23]** you only get 5 out of 100 more correct.
**[2:28]** Or in other words, if only 5% of your errors are dog pictures, then the best you
**[2:33]** then the best you could easily hope to do, if you spend a lot of time on the dog problem.
**[2:38]** Is that your error might go down from 10% error,
**[2:43]** down to 9.5% error, right?
**[2:46]** So this a 5% relative decrease in error, from 10% down to 9.5%.
**[2:53]** And so you might reasonably decide that this is not the best use of your time.
**[2:58]** Or maybe it is, but at least this gives you a ceiling, right?
**[3:02]** Upper bound on how much you could improve performance by working on the dog problem,
**[3:08]** right?
**[3:10]** In machine learning, sometimes we call this the ceiling on performance.
**[3:15]** Which just means, what's in the best case?
**[3:17]** How well could working on the dog problem help you?
**[3:22]** But now, suppose something else happens.
**[3:25]** Suppose that we look at your 100 mislabeled dev set examples,
**[3:28]** you find that 50 of them are actually dog images.
**[3:32]** So 50% of them are dog pictures.
**[3:35]** Now you could be much more optimistic about spending time on the dog problem.
**[3:39]** In this case, if you actually solve the dog problem,
**[3:42]** your error would go down from this 10%, down to potentially 5% error.
**[3:47]** And you might decide that halving your error could be worth a lot of effort.
**[3:52]** Focus on reducing the problem of mislabeled dogs.
**[3:56]** I know that in machine learning, sometimes we speak disparagingly of hand
**[4:00]** engineering things, or using too much value insight.
**[4:03]** But if you're building applied systems, then this simple counting procedure,
**[4:09]** error analysis, can save you a lot of time.
**[4:12]** In terms of deciding what's the most important, or
**[4:14]** what's the most promising direction to focus on.
**[4:19]** In fact, if you're looking at 100 mislabeled dev set examples,
**[4:24]** maybe this is a 5 to 10 minute effort.
**[4:27]** To manually go through 100 examples, and
**[4:29]** manually count up how many of them are dogs.
**[4:32]** And depending on the outcome, whether there's more like 5%, or
**[4:36]** 50%, or something else.
**[4:37]** This, in just 5 to 10 minutes,
**[4:39]** gives you an estimate of how worthwhile this direction is.
**[4:44]** And could help you make a much better decision, whether or
**[4:46]** not to spend the next few months focused on trying to find solutions to
**[4:51]** solve the problem of mislabeled dogs.
**[4:54]** In this slide, we'll describe using error analysis to evaluate whether or
**[4:58]** not a single idea, dogs in this case, is worth working on.
**[5:02]** Sometimes you can also evaluate multiple ideas in parallel doing error analysis.
**[5:08]** For example, let's say you have several ideas in improving your cat detector.
**[5:12]** Maybe you can improve performance on dogs?
**[5:16]** Or maybe you notice that sometimes, what are called great cats,
**[5:19]** such as lions, panthers, cheetahs, and so on.
**[5:22]** That they are being recognized as small cats, or house cats.
**[5:25]** So you could maybe find a way to work on that.
**[5:28]** Or maybe you find that some of your images are blurry, and it would be nice if you
**[5:32]** could design something that just works better on blurry images.
**[5:37]** And maybe you have some ideas on how to do that.
**[5:41]** So if carrying out error analysis to evaluate these three ideas,
**[5:45]** what I would do is create a table like this.
**[5:50]** And I usually do this in a spreadsheet, but
**[5:53]** using an ordinary text file will also be okay.
**[5:57]** And on the left side,
**[5:58]** this goes through the set of images you plan to look at manually.
**[6:02]** So this maybe goes from 1 to 100, if you look at 100 pictures.
**[6:06]** And the columns of this table, of the spreadsheet,
**[6:09]** will correspond to the ideas you're evaluating.
**[6:12]** So the dog problem, the problem of great cats, and blurry images.
**[6:18]** And I usually also leave space in the spreadsheet to write comments.
**[6:23]** So remember, during error analysis,
**[6:25]** you're just looking at dev set examples that your algorithm has misrecognized.
**[6:30]** So if you find that the first misrecognized image is a picture of a dog,
**[6:34]** then I'd put a check mark there.
**[6:36]** And to help myself remember these images,
**[6:39]** sometimes I'll make a note in the comments.
**[6:41]** So maybe that was a pit bull picture.
**[6:44]** If the second picture was blurry, then make a note there.
**[6:48]** If the third one was a lion, on a rainy day, in the zoo that was misrecognized.
**[6:53]** Then that's a great cat, and the blurry data.
**[6:56]** Make a note in the comment section, rainy day at zoo, and
**[7:00]** it was the rain that made it blurry, and so on.
**[7:05]** Then finally, having gone through some set of images,
**[7:08]** I would count up what percentage of these algorithms.
**[7:11]** Or what percentage of each of these error categories were attributed to the dog,
**[7:16]** or great cat, blurry categories.
**[7:19]** So maybe 8% of these images you examine turn out be dogs, and
**[7:26]** maybe 43% great cats, and 61% were blurry.
**[7:32]** So this just means going down each column, and
**[7:34]** counting up what percentage of images have a check mark in that column.
**[7:39]** As you're part way through this process,
**[7:41]** sometimes you notice other categories of mistakes.
**[7:44]** So, for example, you might find that Instagram style filter, those fancy
**[7:50]** image filters, are also messing up your classifier.
**[7:55]** In that case,
**[7:55]** it's actually okay, part way through the process, to add another column like that.
**[8:00]** For the multi-colored filters, the Instagram filters, and
**[8:03]** the Snapchat filters.
**[8:04]** And then go through and count up those as well, and
**[8:07]** figure out what percentage comes from that new error category.
**[8:12]** The conclusion of this process gives you an estimate of how worthwhile it might
**[8:16]** be to work on each of these different categories of errors.
**[8:19]** For example, clearly in this example, a lot of the mistakes were made on blurry
**[8:23]** images, and quite a lot on were made on great cat images.
**[8:28]** And so the outcome of this analysis is not that you must work on blurry images.
**[8:35]** This doesn't give you a rigid mathematical formula that tells you what to do,
**[8:39]** but it gives you a sense of the best options to pursue.
**[8:43]** It also tells you, for example,
**[8:44]** that no matter how much better you do on dog images, or on Instagram images.
**[8:50]** You at most improve performance by maybe 8%, or 12%, in these examples.
**[8:55]** Whereas you can to better on great cat images, or
**[8:57]** blurry images, the potential improvement.
**[9:00]** Now there's a ceiling in terms of how much you could improve performance,
**[9:03]** is much higher.
**[9:05]** So depending on how many ideas you have for improving performance on great cats,
**[9:09]** on blurry images.
**[9:10]** Maybe you could pick one of the two, or if you have enough personnel on your team,
**[9:13]** maybe you can have two different teams.
**[9:15]** Have one work on improving errors on great cats, and
**[9:18]** a different team work on improving errors on blurry images.
**[9:27]** But this quick counting procedure, which you can often do in, at most,
**[9:31]** small numbers of hours.
**[9:33]** Can really help you make much better prioritization decisions,
**[9:36]** and understand how promising different approaches are to work on.
**[9:40]** So to summarize, to carry out error analysis, you should find a set of
**[9:44]** mislabeled examples, either in your dev set, or in your development set.
**[9:48]** And look at the mislabeled examples for false positives and false negatives.
**[9:53]** And just count up the number of errors that fall into various
**[9:56]** different categories.
**[9:57]** During this process, you might be inspired to generate new categories of errors,
**[10:01]** like we saw.
**[10:02]** If you're looking through the examples and you say gee, there are a lot of Instagram filters,
**[10:06]** or Snapchat filters, they're also messing up my classifier.
**[10:09]** You can create new categories during that process.
**[10:11]** But by counting up the fraction of examples that are mislabeled in
**[10:14]** different ways, often this will help you prioritize.
**[10:17]** Or give you inspiration for new directions to go in.
**[10:21]** Now as you're doing error analysis,
**[10:23]** sometimes you notice that some of your examples in your dev sets are mislabeled.
**[10:27]** So what do you do about that?
**[10:29]** Let's discuss that in the next video.
