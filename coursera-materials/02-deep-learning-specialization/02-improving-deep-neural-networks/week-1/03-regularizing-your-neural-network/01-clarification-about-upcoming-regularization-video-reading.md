---
type: reading
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 1
section: Regularizing your Neural Network
item_title: Clarification about Upcoming Regularization Video
source_url: https://www.coursera.org/learn/deep-neural-network/supplement/NcThD/clarification-about-upcoming-regularization-video
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---
# Clarification about Upcoming Regularization Video

Please note that in the next video at 5:45, the Frobenius norm formula should be the following:

$$||w^{[l]}||^{2} = \sum\_{i=1}^{n^{[l]}} \sum\_{j=1}^{n^{[l-1]}} (w\_{i,j}^{[l]})^{2}$$

The limit of summation of i should be from 1 to $$n^{[l]}$$,

The limit of summation of j should be from 1 to $$n^{[l-1]}$$.

(it's flipped in the video). The rows "i" of the matrix should be the number of neurons in the current layer $$n^{[l]}$$;

whereas the columns "j" of the weight matrix should equal the number of neurons in the previous layer $$n^{[l-1]}$$.
