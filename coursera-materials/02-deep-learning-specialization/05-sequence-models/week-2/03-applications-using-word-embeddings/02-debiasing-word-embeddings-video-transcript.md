---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 2
section: Applications Using Word Embeddings
item_title: Debiasing Word Embeddings
duration: 11 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/zHASj/debiasing-word-embeddings
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Debiasing Word Embeddings — Transcript

**[0:00]** Machine learning and AI algorithms are increasingly trusted to help with, or
**[0:05]** to make, extremely important decisions.
**[0:07]** And so we like to make sure that as much as possible that they're free
**[0:11]** of undesirable forms of bias, such as gender bias, ethnicity bias and so on.
**[0:16]** What I want to do in this video is show you some of the ideas for diminishing or
**[0:20]** eliminating these forms of bias in word embeddings.
**[0:24]** When I use the term bias in this video, I don't mean the bias variants.
**[0:28]** Sense the bias, instead I mean gender, ethnicity, sexual orientation bias.
**[0:33]** That's a different sense of bias then is typically used in the technical discussion
**[0:38]** on machine learning.
**[0:40]** But mostly the problem, we talked about how
**[0:43]** word embeddings can learn analogies like man is to woman as king is to queen.
**[0:47]** But what if you ask it, man is to computer programmer as woman is to what?
**[0:52]** And so the authors of this paper
**[0:56]** Tolga Bolukbasi, Kai-Wei Chang, James Zou, Venkatesh Saligrama, and
**[1:00]** Adam Kalai found a somewhat horrifying result where a learned word embedding
**[1:06]** might output Man:Computer_Programmer as Woman:Homemaker.
**[1:11]** And that just seems wrong and it enforces a very unhealthy gender stereotype.
**[1:17]** It'd be much more preferable to have algorithm output man is to computer
**[1:20]** programmer as a woman is to computer programmer.
**[1:22]** And they found also, Father:Doctor as Mother is to what?
**[1:27]** And the really unfortunate result is that some learned word embeddings would
**[1:32]** output Mother:Nurse.
**[1:34]** So word embeddings can reflect the gender, ethnicity, age,
**[1:38]** sexual orientation, and other biases of the text used to train the model.
**[1:42]** One that I'm especially passionate about is bias relating to socioeconomic status.
**[1:48]** I think that every person, whether you come from a wealthy family,
**[1:52]** or a low income family, or anywhere in between,
**[1:54]** I think everyone should have great opportunities.
**[1:57]** And because machine learning algorithms are being used to make very important
**[2:02]** decisions.
**[2:03]** They're influencing everything ranging from college admissions, to the way people
**[2:08]** find jobs, to loan applications, whether your application for a loan gets approved,
**[2:13]** to in the criminal justice system, even sentencing guidelines.
**[2:17]** Learning algorithms are making very important decisions and so I think it's
**[2:22]** important that we try to change learning algorithms to diminish as much as
**[2:28]** is possible, or, ideally, eliminate these types of undesirable biases.
**[2:33]** Now in the case of word embeddings, they can pick up the biases of the text used
**[2:38]** to train the model and so the biases they pick up or
**[2:42]** tend to reflect the biases in text as is written by people.
**[2:48]** Over many decades, over many centuries,
**[2:50]** I think humanity has made progress in reducing these types of bias.
**[2:55]** And I think maybe fortunately for AI, I think we actually have better ideas for
**[2:59]** quickly reducing the bias in AI than for
**[3:02]** quickly reducing the bias in the human race.
**[3:05]** Although I think we're by no means done for AI as well and
**[3:09]** there's still a lot of research and
**[3:12]** hard work to be done to reduce these types of biases in our learning algorithms.
**[3:16]** But what I want to do in this video is share with you one example of a set
**[3:20]** of ideas due to the paper referenced at the bottom by Bolukbasi and
**[3:24]** others on reducing the bias in word embeddings.
**[3:30]** So here's the idea.
**[3:32]** Let's say that we've already learned a word embedding,
**[3:36]** so the word babysitter is here, the word doctor is here.
**[3:43]** We have grandmother here,
**[3:48]** and grandfather here.
**[3:52]** Maybe the word girl is embedded there, the word boy is embedded there.
**[3:56]** And maybe she is embedded here, and he is embedded there.
**[4:01]** So the first thing we're going to do it is identify the direction
**[4:07]** corresponding to a particular bias we want to reduce or eliminate.
**[4:11]** And, for illustration, I'm going to focus on gender bias but
**[4:15]** these ideas are applicable to all of the other
**[4:18]** types of bias that I mention on the previous slide as well.
**[4:21]** So, in this example
**[4:26]** And so how do you identify the direction corresponding to the bias?
**[4:30]** For the case of gender, what we can do is take the embedding vector for he and
**[4:36]** subtract the embedding vector for she, because that differs by gender.
**[4:41]** And take e male, subtract e female, and
**[4:46]** take a few of these and average them, right?
**[4:48]** And take a few of these differences and basically average them.
**[4:51]** And this will allow you to figure out in this case that what looks like
**[4:56]** this direction is the gender direction, or the bias direction.
**[5:02]** Whereas this direction is unrelated to the particular bias we're trying to address.
**[5:10]** So this is the non-bias direction.
**[5:16]** And in this case, the bias direction, think of this as a 1D subspace whereas
**[5:21]** a non-bias direction, this will be 299-dimensional subspace.
**[5:27]** Okay, and I've simplified the description a little bit in the original paper.
**[5:31]** The bias direction can be higher than 1-dimensional, and
**[5:34]** rather than take an average, as I'm describing it here, it's actually found
**[5:38]** using a more complicated algorithm called a SVU, a singular value decomposition.
**[5:42]** Which is closely related to,
**[5:44]** if you're familiar with principle component analysis,
**[5:48]** it uses ideas similar to the pc or the principle component analysis algorithm.
**[5:53]** After that, the next step is a neutralization step.
**[5:57]** So for every word that's not definitional, project it to get rid of bias.
**[6:02]** So there are some words that intrinsically capture gender.
**[6:07]** So words like grandmother,
**[6:08]** grandfather, girl, boy, she, he, a gender is intrinsic in the definition.
**[6:13]** Whereas there are other word like doctor and
**[6:16]** babysitter that we want to be gender neutral.
**[6:19]** And really, in the more general case, you might want words like doctor or babysitter
**[6:24]** to be ethnicity neutral or sexual orientation neutral, and
**[6:28]** so on, but we'll just use gender as the illustrating example here.
**[6:32]** But so for every word that is not definitional,
**[6:35]** this basically means not words like grandmother and grandfather,
**[6:39]** which really have a very legitimate gender component, because, by definition,
**[6:44]** grandmothers are female, and grandfathers are male.
**[6:48]** So for words like doctor and babysitter,
**[6:51]** let's just project them onto this axis to reduce their components,
**[6:56]** or to eliminate their component, in the bias direction.
**[7:00]** So reduce their component in this horizontal direction.
**[7:06]** So that's the second neutralize step.
**[7:08]** And then the final step is called equalization in which
**[7:12]** you might have pairs of words such as grandmother and
**[7:17]** grandfather, or girl and boy, where you want the only
**[7:22]** difference in their embedding to be the gender.
**[7:27]** And so, why do you want that?
**[7:30]** Well in this example, the distance, or
**[7:33]** the similarity, between babysitter and grandmother is actually
**[7:38]** smaller than the distance between babysitter and grandfather.
**[7:42]** And so this maybe reinforces an unhealthy, or
**[7:46]** maybe undesirable, bias that grandmothers end up babysitting more than grandfathers.
**[7:50]** So in the final equalization step,
**[7:53]** what we'd like to do is to make sure that words like grandmother and
**[7:57]** grandfather are both exactly the same similarity, or exactly the same distance,
**[8:01]** from words that should be gender neutral, such as babysitter or such as doctor.
**[8:06]** So there are a few linear algebra steps for that.
**[8:09]** But what it will basically do is move grandmother and
**[8:13]** grandfather to a pair of points that are equidistant from this axis in the middle.
**[8:20]** And so the effect of that is that now the distance between babysitter,
**[8:24]** compared to these two words, will be exactly the same.
**[8:29]** And so, in general, there are many pairs of words like this
**[8:33]** grandmother-grandfather, boy-girl, sorority-fraternity,
**[8:38]** girlhood-boyhood, sister-brother, niece-nephew, daughter-son,
**[8:44]** that you might want to carry out through this equalization step.
**[8:49]** So the final detail is, how do you decide what word to neutralize?
**[8:54]** So for example, the word doctor seems like a word you should neutralize
**[8:59]** to make it non-gender-specific or non-ethnicity-specific.
**[9:04]** Whereas the words grandmother and
**[9:06]** grandmother should not be made non-gender-specific.
**[9:09]** And there are also words like beard, right,
**[9:12]** that it's just a statistical fact that men are much more likely to have
**[9:16]** beards than women, so maybe beards should be closer to male than female.
**[9:21]** And so what the authors did is train a classifier to try to figure
**[9:26]** out what words are definitional,
**[9:29]** what words should be gender-specific and what words should not be.
**[9:34]** And it turns out that most words in the English language are not definitional,
**[9:39]** meaning that gender is not part of the definition.
**[9:41]** And it's such a relatively small subset of words like this, grandmother-grandfather,
**[9:47]** girl-boy, sorority-fraternity, and so on that should not be neutralized.
**[9:53]** And so a linear classifier can tell you what words to pass through
**[9:58]** the neutralization step to project out this bias direction,
**[10:02]** to project it on to this essentially 299-dimensional subspace.
**[10:08]** And then, finally, the number of pairs you want to equalize,
**[10:10]** that's actually also relatively small, and is, at least for the gender example,
**[10:16]** it is quite feasible to hand-pick most of the pairs you want to equalize.
**[10:22]** So the full algorithm is a bit more complicated than I present it here,
**[10:26]** you can take a look at the paper for the full details.
**[10:29]** And you also get to play with a few of these ideas
**[10:32]** in the programming exercises as well.
**[10:35]** So to summarize, I think that reducing or eliminating bias of our learning
**[10:39]** algorithms is a very important problem because these algorithms are being asked
**[10:44]** to help with or to make more and more important decisions in society.
**[10:48]** In this video I shared just one set of ideas for
**[10:51]** how to go about trying to address this problem, but
**[10:53]** this is still a very much an ongoing area of active research by many researchers.
**[11:00]** So that's it for this week's videos.
**[11:03]** Best of luck with this week's programming exercises and
**[11:06]** I look forward to seeing you next week.
