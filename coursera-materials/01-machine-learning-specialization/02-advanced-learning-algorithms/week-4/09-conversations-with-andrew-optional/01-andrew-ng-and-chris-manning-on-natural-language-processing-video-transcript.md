---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 4
section: Conversations with Andrew (Optional)
item_title: Andrew Ng and Chris Manning on Natural Language Processing
duration: 47 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/YFE7M/andrew-ng-and-chris-manning-on-natural-language-processing
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Andrew Ng and Chris Manning on Natural Language Processing — Transcript

**[0:07]** [MUSIC] Hi,
**[0:08]** I'm delighted to be here with my old friend and
**[0:10]** collaborator, Professor Chris Manning.
**[0:12]** Chris has a very long and impressive bio but just briefly,
**[0:15]** he is Professor of Computer Science at Stanford University and
**[0:19]** also the director of the Stanford AI lab.
**[0:21]** And he also has the distinction of being the most highly cited researcher in NLP or
**[0:26]** natural language processing.
**[0:28]** So, really good to be here with you, Chris.
**[0:31]** >> Good to get a chance to chat Andrew.
**[0:33]** >> So we've known each other collaborated for many years and
**[0:36]** one interesting part of your background I always thought was that even though today
**[0:41]** you're distinguished researcher in machine learning in NLP,
**[0:45]** you actually started off in a very different area.
**[0:48]** Your PhD if I remember correctly was in linguistics and
**[0:52]** you were studying the syntax of language.
**[0:55]** So how did you go from studying syntax to being an NLP researcher?
**[1:00]** >> So I can certainly tell you about that, but I should also point out that I'm still
**[1:04]** actually a professor of linguistics as well.
**[1:07]** I have a joint appointment at Stanford.
**[1:09]** And once in a blue moon not very often, I do actually still teach some real
**[1:13]** linguistics as well as computer involved natural language processing.
**[1:18]** So starting out, I was very interested in human languages and
**[1:24]** how they work, how people understand them,
**[1:28]** how they're inquired are acquired.
**[1:32]** So I had this sort of appeal, I saw this appeal in human languages.
**[1:38]** But that equally led me to think about ideas that we now very
**[1:43]** much think about as machine learning or computational ideas.
**[1:48]** So two of the central ideas in human language,
**[1:52]** how do little children acquire human language?
**[1:57]** And for adults, well, we're just talking to each other now and
**[2:00]** we pretty much understand each other.
**[2:02]** And that's actually an amazing thing, how we manage to do that.
**[2:06]** So what kind of processing allows that?
**[2:08]** And so that early on got me interested in looking at machine learning.
**[2:13]** In fact, even before I'd made it to grad school, I started baby steps and
**[2:17]** learning machine learning coming off of those interests.
**[2:21]** >> That all human language has learned,
**[2:23]** we had learned at some point in the lives to speak English and
**[2:26]** we grown up in a different place, we would have learned a totally different language.
**[2:30]** So is amazing to think how humans do that and now maybe machines learn language too.
**[2:36]** But so just tell us more about your journey.
**[2:40]** So you had a PhD in linguistics and then how did you?
**[2:45]** >> So there's some stuff before that as well.
**[2:47]** So I mean when I was an undergrad, well, officially I actually did three majors.
**[2:53]** This was in Australia, one in math, one in computer science and one in linguistics.
**[2:58]** Now people get a slightly exaggerated sense of what that means if you're in
**[3:03]** an American context because it'd be I think impossible to complete three majors,
**[3:09]** the undergrad at Stanford.
**[3:11]** But actually where I was as an undergrad doing, I did an arts degree so
**[3:15]** I could do whatever I wanted like linguistics,
**[3:18]** you had to complete two majors to complete the arts degree.
**[3:21]** So it was sort of more like double majoring maybe in US terms.
**[3:25]** >> You probably don't know this about me but Mellon,
**[3:28]** I actually was a triple major, that was once in the statistics and economics.
**[3:33]** Okay, we both fellow triple majors.
**[3:36]** >> Yeah, so anyway, I did have background and
**[3:39]** interest in doing things with computer science.
**[3:43]** And so my interests were kind of mixed and I mean actually,
**[3:46]** when I applied to grad schools, I mean one of the places I applied to
**[3:50]** was Carnegie Mellon because they were strong in computational linguistics.
**[3:55]** And if I'd gone there I would have been enrolled as a CS student but
**[4:00]** I ended up at as a linguistics student because at that time,
**[4:03]** there wasn't any natural language processing in the CS Department.
**[4:08]** But I was still interested in pursuing ideas in natural language processing.
**[4:14]** But at that point in the early nineties, things were just starting to change.
**[4:20]** But the bulk of natural language processing was
**[4:25]** rule based logical declarative systems.
**[4:29]** But it was also in those years at the beginning of the nineties,
**[4:33]** when they first started to be lots of human language material, text and
**[4:38]** speech available digitally.
**[4:40]** So this was really actually just before the world wide web exploded.
**[4:43]** But they already started to be things like legal materials and
**[4:48]** newspaper articles and parliamentary hand SARS where you could last
**[4:53]** get your hands on millions of words of human language.
**[4:57]** And it just seemed really clear that there had to be exciting things that you could
**[5:01]** do by working empirically from lots of human language.
**[5:05]** And that's what really sort of got me involved in a new kind of
**[5:09]** natural language processing that then led into my subsequent career.
**[5:13]** >> It sounds like your career was initially more linguistics and
**[5:17]** of the rise of data and machine learning and
**[5:20]** empirical methods it shifted to what NLP and machine learning and NLP.
**[5:24]** >> Yeah, I mean it absolutely certainly shifted and I've certainly sort of shifted
**[5:29]** much more to doing both natural language processing and machine learning models.
**[5:35]** But to some extent, the balance has varied.
**[5:38]** But I've sort of been with that as a while, actually as an undergrad for
**[5:44]** my undergrad honors thesis, it was sort of learning the forms of words.
**[5:50]** So how you can which became a famous problem of sort of learning past tense of
**[5:55]** English verbs and the early connection literature.
**[5:58]** And I was trying to sort of learn paradigms of forms of verbs.
**[6:02]** And I was learning rules for
**[6:04]** the different forms using the C 4.5 decision tree learning algorithm.
**[6:10]** [LAUGH] If you remember that.
**[6:11]** >> Yeah right, good times.
**[6:15]** Yeah and it's surprisingly non intuitive, right?
**[6:17]** How going from present tense to past tense from I don't know to and
**[6:22]** all the other special cases can be.
**[6:26]** >> Yeah.
**[6:26]** >> Yeah, so we talked a bunch about NLP natural language processing.
**[6:31]** So for some of the learners pick up machine learning for
**[6:35]** the first time, can you say what is NLP?
**[6:38]** >> Sure, absolutely, yeah.
**[6:40]** So NLP stands for natural language processing another word that's or
**[6:43]** term that's sometimes used for that is computational linguistics,
**[6:47]** it's the same thing.
**[6:48]** I mean natural language processing is actually a weird term, right?
**[6:52]** So it means that we're doing things with human languages.
**[6:56]** So you have to have the conception that you're enough of a computer scientist that
**[7:00]** when you say language, you think in your brain programming language.
**[7:03]** And therefore you need to say natural language to mean that you're
**[7:06]** talking about the languages that human beings use.
**[7:09]** So overall natural language processing is doing anything intelligent with
**[7:14]** human languages.
**[7:15]** So in one sense that breaks down into understanding human languages,
**[7:20]** producing human languages, acquiring human languages,
**[7:24]** though people also often think about it in terms of different applications.
**[7:29]** And so then you might think about things like machine translation or
**[7:35]** doing question answering or generating advertising copy or summarization.
**[7:41]** There are so many different tasks that people work on with particular
**[7:46]** goals in mind where you do things with human language.
**[7:49]** And there's a lot of natural language processing because so
**[7:53]** much of what the world works on our human world is dealt with and
**[7:57]** transmitted in terms of human language material.
**[8:02]** So, because of all of these applications or even web search, right?
**[8:06]** Most of us use NLP.
**[8:08]** >> Yeah.
**[8:08]** >> Many, many times a day >> You're right, in some sense,
**[8:11]** the biggest application of natural language is web search, right?
**[8:16]** [LAUGH] And that's really the the big one, I mean,
**[8:19]** traditionally, it was a kind of a simple one, right?
**[8:22]** That in the good old days, it was, you know, there were various weighting factors
**[8:27]** and so on, but it was mainly sort of matching keywords,
**[8:30]** then your search terms and then some factors about the quality of the page.
**[8:35]** It didn't really feel like language understanding, but
**[8:38]** that's really been changing over the years.
**[8:40]** So these days, you'll often, if you ask a question to a search engine,
**[8:45]** it will give you an answer box where it has extracted a piece of text and
**[8:50]** puts what it thinks is the answer in bold or color or something like that.
**[8:54]** Which is then this task of question answering and
**[8:57]** then it's really a natural language understanding task.
**[9:00]** >> Yeah, yeah, and I feel like in addition to web searches, maybe the big one,
**[9:05]** even when we're going to a online shopping website or a movie website and
**[9:09]** typing in what we want and
**[9:11]** doing a website search on a much smaller website than the big search engines.
**[9:16]** That also increasingly uses sophisticated NLP algorithms, and
**[9:20]** it is also creating quite a lot of value.
**[9:22]** Maybe to you is not the real NLP, but it still seems very valuable.
**[9:27]** >> I agree, it's very valuable.
**[9:28]** And there are lots of interesting problems in any e-commerce website with search very
**[9:34]** difficult problems actually when people describe the kind of goods they want.
**[9:39]** And you need to be trying to match it to products that are available,
**[9:42]** that isn't an easy problem at all, it turns out.
**[9:45]** >> Yeah, that's true, yeah.
**[9:47]** So over the last, I don't know, couple of decades,
**[9:50]** NLP has gone through a major shift from more of the rule based techniques that
**[9:55]** you alluded to just now to using really machine learning much more pervasively.
**[10:01]** And so you were one of the people that leading parts of that charge and
**[10:05]** seeing every step of the way, you're creating some of the stems as it happened,
**[10:11]** can you say a bit about that process and what you saw?
**[10:14]** >> Sure, absolutely.
**[10:16]** Yeah, so when I started off as an undergrad in grad student,
**[10:21]** really most of natural language processing was done by hand built
**[10:26]** systems which variously used rules and inference procedures to sort of try and
**[10:33]** build up a path and an understanding of a piece of text.
**[10:38]** >> What's an example of a rule or inference system?
**[10:41]** So, a rule could be part of the structure of human language.
**[10:46]** Like English sentence normally consists of a subject noun phrase,
**[10:51]** followed by a verb and an object noun phrase.
**[10:54]** And that gives you some idea as to how to understand the meaning of the sentence.
**[10:59]** But it might also be saying something about how to interpret a word so
**[11:05]** that a lot of words in English are very ambiguous.
**[11:10]** But if you have something like the word star and it's in the context of a movie,
**[11:16]** then it's probably referring to a human being not an astronomical object.
**[11:21]** And in those days people tried to deal with things like that using
**[11:26]** rules of that sort.
**[11:28]** That doesn't seem very likely to work to us these days, but,
**[11:33]** once upon a time that was pretty standard.
**[11:36]** And so it was only when lots of digital text and speech started to become
**[11:41]** available that it really seemed like there was this different way that
**[11:46]** instead we could start calculating statistics over human language,
**[11:51]** material and building machine learning models.
**[11:55]** And so that was the first thing that I got into,
**[12:00]** in the sort of mid to late 1990s.
**[12:05]** And so the first area where I started doing lots of research and
**[12:09]** publishing papers and getting well known is building what in the early days,
**[12:14]** we often called statistical natural language processing.
**[12:18]** But it later merged into in general prob approaches to artificial intelligence and
**[12:23]** machine learning.
**[12:24]** And that sort of took us through to approximately 2010, let's say.
**[12:30]** And that's roughly when the new interest in deep learning
**[12:35]** using large artificial neural networks started to take off.
**[12:41]** For my interest in that I really have you to thank Andrew because at this stage,
**[12:46]** Andrew is still full time at Stanford and
**[12:49]** he was in the office next door to me and he was really excited about the new
**[12:54]** things that were happening in the area of deep learning, I guess.
**[12:58]** Anyone who walked into his office, he'd tell them, it's sort of exciting for
**[13:02]** what's happening now and I'm on neural network,
**[13:04]** you have to start looking at that.
**[13:06]** And so that was really the impetus that got me pretty
**[13:11]** early on involved in looking at things in neural networks.
**[13:17]** I had actually seen a bit of it before, so while I was a grad student here, actually,
**[13:22]** Dave Rummelhardt was at Stanford in Psych and I'd taken his neural networks class.
**[13:27]** And so, I'd seen some of that, but
**[13:29]** it hadn't actually really been what I'd gotten into for my own research.
**[13:34]** So- >> I didn't know that, thank you, yeah.
**[13:38]** >> Yeah.
**[13:39]** >> And then we wound up supervising some students together.
**[13:43]** >> Yeah, absolutely.
**[13:44]** >> I'd love to hear the rise of also deep learning and NLP,
**[13:47]** what did you see since you were in the field?
**[13:49]** >> Yeah, so starting about 2010, yeah, me,
**[13:54]** students started to do the first papers and
**[13:58]** deep learning aimed at NLP conferences.
**[14:02]** It's always hard when you're trying to do something new.
**[14:04]** We had exactly the same experiences that people 15 or so years earlier had
**[14:09]** had when they start trying to do statistical NLP of when there's
**[14:13]** an established way of doing things, it's really hard to push out new ideas.
**[14:18]** So really some of our first papers were rejected from conferences and
**[14:23]** instead appeared at machine learning conferences or
**[14:27]** deep learning workshops, but very quickly that started to change and
**[14:31]** people got super interested in neural network ideas.
**[14:35]** But I sort of feel like the neural network period which sort of started
**[14:40]** effectively about 2010, it's self divides in two because for
**[14:46]** the first period, let's say, basically say it's till 2018.
**[14:51]** We showed a lot of success at building neural networks for all sorts of tasks.
**[14:55]** We built them for syntactic parsing and sentiment analysis.
**[15:00]** And what else dude?
**[15:02]** >> Question answering.
**[15:05]** But it was sort of like we were doing the same thing that we used to do with
**[15:09]** other kinds of machine learning models,
**[15:12]** except we now had a better machine learning model.
**[15:16]** And we were sort of instead of training up a logistic regression or
**[15:19]** a support vector machine, we were still doing the same kind of sentiment analysis
**[15:24]** task, but now we are doing it with a neural network.
**[15:27]** So I think in looking back now in some sense,
**[15:31]** the bigger change came around 2018.
**[15:35]** Because that was when the idea of, well,
**[15:38]** we could just start with a large amount of human language material and
**[15:44]** build large what are self supervised models.
**[15:47]** So that was models then and like BERT and GPTs and
**[15:52]** successor models to that.
**[15:54]** And they could just sort of acquire from word prediction over
**[15:59]** a huge amount of text this amazing knowledge of human languages.
**[16:04]** And I think really probably that's going to be viewed in retrospect as
**[16:09]** the bigger kind of cut point where the way Things were done really changed.
**[16:14]** >> Yeah, I think there is that trend for
**[16:16]** the large language models learning from massive amount of data.
**[16:20]** I think even in the lead up to that, there was one of your
**[16:24]** research papers that really slightly blew my mind, which is a glove paper.
**[16:28]** So because with word embeddings where you learn the vector
**[16:33]** numbers to represent a word using a neural network.
**[16:38]** That was quite mind blowing for me.
**[16:40]** And then the glove work that you did really cleaned up the math, made it so
**[16:44]** much simpler.
**[16:45]** And then I remember I said, that's all there is to do.
**[16:48]** And then you can learn these really surprisingly detailed
**[16:52]** representations of the computer learns nuances of what words mean.
**[16:57]** >> Absolutely.
**[16:58]** Yeah, so I should give a little bit of credit to others.
**[17:01]** Other people also worked on some similar ideas including
**[17:07]** and Ja Weston and colleagues at Google.
**[17:11]** But the glove word vectors is one of the very prominent systems of word vectors.
**[17:17]** So these word vectors already did.
**[17:19]** Yeah, you're right, illustrate this idea of using self supervised learning that we
**[17:24]** just took massive amounts of text.
**[17:26]** And then we could build these models that knew an enormous amount
**[17:30]** about the meaning of words.
**[17:32]** It's still something I sort of show people every year
**[17:37]** in the first lecture of my NLP class.
**[17:41]** Because it's something simple but it actually just works so surprisingly well.
**[17:47]** You can do this sort of simple modeling of trying to predict a word given
**[17:51]** the words in the context and
**[17:53]** simply by sort of running the math of learning to do those predictions.
**[17:58]** Well, you learn all these things about word meaning and
**[18:02]** you can do these really nice patterns of similar word meaning or
**[18:07]** analogies of something pencil is to drawing as paintbrush is to and
**[18:13]** it'll say painting, right?
**[18:15]** That it's sort of already showing just a lot of successful learning.
**[18:21]** So that was the precursor to what then got developed to the next
**[18:26]** stage with things like BERT and GPT where it wasn't just meanings of individual words.
**[18:33]** But meanings of whole pieces of text and context.
**[18:37]** >> Yeah, so I found it amazing that you can take a small neural network or
**[18:41]** some model and then give it lots of English sentences or
**[18:45]** some other language and hide the word.
**[18:47]** Ask it to predict what is the word that I just hid and
**[18:51]** that allows it to learn these analogies.
**[18:54]** And these very deep,
**[18:55]** what you think are really deep things behind the meaning of the word.
**[19:00]** And then 2018, maybe this other infection point what happened after that?
**[19:06]** >> Yeah.
**[19:07]** So, in 2018, that was the point in which well,
**[19:12]** sort of really two things happened.
**[19:15]** One thing is that people, or really in 2017 had developed this new architecture.
**[19:22]** Which was much more scalable onto modern parallel GPUs.
**[19:26]** And so that was the transformer architecture.
**[19:30]** The second part of it though was maybe people rediscover of it
**[19:35]** because I was using the same trick as the glove model that if you
**[19:40]** have the task of just predicting a word given a context.
**[19:44]** Either a context on both sides of it or
**[19:47]** the preceding words that that just turns out to be an amazing learning task.
**[19:53]** And that surprises a lot of people.
**[19:55]** And a lot of the time you see discussions where people say disparaging things of
**[19:59]** this is nothing interesting is happening.
**[20:02]** And all it's doing is statistics to predict which word is
**[20:06]** most likely to come after the preceding words.
**[20:10]** And I think the really interesting thing is that that's true, but it's not true.
**[20:18]** Because yes what the task is is you're predicting the next word given
**[20:22]** preceding words.
**[20:24]** But the really interesting thing is if you want to do that task
**[20:29]** really as well as possible.
**[20:31]** Then it actually helps to understand the whole of the rest of the sentence and
**[20:37]** know who's doing what to who and what's in the sentence.
**[20:41]** But more than that, it also helps to understand
**[20:46]** the world because if your text is going something
**[20:51]** along the lines of the currency used in Fiji is that.
**[20:56]** Well, you need to have some world knowledge to know what the right answer
**[21:00]** to that is.
**[21:00]** And so good models at doing this,
**[21:03]** learn both to follow the structure of sentences and their meaning and
**[21:09]** to know facts about the world also so that they can predict.
**[21:14]** And therefore this turns into what's sometimes referred to as an AI complete
**[21:18]** task, right?
**[21:19]** That you really need.
**[21:21]** There's nothing that can't actually be useful in answering this
**[21:26]** what word comes next sense, right?
**[21:28]** You can be in the World Cup semifinals the teams and
**[21:33]** you need to know something about soccer [LAUGH] to be giving the right answer.
**[21:40]** >> I complete this funny concept, right?
**[21:41]** Is this idea that you can solve this one problem, you can solve everything in AI or
**[21:46]** kind of make an analogy to NP complete problems from the theory of computing.
**[21:51]** What do you think?
**[21:53]** Do you think predicting the next word is AI complete,
**[21:56]** I have very mixed feelings about that myself.
**[21:59]** I can say, I don't think it's true.
**[22:01]** I'm curious what you think.
**[22:04]** I think it's not quite true because I think there are other
**[22:10]** kind of things that human beings manage to work out.
**[22:15]** There are human beings that have clever insights in mathematics or
**[22:20]** there are human beings who are looking at something that's a much more.
**[22:26]** Three dimensional real world puzzle of sort of figuring out how
**[22:30]** to do something mechanical or something like that.
**[22:34]** And that's just not a language problem.
**[22:38]** But on the other hand, I think language gets
**[22:43]** closer to universality than some people think
**[22:49]** as well because we live in this 3D world.
**[22:53]** And operate in it with our bodies and our feelings and
**[22:59]** other creatures and artifacts around it.
**[23:03]** And you could think, well, not much of that is in language at all.
**[23:08]** But actually just about all of this stuff we think about,
**[23:12]** we talk about, we write about it in language.
**[23:16]** We can describe the positions of things relative to each other in language.
**[23:20]** So a surprising amount of the other parts of the world are seen in reflection
**[23:25]** in language.
**[23:26]** And therefore you're learning about all of them too.
**[23:29]** When you learn about language use.
**[23:32]** >> You learn about one aspect of a lot of things even if things how
**[23:37]** do you ride a bicycle can't really.
**[23:40]** >> You don't really learn how to ride a bicycle, [LAUGH] but
**[23:43]** you learn some aspects of what it involves that you need to balance.
**[23:47]** And you have to have your feet on the pedals and push them and
**[23:50]** all of that kind of things.
**[23:52]** Yeah.
**[23:54]** >> And so with this trend in NLP, the large language models has
**[23:59]** been very exciting for the last several years.
**[24:03]** What are your thoughts on where all this will go?
**[24:06]** >> Well yeah, so it's just been amazingly.
**[24:10]** Successful and exciting, right?
**[24:12]** That so we haven't really explained all the details, right?
**[24:17]** So there's the first stage of learning these large language models where
**[24:21]** the task is just to predict the next word.
**[24:24]** And you do that billions of times over a very large piece of text.
**[24:29]** And behold, you get this large neural network, which is just a really useful
**[24:33]** artifact for all sorts of natural language processing tasks.
**[24:37]** But then you still actually have to do something with it if you want to do
**[24:41]** a particular task, whether that's question answering or summarization or
**[24:45]** detecting toxic content in social media or something like that.
**[24:49]** And at that point, there's a choice of things that you could do with it.
**[24:53]** The traditional answer was then you had a particular task,
**[24:57]** let's say it's detecting toxic comments in social media.
**[25:01]** And you'd take some supervised data for that and
**[25:04]** then you'd fine tune the language model to answer that classification task.
**[25:09]** But you were enormously helped by having this base of this large self supervised
**[25:14]** model because it meant that the model had enormous knowledge of language and
**[25:19]** it could generalize very quickly.
**[25:21]** So unlike the sort of the standard old days of, of supervised learning where
**[25:27]** it was kind of, well, if you give me 10,000 labeled example examples,
**[25:32]** I might be able to produce a halfway decent model for you.
**[25:36]** But if you give me 50,000 labeled examples, it will be a lot better.
**[25:40]** It's sort of turned it into this world of.
**[25:43]** Well, if you give me 100 labeled examples and
**[25:46]** I fine tuning a large language model, I'll be able to do great better than I
**[25:50]** would have been able to do with the 50,000 examples in the old world.
**[25:55]** Some of the more recent exciting works now, even going beyond that,
**[25:58]** it's now, well, maybe you don't actually have to fine tune the model at all.
**[26:02]** So people have done a lot of work using methods, sometimes referred to
**[26:07]** as prompting or instruction where you can simply in natural language,
**[26:13]** perhaps with examples, perhaps with explicit instructions,
**[26:17]** just tell the model what you want it to do and it does it which even as someone
**[26:23]** who's been working in natural language processing for 30 years.
**[26:28]** I mean, it actually just blows my mind how well this works it,
**[26:33]** I guess I wasn't a decade ago thinking that in now we'd be
**[26:38]** able to just tell the model, I want you to summarize this
**[26:42]** piece of text here and it, they will then summarize it.
**[26:47]** I think that is incredible.
**[26:50]** Yeah, so we are in this very exciting time where a lot of new
**[26:54]** natural language capabilities are unfolding.
**[26:59]** I think there's just no doubt at all for the next couple of years,
**[27:03]** the future of that is extremely bright as people work out different things and
**[27:09]** different ways to do things and
**[27:11]** people start to apply in different application areas.
**[27:15]** The kind of capabilities that have been unlocked with recent
**[27:18]** technological developments.
**[27:20]** There's always a question in technology as to sort of whether the curve keeps on
**[27:25]** heading steeply upwards or
**[27:27]** whether there's then some new things, we have to discover how to do it.
**[27:33]** >> It's been going up for quite a while.
**[27:35]** So hopefully extrapolation is always dangerous.
**[27:37]** But, but we'll see, I I'm just curious, you know, you,
**[27:41]** you mentioned writing prompts to the NLP system, the large language model,
**[27:45]** what you want and it seems to magically do it.
**[27:49]** I'm curious, do you think prompt engineering is the path of the future
**[27:53]** where actually when I write these prompts, I sometimes find it works miraculously and
**[27:58]** sometimes it's frustrating the process of rewording my instructions to tweak
**[28:03]** the wording to get it just right to generate the result I want.
**[28:06]** So, do you think prompt engineering is the way of the future or
**[28:10]** do you think is a intermediate hack until someone invents a better way to
**[28:14]** control these, control the outputs of these systems.
**[28:19]** >> I think it's both, I think will be the way of the future but
**[28:24]** I also think at the moment people are doing, yeah,
**[28:29]** a lot of hacking around and rewording to try and
**[28:33]** get things to work better and with any luck with a few
**[28:38]** more years of development that will start to go away.
**[28:43]** I mean, one way of to think about the difference is sort of in comparison
**[28:48]** to the kind of voice assistance or virtual assistance that are available on
**[28:54]** phones speaker devices like Amazon, Alexa these days, right?
**[29:00]** I mean, I think all of us have had the experience that present
**[29:04]** those devices aren't always great, but
**[29:07]** if you know the right way to word things, it'll do something.
**[29:11]** But if you use the wrong wording, it won't and
**[29:14]** the difference with human beings is by and large, you don't have to think about that.
**[29:20]** You can say what you want and it doesn't matter what words you choose,
**[29:23]** they'll the other human being assuming that someone who knows the same language,
**[29:28]** et cetera will understand you and do what you want.
**[29:30]** And I think and would hope that we'll start to see the same kind of progression
**[29:36]** with these models that at the moment fiddling around with the particular
**[29:41]** wording, you use can make a very big difference to how well it works.
**[29:45]** But hopefully in a few years time, that just won't be true,
**[29:49]** you'll be able to use different wordings and it'll still work.
**[29:53]** But the basic idea that we're moving into this age where actually human language
**[29:59]** will be able to be used as an instruction language to tell your computer what to do.
**[30:06]** So, instead of having to use menus and radio buttons and things like that or
**[30:11]** writing Python code, instead of either of those things that
**[30:16]** you'll be able to say what you want in the computer will do it.
**[30:20]** I think that age is opening up in front of us that will continue to build and
**[30:26]** that will be hugely transformative.
**[30:29]** >> Feels like come a long ways but only a much more to come and much more to go.
**[30:36]** >> Yeah, absolutely.
**[30:37]** >> In the development of NLP technology, the only thing I want to ask you and
**[30:40]** I suspect you and I may have different perspectives on this.
**[30:43]** But in the last couple of decades, the trend has been to rely less on
**[30:48]** rule based engineering and more on machine learning on data.
**[30:52]** Sometimes lots of data look into the future.
**[30:56]** Where do you think that mix of hand coded constraints or other constraints,
**[31:01]** explicit constraints versus let's get a neural network and throw lots of data at it.
**[31:07]** Where do you think that balance will fall?
**[31:10]** >> I think that there's no doubt that using learning from
**[31:15]** data is the way forward and what we're going to continue to do.
**[31:21]** But I think there's still a space for
**[31:24]** models that have more structure, more inductive bias that
**[31:30]** have some kind of basis of exploiting the nature of language.
**[31:35]** So in recent years, the model that's been enormously successful is
**[31:40]** the transformer neural network and the transformer neural networks,
**[31:44]** essentially this huge association machine.
**[31:47]** So it'll just suck associations from anywhere.
**[31:51]** >> And look at two words and figure out which words to which other word.
**[31:56]** >> Yes. So you use everything to predict anything
**[31:58]** and do it over and over again and you'll get anything you want.
**[32:02]** And you know, that's been incredibly, incredibly successful, but it's
**[32:08]** been incredibly successful in the domain where you have humongous amounts of data.
**[32:14]** Right, so that these transformer models for these large language
**[32:19]** models are now being trained on tens of billions of words of text.
**[32:23]** When I started off in statistical natural language processing.
**[32:28]** And some of the traditional linguists used to complain about the fact
**[32:33]** that I was collecting statistics from 30 million words of Newswire.
**[32:38]** And building a predictive model and
**[32:40]** thought that was just not what linguistics was about.
**[32:44]** I felt I had a perfectly good answer,
**[32:48]** which is that a human kid as they're learning language.
**[32:53]** They're exposed to actually, well, more than 30 million words of data.
**[32:58]** But that kind of amount of data, so the kind of amount of some data we were
**[33:03]** using were perfectly reasonable amounts of data to be using.
**[33:07]** To be not exactly trying to model human language acquisition.
**[33:11]** But to be thinking about how we can learn about language for lots of data.
**[33:17]** But these modern transformers are now using already
**[33:23]** at least two orders of magnitude, more data.
**[33:28]** And most most people think the way to get things to the next level
**[33:33]** is to use more still and make it three orders of magnitude.
**[33:37]** And in one sense that scaling up strategy has been hugely effective.
**[33:42]** So, I don't blame anybody for saying, let's make another order of magnitude
**[33:47]** bigger and see what amazing things we can do.
**[33:49]** But it also shows that human learning is just way,
**[33:54]** way better in being able to extract a lot more
**[33:58]** information out of a quite limited amount of data.
**[34:03]** And at that point, you can have various hypotheses.
**[34:07]** But I think it's reasonable to assume that human learning is
**[34:12]** somewhat structured towards the structure of the world.
**[34:17]** And things it sees in the world and
**[34:19]** that allows it to learn more quickly from less data.
**[34:22]** >> Right, I'm with you on that.
**[34:23]** I think better learning algorithms, our current machine learning,
**[34:27]** our rooms are much less efficient or makes much less efficient use of data.
**[34:31]** And so there's way more data than any child.
**[34:35]** And then I think whether the improved learning algorithms will be from
**[34:39]** linguistic rules or whether it will just be engineers.
**[34:42]** Engineering much more efficient versions of the transformer or
**[34:45]** whatever comes after it.
**[34:46]** That I think will be.
**[34:48]** >> That will be traditional.
**[34:50]** I don't think it'll be by people explicitly
**[34:54]** putting traditional linguistic rules into the system.
**[34:58]** I don't think that's the way forward.
**[35:00]** On the other hand I think what we're starting to see is models
**[35:05]** like these transformer models are actually discovering
**[35:10]** the structure of language themselves, right?
**[35:15]** So the broad effects of human language that English has
**[35:19]** the subject before the verb and the object afterwards.
**[35:24]** Whereas in Japanese that the verbs at the end of the sentence and the subject and
**[35:28]** object are normally in that order before it.
**[35:31]** But could be in the other order actually transformer models are learning
**[35:36]** these facts.
**[35:36]** You can interrogate them and see that even though they were
**[35:40]** never explicitly told about subjects and objects that they know these notions.
**[35:45]** So I think they're discovering a lot else as well about language use and context and
**[35:50]** the meanings and senses of words and what is and isn't, unpleasant language.
**[35:56]** But part of what they're learning is the same kind of structure that linguists
**[36:01]** have laid out as the sort of structure of different human languages.
**[36:05]** >> So it's as if over many decades, linguists discovered certain things.
**[36:09]** And by training on billions of words, transformers are discovering the same
**[36:13]** things that linguists discovered in humans.
**[36:15]** That's cool.
**[36:18]** So all this is really exciting progress in NLP,
**[36:21]** driven by machine learning and by other things.
**[36:24]** To someone entering the field, entering machine learning or AI or NLP.
**[36:28]** There's just a lot going on.
**[36:30]** What advice would you have for someone wanting to break into machine learning?
**[36:36]** >> Yeah.
**[36:37]** Well it's a great time to break in.
**[36:39]** I think there's just no doubt at all that we're still in the early stages
**[36:45]** of seeing the impact of this new approach where effectively software computer
**[36:52]** science is being reinvented on the basis of much more use of machine learning.
**[36:58]** And the various other things that come up away from that.
**[37:01]** And then more generally across industries, there are just lots of opportunities for
**[37:06]** more automation.
**[37:07]** Making more use of interpretation of human language material for me or
**[37:12]** in other areas like vision and robotics, the same kind of things.
**[37:17]** So, lots of possibilities.
**[37:20]** So at that point, there's lots to do obviously in that you want to get
**[37:25]** some kind of good foundation, right.
**[37:28]** So knowing some of the core technical methods of machine learning,
**[37:33]** understanding ideas of how to build models from data.
**[37:37]** Look at losses, do training diagnose errors, all of these core things.
**[37:43]** That's definitely useful for natural language processing in particular,
**[37:48]** some of those skills are completely relevant.
**[37:51]** But then there are particular kind of models that are commonly used,
**[37:55]** including the the transformer that we've talked about a lot today.
**[37:59]** You definitely should know about transformers and indeed
**[38:02]** they're increasingly being used in every other part of machine learning as well for
**[38:07]** vision bioinformatics, even robotics is now using transformers.
**[38:11]** But beyond that, I think it's also useful to learn something
**[38:15]** about human language and the nature of the problems that involves.
**[38:19]** Because even though people aren't directly going to be encoding
**[38:24]** rules of human language into their computing system.
**[38:29]** A sensitivity to sort of what kind of things happen in language and
**[38:34]** what to look out for and
**[38:36]** what you might want to model that's still a useful skill to have.
**[38:42]** >> And then in terms of learning the foundations,
**[38:44]** learning about these concepts.
**[38:46]** You had entered AI from a linguistic background and
**[38:51]** we now see people from all walks of life wanting to start doing work in AI.
**[38:58]** What are your thoughts on the preparation one should have or and your thoughts on
**[39:02]** how to start from something other than computer science or AI.
**[39:05]** So there are lots of places you can come from and
**[39:10]** vector across and different ways.
**[39:13]** And we're seeing tons of people doing that that they are people
**[39:18]** who started off in different areas, whether it was chemistry,
**[39:24]** physics or even much further in field.
**[39:27]** And people have history, whatever have started to look at machine learning.
**[39:31]** I think there are sort of two levels of answer there.
**[39:35]** One level of answer is one of the amazing transformations
**[39:40]** is that there's now these very good software packages for
**[39:45]** doing things with neural network models.
**[39:48]** This software is really easy to use.
**[39:52]** You don't actually need to understand a lot of highly technical stuff.
**[39:56]** You've got need to have some kind of high level conception about what is the idea of
**[40:01]** machine learning.
**[40:02]** And how do I go about training a model and what should I look at and
**[40:05]** the numbers that are being printed out to see if it's working, right.
**[40:09]** But you don't actually have to have a higher degree to be able to build these
**[40:13]** models.
**[40:14]** I mean, and indeed what we're seeing is, lots of high school students
**[40:18]** are getting into doing this because it's actually something that if you have
**[40:23]** some basic computer skills and a bit of programming, you can pick up and do.
**[40:28]** It's just way more accessible than lots of stuff that proceeded at
**[40:33]** whether in AI outside of AI and other areas, like operating systems or security.
**[40:39]** But if you want to get to a deeper level than that and
**[40:42]** actually want to understand more of what's going on.
**[40:46]** I think you can't really get there if you don't have a certain
**[40:51]** mathematics foundation, like at the end of the day that DeepLearning
**[40:57]** is based on calculus and you need to be optimising functions.
**[41:02]** And if you sort of don't have any background in that,
**[41:06]** I think that sort of ends up as a war at some point.
**[41:10]** So >> The machines learning in data science.
**[41:14]** It does come in handy for
**[41:15]** some of the work we >> Yeah.
**[41:17]** So I think at some level, if you're at the major in history or
**[41:22]** non mathematical parts of psychology, I actually have a good friend who,
**[41:28]** yeah, he learned calculus in grad school because he was a psychologist and
**[41:34]** he'd never done it before.
**[41:36]** And decided that he wanted to start learning about these new kinds of models
**[41:41]** and decided it wasn't too late to be able to go and take a calc course.
**[41:45]** And so he did, right.
**[41:46]** So you do need to know some of that stuff, but for lots of people,
**[41:52]** if they've seen some of that before, even if you're kind of rusty.
**[41:58]** I think you can kind of, get back in the zone and it doesn't really matter that
**[42:03]** you haven't done AI as an undergrad or machine learning and things like that,
**[42:08]** that you can really start to learn how to build these models and do things and
**[42:13]** really, that's my own story, right?
**[42:15]** That despite the fact that they let me sit in the school of engineering at
**[42:20]** Stanford these days, my background isn't as an engineer.
**[42:25]** My PhD is in linguistics, that I've sort of largely vectored
**[42:30]** across from having some knowledge of mathematics and linguistics and
**[42:36]** knowing some programming into sort of getting much more into building AI models.
**[42:43]** >> I about something.
**[42:44]** Do you think the improved libraries and abstractions that are now available like
**[42:49]** coding frameworks, like TensorFlow or PyTorch?
**[42:51]** Do you think that reduces the need to understand calculus?
**[42:54]** Because boy it's been a while since I had to actually take a derivative in
**[42:59]** order to even implement or create a new neural network architecture because of
**[43:03]** automatic differentiation >> Yeah, I mean, absolutely.
**[43:08]** I mean, so in the early days, when we were doing things sort of 2010 to 2015, right?
**[43:16]** For every model we built, we were working out the derivatives by hand and
**[43:21]** then writing some code and whatever it was.
**[43:24]** Sometimes it was Python but sometimes it might have been Java or
**[43:29]** C [LAUGH] to calculate these derivatives and
**[43:32]** checking that we got them right and so on, where these days you actually
**[43:37]** don't need to know any of that to build DeepLearning models.
**[43:42]** I mean, this is actually something I think about,
**[43:45]** been thinking about even with respect to my own natural language processing
**[43:49]** with DeepLearning class that I teach.
**[43:52]** At the beginning, we do still go through doing, matrix calculus and
**[43:58]** making sure people know about Jacobian and things like that so
**[44:03]** that they understand what's being done in back propagation, DeepLearning.
**[44:10]** But there's sort of this thing in which that means that we just give them hell for
**[44:16]** two weeks.
**[44:16]** It's sort of like boot camp or something to make them suffer.
**[44:20]** And then we say, but you do the rest of the class with pytorch and
**[44:24]** they sort of never have to know any of that again, right?
**[44:28]** There's always a question of how deep you want to go on technical foundations you,
**[44:33]** right.
**[44:33]** You can keep on going, right?
**[44:35]** Like does a computer scientist in the 2020 need to understand,
**[44:42]** electronics and transistors or what happens in your CPU.
**[44:47]** Well, it's complicated, I mean, in various ways,
**[44:50]** it is helpful to know some of that stuff.
**[44:52]** I mean, I know Andrew,
**[44:54]** you were one of the pioneers in getting machine learning on to GPU and, well, that
**[44:59]** sort of means you had to have some sense that there's this new hardware out there.
**[45:05]** And it has some attributes of parallelism that means there's likely to be able to do
**[45:09]** something exciting.
**[45:10]** So it is useful to have some broader knowledge and understanding and
**[45:14]** sometimes something breaks and if you have some deeper knowledge,
**[45:19]** you can understand why it broke.
**[45:21]** But there's another sense in which most people have to take some
**[45:26]** things on trust and you can do most of what you want to do in neural
**[45:31]** network modeling these days without knowing calculus at all.
**[45:36]** >> Yeah, I think that's a great point.
**[45:37]** I feel like sometimes the reliability of the abstraction determines how often you
**[45:41]** need to go in to fix something that's broken.
**[45:43]** So I'm, actually my understanding of quantum physics is very weak.
**[45:47]** I barely understand it.
**[45:49]** So you could argue, I don't understand how computers work
**[45:51]** because transistors are built in quantum physics.
**[45:53]** But fortunately, if something went wrong with the transistor,
**[45:59]** I've never had to go hard to fix it, [CROSSTALK] I think.
**[46:03]** And so I think or another example, the sort function, the library to sort things,
**[46:08]** and sometimes they actually don't work, right, swap in the memory or whatever.
**[46:14]** And that's when, if you really understand how the sort function works,
**[46:17]** you can go in and fix it.
**[46:18]** But then sometimes if we have abstractions, libraries,
**[46:21]** APIs are reliable enough, then that it's nice to those abstractions then diminishes
**[46:26]** the need to understand some of the things that happen on me.
**[46:29]** So it's an exciting world.
**[46:31]** Feels like we have giants building on the shoulders of giants and all of
**[46:35]** these things are becoming more complex and more exciting every month really.
**[46:40]** >> Yeah, absolutely.
**[46:41]** >> So thanks Chris, that was really interesting and inspiring and
**[46:46]** I hope that to everyone watching this hearing Chris own journey to
**[46:50]** become a computer scientist.
**[46:53]** And to become a leading, maybe the leading NLP computer scientist as well as all of
**[46:57]** this exciting work happening in NLP right now.
**[47:00]** I hope that inspires you too to jump into the steam and take a go at it.
**[47:05]** There's just a lot more work to be done collectively by our community that still,
**[47:09]** so I think the more of us are working on this, the better off the world will be.
**[47:13]** So thanks a lot, Chris.
**[47:15]** It was really great having you here.
**[47:16]** >> Thanks a lot, Andrew.
**[47:17]** It's been fun chatting.
**[47:18]** [MUSIC]
