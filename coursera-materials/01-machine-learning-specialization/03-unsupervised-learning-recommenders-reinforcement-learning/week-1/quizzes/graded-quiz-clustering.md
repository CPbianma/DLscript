---
type: graded-quiz
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 1
section: "Practice Quiz: Clustering"
item_title: Clustering
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/assignment-submission/pThlX/clustering
language: en
extracted_at: 2026-10-08T22:52:07+08:00
grade: 100%
status: success
---
# Clustering

**Grade: 100%**

## Question 1 (GradedMultipleChoiceQuestion)

Which of these best describes unsupervised learning?

- [ ] A form of machine learning that finds patterns in data using only labels (y) but without any inputs (x) .
- [ ] A form of machine learning that finds patterns without using a cost function.
- [x] A form of machine learning that finds patterns using unlabeled data (x).
- [ ] A form of machine learning that finds patterns using labeled data (x, y)

*Points: 1 / 1*

## Question 2 (GradedCheckboxQuestion)

Which of these statements are true about K-means? Check all that apply.

- [x] If each example x is a vector of 5 numbers, then each cluster centroid μk\mu\_kμk​mu, start subscript, k, end subscript is also going to be a vector of 5 numbers. ✅correct
  > Feedback: Nice work The dimension of 𝜇 𝑘 μ k ​ mu, start subscript, k, end subscript matches the dimension of the examples.
- [x] The number of cluster assignment variables c(i)c^{(i)}c(i)c, start superscript, left parenthesis, i, right parenthesis, end superscript is equal to the number of training examples. ✅correct
  > Feedback: Nice work 𝑐 ( 𝑖 ) c (i) c, start superscript, left parenthesis, i, right parenthesis, end superscript describes which centroid example ( 𝑖 ) (i) left parenthesis, i, right parenthesis is assigned to.
- [x] If you are running K-means with K=3K=3K=3K, equals, 3 clusters, then each c(i)c^{(i)}c(i)c, start superscript, left parenthesis, i, right parenthesis, end superscript should be 1, 2, or 3. ✅correct
  > Feedback: Nice work 𝑐 ( 𝑖 ) c (i) c, start superscript, left parenthesis, i, right parenthesis, end superscript describes which centroid example( 𝑖 i i ) is assigned to. If 𝐾 = 3 K=3 K, equals, 3 , then 𝑐 ( 𝑖 ) c (i) c, start superscript, left parenthesis, i, right parenthesis, end superscript would be one of 1,2 or 3 assuming counting starts at 1.
- [ ] The number of cluster centroids μk\mu\_kμk​mu, start subscript, k, end subscript is equal to the number of examples.

*Points: 1 / 1*

## Question 3 (GradedMultipleChoiceQuestion)

You run K-means 100 times with different initializations. How should you pick from the 100 resulting solutions?

- [ ] Pick randomly -- that was the point of random initialization.
- [x] Pick the last one (i.e., the 100th random initialization) because K-means always improves over time
- [ ] Pick the one with the lowest cost JJJJ
- [ ] Average all 100 solutions together.

*Points: 0 / 1*

## Question 4 (GradedMultipleChoiceQuestion)

You run K-means and compute the value of the cost function J(c(1),…,c(m),μ1,…,μK)J(c^{(1)}, …, c^{(m)}, \mu\_1, …, \mu\_K)J(c(1),…,c(m),μ1​,…,μK​)J, left parenthesis, c, start superscript, left parenthesis, 1, right parenthesis, end superscript, comma, …, comma, c, start superscript, left parenthesis, m, right parenthesis, end superscript, comma, mu, start subscript, 1, end subscript, comma, …, comma, mu, start subscript, K, end subscript, right parenthesis after each iteration. Which of these statements should be true?

- [ ] The cost can be greater or smaller than the cost in the previous iteration, but it decreases in the long run.
- [ ] There is no cost function for the K-means algorithm.
- [x] The cost will either decrease or stay the same after each iteration. .
- [ ] Because K-means tries to maximize cost, the cost is always greater than or equal to the cost in the previous iteration.

*Points: 1 / 1*

## Question 5 (GradedMultipleChoiceQuestion)

In K-means, the elbow method is a method to

- [ ] Choose the best random initialization
- [ ] Choose the maximum number of examples for each cluster
- [x] Choose the number of clusters K
- [ ] Choose the best number of samples in the dataset

*Points: 1 / 1*

