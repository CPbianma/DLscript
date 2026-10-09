---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 3
section: Shallow Neural Network
item_title: Backpropagation Intuition (Optional)
duration: 16 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/6dDj7/backpropagation-intuition-optional
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Backpropagation Intuition (Optional) — Transcript

**[0:00]** In the last video, you saw
**[0:01]** the equations for back-propagation.
**[0:03]** In this video, let's go over some intuition using
**[0:06]** the computation graph for
**[0:08]** how those equations were derived.
**[0:10]** This video is completely optional
**[0:12]** so feel free to watch it or not.
**[0:14]** You should be able to do the whole works either way.
**[0:16]** Recall that when we talked about logistic regression,
**[0:19]** we had this forward pass where we compute z, then A,
**[0:24]** and then A loss and the to take derivatives we
**[0:27]** had this backward pass where we can
**[0:30]** first compute da and then go on to compute dz,
**[0:35]** and then go on to compute dw and db.
**[0:40]** The definition for the loss was L of a comma y equals
**[0:48]** negative y log A minus 1 minus y times log 1 minus A.
**[0:57]** If you're familiar with
**[0:59]** calculus and you take the derivative of
**[1:01]** this with respect to A
**[1:03]** that will give you the formula for da.
**[1:06]** So da is equal to that.
**[1:08]** If you actually figure out the calculus,
**[1:11]** you can show that this is
**[1:13]** negative y over A plus 1 minus y over one minus A.
**[1:19]** Just kind of derived that from
**[1:20]** calculus by taking derivatives of this.
**[1:22]** It turns out when you take
**[1:24]** another step backwards to compute dz,
**[1:26]** we then worked out that dz is equal to A
**[1:29]** minus y. I didn't explain why previously,
**[1:32]** but it turns out that from the chain rule of calculus,
**[1:36]** dz is equal to da times g prime of z.
**[1:44]** Where here g of z equals sigmoid of
**[1:49]** z as our activation function
**[1:52]** for this output unit in logistic regression.
**[1:55]** Just remember, this is still logistic regression,
**[1:59]** will have X_1, X_2,
**[2:00]** X_3, and then just one sigmoid unit,
**[2:03]** and then that gives us a, gives us y hat.
**[2:07]** Here the activation function was sigmoid function.
**[2:11]** As an aside, only for those of you familiar
**[2:14]** with the chain rule of calculus.
**[2:17]** The reason for this is
**[2:18]** because a is equal to sigmoid of z,
**[2:22]** and so partial of L with respect
**[2:25]** to z is equal to partial of
**[2:29]** L with respect to a times da, dz.
**[2:36]** Since A is equal to sigmoid of z.
**[2:39]** This is equal to d,
**[2:41]** dz g of z,
**[2:45]** which is equal to g prime of z.
**[2:48]** That's why this expression,
**[2:51]** which is dz in our code is equal to this expression,
**[2:55]** which is da in our code times g prime of z
**[2:59]** and so this just that.
**[3:05]** That last derivation would have made sense only if you're
**[3:09]** familiar with calculus and
**[3:11]** specifically the chain rule from calculus.
**[3:13]** But if not, don't worry about it,
**[3:15]** I'll try to explain the intuition wherever it's needed.
**[3:18]** Then finally, having computed dz for logistic regression,
**[3:22]** we will compute dw,
**[3:24]** which it turned out was dz times x and
**[3:27]** db which is just
**[3:29]** dz where you have a single training example.
**[3:31]** That was logistic regression.
**[3:33]** What we're going to do when computing
**[3:36]** back-propagation for a neural network
**[3:38]** is a calculation a lot like this,
**[3:40]** but only we'll do it twice.
**[3:42]** Because now we have not x going to an output unit,
**[3:47]** but x going to a hidden layer
**[3:49]** and then going to an output unit.
**[3:51]** Instead of this computation
**[3:54]** being one step as we have here,
**[3:58]** we'll have two steps here
**[4:00]** in this neural network with two layers.
**[4:04]** In this two-layer neural network,
**[4:07]** that is with the input layer,
**[4:08]** hidden layer, and an output layer.
**[4:10]** Remember the steps of a computation.
**[4:12]** First, you compute z_1
**[4:15]** using this equation and then compute a_1,
**[4:19]** and then you compute z_2.
**[4:21]** Notice z_2 also depends on the parameters W_2 and b_2,
**[4:25]** and then based on z_2 you compute a_2.
**[4:28]** Then finally, that gives you the loss.
**[4:32]** What back-propagation does, is it will go backward to
**[4:37]** compute da_2 and then dz_2,
**[4:42]** then go back to compute dW_2 and db_2.
**[4:48]** Go back to compute da_1,
**[4:53]** dz_1, and so on.
**[4:57]** We don't need to take
**[4:59]** derivatives with respect to the input x,
**[5:00]** since input x for supervised learning because
**[5:04]** We're not trying to optimize x,
**[5:05]** so we won't bother to take derivatives,
**[5:07]** at least for supervised learning with respect to
**[5:10]** x. I'm going to skip explicitly computing da.
**[5:16]** If you want, you can actually compute da^2,
**[5:18]** and then use that to compute dz^2.
**[5:20]** But in practice, you could collapse both of
**[5:22]** these steps into one step.
**[5:25]** You end up that dz^2 is equal to a^2 minus y,
**[5:30]** same as before, and you have also going to
**[5:34]** write dw^2 and db^2 down here below.
**[5:38]** You have that dw^2 is equal to dz^2 times a^1 transpose,
**[5:47]** and db^2 equals dz^2.
**[5:51]** This step is quite similar for logistic regression,
**[5:55]** where we had that dw was equal to dz times x,
**[6:01]** except that now, a^1 plays the role of x,
**[6:05]** and there's an extra transpose there.
**[6:08]** Because the relationship between
**[6:10]** the capital matrix W
**[6:12]** and our individual parameters w was,
**[6:14]** there's a transpose there,
**[6:16]** because w is equal to a row vector.
**[6:21]** In the case of logistic regression
**[6:23]** with the single output,
**[6:25]** dw^2 is like that, whereas w here was a column vector.
**[6:28]** That's why there's an extra transpose for a^1,
**[6:32]** whereas we didn't for x here for logistic regression.
**[6:36]** This completes half of backpropagation.
**[6:40]** Then again, you can compute da^1,
**[6:43]** if you wish although in practice,
**[6:45]** the computation for da^1,
**[6:49]** and dz^1 are usually collapsed into one step.
**[6:52]** What you'd actually implement is that dz^1 is equal to
**[6:56]** w^2 transpose times dz^2 and then,
**[7:02]** times an element-wise product of g^1 prime of z^1.
**[7:11]** Just to do a check on the dimensions.
**[7:13]** If you have a neural network that looks like this,
**[7:20]** outputs y if so.
**[7:22]** If you have n^0 and x equals n^0,
**[7:27]** and for features, n^1 hidden units,
**[7:30]** and n^2 so far,
**[7:32]** and n^2 in our case,
**[7:36]** just one output unit,
**[7:38]** then the matrix w^2 is n^2 by n^1 dimensional,
**[7:49]** z^2, and therefore, dz^2 are going
**[7:53]** to be n^2 by one-dimensional.
**[7:57]** There's really going to be a one by one
**[7:59]** when we're doing binary classification,
**[8:02]** and z^1, and therefore also dz^1
**[8:05]** are going to be n^1 by one-dimensional.
**[8:09]** Note that for any variable,
**[8:12]** foo and dfoo always have the same dimensions.
**[8:16]** That's why, w and dw always have the same dimension.
**[8:20]** Similarly, for b and db,
**[8:22]** and z and dz, and so on.
**[8:23]** To make sure that the dimensions of these all match up,
**[8:26]** we have that dz^1 is equal to w^2 transpose, times dz^2.
**[8:35]** Then, this is an element-wise product times
**[8:41]** g^1 prime of z^1.
**[8:44]** Mashing the dimensions from above,
**[8:46]** this is going to be n^1 by 1,
**[8:50]** is equal to w^2 transpose,
**[8:52]** we transpose of this.
**[8:53]** It is just going to be, n^1 by n^2-dimensional,
**[8:59]** dz^2 is going to be n^2 by one-dimensional.
**[9:04]** Then, this is same dimension as z^.
**[9:07]** This is also, n^1 by
**[9:10]** one-dimensional, so element-wise product.
**[9:12]** The dimensions do make sense.
**[9:14]** N^1 by one-dimensional vector can be
**[9:17]** obtained by n^1 by n^2 dimensional matrix,
**[9:20]** times n^2 by n^1,
**[9:21]** because the product of these two things gives you
**[9:24]** an n^1 by one-dimensional matrix.
**[9:27]** This becomes the element-wise product of 2,
**[9:32]** n^1 by one-dimensional vectors,
**[9:34]** so the dimensions do match up.
**[9:36]** One tip when implementing backprop,
**[9:40]** if you just make sure that the dimensions of
**[9:42]** your matrices match up, if you think through,
**[9:45]** what are the dimensions of
**[9:47]** your various matrices including w^1,
**[9:49]** w^2, z^1, z^2, a^1,
**[9:52]** a^2, and so on,
**[9:53]** and just make sure that
**[9:54]** the dimensions of these matrix operations may match up,
**[9:58]** sometimes that will already
**[10:00]** eliminate quite a lot of bugs in backprop.
**[10:03]** This gives us dz^1. Then finally,
**[10:06]** just to wrap up, dw^1 and db^1,
**[10:11]** we should write them here, I guess.
**[10:13]** But since I'm running out of space,
**[10:15]** I'll write them on the right of the slide,
**[10:17]** dw^1 and db^1 are given by the following formulas.
**[10:21]** This is going to equal to dz^1 times x transpose,
**[10:25]** and this is going to be equal to dz.
**[10:29]** You might notice a similarity between
**[10:31]** these equations and these equations,
**[10:34]** which is really no coincidence,
**[10:35]** because x plays the role of a^0.
**[10:39]** X transpose is a^0 transpose.
**[10:41]** Those equations are actually very similar.
**[10:44]** That gives a sense for how backpropagation is derived.
**[10:50]** We have six key equations here for dz_2,
**[10:54]** dw_2, db_2, dz_1, dw_1, and db_1.
**[11:00]** Let me just take these six equations and
**[11:02]** copy them over to the next slide.
**[11:04]** Here they are. So far we've derived
**[11:07]** that propagation for training
**[11:10]** on a single training example at a time.
**[11:13]** But it should come as no surprise that
**[11:17]** rather than working on a single example at a time,
**[11:21]** we would like to vectorize
**[11:24]** across different training examples.
**[11:27]** You remember that for
**[11:29]** a propagation when we're
**[11:31]** operating on one example at a time,
**[11:33]** we had equations like this,
**[11:35]** as well as say a^1 equals g^1 plus z^1.
**[11:41]** In order to vectorize, we took say,
**[11:45]** the z's and stack them up in columns like this,
**[11:54]** z^1m, and call this capital Z.
**[12:00]** Then we found that by stacking things up in columns
**[12:04]** and defining the capital uppercase version of these,
**[12:10]** we then just had z^1 equals to the w^1x plus
**[12:16]** b and a^1 equals g^1 of z^1.
**[12:25]** We defined the notation very carefully
**[12:26]** in this course to make sure that
**[12:28]** stacking examples into different columns
**[12:32]** of a matrix makes all this workout.
**[12:35]** It turns out that if you go through the math carefully,
**[12:40]** the same trick also works for backpropagation.
**[12:43]** The vectorized equations are as follows.
**[12:46]** First, if you take this dzs for
**[12:50]** different training examples and stack
**[12:52]** them as different columns of a matrix,
**[12:55]** same for this, same for this.
**[12:58]** Then this is the vectorized implementation.
**[13:01]** Here's how you can compute dW^2.
**[13:06]** There is this extra 1 over n
**[13:08]** because the cost function J is
**[13:11]** this 1 over m of the sum from I
**[13:14]** equals 1 through m of the losses.
**[13:18]** When computing derivatives, we
**[13:20]** have that extra 1 over m term,
**[13:22]** just as we did when we were
**[13:23]** computing the weight updates for logistic regression.
**[13:27]** That's the update you get for db^2,
**[13:31]** again, some of the dz's.
**[13:33]** Then, we have 1 over m. Dz^1 is computed as follows.
**[13:40]** Once again, this is an element-wise product only,
**[13:46]** whereas previously, we saw on
**[13:50]** the previous slide that this was
**[13:52]** an n1 by one-dimensional vector.
**[13:56]** No w, this is n1 by m dimensional matrix.
**[14:02]** Both of these are also n1 by m dimensional.
**[14:09]** That's why that asterisk is the element-wise product.
**[14:17]** Finally, the remaining two updates
**[14:21]** perhaps shouldn't look too surprising.
**[14:24]** I hope that gives you some intuition for how
**[14:27]** the backpropagation algorithm is derived.
**[14:30]** In all of machine learning,
**[14:32]** I think the derivation of the backpropagation algorithm
**[14:35]** is actually one of the most
**[14:36]** complicated pieces of math I've seen.
**[14:38]** It requires knowing both linear algebra as well as
**[14:42]** the derivative of matrices to really
**[14:44]** derive it from scratch from first principles.
**[14:46]** If you are an expert in matrix calculus,
**[14:50]** using this process, you
**[14:52]** might want to derive the algorithm yourself.
**[14:54]** But I think that there actually plenty of
**[14:56]** deep learning practitioners that have seen
**[14:59]** the derivation at about the level you've
**[15:01]** seen in this video and are already
**[15:03]** able to have all the right intuitions and be able
**[15:05]** to implement this algorithm very effectively.
**[15:08]** If you are an expert in calculus
**[15:10]** do see if you can derive the whole thing from scratch.
**[15:13]** It is one of the hardest pieces of math on
**[15:15]** the very hardest derivations
**[15:17]** that I've seen in all of machine learning.
**[15:19]** But either way, if you implement this,
**[15:22]** this will work and I think you have
**[15:24]** enough intuitions to tune in and get it to work.
**[15:28]** There's just one last detail,
**[15:30]** my share of you before you implement your neural network,
**[15:34]** which is how to
**[15:35]** initialize the weights of your neural network.
**[15:37]** It turns out that
**[15:38]** initializing your parameters not to zero,
**[15:41]** but randomly turns out to be
**[15:43]** very important for training your neural network.
**[15:45]** In the next video, you'll see why.
