---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 2
section: Introduction to Word Embeddings
item_title: Properties of Word Embeddings
duration: 11 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/S2mat/properties-of-word-embeddings
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Properties of Word Embeddings — Transcript

**[0:00]** By now, you should have a sense of how word embeddings can help you build NLP
**[0:04]** applications.
**[0:06]** One of the most fascinating properties of word embeddings is that they can also
**[0:10]** help with analogy reasoning.
**[0:12]** And while reasonable analogies may not be by itself the most important NLP
**[0:17]** application, they might also help convey a sense of what these word embeddings
**[0:21]** are doing, what these word embeddings can do.
**[0:24]** Let me show you what I mean here are the featurized representations of a set of
**[0:29]** words that you might hope a word embedding could capture.
**[0:32]** Let's say I pose a question,
**[0:37]** man is to woman as king is to what?
**[0:43]** Many of you will say, man is to woman as king is to queen.
**[0:48]** But is it possible to have an algorithm figure this out automatically?
**[0:52]** Well, here's how you could do it,
**[0:54]** let's say that you're using this four dimensional vector to represent man.
**[0:58]** So this will be your E5391, although just for
**[1:03]** this video, let me call this e subscript man.
**[1:08]** And let's say that's the embedding vector for woman, so
**[1:12]** I'm going to call that e subscript woman, and similarly for king and queen.
**[1:17]** And for this example,
**[1:19]** I'm just going to assume you're using four dimensional embeddings,
**[1:22]** rather than anywhere from 50 to 1,000 dimensional, which would be more typical.
**[1:27]** One interesting property of these vectors is that if you take the vector,
**[1:35]** e man, and subtract the vector e woman, then,
**[1:45]** You end up with approximately -1,
**[1:48]** negative another 1 is -2, decimal 0- 0,
**[1:54]** 0- 0, close to 0- 0, so you get roughly -2 0 0 0.
**[2:00]** And similarly if you take e king minus e queen,
**[2:07]** then that's approximately the same thing.
**[2:13]** That's about -1- 0.97, it's about -2.
**[2:20]** This is about 1- 1, since kings and queens are both about equally royal.
**[2:25]** So that's 0, and then age difference, food difference, 0.
**[2:30]** And so what this is capturing is that the main difference
**[2:35]** between man and woman is the gender.
**[2:39]** And the main difference between king and queen,
**[2:42]** as represented by these vectors, is also the gender.
**[2:45]** Which is why the difference e man- e woman, and
**[2:48]** the difference e king- e queen, are about the same.
**[2:53]** So one way to carry out this analogy reasoning is,
**[2:58]** if the algorithm is asked, man is to woman as king is to what?
**[3:03]** What it can do is compute e man- e woman, and
**[3:07]** try to find a vector, try to find a word so
**[3:12]** that e man- e woman is close to e king- e of that new word.
**[3:20]** And it turns out that when queen is the word plugged in here,
**[3:25]** then the left hand side is close to the the right hand side.
**[3:29]** So these ideas were first pointed out by Tomas Mikolov, Wen-tau Yih,
**[3:35]** and Geoffrey Zweig.
**[3:36]** And it's been one of the most remarkable and
**[3:38]** surprisingly influential results about word embeddings.
**[3:45]** And I think has helped the whole community
**[3:47]** get better intuitions about what word embeddings are doing.
**[3:51]** So let's formalize how you can turn this into an algorithm.
**[3:56]** In pictures, the word embeddings live in maybe a 300 dimensional space.
**[4:03]** And so the word man is represented as a point in the space,
**[4:08]** and the word woman is represented as a point in the space.
**[4:12]** And the word king is represented as another point,
**[4:18]** and the word queen is represented as another point.
**[4:24]** And what we pointed out really on the last slide is that
**[4:27]** the vector difference between man and woman
**[4:31]** is very similar to the vector difference between king and queen.
**[4:36]** And this arrow I just drew is really the vector that represents a difference
**[4:42]** in gender. And remember, these are points we're plotting in a 300 dimensional space.
**[4:48]** So in order to carry out this kind of analogical reasoning to figure out,
**[4:52]** man is to woman is king is to what, what you can do is try to find the word w,
**[5:02]** So that, This equation holds true,
**[5:09]** so you want there to be, so you want to find the word w
**[5:14]** Then finding the word that maximizes the similarity e w compared to e king
**[5:32]** minus e man plus e woman
**[5:35]** Right, so what I did is, I took this e question mark, and
**[5:39]** replaced that with ew, and then brought ew to just one side of the equation.
**[5:48]** And then the other three terms to the right hand side of this equation.
**[5:53]** So we have some appropriate similarity function for
**[5:56]** measuring how similar is the embedding of some word w to this quantity of the right.
**[6:00]** Then finding the word that maximizes the similarity should hopefully let you
**[6:05]** pick out the word queen.
**[6:11]** And the remarkable thing is, this actually works.
**[6:15]** If you learn a set of word embeddings and find a word w that maximizes this type
**[6:19]** of similarity, you can actually get the exact right answer.
**[6:23]** Depending on the details of the task, but if you look at research papers,
**[6:29]** it's not uncommon for research papers to report anywhere from, say,
**[6:32]** 30% to 75% accuracy on analogy using tasks like these.
**[6:36]** Where you count an anology attempt as correct only if it guesses
**[6:41]** the exact word right.
**[6:43]** So only if, in this case, it picks out the word queen.
**[6:47]** Before moving on, I just want to clarify what this plot on the left is.
**[6:52]** Previously, we talked about using algorithms like t-SAE to visualize words.
**[6:58]** What t-SAE does is, it takes 300-D data,
**[7:02]** and it maps it in a very non-linear way to a 2D space.
**[7:08]** And so the mapping that t-SAE learns, this is a very complicated and
**[7:13]** very non-linear mapping.
**[7:14]** So after the t-SAE mapping, you should not expect these types of
**[7:19]** parallelogram relationships, like the one we saw on the left, to hold true.
**[7:24]** And it's really in this original 300 dimensional space that
**[7:29]** you can more reliably count on these types of parallelogram relationships
**[7:33]** in analogy pairs to hold true.
**[7:35]** And it may hold true after a mapping through t-SAE, but in most cases,
**[7:40]** because of t-SAE's non-linear mapping, you should not count on that.
**[7:45]** And many of the parallelogram analogy relationships will be broken by t-SAE.
**[7:50]** Now before moving on, let me just describe the similarity function that is most commonly used.
**[7:58]** So the most commonly used similarity function is called cosine similarity.
**[8:03]** So this is the equation we had from the previous slide.
**[8:08]** So in cosine similarity, you define the similarity between two vectors u and
**[8:14]** v as u transpose v divided by the lengths by the Euclidean lengths.
**[8:21]** So ignoring the denominator for
**[8:23]** now, this is basically the inner product between u and v.
**[8:26]** And so if u and v are very similar, their inner product will tend to be large.
**[8:30]** And this is called cosine similarity because this is actually
**[8:34]** the cosine of the angle between the two vectors, u and v.
**[8:40]** So that's the angle phi, so this formula is actually the cosine of the angle between them.
**[8:46]** And so you remember from calculus that if this phi,
**[8:51]** then the cosine of phi looks like this.
**[8:56]** So if the angle between them is 0, then the cosine similarity is equal to 1.
**[9:02]** And if their angle is 90 degrees, the cosine similarity is 0.
**[9:06]** And then if they're 180 degrees, or
**[9:08]** pointing in completely opposite directions, it ends up being -1.
**[9:13]** So that's where the term cosine similarity comes from, and it works quite well for
**[9:19]** these analogy reasoning tasks.
**[9:20]** If you want, you can also use square distance or
**[9:24]** Euclidian distance, u-v squared.
**[9:27]** Technically, this would be a measure of dissimilarity rather than a measure of similarity.
**[9:32]** So we need to take the negative of this, and this will work okay as well.
**[9:36]** Although I see cosine similarity being used a bit more often.
**[9:40]** And the main difference between these is how it normalizes the lengths of
**[9:44]** the vectors u and v.
**[9:47]** So one of the remarkable results about word embeddings is the generality of
**[9:53]** analogy relationships they can learn.
**[9:55]** So for example, it can learn that man is to woman as boy is to girl,
**[10:01]** because the vector difference between man and
**[10:03]** woman, similar to king and queen and boy and girl, is primarily just the gender.
**[10:08]** It can learn that Ottawa, which is the capital of Canada,
**[10:13]** that Ottawa is to Canada as Nairobi is to Kenya.
**[10:16]** So that's the city capital is to the name of the country.
**[10:22]** It can learn that big is to bigger as tall is to taller, and
**[10:24]** it can learn things like that.
**[10:26]** Yen is to Japan, since yen is the currency of Japan, as ruble is to Russia.
**[10:31]** And all of these things can be learned just by running
**[10:36]** a word embedding learning algorithm on the large text corpus
**[10:41]** It can spot all of these patterns by itself,
**[10:42]** So in this video, you saw how word embeddings can be used for
**[10:50]** analogy reasoning.
**[10:52]** And while you might not be trying to build an analogy reasoning system yourself as
**[10:55]** an application, this I hope conveys some intuition about the types of feature-like
**[11:00]** representations that these representations can learn.
**[11:05]** And you also saw how cosine similarity can be a way to measure
**[11:10]** the similarity between two different word embeddings.
**[11:13]** Now, we talked a lot about properties of these embeddings and how you can use them.
**[11:17]** Next, let's talk about how you'd actually learn these word embeddings,
**[11:21]** let's go on to the next video.
