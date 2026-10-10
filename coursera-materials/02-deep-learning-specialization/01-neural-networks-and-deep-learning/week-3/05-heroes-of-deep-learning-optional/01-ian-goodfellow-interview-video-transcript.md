---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 3
section: Heroes of Deep Learning (Optional)
item_title: Ian Goodfellow Interview
duration: 15 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/WSia1/ian-goodfellow-interview
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Ian Goodfellow Interview — Transcript

**[0:02]** Hi, Ian. Thanks a lot for joining us today.
**[0:05]** Thank you for inviting me,
**[0:06]** Andrew. I am glad to be here.
**[0:08]** Today, you are one of the world's most visible deep learning researchers.
**[0:11]** Let us share a bit about your personal story.
**[0:14]** So, how do you end up doing this work that you now do?
**[0:16]** Yeah. That sounds great.
**[0:19]** I guess I first became interested in machine learning right before I met you, actually.
**[0:24]** I had been working on neuroscience and my undergraduate adviser,
**[0:29]** Jerry Cain, at Stanford encouraged me to take your Intro to AI class.
**[0:34]** Oh, I didn't know that. Okay.
**[0:35]** So I had always thought that AI was a good idea,
**[0:39]** but that in practice, the main, I think,
**[0:42]** idea that was happening was like game AI,
**[0:44]** where people have a lot of hard-coded rules for
**[0:47]** non-player characters in games to say
**[0:49]** different scripted lines at different points in time.
**[0:52]** And then, when I took your Intro to AI class and you covered topics like
**[0:56]** linear regression and the variance decomposition of the error of linear regression,
**[1:02]** I started to realize that this is a real science and I could actually
**[1:06]** have a scientific career in AI rather than neuroscience.
**[1:10]** I see. Great. And then what happened?
**[1:12]** Well, I came back and I was the TA to your course later.
**[1:15]** Oh, I see. Right. Like a TA.
**[1:17]** So a really big turning point for me was while I was TA-ing that course,
**[1:22]** one of the students,
**[1:23]** my friend Ethan Dreifuss,
**[1:25]** got interested in Geoff Hinton's deep belief net paper.
**[1:28]** I see.
**[1:29]** And the two of us ended up building one of the first GPU CUDA-based machines at
**[1:35]** Stanford in order to run Watson machines in our spare time over winter break.
**[1:43]** I see.
**[1:43]** And at that point, I started to have
**[1:46]** a very strong intuition that deep learning was the way to go in the future,
**[1:50]** that a lot of the other algorithms that I was working with,
**[1:53]** like support vector machines,
**[1:56]** didn't seem to have the right asymptotics,
**[1:58]** that you add more training data and they get slower,
**[2:01]** or for the same amount of training data,
**[2:03]** it's hard to make them perform a lot better by changing other settings.
**[2:08]** At that point, I started to focus on deep learning as much as possible.
**[2:13]** And I remember Richard Reyna's very old GPU paper
**[2:18]** acknowledges you for having done a lot of early work.
**[2:21]** Yeah. Yeah. That was written using some of the machines that we built.
**[2:25]** Yeah.
**[2:26]** The first machine I built was just something that Ethan and I built at
**[2:30]** Ethan's mom's house with our own money,
**[2:35]** and then later, we used lab money to build the first two or three for the Stanford lab.
**[2:39]** Wow that's great. I never knew that story. That's great.
**[2:42]** And then, today, one of
**[2:45]** the things that's really taken
**[2:48]** the deep learning world by storm is your invention of GANs.
**[2:51]** So how did you come up with that?
**[2:54]** I've been studying generative models for a long time,
**[2:56]** so GANs are a way of doing
**[2:59]** generative modeling where you have a lot of training data and you'd like
**[3:02]** to learn to produce more examples that resemble the trading data, but they're imaginary.
**[3:08]** They've never been seen exactly in that form before.
**[3:13]** There were several other ways of doing generative models that had been
**[3:16]** popular for several years before I had the idea for GANs.
**[3:19]** And after I'd been working on all those other methods throughout most of my Ph.D.,
**[3:24]** I knew a lot about the advantages and disadvantages of all the other frameworks like
**[3:29]** Boltzmann machines and sparse coding
**[3:32]** and all the other approaches that have been really popular for years.
**[3:35]** I was looking for something that avoid all these disadvantages at the same time.
**[3:40]** And then finally, when I was arguing about generative models with my friends in a bar,
**[3:44]** something clicked into place,
**[3:45]** and I started telling them, You need to do,
**[3:47]** this, this, and this and I swear it will work.
**[3:49]** And my friends didn't believe me that it would work.
**[3:52]** I was supposed to be writing the deep learning textbook at the time,
**[3:55]** I see.
**[3:55]** But I believed strongly enough that it would work that I
**[3:57]** went home and coded it up the same night and it worked.
**[3:59]** So it take you one evening to implement the first version of GANs?
**[4:02]** I implemented it around midnight
**[4:06]** after going home from the bar where my friend had his going-away party.
**[4:09]** I see.
**[4:10]** And the first version of it worked,
**[4:11]** which is very, very fortunate.
**[4:13]** I didn't have to search for hyperparameters or anything.
**[4:15]** There was a story, I read it somewhere,
**[4:17]** where you had a near-death experience and that reaffirmed your commitment to AI.
**[4:21]** Tell me that one.
**[4:24]** So, yeah. I wasn't actually near death but I briefly thought that I was.
**[4:30]** I had a very bad headache and some of
**[4:33]** the doctors thought that I might have a brain hemorrhage.
**[4:37]** And during the time that I was waiting for
**[4:39]** my MRI results to find out whether I had a brain hemorrhage or not,
**[4:43]** I realized that most of the thoughts I was having were about making
**[4:47]** sure that other people would eventually
**[4:49]** try out the research ideas that I had at the time.
**[4:52]** I see. I see.
**[4:53]** In retrospect, they're all pretty silly research ideas.
**[4:55]** I see.
**[4:56]** But at that point,
**[4:58]** I realized that this was actually one of my highest priorities in life,
**[5:02]** was carrying out my machine learning research work.
**[5:05]** I see. Yeah. That's great,
**[5:07]** that when you thought you might be dying soon,
**[5:10]** you're just thinking how to get the research done.
**[5:12]** Yeah.
**[5:12]** Yeah. That's commitment.
**[5:15]** Yeah.
**[5:17]** Yeah. Yeah. So today, you're still at the center of a lot of the activities with GANs,
**[5:21]** with Generative Adversarial Networks.
**[5:24]** So tell me how you see the future of GANs.
**[5:27]** Right now, GANs are used for a lot of different things, like semi-supervised learning,
**[5:32]** generating training data for other models and even simulating scientific experiments.
**[5:39]** In principle, all of these things could be done by other kinds of generative models.
**[5:43]** So I think that GANs are at an important crossroads right now.
**[5:47]** Right now, they work well some of the time,
**[5:50]** but it can be more of an art than a science to really bring that performance out of them.
**[5:55]** It's more or less how people felt about deep learning in general 10 years ago.
**[5:59]** And back then, we were using
**[6:01]** deep belief networks with Boltzmann machines as the building blocks,
**[6:05]** and they were very, very finicky.
**[6:07]** Over time, we switched to things like rectified linear units and batch normalization,
**[6:11]** and deep learning became a lot more reliable.
**[6:14]** If we can make GANs become as reliable as deep learning has become,
**[6:18]** then I think we'll keep seeing GANs used in
**[6:20]** all the places they're used today with much greater success.
**[6:24]** If we aren't able to figure out how to stabilize GANs,
**[6:29]** then I think their main contribution to the history of deep learning is
**[6:32]** that they will have shown people how to
**[6:35]** do all these tasks that involve generative modeling,
**[6:37]** and eventually, we'll replace them with other forms of generative models.
**[6:41]** So I spend maybe about 40 percent of my time right now working on stabilizing GANs.
**[6:47]** I see. Cool. Okay. Oh, and so just as a lot of people
**[6:50]** that joined deep learning about 10 years ago, such as yourself,
**[6:53]** wound up being pioneers,
**[6:54]** maybe the people that join GANs today,
**[6:57]** if it works out, could end up the early pioneers.
**[7:00]** Yeah. A lot of people already are early pioneers of GANs,
**[7:04]** and I think if you wanted to give any kind of history of GANs so far,
**[7:09]** you'd really need to mention other groups like Indico
**[7:12]** and Facebook and Berkeley for all the different things that they've done.
**[7:17]** So in addition to all your research,
**[7:19]** you also coauthored a book on deep learning. How is that going?
**[7:24]** That's right, with Yoshua Bengio and Aaron Courville,
**[7:26]** who are my Ph.D. co-advisers.
**[7:29]** We wrote the first textbook on the modern version of deep learning,
**[7:35]** and that has been very popular,
**[7:38]** both in the English edition and the Chinese edition.
**[7:42]** We've sold about, I think around 70,000 copies total between those two languages.
**[7:48]** And I've had a lot of feedback from students who said that they've learned a lot from it.
**[7:54]** One thing that we did a little bit differently than some other books is we start with
**[7:58]** a very focused introduction to the kind of math that you need to do in deep learning.
**[8:03]** I think one thing that I got from your courses at Stanford is
**[8:07]** that linear algebra and probability are very important,
**[8:11]** that people get excited about the machine learning algorithms,
**[8:15]** but if you want to be a really excellent practitioner,
**[8:18]** you've got to master the basic math that underlies the whole approach in the first place.
**[8:26]** So we make sure to give
**[8:27]** a very focused presentation of the math basics at the start of the book.
**[8:31]** That way, you don't need to go ahead and learn all that linear algebra,
**[8:34]** that you can get
**[8:35]** a very quick crash course in the pieces of
**[8:37]** linear algebra that are the most useful for deep learning.
**[8:40]** So even someone whose math is a little shaky or haven't seen the math for
**[8:44]** a few years will be able to start from the beginning of your book and
**[8:47]** get that background and get into deep learning?
**[8:49]** All of the facts that you would need to know are there.
**[8:52]** It would definitely take some focused effort to practice making use of them.
**[8:59]** Yeah. Yeah. Great.
**[8:59]** If someone's really afraid of math,
**[9:01]** it might be a bit of a painful experience.
**[9:03]** But if you're ready for the learning experience and you believe you can master it,
**[9:08]** I think all the tools that you need are there.
**[9:11]** As someone that worked in deep learning for a long time,
**[9:15]** I'd be curious, if you look back over the years.
**[9:18]** Tell me a bit about how you're thinking
**[9:21]** of AI and deep learning has evolved over the years.
**[9:24]** Ten years ago, I felt like, as a community,
**[9:28]** the biggest challenge in machine learning was just how
**[9:31]** to get it working for AI-related tasks at all.
**[9:34]** We had really good tools that we could use for simpler tasks,
**[9:39]** where we wanted to recognize patterns in how to extract features,
**[9:44]** where a human designer could do a lot of
**[9:47]** the work by creating those features and then hand it off to the computer.
**[9:51]** Now, that was really good for different things
**[9:54]** like predicting which ads a user would click
**[9:56]** on or different kinds of basic scientific analysis.
**[10:01]** But we really struggled to do anything involving millions of pixels in an image or
**[10:07]** a raw audio wave form where
**[10:10]** the system had to build all of its understanding from scratch.
**[10:13]** We finally got over the hurdle really thoroughly maybe five years ago.
**[10:18]** And now, we're at a point where there are
**[10:22]** so many different paths open that someone who wants to get involved in AI,
**[10:26]** maybe the hardest problem they face is choosing which path they want to go down.
**[10:31]** Do you want to make reinforcement learning work as well as supervised learning works?
**[10:35]** Do you want to make unsupervised learning work as well as supervised learning works?
**[10:40]** Do you want to make sure that machine learning algorithms are fair
**[10:44]** and don't reflect biases that we'd prefer to avoid?
**[10:48]** Do you want to make sure that the societal issues surrounding AI work out well,
**[10:54]** that we're able to make sure that AI benefits everyone
**[10:58]** rather than causing social upheaval and trouble with loss of jobs?
**[11:03]** I think right now,
**[11:04]** there's just really an amazing amount of different things that can be done,
**[11:08]** both to prevent downsides from AI but also to make sure
**[11:11]** that we leverage all of the upsides that it offers us.
**[11:14]** And so today, there are a lot of people wanting to get into AI.
**[11:19]** So, what advice would you have for someone like that?
**[11:23]** I think a lot of people that want to get into AI start thinking that
**[11:26]** they absolutely need to get a Ph.D. or some other kind of credential like that.
**[11:32]** I don't think that's actually a requirement anymore.
**[11:35]** One way that you could get a lot of attention is to write good code and put it on GitHub.
**[11:40]** If you have an interesting project that solves
**[11:43]** a problem that someone working at the top level wanted to solve,
**[11:47]** once they find your GitHub repository,
**[11:49]** they'll come find you and ask you to come work there.
**[11:53]** A lot of the people that I've hired or
**[11:56]** recruited at OpenAI last year or at Google this year,
**[12:00]** I first became interested in working with them because of
**[12:02]** something that I saw that they released in an open-source forum on the Internet.
**[12:06]** Writing papers and putting them on Archive can also be good.
**[12:11]** A lot of the time,
**[12:12]** it's harder to reach the point where you have something polished enough to really be
**[12:16]** a new academic contribution to the scientific literature,
**[12:20]** but you can often get to the point of having a useful software product much earlier.
**[12:27]** So read your book,
**[12:30]** practice the materials and post on GitHub and maybe on Archive.
**[12:33]** I think if you learned by reading the book,
**[12:36]** it's really important to also work on a project at the same time,
**[12:39]** to either choose some way of
**[12:42]** applying machine learning to an area that you are already interested in.
**[12:46]** Like if you're a field biologist and you want to get into deep learning,
**[12:50]** maybe you could use it to identify birds,
**[12:53]** or if you don't have an idea for how you'd like to use machine learning in your own life,
**[12:56]** you could pick something like making a Street View house numbers classifier,
**[13:01]** where all the data sets are set up to make it very straightforward for you.
**[13:05]** And that way, you get to exercise all of
**[13:07]** the basic skills while you read the book or while
**[13:09]** you watch Coursera videos that explain the concepts to you.
**[13:14]** So over the last couple of years,
**[13:15]** I've also seen you do one more work on adversarial examples.
**[13:20]** Tell us a bit about that.
**[13:21]** Yeah. I think adversarial examples are
**[13:24]** the beginning of a new field that I call machine learning security.
**[13:29]** In the past, we've seen computer security issues
**[13:33]** where attackers could fool a computer into running the wrong code.
**[13:38]** That's called application-level security.
**[13:40]** And there's been attacks where people can fool a computer into believing that
**[13:46]** messages on a network come from somebody that is not actually who they say they are.
**[13:52]** That's called network-level security.
**[13:55]** Now, we're starting to see that you can also fool
**[13:57]** machine-learning algorithms into doing things they shouldn't,
**[13:59]** even if the program running the machine-learning algorithm is running the correct code,
**[14:06]** even if the program running
**[14:07]** the machine-learning algorithm knows
**[14:10]** who all the messages on the network really came from.
**[14:13]** And I think, it's important to build security
**[14:17]** into a new technology near the start of its development.
**[14:20]** We found that it's very hard to build a working system first and then add security later.
**[14:27]** So I am really excited about the idea that if
**[14:30]** we dive in and start anticipating security problems with machine learning now,
**[14:34]** we can make sure that these algorithms are secure from
**[14:37]** the start instead of trying to patch it in retroactively years later.
**[14:41]** Thank you. That was great.
**[14:43]** There's a lot about your story that I thought was fascinating and that,
**[14:46]** despite having known you for years,
**[14:47]** I didn't actually know, so thank you for sharing all that.
**[14:49]** Oh, very welcome. Thank you for inviting me. It was a great shot.
**[14:53]** Okay. Thank you.
**[14:53]** Very welcome.
