---
type: video-transcript
specialization: Machine Learning Specialization
course: Supervised Machine Learning: Regression and Classification
week: 2
section: Multiple linear regression
item_title: Multiple features
duration: 10 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/gFuSx/multiple-features
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Multiple features — Transcript

**[0:01]** Welcome back. In this week,
**[0:04]** we'll learn to make linear regression
**[0:05]** much faster and much more powerful,
**[0:08]** and by the end of this week,
**[0:10]** you'll be two thirds of the way
**[0:11]** to finishing this first course.
**[0:13]** Let's start by looking at the version of
**[0:16]** linear regression that look at not just one feature,
**[0:19]** but a lot of different features. Let's take a look.
**[0:22]** In the original version of linear regression,
**[0:26]** you had a single feature x,
**[0:29]** the size of the house and you're able to predict y,
**[0:33]** the price of the house.
**[0:35]** The model was fwb of x equals wx plus b.
**[0:43]** But now, what if you did not only have the size of
**[0:46]** the house as a feature with
**[0:47]** which to try to predict the price,
**[0:49]** but if you also knew the number of bedrooms,
**[0:53]** the number of floors and the age of the home in years.
**[0:56]** It seems like this would give you
**[0:58]** a lot more information with which to predict the price.
**[1:01]** To introduce a little bit of new notation,
**[1:04]** we're going to use the variables X_1,
**[1:07]** X_2, X_3 and X_4,
**[1:12]** to denote the four features.
**[1:14]** For simplicity, let's introduce
**[1:16]** a little bit more notation.
**[1:18]** We'll write X subscript j
**[1:20]** or sometimes I'll just say for short,
**[1:23]** X sub j, to represent the list of features.
**[1:26]** Here, j will go from one to four,
**[1:29]** because we have four features.
**[1:31]** I'm going to use lowercase
**[1:33]** n to denote the total number of features,
**[1:37]** so in this example,
**[1:38]** n is equal to 4.
**[1:40]** As before, we'll use X superscript
**[1:43]** i to denote the ith training example.
**[1:48]** Here X superscript i is actually
**[1:51]** going to be a list of four numbers,
**[1:55]** or sometimes we'll call this a vector that
**[1:59]** includes all the features of the ith training example.
**[2:04]** As a concrete example,
**[2:07]** X superscript in parentheses 2,
**[2:10]** will be a vector of
**[2:11]** the features for the second training example,
**[2:14]** so it will equal to this 1416, 3,
**[2:18]** 2 and 40 and technically,
**[2:21]** I'm writing these numbers in a row,
**[2:23]** so sometimes this is called
**[2:25]** a row vector rather than a column vector.
**[2:28]** But if you don't know what the difference is,
**[2:30]** don't worry about it, it's
**[2:31]** not that important for this purpose.
**[2:34]** To refer to a specific feature
**[2:38]** in the ith training example,
**[2:40]** I will write X superscript i, subscript j,
**[2:45]** so for example, X superscript 2 subscript
**[2:49]** 3 will be the value of the third feature,
**[2:53]** that is the number of floors in
**[2:55]** the second training example and
**[2:57]** so that's going to be equal to 2.
**[3:00]** Sometimes in order to emphasize that this X^2
**[3:04]** is not a number but is
**[3:06]** actually a list of numbers that is a vector,
**[3:08]** we'll draw an arrow on top of that just to
**[3:12]** visually show that is a vector and over here as well,
**[3:17]** but you don't have to draw this arrow in your notation.
**[3:21]** You can think of the arrow as an optional signifier.
**[3:25]** They're sometimes used just to
**[3:27]** emphasize that this is a vector and not a number.
**[3:30]** Now that we have multiple features,
**[3:32]** let's take a look at what a model would look like.
**[3:36]** Previously, this is how we defined the model,
**[3:39]** where X was a single feature,
**[3:41]** so a single number.
**[3:42]** But now with multiple features,
**[3:45]** we're going to define it differently.
**[3:47]** Instead, the model will be,
**[3:51]** fwb of X equals w1x1
**[3:55]** plus w2x2 plus w3x3 plus w4x4 plus b.
**[4:01]** Concretely for housing price prediction,
**[4:05]** one possible model may be that we estimate the price
**[4:10]** of the house as 0.1 times X_1, the size of the house,
**[4:14]** plus four times X_2,
**[4:18]** the number of bedrooms,
**[4:19]** plus ten times X_3, the number of floors,
**[4:22]** minus 2 times X_4,
**[4:24]** the age of the house in years plus 80.
**[4:27]** Let's think a bit about how you
**[4:29]** might interpret these parameters.
**[4:31]** If the model is trying to predict
**[4:33]** the price of the house in thousands of dollars,
**[4:36]** you can think of this b equals 80 as
**[4:40]** saying that the base price of a house
**[4:42]** starts off at maybe $80,000,
**[4:45]** assuming it has no size,
**[4:46]** no bedrooms, no floor and no age.
**[4:49]** You can think of this 0.1 as saying
**[4:52]** that maybe for every additional square foot,
**[4:55]** the price will increase by 0.1 $1,000 or by $100,
**[5:01]** because we're saying that for each square foot,
**[5:04]** the price increases by 0.1,
**[5:07]** times $1,000, which is $100.
**[5:11]** Maybe for each additional bathroom,
**[5:15]** the price increases by
**[5:16]** $4,000 and for each additional floor
**[5:20]** the price may increase by
**[5:21]** $10,000 and for each additional year of the house's age,
**[5:25]** the price may decrease by $2,000,
**[5:28]** because the parameter is negative 2.
**[5:31]** In general, if you have n features,
**[5:35]** then the model will look like this.
**[5:39]** Here again is the definition
**[5:42]** of the model with n features.
**[5:44]** What we're going to do next is
**[5:46]** introduce a little bit of notation
**[5:48]** to rewrite this expression in
**[5:50]** a simpler but equivalent way.
**[5:52]** Let's define W as a list of
**[5:54]** numbers that list the parameters W_1,
**[5:58]** W_2, W_3,
**[5:59]** all the way through W_n.
**[6:01]** In mathematics, this is called a vector
**[6:04]** and sometimes to designate that this is a vector,
**[6:08]** which just means a list of numbers,
**[6:10]** I'm going to draw a little arrow on top.
**[6:12]** You don't always have to draw this arrow
**[6:15]** and you can do so or not in your own notation,
**[6:19]** so you can think of this little arrow as
**[6:21]** just an optional signifier
**[6:23]** to remind us that this is a vector.
**[6:26]** If you've taken the linear algebra class before,
**[6:29]** you might recognize that this is
**[6:31]** a row vector as opposed to a column vector.
**[6:34]** But if you don't know what those terms means,
**[6:36]** you don't need to worry about it.
**[6:38]** Next, same as before,
**[6:39]** b is a single number and not a vector and so this vector
**[6:45]** W together with this number b
**[6:47]** are the parameters of the model.
**[6:51]** Let me also write X as a list or a vector,
**[6:57]** again a row vector that
**[6:59]** lists all of the features X_1, X_2,
**[7:02]** X_3 up to X_n,
**[7:04]** this is again a vector,
**[7:07]** so I'm going to add a little arrow up on top to signify.
**[7:13]** In the notation up on top,
**[7:16]** we can also add little arrows here and here
**[7:20]** to signify that that W and that X
**[7:23]** are actually these lists of numbers,
**[7:26]** that they're actually these vectors.
**[7:29]** With this notation, the model can now be rewritten more
**[7:34]** succinctly as f of x equals,
**[7:39]** the vector w dot and this dot refers to
**[7:43]** a dot product from linear algebra of X the vector,
**[7:48]** plus the number b.
**[7:50]** What is this dot product thing?
**[7:53]** Well, the dot products of
**[7:55]** two vectors of two lists of numbers W and X,
**[7:59]** is computed by checking
**[8:02]** the corresponding pairs of numbers,
**[8:05]** W_1 and X_1 multiplying that,
**[8:09]** W_2 X_2 multiplying that,
**[8:12]** W_3 X_3 multiplying that,
**[8:15]** all the way up to W_n and X_n multiplying
**[8:19]** that and then summing up all of these products.
**[8:23]** Writing that out,
**[8:25]** this means that the dot products is equal to W_1X_1 plus
**[8:32]** W_2X_2 plus W_3X_3 plus all the way up to W_nX_n.
**[8:41]** Then finally we add back in the b on top.
**[8:46]** You notice that this gives us
**[8:49]** exactly the same expression as we had on top.
**[8:53]** The dot traffic notation lets you write the model in
**[8:57]** a more compact form with fewer characters.
**[9:01]** The name for this type of linear regression model with
**[9:04]** multiple input features is multiple linear regression.
**[9:08]** This is in contrast to univariate regression,
**[9:11]** which has just one feature.
**[9:13]** By the way, you might think
**[9:15]** this algorithm is called multivariate regression,
**[9:18]** but that term actually refers to something
**[9:20]** else that we won't be using here.
**[9:23]** I'm going to refer to this model
**[9:24]** as multiple linear regression.
**[9:27]** That's it for linear regression with multiple features,
**[9:31]** which is also called multiple linear regression.
**[9:34]** In order to implement this,
**[9:36]** there's a really neat trick called vectorization,
**[9:39]** which will make it much simpler to implement
**[9:42]** this and many other learning algorithms.
**[9:44]** Let's go on to the next video to take
**[9:47]** a look at what is vectorization.
