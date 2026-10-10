---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 2
section: Logistic Regression as a Neural Network
item_title: Derivatives with a Computation Graph
duration: 15 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/0VSHe/derivatives-with-a-computation-graph
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Derivatives with a Computation Graph — Transcript

**[0:00]** In the last video,
**[0:01]** we worked through an example of using a computation graph to compute a function J.
**[0:06]** Now, let's take a cleaned up version of that computation graph
**[0:09]** and show how you can use it to figure out derivative calculations for
**[0:13]** that function J.
**[0:15]** So here's a computation graph.
**[0:17]** Let's say you want to compute the derivative of J with respect to v.
**[0:23]** So what is that?
**[0:24]** Well, this says, if we were to take this value of v and
**[0:27]** change it a little bit, how would the value of J change?
**[0:32]** Well, J is defined as 3 times v.
**[0:37]** And right now, v = 11.
**[0:42]** So if we're to bump up v by a little bit to 11.001,
**[0:48]** then J, which is 3v, so currently 33,
**[0:52]** will get bumped up to 33.003.
**[0:56]** So here, we've increased v by 0.001.
**[0:59]** And the net result of that is that J goes up 3 times as much.
**[1:03]** So the derivative of J with respect to v is equal to 3.
**[1:08]** Because the increase in J is 3 times the increase in v.
**[1:12]** And in fact, this is very analogous to the example
**[1:18]** we had in the previous video, where we had f(a) = 3a.
**[1:24]** And so we then derived that df/da, which with slightly simplified,
**[1:30]** a slightly sloppy notation, you can write as df/da = 3.
**[1:36]** So instead, here we have J = 3v,
**[1:41]** and so dJ/dv = 3.
**[1:44]** With here, J playing the role of f, and
**[1:51]** v playing the role of a in this previous example that we had from an earlier video.
**[1:58]** So indeed, terminology of backpropagation, what we're seeing
**[2:03]** is that if you want to compute the derivative of this final output variable,
**[2:09]** which usually is a variable you care most about,
**[2:13]** with respect to v, then we've done one step of backpropagation.
**[2:18]** So we call it one step backwards in this graph.
**[2:22]** Now let's look at another example.
**[2:24]** What is dJ/da?
**[2:28]** In other words, if we bump up the value of a, how does that affect the value of J?
**[2:35]** Well, let's go through the example, where now a = 5.
**[2:39]** So let's bump it up to 5.001.
**[2:42]** The net impact of that is that v, which was a + u, so that was previously 11.
**[2:48]** This would get increased to 11.001.
**[2:52]** And then we've already seen as above that
**[2:57]** J now gets bumped up to 33.003.
**[3:01]** So what we're seeing is that if you increase a by 0.001, J increases by 0.003.
**[3:07]** And by increase a, I mean, you have to take this value of 5 and
**[3:11]** just plug in a new value.
**[3:14]** Then the change to a will propagate to the right of the computation graph so
**[3:17]** that J ends up being 33.003.
**[3:19]** And so the increase to J is 3 times the increase to a.
**[3:28]** So that means this derivative is equal to 3.
**[3:31]** And one way to break this down is to say that if you change a,
**[3:37]** then that will change v.
**[3:40]** And through changing v, that would change J.
**[3:43]** And so the net change to the value of J when you bump up the value,
**[3:49]** when you nudge the value of a up a little bit, is that,
**[3:57]** First, by changing a, you end up increasing v.
**[4:02]** Well, how much does v increase?
**[4:05]** It is increased by an amount that's determined by dv/da.
**[4:11]** And then the change in v will cause the value of J to also increase.
**[4:19]** So in calculus, this is actually called the chain rule that if a affects v,
**[4:27]** affects J, then the amounts that J changes when you
**[4:32]** nudge a is the product of how much v changes when you
**[4:36]** nudge a times how much J changes when you nudge v.
**[4:42]** So in calculus, again, this is called the chain rule.
**[4:46]** And what we saw from this calculation is that if you increase a by 0.001,
**[4:52]** v changes by the same amount.
**[4:55]** So dv/da = 1.
**[4:59]** So in fact, if you plug in what we have wrapped up previously,
**[5:07]** dv/dJ = 3 and dv/da = 1.
**[5:11]** So the product of these 3 times 1,
**[5:14]** that actually gives you the correct value that dJ/da = 3.
**[5:18]** So this little illustration shows hows by having computed dJ/dv,
**[5:24]** that is, derivative with respect to this variable,
**[5:30]** it can then help you to compute dJ/da.
**[5:34]** And so that's another step of this backward calculation.
**[5:39]** I just want to introduce one more new notational convention.
**[5:44]** Which is that when you're witting codes to implement backpropagation,
**[5:50]** there will usually be some final output variable that you really care about.
**[5:54]** So a final output variable that you really care about or that you want to optimize.
**[6:01]** And in this case, this final output variable is J.
**[6:04]** It's really the last node in your computation graph.
**[6:07]** And so a lot of computations will be trying to compute the derivative of that
**[6:11]** final output variable.
**[6:13]** So d of this final output variable with respect to some other variable.
**[6:17]** Then we just call that dvar.
**[6:23]** So a lot of the computations you have will be to compute the derivative of the final
**[6:27]** output variable, J in this case, with various intermediate variables,
**[6:32]** such as a, b, c, u or v.
**[6:34]** And when you implement this in software, what do you call this variable name?
**[6:41]** One thing you could do is in Python,
**[6:44]** you could give us a very long variable name like dFinalOurputVar/dvar.
**[6:50]** But that's a very long variable name.
**[6:51]** You could call this, I guess, dJdvar.
**[6:55]** But because you're always taking derivatives with respect to dJ, with
**[6:58]** respect to this final output variable, I'm going to introduce a new notation.
**[7:03]** Where, in code, when you're computing this thing in the code you write,
**[7:09]** we're just going to use the variable name dvar in order to represent that quantity.
**[7:16]** So dvar in a code you write will represent the derivative of
**[7:21]** the final output variable you care about such as J.
**[7:25]** Well, sometimes, the last l with respect to the various intermediate quantities
**[7:29]** you're computing in your code.
**[7:31]** So this thing here in your code, you use dv to denote this value.
**[7:38]** So dv would be equal to 3.
**[7:42]** And your code, you represent this as da,
**[7:46]** which is we also figured out to be equal to 3.
**[7:51]** So we've done backpropagation partially through this computation graph.
**[7:58]** Let's go through the rest of this example on the next slide.
**[8:02]** So let's go to a cleaned up copy of the computation graph.
**[8:06]** And just to recap, what we've done so
**[8:09]** far is go backward here and figured out that dv = 3.
**[8:14]** And again, the definition of dv, that's just a variable name,
**[8:18]** where the code is really dJ/dv.
**[8:20]** We've figured out that da = 3.
**[8:24]** And again, da is the variable name in your code and that's really the value dJ/da.
**[8:32]** And we hand wave how we've gone backwards on these two edges like so.
**[8:39]** Now let's keep computing derivatives.
**[8:41]** Now let's look at the value u.
**[8:44]** So what is dJ/du?
**[8:47]** Well, through a similar calculation as what we did before and
**[8:52]** then we start off with u = 6.
**[8:54]** If you bump up u to 6.001, then v,
**[8:57]** which is previously 11, goes up to 11.001.
**[9:02]** And so J goes from 33 to 33.003.
**[9:07]** And so the increase in J is 3x, so this is equal.
**[9:12]** And the analysis for u is very similar to the analysis we did for a.
**[9:16]** This is actually computed as dJ/dv times dv/du,
**[9:23]** where this we had already figured out was 3.
**[9:30]** And this turns out to be equal to 1.
**[9:33]** So we've gone up one more step of backpropagation.
**[9:36]** We end up computing that du is also equal to 3.
**[9:42]** And du is, of course, just this dJ/du.
**[9:47]** Now we just step through one last example in detail.
**[9:51]** So what is dJ/db?
**[9:54]** So here, imagine if you are allowed to change the value of b.
**[9:57]** And you want to tweak b a little bit in order to minimize or
**[10:01]** maximize the value of J.
**[10:04]** So what is the derivative or
**[10:05]** what's the slope of this function J when you change the value of b a little bit?
**[10:11]** It turns out that using the chain rule for calculus,
**[10:15]** this can be written as the product of two things.
**[10:18]** This dJ/du times du/db.
**[10:24]** And the reasoning is if you change b a little bit,
**[10:30]** so b = 3 to, say, 3.001.
**[10:34]** The way that it will affect J is it will first affect u.
**[10:38]** So how much does it affect u?
**[10:40]** Well, u is defined as b times c.
**[10:44]** So this will go from 6,
**[10:48]** when b = 3, to now 6.002
**[10:53]** because c = 2 in our example here.
**[10:59]** And so this tells us that du/db = 2.
**[11:05]** Because when you bump up b by 0.001, u increases twice as much.
**[11:10]** So du/db, this is equal to 2.
**[11:15]** And now, we know that u has gone up twice as much as b has gone up.
**[11:21]** Well, what is dJ/du?
**[11:24]** We've already figured out that this is equal to 3.
**[11:27]** And so by multiplying these two out, we find that dJ/db = 6.
**[11:32]** And again, here's the reasoning for the second part of the argument.
**[11:36]** Which is we want to know when u goes up by 0.002, how does that affect J?
**[11:43]** The fact that dJ/du = 3, that tells us that when
**[11:48]** u goes up by 0.002, J goes up 3 times as much.
**[11:54]** So J should go up by 0.006.
**[11:59]** So this comes from the fact that dJ/du = 3.
**[12:05]** And if you check the math in detail,
**[12:09]** you will find that if b becomes 3.001,
**[12:13]** then u becomes 6.002, v becomes 11.002.
**[12:20]** So that's a + u, so that's 5 + u.
**[12:24]** And then J, which is equal to 3 times v,
**[12:28]** that ends up being equal to 33.006.
**[12:33]** And so that's how you get that dJ/db = 6.
**[12:37]** And to fill that in, this is if we go backwards, so this is db = 6.
**[12:43]** And db really is the Python code variable name for dJ/db.
**[12:50]** And I won't go through the last example in great detail.
**[12:53]** But it turns out that if you also compute out dJ,
**[13:00]** this turns out to be dJ/du times du.
**[13:05]** And this turns out to be 9, this turns out to be 3 times 3.
**[13:09]** I won't go through that example in detail.
**[13:11]** So through this last step, it is possible to derive that dc is equal to.
**[13:20]** So the key takeaway from this video, from this example, is that when computing
**[13:24]** derivatives and computing all of these derivatives, the most efficient way to do
**[13:29]** so is through a right to left computation following the direction of the red arrows.
**[13:34]** And in particular, we'll first compute the derivative with respect to v.
**[13:37]** And then that becomes useful for
**[13:40]** computing the derivative with respect to a and the derivative with respect to u.
**[13:45]** And then the derivative with respect to u, for
**[13:48]** example, this term over here and this term over here.
**[13:52]** Those in turn become useful for computing the derivative with respect to b and
**[13:55]** the derivative with respect to c.
**[13:57]** So that was the computation graph and how does a forward or left to right
**[14:02]** calculation to compute the cost function such as J that you might want to optimize.
**[14:07]** And a backwards or a right to left calculation to compute derivatives.
**[14:12]** If you're not familiar with calculus or the chain rule,
**[14:15]** I know some of those details, but they've gone by really quickly.
**[14:18]** But if you didn't follow all the details, don't worry about it.
**[14:21]** In the next video,
**[14:22]** we'll go over this again in the context of logistic regression.
**[14:26]** And show you exactly what you need to do in order to implement the computations you
**[14:30]** need to compute the derivatives of the logistic regression model.
