---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 3
section: Various Sequence To Sequence Architectures
item_title: Refinements to Beam Search
duration: 10 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/AkjG2/refinements-to-beam-search
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Refinements to Beam Search — Transcript

**[0:00]** In the last video, you saw the basic search algorithm,
**[0:04]** in this video, you learn some little changes,
**[0:07]** they'll make it work even better.
**[0:09]** Length normalization is a small change to the beam search,
**[0:13]** however, they can help you get much better results.
**[0:16]** Here's what it is, we talked about beam search
**[0:19]** as maximizing this probability and
**[0:23]** this product here is just
**[0:24]** expressing the observation that p
**[0:27]** of y1 up to yt y given x
**[0:32]** can be expressed as p of y1 given x times p
**[0:38]** of y2 given x and y1 times up to,
**[0:46]** I guess, p y ty given x and y1 up to y ty minus 1.
**[0:55]** But maybe this notation is a bit
**[0:58]** more scary and more intimidating than it needs to be,
**[1:01]** but is that probabilities that you've seen previously.
**[1:06]** Now, if you're implementing these,
**[1:09]** these probabilities are all numbers
**[1:12]** less than one, in fact,
**[1:13]** often they're much less than one and multiplying a lot
**[1:17]** of numbers less than one result in a tiny number,
**[1:21]** which can result in numerical under-floor,
**[1:24]** meaning that is too small for the floating point of
**[1:26]** representation in your computer to store accurately.
**[1:31]** In practice, instead of maximizing this product,
**[1:35]** we will take logs and if you insert a log there,
**[1:42]** then a log of a product becomes a sum of a log,
**[1:45]** and maximizing this sum of log probabilities should
**[1:49]** give you the same results in terms
**[1:51]** of selecting the most likely sentence.
**[1:55]** By taking logs,
**[1:56]** you end up with a more numerically stable algorithm
**[2:01]** that is less prone
**[2:02]** to numerical rounding errors
**[2:07]** or really numerical under-floor.
**[2:09]** Because the logarithmic function is
**[2:11]** a strictly monotonically increasing function,
**[2:16]** we know that maximizing
**[2:18]** log p of y given x should give you the same result as
**[2:22]** maximizing p of y given
**[2:25]** x as in the same value of y that maximizes,
**[2:29]** this should also maximize that.
**[2:32]** In most implementations, you keep track of the sum
**[2:36]** of logs of the probabilities
**[2:38]** rather than the product of probabilities.
**[2:40]** Now there's one other change to
**[2:44]** this objective function that makes
**[2:47]** the machine translation algorithm work even better.
**[2:52]** Which is that if
**[2:55]** you refer to this original objective up here,
**[2:58]** if you have a very long sentence,
**[3:00]** the probability of that sentence is going to be low
**[3:03]** because you're multiplying as many terms here,
**[3:06]** lots of numbers less than one
**[3:09]** to estimate the probability of that sentence.
**[3:11]** If you multiply log of the numbers
**[3:13]** less than one together,
**[3:14]** you just tend to end up with a smaller probability.
**[3:19]** This objective function has
**[3:22]** an undesirable effect that
**[3:24]** it may be unnaturally tend to prefer
**[3:27]** very short translations to prefer
**[3:30]** very short outputs because
**[3:33]** the probability of a short sentence is
**[3:35]** just by multiplying fewer of these numbers are
**[3:39]** less than one and
**[3:42]** so the product will just be not quite as small.
**[3:46]** By the way, the same thing is true for this,
**[3:48]** the log of a probability is
**[3:50]** always less than or equal to one,
**[3:54]** you're actually in this range of the log,
**[3:56]** so the more terms you add together,
**[3:59]** the more negative this thing becomes.
**[4:04]** There's one other change the algorithm
**[4:06]** that makes it work better,
**[4:08]** which is instead of using this as
**[4:11]** the objective you're trying to maximize.
**[4:14]** One thing you could do is normalizes by
**[4:17]** the number of words in your translation and
**[4:20]** so this takes the average
**[4:23]** of the log of the probability of
**[4:25]** each word and does
**[4:29]** significantly reduces the penalty
**[4:31]** for outputting longer translations.
**[4:34]** In practice as a heuristic
**[4:37]** instead of dividing by
**[4:38]** ty the number of words in the output sentence,
**[4:41]** sometimes you use the softer approach
**[4:44]** we have ty to power of
**[4:45]** Alpha where maybe Alpha is equal to 0.7.
**[4:50]** If Alpha was equal to one,
**[4:51]** then the completely normalized by length,
**[4:54]** if Alpha was equal to 0, then well,
**[4:57]** ty to the 0 will be 1,
**[4:59]** then you're just not normalizing at
**[5:01]** all and this is somewhere
**[5:03]** in between full normalization and no normalization.
**[5:07]** Alpha is another parameter hyperparameter,
**[5:10]** so the algorithm that you
**[5:11]** can tune to try to get the best results.
**[5:15]** Using Alpha this way,
**[5:18]** does this heuristic or does this a hack?
**[5:20]** There isn't a great theoretical justification for it,
**[5:23]** but people found this works well,
**[5:26]** people found it works well in practice,
**[5:28]** so many groups won't do this,
**[5:30]** and you can try out different values of
**[5:32]** Alpha and see which one gives you the best result.
**[5:38]** Just to wrap up how you can beam search,
**[5:41]** as you run beam search you see a lot of
**[5:43]** sentences with length equal 1,
**[5:46]** length sentences were equal 2,
**[5:49]** length sentence that equals 3 and so on,
**[5:53]** and maybe you run beam search for 30 steps you consider,
**[5:57]** output sentences up to 30, let's say.
**[6:01]** Would beam width of three,
**[6:04]** you would be keeping track of
**[6:06]** the top three possibilities for
**[6:08]** each of these possible sentence length 1,
**[6:10]** 2, 3, 4, and so on up to 30.
**[6:18]** Output sentences and score
**[6:22]** them against this score and so you can take
**[6:28]** your top sentences and just computes
**[6:31]** this objective function on the sentences that you
**[6:35]** have seen through the beam search process.
**[6:38]** Then finally, of all these sentences
**[6:42]** that you evaluate this way,
**[6:43]** you pick the one that achieves,
**[6:45]** the highest value on this
**[6:47]** normalize low probability objective,
**[6:50]** sometimes it's called a normalized
**[6:51]** log likelihood objective
**[6:53]** and then that would be the final translation you output.
**[6:57]** That's how you implement beam search and you get to
**[7:00]** play with this yourself in
**[7:02]** this week's programming exercise.
**[7:04]** Finally, a few implementation details,
**[7:07]** how do you choose the beam width?
**[7:09]** Share the pros and cons of setting beam to be
**[7:12]** very large versus very small.
**[7:15]** If the beam width is very large,
**[7:18]** then you consider a lot of possibilities and so you
**[7:22]** tend to get a better result
**[7:24]** because you're considering a lot of different options,
**[7:27]** but it will be slower.
**[7:29]** The memory requirements will also grow and
**[7:32]** also be computationally slower.
**[7:35]** Whereas if you use a very small beam width,
**[7:37]** then you get a worse result because you are just keeping
**[7:40]** less possibilities in mind as the algorithm is running,
**[7:45]** but you get a result faster and
**[7:48]** the memory requirements will also be lower.
**[7:50]** In the previous video,
**[7:53]** we use in our running example a beam width of 3,
**[7:56]** so we're keeping three possibilities in mind in
**[7:59]** practice that is on the small side in production systems,
**[8:03]** it's not uncommon to see a beam width maybe around 10.
**[8:07]** I think a beam width of 100 would be
**[8:09]** considered very large for a production system,
**[8:13]** depending on the application.
**[8:15]** But for research systems where people want to squeeze out
**[8:18]** every last drop of performance in order
**[8:20]** to publish a paper with the best possible result,
**[8:22]** it's not uncommon to see people use
**[8:25]** beam width of 1,000 or 3,000,
**[8:28]** but this is very application
**[8:30]** as well as a domain dependent.
**[8:33]** I would say try out a variety of values of
**[8:36]** beam as see what works for your application,
**[8:39]** but when beam is very large,
**[8:41]** there is often diminishing returns.
**[8:45]** For many applications, I would expect to see
**[8:49]** a huge gain as you go from beam of one,
**[8:51]** which is basically greedy search to three to maybe 10,
**[8:54]** but the gains as you go from the thousands
**[8:57]** to three thousand beam width might not be as big.
**[9:01]** For those of you that have
**[9:03]** taken maybe a lot of computer science courses before,
**[9:08]** if you're familiar with computer science search algorithms
**[9:11]** like BFS breadth first search or DFS depth first search,
**[9:15]** the way to think about beam search is
**[9:17]** that unlike those other algorithms
**[9:19]** which you might have learned about
**[9:20]** in computer science algorithms course,
**[9:23]** and don't worry about it if you've
**[9:24]** not heard of these algorithms.
**[9:25]** But if you've heard of breadth first search or depth first search,
**[9:27]** unlike those algorithms,
**[9:30]** which are exact search algorithms beam search
**[9:33]** runs much faster but is
**[9:35]** not guaranteed to find
**[9:36]** the exact maximum for
**[9:38]** this arg max that you like to find.
**[9:41]** If you haven't heard of breadth first search or depth first search,
**[9:43]** don't worry about it. It is not important for our purposes,
**[9:46]** but if you have, this is how
**[9:48]** the beam search relates to those algorithms.
**[9:51]** That's it for beam search,
**[9:53]** which is a widely used algorithm in
**[9:55]** many production systems or many commercial systems.
**[9:59]** Now in the third course
**[10:01]** in this sequence of courses on deep learning,
**[10:04]** we talk a lot about error analysis,
**[10:06]** it turns out one of the most useful tools I found
**[10:09]** is devoted to error analysis on beam search,
**[10:12]** so you sometimes wonder,
**[10:14]** should I increase my beam width?
**[10:15]** Is beam width working well enough
**[10:17]** and there are some simple things we can compute
**[10:19]** to give you guidance on whether you need to
**[10:21]** work on improving your search algorithm.
**[10:24]** Let's talk about that in the next video.
