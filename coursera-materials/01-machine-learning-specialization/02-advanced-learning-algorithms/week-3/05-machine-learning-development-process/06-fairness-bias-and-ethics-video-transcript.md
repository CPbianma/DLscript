---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 3
section: Machine learning development process
item_title: Fairness, bias, and ethics
duration: 10 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/HYNX7/fairness-bias-and-ethics
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# Fairness, bias, and ethics — Transcript

**[0:02]** Machine learning algorithms today are affecting billions of people.
**[0:05]** You've heard me mention ethics in other videos before.
**[0:09]** And I hope that if you're building a machine learning system that affects
**[0:14]** people that you give some thought to making sure that your system
**[0:18]** is reasonably fair, reasonably free from bias.
**[0:22]** And that you're taking a ethical approach to your application.
**[0:26]** Let's take a look at some issues related to fairness, bias and ethics.
**[0:32]** Unfortunately in the history of machine learning that happened a few systems,
**[0:37]** some widely publicized,
**[0:39]** that turned out to exhibit a completely unacceptable level of bias.
**[0:43]** For example,
**[0:44]** there was a hiring tool that was once shown to discriminate against women.
**[0:49]** The company that built the system stopped using it, but
**[0:52]** one wishes that the system had never been rolled out in the first place.
**[0:57]** Or there was also well documented example of face recognition systems that
**[1:01]** match dark skinned individuals to criminal mug shots much more often than
**[1:06]** lighter skinned individuals.
**[1:08]** And clearly this is not acceptable and we should get better as a community
**[1:13]** at just not building and deploying systems with a problem like this.
**[1:17]** In the first place, there happens systems that gave bank loan approvals in
**[1:22]** a way that was biased and discriminated against subgroups.
**[1:26]** And we also really like learning algorithms to not have the toxic effect of
**[1:31]** reinforcing negative stereotypes.
**[1:33]** For example, I have a daughter and if she searches online for
**[1:37]** certain professions and doesn't see anyone that looks like her, I would hate for
**[1:42]** that to discourage her from taking on certain professions.
**[1:45]** In addition to the issues of bias and fair treatment of individuals,
**[1:51]** there have also been adverse use cases or
**[1:54]** negative use cases of machine learning algorithms.
**[1:58]** For example, there was this widely cited and
**[2:01]** widely viewed video release with full disclosure and full transparency.
**[2:07]** By the company buzzfeed of a deepfake of former US President Barack Obama and
**[2:13]** you can actually find and watch the whole video online if you want.
**[2:18]** But the company that created this video did so
**[2:21]** full transparency and full disclosure.
**[2:24]** But clearly using this technology to generate fake videos without consent and
**[2:30]** without disclosure would be unethical.
**[2:34]** We've also seen unfortunately social media sometimes spreading toxic or
**[2:40]** incendiary speech because optimizing for
**[2:43]** user engagement has led to algorithms doing so.
**[2:47]** There have been bots that were used to generate fake content for
**[2:52]** either commercial purposes such as posting fake comments on products or
**[2:58]** for political purposes.
**[3:01]** And there are users of machine learning to build harmful products,
**[3:05]** commit fraud and so on.
**[3:07]** And in parts of the machine learning world, just as an email,
**[3:12]** there has been a battle between the spammers and the anti spam community.
**[3:17]** I am seeing today in for example, the financial industry,
**[3:22]** a battle between people trying to commit fraud and the people fighting fraud.
**[3:29]** And unfortunately machine learning is used by some of the fraudsters and
**[3:33]** some of the spammers.
**[3:35]** So for goodness sakes please don't build a machine learning system
**[3:39]** that has a negative impact on society.
**[3:42]** And if you are asked to work on an application that you consider unethical,
**[3:48]** I urge you to walk away for what it's worth.
**[3:52]** There have been multiple times that I have looked at the project that seemed to be
**[3:55]** financially sound.
**[3:56]** You'll make money for some company.
**[3:58]** But I have killed the project just on ethical grounds because I think that even
**[4:03]** though the financial case will sound, I felt that it makes the world worse off and
**[4:07]** I just don't ever want to be involved in a project like that.
**[4:11]** Ethics is a very complicated and very rich subject that humanity has studied for
**[4:16]** at least a few 1000 years.
**[4:18]** When aI became more widespread, I actually went and read up multiple books on
**[4:23]** philosophy and multiple books on ethics because I was hoping naively it turned
**[4:28]** out to come up with if only there's a checklist of five things we could do and
**[4:33]** so as we do these five things then we can be ethical, but I failed And
**[4:37]** I don't think anyone has ever managed to come up with a simple checklist of
**[4:42]** things to do to give that level of concrete guidance about how to be ethical.
**[4:47]** So what I hope to share with you instead is not a checklist because I wasn't
**[4:52]** even come up with one with just some general guidance and some suggestions for
**[4:57]** how to make sure the work is less bias more fair and more ethical.
**[5:02]** And I hope that some of these guidance,
**[5:04]** some which would be relatively general will help you with your work as well.
**[5:08]** So here are some suggestions for making your work more fair,
**[5:13]** less biased and more ethical when before deploying a system that could create harm.
**[5:21]** I will usually try to assemble a diverse team to brainstorm possible
**[5:26]** things that might go wrong with an emphasis on possible harm.
**[5:31]** Two vulnerable groups I found many times in my life that having a more
**[5:36]** diverse team and by diverse I mean, diversity on multiple dimensions
**[5:40]** ranging from gender to ethnicity to culture, to many other traits.
**[5:46]** I found that having more diverse teams actually causes a team collectively
**[5:51]** to be better at coming up with ideas about things that might go wrong and
**[5:55]** it increases the odds that will recognize the problem and fix it before
**[6:00]** rolling out the system and having that cause harm to some particular group.
**[6:06]** In addition to having a diverse team carrying out brainstorming.
**[6:10]** I have also found it useful to carry out a literature search on any standards or
**[6:15]** guidelines for your industry or particular application area, for example,
**[6:20]** in the financial industry, there are starting to be established standards for
**[6:25]** what it means to be a system.
**[6:27]** So they want that decides who to approve loans to, what it means for
**[6:30]** a system like that to be reasonably fair and free from bias and
**[6:34]** those standards that still emerging in different
**[6:36]** sectors could inform your work depending on what you're working on.
**[6:41]** After identifying possible problems.
**[6:44]** I found it useful to then audit the system against
**[6:48]** this identified dimensions of possible home.
**[6:53]** Prior to deployment, you saw in the last video,
**[6:57]** the full cycle of machine learning project.
**[7:00]** And one key step that's often a crucial line of defense against deploying
**[7:04]** something problematic is after you've trained the model.
**[7:08]** But before you deployed in production, if the team has brainstormed, then it may be
**[7:12]** biased against certain subgroups such as certain genders or certain ethnicities.
**[7:17]** You can then order the system to measure the performance to see if it really
**[7:22]** is bias against certain genders or ethnicities or other subgroups and
**[7:27]** to make sure that any problems are identified and fixed.
**[7:31]** Prior to deployment.
**[7:33]** Finally, I found it useful to develop a mitigation plan if applicable.
**[7:39]** And one simple mitigation plan would be to roll back to the earlier system
**[7:44]** that we knew was reasonably fair.
**[7:46]** And then even after deployment to continue to monitor harm so
**[7:49]** that you can then trigger a mitigation plan and
**[7:52]** act quickly in case there is a problem that needs to be addressed.
**[7:57]** For example, all of the self driving car teams prior to rolling out self driving
**[8:01]** cars on the road had developed mitigation plans for
**[8:04]** what to do in case the car ever gets involved in an accident so
**[8:08]** that if the car was ever in an accident, there was already a mitigation plan that
**[8:13]** they could execute immediately rather than have a car got into an accident and
**[8:18]** then only scramble after the fact to figure out what to do.
**[8:22]** I've worked on many machine learning systems and let me tell you the issues
**[8:27]** of ethics, fairness and bias issues we should take seriously.
**[8:30]** It's not something to brush off.
**[8:32]** It's not something to take lightly.
**[8:34]** Now of course,
**[8:35]** there's some projects with more serious ethical implications than others.
**[8:40]** For example, if I'm building a neural network to decide how long to roast
**[8:44]** my coffee beans, clearly, the ethical implications of that seems
**[8:48]** significantly less than if, say you're building a system to decide what loans.
**[8:52]** Bank loans are approved, which if it's bias can cause significant harm.
**[8:58]** But I hope that all of us collectively working
**[9:00]** in machine learning can keep on getting better debate these issues.
**[9:05]** Spot problems, fix them before they cause harm so that we collectively can avoid
**[9:09]** some of the mistakes that the machine learning world had made before because
**[9:13]** this stuff matters and the systems we built can affect a lot of people.
**[9:18]** And so that's it on the process of developing a machine learning system and
**[9:24]** congratulations on getting to the end of this week's required videos.
**[9:29]** I have just two more optional videos this week for
**[9:33]** you on addressing skewed data sets and that means data sets where
**[9:37]** the ratio of positive To negative examples is very far from 50, 50.
**[9:43]** And it turns out that some special techniques are needed to address machine
**[9:46]** learning applications like that.
**[9:48]** So I hope to see you in the next video optional video on how to
**[9:53]** handle skewed data sets.
