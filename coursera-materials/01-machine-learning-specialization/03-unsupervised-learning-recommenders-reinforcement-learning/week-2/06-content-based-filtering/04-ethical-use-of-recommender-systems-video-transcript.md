---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 2
section: Content-based filtering
item_title: Ethical use of recommender systems
duration: 11 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/CzEzW/ethical-use-of-recommender-systems
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Ethical use of recommender systems — Transcript

**[0:01]** Even though recommender systems have been very
**[0:04]** profitable for some businesses, that happens,
**[0:07]** some use cases that have left
**[0:09]** people and society at large worse off.
**[0:13]** However, you use recommender systems or
**[0:16]** for that matter other learning algorithms,
**[0:18]** I hope you only do things that make
**[0:21]** society at large and people better off.
**[0:24]** Let's take a look at some of
**[0:26]** the problematic use cases of recommender systems,
**[0:29]** as well as ameliorations to
**[0:31]** reduce harm or to
**[0:32]** increase the amount of good that they can do.
**[0:34]** As you've seen in the last few videos,
**[0:37]** there are many ways of configuring a recommender system.
**[0:41]** When we saw binary labels,
**[0:43]** the label y could be,
**[0:44]** does a user engage or did they click
**[0:46]** or did they explicitly like an item?
**[0:50]** When designing a recommender system,
**[0:53]** choices in setting the goal of the recommender system
**[0:57]** and a lot of choices and
**[0:59]** deciding what to recommend to users.
**[1:01]** For example, you can decide to recommend to
**[1:05]** users movies most likely to be
**[1:08]** rated five stars by that user. That seems fine.
**[1:11]** That seems like a fine way to show
**[1:12]** users movies that they would like.
**[1:15]** Or maybe you can recommend to
**[1:17]** the user products that they are most likely to purchase.
**[1:21]** That seems like a very reasonable use
**[1:23]** of a recommender system as well.
**[1:26]** Versions of recommender systems can also be
**[1:29]** used to decide what ads to show to a user.
**[1:34]** One thing you could do is to recommend or really to
**[1:37]** show to the user ads that are most likely to be clicked on.
**[1:42]** Actually, what many companies will do
**[1:44]** is try to show ads that are likely to be clicked on
**[1:47]** and where the advertiser had put in
**[1:50]** a high bid because for many ad models,
**[1:56]** the revenue that the company
**[1:57]** collects depends on whether the ad was
**[2:00]** clicked on and what the advertiser had bid per-click.
**[2:04]** While this is a profit-maximizing strategy,
**[2:08]** there are also some possible negative implications
**[2:13]** of this type of advertising.
**[2:14]** I'll give a specific example on the next slide.
**[2:17]** One other thing that many companies do is
**[2:21]** try to recommend products that
**[2:23]** generate the largest profit.
**[2:25]** If you go to a website and search for a product today,
**[2:29]** there are many websites that are not showing you
**[2:33]** the most relevant product or the product
**[2:35]** that you are most likely to purchase.
**[2:38]** But is instead trying to show you
**[2:40]** the products that will generate
**[2:41]** the largest profit for the company.
**[2:44]** If a certain product is more profitable for them,
**[2:48]** because they can buy it more
**[2:50]** cheaply and sell it at a higher price,
**[2:52]** that gets ranked higher in the recommendations.
**[2:56]** Now, many companies view a pressure to maximize profit.
**[3:00]** This doesn't seem like
**[3:02]** an unreasonable thing to do but on the flip side,
**[3:05]** from the user perspective,
**[3:07]** when a website recommends to you a product,
**[3:10]** sometimes it feels it could be nice if
**[3:11]** the website was transparent with
**[3:13]** you about the criteria
**[3:15]** by which it is deciding what to show you.
**[3:17]** Is it trying to maximize their profits or
**[3:20]** trying to show you things that are most useful to you?
**[3:24]** On video websites or social media websites,
**[3:28]** a recommender system can also be modified to try to show
**[3:33]** you the content that leads to the maximum watch time.
**[3:38]** Specifically, websites that are
**[3:42]** an ad revenue tend to have
**[3:44]** an incentive to keep you on the website for a long time.
**[3:48]** Trying to maximize the time you
**[3:50]** spend on the site is one way for
**[3:52]** the site to try to get more of
**[3:54]** your time so they can show you more ads.
**[3:57]** Recommender systems today are used to try to maximize
**[4:02]** user engagement or to maximize the amount of
**[4:04]** time that someone spends on a site or a specific app.
**[4:07]** Whereas the first two of these seem quite innocuous,
**[4:12]** the third, fourth, and fifth,
**[4:14]** they may be just fine.
**[4:15]** They may not cause any harm at all.
**[4:17]** Or they could also be
**[4:18]** problematic use cases for recommender systems.
**[4:22]** Let's take a deeper look at some of
**[4:25]** these potentially problematic use cases.
**[4:28]** Let me start with the advertising example.
**[4:32]** It turns out that the advertising
**[4:34]** industry can sometimes be
**[4:36]** an amplifier of some of the most harmful businesses.
**[4:41]** They can also be an amplifier of some of the
**[4:43]** best and the most fruitful businesses.
**[4:46]** Let me illustrate with a good example and a bad example.
**[4:50]** Take the travel industry.
**[4:52]** I think in the travel industry,
**[4:53]** the way to succeed is to try to
**[4:56]** give good travel experiences to users,
**[4:58]** to really try to serve users.
**[5:00]** Now it turns out that if there's
**[5:02]** a really good travel company,
**[5:04]** they can sell you a trip to
**[5:06]** fantastic destinations and make
**[5:09]** sure you and your friends and family have a lot of fun.
**[5:11]** Then a good travel business,
**[5:13]** I think will often end up being more profitable.
**[5:17]** The other business is more profitable.
**[5:19]** They can then bid higher for ads.
**[5:22]** It can afford to pay more to get users.
**[5:26]** Because it can afford to bid higher for ads
**[5:30]** an online advertising site will show
**[5:33]** its ads more often and drive
**[5:35]** more users to this good company.
**[5:37]** This is a virtuous cycle
**[5:39]** where the more users you serve well,
**[5:41]** the more profitable the business,
**[5:43]** and the more you can bid more for
**[5:44]** ads and the more traffic you get and so on.
**[5:47]** Just virtuous circle will maybe even tend to help
**[5:50]** the good travel companies
**[5:53]** do even better statistically example.
**[5:55]** Let's look at the problematic example.
**[5:58]** The payday loan industry tends
**[6:01]** to charge extremely high-interest rates,
**[6:04]** often to low-income individuals.
**[6:07]** One of the ways to do well in
**[6:09]** the payday loan business is to be really
**[6:11]** efficient as squeezing customers
**[6:13]** for every single dollar you can get out of them.
**[6:16]** If there's a payday loan company
**[6:19]** that is very good at exploiting customers,
**[6:21]** really squeezing customers for every single dollar,
**[6:24]** then that company will be more profitable.
**[6:27]** Thus they can be higher for ads.
**[6:30]** Because they can get bid higher for ads
**[6:33]** they will get more traffic sent to them.
**[6:36]** This allows them to squeeze
**[6:37]** even more customers and
**[6:39]** explore even more people for profit.
**[6:41]** This in turn, also increase a positive feedback loop.
**[6:45]** Also, a positive feedback loop
**[6:47]** that can cause the most exploitative,
**[6:50]** the most harmful payday loan companies
**[6:53]** to get sent more traffic.
**[6:55]** This seems like the opposite effect
**[6:58]** than what we think would be good for society.
**[7:01]** I don't know that there's an easy solution to this.
**[7:05]** These are very difficult problems
**[7:07]** that recommender systems face.
**[7:09]** One amelioration might be to
**[7:12]** refuse to set ads from exploitative businesses.
**[7:15]** Of course, that's easy to say.
**[7:17]** But how do you define what is
**[7:19]** an exploitative business and what is not,
**[7:21]** is a very difficult question.
**[7:23]** But as we build
**[7:25]** recommender systems for advertising or for other things,
**[7:28]** I think these are questions that each one
**[7:30]** of us working on these technologies
**[7:33]** should ask ourselves so that we
**[7:35]** can hopefully invite open discussion and debate,
**[7:39]** get multiple opinions from multiple people,
**[7:42]** and try to come up with design choices that allows
**[7:46]** our systems to try to do much
**[7:48]** more good than potential harm.
**[7:50]** Let's look at some other examples.
**[7:52]** It's been widely reported in the news that
**[7:54]** maximizing user engagement such as
**[7:57]** the amount of time that
**[7:58]** someone watches videos on a website
**[8:01]** or the amount of time someone spends on social media.
**[8:05]** This has led to large social media
**[8:07]** and video sharing sites to
**[8:08]** amplify conspiracy theories or hate and toxicity
**[8:12]** because conspiracy theories and certain types of
**[8:16]** hate toxic content is highly
**[8:18]** engaging and causes people to spend a lot of time on it.
**[8:22]** Even if the effect of
**[8:24]** amplifying conspiracy theories amplify
**[8:27]** hidden toxicity turns out to be
**[8:29]** harmful to individuals and to society at large.
**[8:33]** One amelioration for this partial and imperfect
**[8:36]** is to try to filter out
**[8:38]** problematic contents such as hate speech,
**[8:40]** fraud, scams, maybe certain types the violent content.
**[8:44]** Again, the definitions of what exactly we should filter
**[8:47]** out is surprisingly tricky to develop.
**[8:51]** And this is a set of problems that I think
**[8:55]** companies and individuals and
**[8:56]** even governments have to continue to wrestle with.
**[8:59]** Just one last example.
**[9:01]** When a user goes to many apps or websites,
**[9:05]** I think users think the app or website
**[9:08]** I tried to recommend to
**[9:10]** the user thinks that they will like.
**[9:12]** I think many users don't
**[9:13]** realize that many apps and websites are trying to
**[9:16]** maximize their profit rather than necessarily
**[9:20]** the user's enjoyment of
**[9:22]** the media items that are being recommended.
**[9:24]** I would encourage you and
**[9:26]** other companies if at all possible,
**[9:28]** to be transparent with users about
**[9:30]** a criteria by which you're
**[9:32]** deciding what to recommend to them.
**[9:34]** I know this isn't always easy, but ultimately,
**[9:38]** I hope that being more
**[9:40]** transparent with users about why we're
**[9:42]** showing them and why will increase trust and
**[9:45]** also cause our systems to do more good for society.
**[9:50]** Recommender systems are very powerful technology,
**[9:53]** a very profitable, a very lucrative technology.
**[9:56]** There are also some problematic use cases.
**[9:59]** If you are building one of these systems using
**[10:01]** recommender technology or
**[10:03]** really any other machine learning or other technology.
**[10:06]** I hope you think through
**[10:08]** not just the benefits you can create,
**[10:10]** but also the possible harm and
**[10:13]** invite diverse perspectives and discuss and debate.
**[10:16]** Please only build things and do things that
**[10:19]** you really believe can be society better off.
**[10:23]** I hope that collectively,
**[10:25]** all of us in AI can only do work that makes
**[10:28]** people better off. Thanks for listening.
**[10:33]** We have just one more video to go in
**[10:36]** recommender systems in which we take a look at
**[10:38]** some practical tips for how to implement
**[10:41]** a content-based filtering algorithm in TensorFlow.
**[10:44]** Let's go on to that last video on recommender systems.
