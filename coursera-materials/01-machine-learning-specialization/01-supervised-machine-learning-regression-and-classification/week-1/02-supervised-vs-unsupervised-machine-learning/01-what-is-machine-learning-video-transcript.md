---
type: video-transcript
specialization: Machine Learning Specialization
course: "Supervised Machine Learning: Regression and Classification"
week: 1
section: Supervised vs. Unsupervised Machine Learning
item_title: What is machine learning?
duration: 5 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/PNeuX/what-is-machine-learning
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# What is machine learning? — Transcript

**[0:00]** What is machine learning?
**[0:02]** In this video, you'll learn the definition of what it is
**[0:05]** and also get a sense of when you might want to apply it.
**[0:09]** Let's take a look together.
**[0:10]** Here's a definition of what is
**[0:13]** machine learning that is attributed to Arthur Samuel.
**[0:16]** He defined machine learning
**[0:18]** as the field of study that gives
**[0:20]** computers the ability to learn
**[0:21]** without being explicitly programmed.
**[0:24]** Samuel's claim to fame was that back in the 1950s,
**[0:28]** he wrote a checkers playing program.
**[0:30]** The amazing thing about
**[0:32]** this program was that Arthur Samuel
**[0:33]** himself wasn't a very good checkers player.
**[0:37]** What he did was he had programmed the computer
**[0:40]** to play maybe tens of thousands of games against itself.
**[0:43]** By watching what social support positions
**[0:46]** tend to lead to wins and what positions
**[0:48]** tend to lead to losses the checkers plane program
**[0:51]** learned over time what are
**[0:53]** good or bad suport positions by
**[0:56]** trying to get a good and avoid bad positions,
**[0:59]** this program learned to get better and better at playing
**[1:02]** checkers because the computer had
**[1:04]** the patience to play
**[1:05]** tens of thousands of games against itself.
**[1:08]** It was able to get
**[1:09]** so much checkers playing experience that
**[1:12]** eventually it became a better checkers player
**[1:14]** than also, Samuel himself.
**[1:17]** Now throughout these videos,
**[1:19]** besides me trying to talk about stuff,
**[1:21]** I occasionally ask you a question
**[1:23]** to help make sure you understand the content.
**[1:26]** Here's one about what happens if
**[1:28]** the computer had played far fewer games.
**[1:31]** Please take a look and pick
**[1:32]** whichever you think is the better answer.
**[1:37]** Thanks for looking at the quiz.
**[1:40]** If you had selected
**[1:43]** this answer would have
**[1:45]** made it worse then you got the right.
**[1:48]** In general, the more opportunities
**[1:50]** you give a learning algorithm to learn,
**[1:52]** the better it will perform.
**[1:54]** If you didn't select the correct answer the first time,
**[1:57]** that's totally okay too.
**[1:59]** The point of these questions isn't
**[2:01]** to see if you can get them
**[2:02]** all correctly on the first try.
**[2:04]** These questions are here just to help
**[2:06]** you practice the concepts you are learning.
**[2:08]** Arthur Samuel's definition was a rather
**[2:11]** informal one but in the next two videos,
**[2:14]** we'll dive deeper together into what are
**[2:16]** the major types of machine learning algorithms?
**[2:20]** In this course, you learn about
**[2:22]** many different learning algorithms.
**[2:24]** The two main types of machine learning are
**[2:27]** supervised learning and unsupervised learning.
**[2:31]** We'll define what these terms mean
**[2:33]** more in the next couple of videos.
**[2:36]** Of these two, supervised learning
**[2:39]** is the type of machine learning that is used most in
**[2:42]** many real-world applications and has
**[2:45]** seen the most rapid advancements and innovation.
**[2:48]** In this specialization,
**[2:50]** which has three courses in total,
**[2:53]** the first and second courses will
**[2:54]** focus on supervised learning,
**[2:56]** and the third will focus on unsupervised learning,
**[2:59]** recommender systems, and reinforcement learning.
**[3:02]** By far, the most used types of
**[3:05]** learning algorithms today are supervised learning,
**[3:08]** unsupervised learning, and recommender systems.
**[3:11]** The other thing we're going to spend a lot of
**[3:13]** time on in this specialization
**[3:15]** is practical advice for applying learning algorithms.
**[3:20]** This is something I feel pretty strongly about.
**[3:22]** Teaching about learning algorithms is like giving
**[3:25]** someone a set of tools and equally important,
**[3:29]** so even more important to making sure you
**[3:31]** have great tools is making sure
**[3:34]** you know how to apply them
**[3:36]** because like is it is somewhere where it
**[3:39]** gives you a state-of-the-art hammer
**[3:41]** or a state-of-the-art hand drill and say good luck.
**[3:44]** Now you have all the tools you need
**[3:45]** to build a three-story house.
**[3:47]** It doesn't really work like that
**[3:49]** and so too, in machine learning,
**[3:52]** making sure you have the tools is
**[3:53]** really important and so is making
**[3:55]** sure that you know how to apply
**[3:57]** the tools of machine learning effectively.
**[4:00]** That's what you get in this class,
**[4:02]** the tools as well as the
**[4:03]** skills to apply them effectively.
**[4:06]** I regularly visit with friends and
**[4:09]** teams in some of the top tech companies,
**[4:11]** and even today I see experienced machine learning teams
**[4:15]** apply machine learning algorithms to some problems,
**[4:18]** and sometimes they've been going at it for
**[4:20]** six months without much success.
**[4:23]** When I look at what they're doing,
**[4:25]** I sometimes feel like I could have told them
**[4:27]** six months ago that the current approach won't work
**[4:29]** and there's a different way of using
**[4:31]** these tools that will give
**[4:33]** them a much better chance of success.
**[4:35]** In this class, one of
**[4:37]** the relatively unique things you learn is
**[4:39]** you learn a lot about the best practices for
**[4:42]** how to actually develop a practical,
**[4:44]** valuable machine learning system.
**[4:47]** This way, you're less likely to
**[4:48]** end up in one of those teams that
**[4:50]** end up losing six months going in the wrong direction.
**[4:54]** In this class, you gain a sense of how
**[4:56]** the most skilled machine
**[4:57]** learning engineers build systems.
**[4:59]** I hope you finish
**[5:01]** this class as one of those very rare people in
**[5:04]** today's world that know how to
**[5:06]** design and build serious machine learning systems.
**[5:08]** That's machine learning.
**[5:11]** In the next video,
**[5:13]** let's look more deeply at what is
**[5:15]** supervised learning and also
**[5:17]** what is unsupervised learning.
**[5:19]** In addition, you'll learn
**[5:21]** when you might want to use each of them,
**[5:23]** supervised and unsupervised learning.
**[5:25]** I'll see you in the next video.
