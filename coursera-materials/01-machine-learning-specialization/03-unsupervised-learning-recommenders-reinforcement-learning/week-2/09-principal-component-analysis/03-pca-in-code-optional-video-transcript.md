---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 2
section: Principal Component Analysis
item_title: PCA in code (optional)
duration: 11 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/2C2KO/pca-in-code-optional
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# PCA in code (optional) — Transcript

**[0:01]** In this video, we'll take a look at how you can use the
**[0:05]** scikit-learn library to implement PCA.
**[0:08]** These are the main steps.
**[0:10]** First, if your features take
**[0:13]** on very different ranges of values,
**[0:15]** you can perform pre-processing to
**[0:19]** scale the features to take on
**[0:20]** comparable ranges of values.
**[0:23]** If you were looking
**[0:25]** at the features of different countries,
**[0:27]** those features take on very different ranges of values.
**[0:31]** GDP could be in trillions of dollars,
**[0:33]** whereas other features are less than 100.
**[0:37]** Feature scaling in applications like that would be
**[0:40]** important to help PCA find a good choice of axes for you.
**[0:45]** The next step then is to run the PCA algorithm to
**[0:49]** "fit" the data to obtain two or three new axes,
**[0:55]** Z_1, Z_2, and maybe Z_3.
**[0:58]** Here I'm assuming you want
**[1:00]** two or three axes if you
**[1:02]** want to visualize the data in 2D or 3D.
**[1:06]** If you have an application where you
**[1:07]** want more than two or three axes,
**[1:10]** the PCA implementation can
**[1:12]** also give you more than two or three axes,
**[1:14]** it's just that it'd then be harder to visualize.
**[1:17]** In scikit-learn, you will use the fit function,
**[1:21]** or the fit method in order to do this.
**[1:23]** The fit function in PCA
**[1:25]** automatically carries out mean normalization,
**[1:29]** it subtracts out the mean of each feature.
**[1:32]** So you don't need to
**[1:33]** separately perform mean normalization.
**[1:37]** After running the fit function,
**[1:40]** you would get the new axes, Z_1,
**[1:42]** Z_2, maybe Z_3, and in PCA,
**[1:46]** we also call these the principal components,
**[1:48]** where Z_1 is the first principal component,
**[1:50]** Z_2 the second principal component,
**[1:52]** and Z_3 the third principal component.
**[1:56]** After that, I would recommend taking
**[1:59]** a look at how much each of these new axes,
**[2:02]** or each of these new principal components
**[2:04]** explains the variance in your data.
**[2:07]** I'll show a concrete example of
**[2:08]** what this means on the next slide,
**[2:10]** but this lets you get
**[2:12]** a sense of whether or not projecting
**[2:15]** the data onto these axes help
**[2:17]** you to retain most of the variability,
**[2:21]** or most of the information in the original dataset.
**[2:24]** This is done using the explained variance ratio function.
**[2:28]** Finally, you can transform,
**[2:31]** meaning just project the data onto the new axes,
**[2:34]** onto the new principal components,
**[2:35]** which you will do with the transform method.
**[2:38]** Then for each training example,
**[2:40]** you would just have two or three numbers,
**[2:42]** you can then plot those two or three numbers
**[2:45]** to visualize your data.
**[2:47]** In detail, this is what PCA in code looks like.
**[2:51]** Here's the dataset X with six examples.
**[2:56]** X equals NumPy array,
**[2:58]** the six examples over here.
**[3:01]** To run PCA to reduce this data from two numbers, X_1,
**[3:07]** X_2 to just one number Z,
**[3:09]** you would run PCA and ask it
**[3:13]** to fit one principal component.
**[3:16]** N components here is equal to one,
**[3:19]** and fit PCA to X. Pca_1
**[3:23]** here is my notation
**[3:26]** for PCA with a single principle component,
**[3:29]** with a single axis.
**[3:31]** It turns out, if you were to print out
**[3:34]** pca_1.explained_variance_ratio, this is 0.992.
**[3:40]** This tells you that in this example
**[3:42]** when you choose one axis,
**[3:45]** this captures 99.2 percent
**[3:48]** of the variability or of
**[3:50]** the information in the original dataset.
**[3:52]** Finally, if you want to take each of
**[3:55]** these training samples and project it to a single number,
**[4:00]** you would then call this,
**[4:02]** and this will output this array with
**[4:05]** six numbers corresponding to your six training examples.
**[4:10]** For example, the first training example 1,1,
**[4:14]** projected to the Z-axis gives you
**[4:17]** this number, 1.383, so on.
**[4:20]** So if you were to visualize
**[4:23]** this dataset using just one dimension,
**[4:26]** this will be the number I
**[4:27]** use to represent the first example.
**[4:29]** The second example is projected
**[4:32]** to be this number and so on.
**[4:35]** I hope you take a look at the optional
**[4:37]** lab where you see that
**[4:38]** these six examples have been projected
**[4:40]** down onto this axis,
**[4:43]** onto this line which is now Y.
**[4:45]** All six examples now lie
**[4:47]** on this line that looks like this.
**[4:50]** The first training example,
**[4:53]** which was 1,1,
**[4:55]** has been mapped to this example,
**[4:57]** which has a distance of 1.38 from the origin,
**[5:01]** so that's why this is 1.38.
**[5:04]** Just one more quick example.
**[5:07]** This data is two-dimensional data,
**[5:10]** and we reduced it to one dimensions.
**[5:13]** What if you were to compute two principal components?
**[5:17]** Starts with two-dimensions,
**[5:19]** and then also end up with two-dimensions.
**[5:22]** This isn't that useful for
**[5:23]** visualization but it might help us understand
**[5:25]** better how PCA and how they code for PCA works.
**[5:30]** Here's the same code except that I've
**[5:32]** changed n components to two.
**[5:34]** I'm going to ask the algorithm to
**[5:36]** find two principal components.
**[5:39]** If you do that the pca_2 explain
**[5:42]** ratio becomes 0.992, 0.008.
**[5:47]** What that means is that z_1,
**[5:49]** the first principle components,
**[5:50]** still continuous explain 99.2 percent of the variance,
**[5:54]** Z_2 the second principle components,
**[5:57]** or the second axis,
**[5:58]** explains 0.8 percent of the variance.
**[6:02]** These two numbers together add up to one.
**[6:05]** Because while this data is two-dimensional,
**[6:08]** so the two axes,
**[6:09]** Z_1 and Z_2,
**[6:10]** together they explain 100 percent
**[6:12]** of the variance in the data.
**[6:14]** If you were to transform our project
**[6:16]** the data onto the Z_1 and Z_2 axes,
**[6:19]** this is what you get,
**[6:21]** with now the first training example is
**[6:24]** napped too these two numbers,
**[6:27]** corresponding to its projection onto z_1,
**[6:30]** and z_2, and the second example,
**[6:34]** which is this projected onto z_1 and z_2,
**[6:37]** becomes these two numbers.
**[6:40]** If you were to reconstruct
**[6:43]** the original data roughly this is z_1,
**[6:46]** and this z_2,
**[6:48]** then the first training example which was a [1,
**[6:51]** 1] has a distance of 1.38 on the z_1 axis,
**[6:57]** has this number and the distance here of
**[7:01]** 0.29 hence this distance on the z_2 axis,
**[7:05]** and the reconstruction actually looks
**[7:07]** exactly the same as the original data.
**[7:09]** Because, if you reduce or not really
**[7:12]** reduce two-dimensional data to two-dimensional data,
**[7:15]** there is no approximation
**[7:18]** and you can get back to your original dataset,
**[7:20]** with the projections onto z_1 and z_2.
**[7:24]** This is what the code to run PCA looks like.
**[7:27]** I hope you take a look at
**[7:29]** the optional lab where you can
**[7:30]** play with this more yourself.
**[7:31]** Also try varying the parameters look at
**[7:35]** a specific example to deepen
**[7:37]** your intuition about how PCA works.
**[7:40]** Before wrapping up, I'd like to share
**[7:43]** a little bit of advice for applying PCA.
**[7:45]** PCA is frequently used for visualization where you reduce
**[7:48]** data to two or three numbers so you can plot it.
**[7:53]** Like you saw in an earlier video with the data
**[7:55]** on different countries so you
**[7:56]** can visualize different countries.
**[7:58]** There are some other applications of
**[8:01]** PCA that you may occasionally hear about.
**[8:03]** That used to be more popular,
**[8:06]** maybe 10,15, 20 years ago but much less so now.
**[8:10]** Another possible use of PCA is data compression.
**[8:13]** For example, if you have
**[8:15]** a database of lots of different cars,
**[8:18]** and you have 50 features per car,
**[8:21]** but it's just taking up too much space on
**[8:24]** your database or maybe
**[8:25]** transmitting 50 numbers over the Internet,
**[8:28]** just takes too long.
**[8:30]** Then one thing you could do is reduce
**[8:32]** these 50 features to a smaller number of features.
**[8:36]** It could be 10 features with
**[8:39]** 10 axes or 10 principal components.
**[8:42]** You can visualize 10-dimensional data that easily,
**[8:45]** but this is 1/5 of the storage space,
**[8:48]** or maybe 1/5 over the network transmission costs needed.
**[8:52]** Many years ago I saw
**[8:54]** PCA use for this application and more often,
**[8:57]** but today with modern storage
**[9:01]** being able to store pretty large datasets
**[9:03]** and modern networking,
**[9:04]** able to transmit faster and more data than ever before.
**[9:08]** I see this use much less often as an application of PCA.
**[9:12]** One of the applications of PCA that again
**[9:15]** used to be more common maybe 10 years ago,
**[9:17]** 20 years ago, but much less so now is
**[9:20]** using it to speed up
**[9:21]** training of a supervised learning model.
**[9:23]** Where the idea is,
**[9:25]** if you had 1,000 features,
**[9:27]** and having a 1,000 features may
**[9:29]** the supervised learning algorithm runs too slowly.
**[9:32]** Maybe you can reduce it to 100 features using PCA
**[9:37]** and then your dataset is basically smaller and
**[9:39]** your supervised learning algorithm may run faster.
**[9:42]** This used to make a difference in the running time
**[9:45]** of some of the older generations of learning algorithms,
**[9:49]** such as if you have had a support vector machines.
**[9:52]** This will speed up a support vector machine.
**[9:54]** But it turns out with modern machine learning algorithms,
**[9:57]** algorithms like deep learning,
**[9:59]** this doesn't actually help that much,
**[10:02]** and is much more common to
**[10:04]** just take the high-dimensional dataset,
**[10:06]** and feed it into say your neural network.
**[10:09]** Rather than run PCA because
**[10:11]** PCA has some computational cost as well.
**[10:14]** You may hear about this in some
**[10:17]** of the older research papers,
**[10:19]** but I don't really see this done much anymore.
**[10:22]** But the most common thing that I use
**[10:24]** PCA for today is visualization and then I
**[10:26]** find it very useful to reduce
**[10:28]** the dimensional data to visualize it.
**[10:30]** Thanks for sticking with me through
**[10:33]** the end of the optional videos for this week,
**[10:36]** I hope you enjoy learning about
**[10:38]** PCA and that you find a useful when
**[10:41]** you get a new dataset for reducing
**[10:43]** the dimension of the dataset to two or three dimensions
**[10:46]** so you can visualize it and hopefully
**[10:48]** gain new insights into your data sets.
**[10:51]** There's helped me many times
**[10:52]** understand my own datasets and I
**[10:54]** hope that you find it equally useful as well.
**[10:58]** Thanks for watching these videos and I
**[11:01]** look forward to seeing you next week.
